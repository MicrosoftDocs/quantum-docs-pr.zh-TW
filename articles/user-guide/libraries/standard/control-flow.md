---
title: 標準 libararies 中的流程式控制制 Q#
description: 深入瞭解 Microsoft 標準程式庫中的流程式控制製作業和功能 Q# 。
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: a440f1ef2b901b18593816ca27aeadf7ab827104
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868571"
---
# <a name="higher-order-control-flow"></a>較高順序的控制流程 #

標準程式庫的主要角色之一，是為了讓高階演算法概念更容易表達為[量副程式](https://en.wikipedia.org/wiki/Quantum_programming)。
因此， Q# canon 會提供各種不同的流程式控制制結構，每個都是使用部分應用於函式和作業來執行。
立即跳入範例，請考慮要在暫存器上建立「CNOT-CONTAINS 階梯」的情況：

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

我們可以使用反復專案和迴圈來表示此模式 `for` ：

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

以 <xref:microsoft.quantum.canon.applytoeachca> 和陣列操作函式表示 <xref:microsoft.quantum.arrays.zip> ，例如，這會更短且更容易閱讀：

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

在本節的其餘部分，我們將提供一些範例，說明如何使用 canon 所提供的各種流程式控制製作業和函式來簡潔地 express 量副程式。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>在陣列和範圍上套用作業和函式 ##

Canon 所提供的其中一個主要抽象概念是反復專案的其中一個。
例如，假設有一個表單 $U \otimes U \otimes \cdots \otimes U $ 適用于單一 qubit 單一 $U $。
在中 Q# ，我們可能會使用將此表示為在暫存器 <xref:microsoft.quantum.arrays.indexrange> `for` 上的迴圈：

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

然後，我們可以使用這個新的作業 `HAll(register)` 來套用 $H \Otimes h \otimes \cdots \Otimes h $。

不過，這樣做很麻煩，特別是在較大的演算法中。
此外，這種方法專門用於我們想要套用至每個 qubit 的特定作業。
我們可以使用作業的第一方，更明確地表達此演算法概念：

```qsharp
ApplyToEachCA(H, register);
```

在這裡，後置詞 `CA` 表示的呼叫 `ApplyToEach` 本身是 adjointable 且可控制的。
因此，如果 `U` 支援 `Adjoint` 和 `Controlled` ，則下列幾行是相等的：

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

特別是，這表示對的呼叫 `ApplyToEachCA` 可能會出現在自動產生 adjoint 特製化的作業中。
同樣地，適用 <xref:microsoft.quantum.canon.applytoeachindex> 于代表表單的模式 `U(0, targets[0]); U(1, targets[1]); ...` ，並為其輸入所支援的每個函子組合提供版本。

> [!TIP]
> `ApplyToEach`是型別參數化，因此可以搭配接受以外之輸入的作業使用 `Qubit` 。
> 例如，假設 `codeBlocks` 是 <xref:microsoft.quantum.errorcorrection.logicalregister> 需要復原的值陣列。
> 然後 `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 會個別將錯誤更正程式碼 `code` 和修復功能套用 `recoveryFn` 至每個區塊。
> 這甚至適用于傳統輸入： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 會套用 $ \pi/$2 的旋轉，$X $，後面接著 $Y $ 的 $pi/$3 旋轉。

Q#Canon 也提供功能程式設計熟悉的傳統列舉模式的支援。
例如，會執行 <xref:microsoft.quantum.arrays.fold> 模式 $f (f (f (s \_ {\text{initial}}，x \_ 0) ，x \_ 1) ，\dots ..) $ 來減少清單上的函式。
此模式可以用來執行 sum、products、minima、maxima 和其他這類函數：

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同樣地，和之類的函式 <xref:microsoft.quantum.arrays.mapped> <xref:microsoft.quantum.arrays.mappedbyindex> 可以用來表示中的功能程式設計概念 Q# 。

## <a name="composing-operations-and-functions"></a>撰寫作業和函數 ##

Canon 所提供的控制流程結構會採用作業和函式做為其輸入，因此能夠將數個作業或函式組成單一可呼叫，是很有説明的。
比方說，模式 $UVU ^ {\dagger} $ 在量副程式設計中非常常見，因此 canon 會提供 <xref:microsoft.quantum.canon.applywith> 此作業做為此模式的抽象概念。
此抽象層也可讓您更有效率地 compliation 到線路，因為 `Controlled` 順序不 `U(qubit); V(qubit); Adjoint U(qubit);` 需要對每個進行動作 `U` 。
若要查看此情況，請讓 $c (U) $ 是代表的單一， `Controlled U([control], target)` 並讓 $c (V) $ 以相同的方式定義。
然後，針對任意狀態 $ \ket{\psi} $、\begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (UVU ^ {\dagger} \ket{\psi} ) & \\ \\ = ( \boldone \otimes U)  (c (V) # A13 ( \boldone \otimes U ^ \dagger) \ket \otimes {1} \ket{\psi}。
由的定義 \end{align} `Controlled` 。
另一方面，\begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi} ) \\ \\ & = ( \Boldone \otimes U)  (c (V) # A13 {0} ( \boldone \otimes \dagger
藉由線性 \end{align}，我們可以讓我們以這種方式將所有輸入狀態的 $U $ out 納入考慮。
也就是說，$c (UVU ^ \dagger) = U c (V) U ^ \dagger $。
由於控制作業通常會耗用大量資源，因此使用和之類的控制變異 `WithC` `WithCA` 有助於減少需要套用的控制項函子數目。

> [!NOTE]
> 分解 $U $ 的另一個結果是，我們甚至不知道如何將 `Controlled` 仿函數套用至 `U` 。
> `ApplyWithCA`因此，簽章會比預期的更弱：
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同樣地，會 <xref:microsoft.quantum.canon.bound> 產生作業，這會依次套用其他作業的順序。
例如，下列是相同的：

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

結合反復專案模式可以讓此功能特別有用：

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>依時間排序的組合 ###

我們還可以在部分應用程式和傳統函式的角度思考流量控制，也可以根據傳統流量控制來建立更複雜的量子概念模型。
這種比喻是精確的辨識，因為單一運算子會完全對應到呼叫作業的副作用，因此任何針對其他單一運算子的任何單一運算子分解都會對應到傳統副程式的特定呼叫順序，而這些方法會發出指示來作為特定的單一運算子。
在此視圖下， `Bound` 會精確地表示矩陣產品，因為 `Bound([A, B])(target)` 相當於 `A(target); B(target);` ，而後者則是對應至 $BA $ 的呼叫序列。

更複雜的範例是[Trotter – plat'home co. 擴充](https://arxiv.org/abs/math-ph/0506007v1)。
如[資料結構](xref:microsoft.quantum.libraries.data-structures)的 Dynamical 產生器表示一節中所述，Trotter – plat'home co. 擴充提供特別有用的方式來表達矩陣指數。
例如，以最低順序套用擴充，會產生適用于任何運算子 $A $ 和 $B $，因此 $A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-plat'home co.-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left ( \exp (我 A t/n) \exp (i B t/n) \right) ^ n。
\end{align} 堆疊，這表示我們可以在 $A $ 和 $B $ 獨立的情況下，在 $A + B $ 之下，進一步演變狀態。
如果我們以 `A : (Double, Qubit[]) => Unit` 適用于 $e ^ {i t} $ 的作業來表示 $A $ 之下的演進，則 Trotter – plat'home co. 擴充在重新排列呼叫序列方面的標記法會變得很清楚。
具體而言，在給定的作業中， `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` `B = U(1, _, _)` 我們可以藉由產生格式的順序，定義代表 `U` 時間 $t $ 之整數的新運算

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

到目前為止，我們現在可以 Trotter – Plat'home co. 擴充，*完全不需要參考量子機制*。
擴充實際上是一個由 $ \eqref{eq： trotter-plat'home co.-0} $ 所積極的特別反復專案模式。
這個反復專案模式是由下列專案所執行 <xref:microsoft.quantum.canon.decomposeintotimestepsca> ：

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

的簽章 `DecomposeIntoTimeStepsCA` 遵循中常見的模式 Q# ，其中的集合可能會由陣列所支援，或由其上的計算元素，由其第一個專案為值的元組代表 `Int` 其長度。

## <a name="putting-it-together-controlling-operations"></a>將它放在一起：控制作業 ##

最後，canon 會藉 `Controlled` 由提供其他方式來進行條件配量作業，以在仿函數上建立。
通常是在量子算術中，對 $ \ket{0\cdots 0} $ 以外的計算基礎狀態進行條件運算。
使用上述的控制作業和函式，我們可以在單一語句中進行更一般的配量條件。
讓我們來看看 <xref:microsoft.quantum.canon.controlledonbitstring> 它如何 (san 類型參數) ，然後逐一細分各部分。
我們要做的第一件事，就是定義一項作業，此作業實際上會在任意計算基礎狀態上執行大量的控制項。
不過，我們不會直接呼叫這項作業，因此我們會新增 `_` 至名稱的開頭，以指出它是其他位置的另一個結構。

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

請注意，我們會採用以陣列表示的位字串 `Bool` ，讓我們用來指定要套用至我們所提供之作業的調節 `oracle` 。
因為此作業實際上會直接執行應用程式，所以我們也需要將控制項和目標暫存器（在此以表示） `Qubit[]` 。

接下來，我們會注意到，您 \_ \_ 可以藉由將 \_ $ \ket{\vec{s}} $ 轉換成 $ \ket{0\cdots 0} $，來控制針對位字串 $ \vec{s} $ 的計算基礎狀態 $ \ket{\vec{s}} = \ket{s 0 s 1 \dots .. s {n-1}} $。
具體而言，$ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{0\cdots 0} $。
由於 $X ^ {\dagger} = X $，這表示 $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $。
因此，我們可以套用 $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $、apply `Controlled oracle` 和 transform 回到 $ \vec{s} $。
這是精確 `ApplyWith` 的結構，所以我們會據此撰寫新作業的本文：

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

在這裡，我們用 <xref:microsoft.quantum.canon.applypaulifrombitstring> 來套用 $P $，部分套用在其目標上，以便搭配使用 `ApplyWith` 。
不過，請注意，我們需要將*控制項*暫存器轉換成所需的格式，因此我們會 `(Controlled oracle)` 在*目標*上部分套用內部作業。
這會 `ApplyWith` 讓控制項暫存器以 $P $ 括住，完全如我們所需。

此時，我們可以完成，但有一點回答，我們的新作業不會像套用仿函數一樣「感覺」 `Controlled` 。
因此，我們會撰寫一個函式，此函式會接受 oracle 的控制，並傳回新的作業，藉此定義新的控制流程概念。
如此一來，新函式的外觀和感覺非常類似 `Controlled` ，說明我們可以使用和 canon，輕鬆地定義強大的新控制流程結構 Q# ：

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
