---
title: '問 # 標準程式庫-控制項和流程 |Microsoft Docs'
description: 'Q # 標準程式庫-控制項和流程'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ff73cef12a3b8c2a6559308dc244c7c2e865ba9f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820448"
---
# <a name="higher-order-control-flow"></a>較高順序的控制流程 #

標準程式庫的主要角色之一，是為了讓高階演算法概念更容易表達為[量副程式](https://en.wikipedia.org/wiki/Quantum_programming)。
因此，Q # canon 會提供各種不同的流程式控制制結構，每個都是使用部分應用於函式和作業來執行。
立即跳入範例，請考慮要在暫存器上建立「CNOT-CONTAINS 階梯」的情況：

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

我們可以使用反復專案和 `for` 迴圈來表示此模式：

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

以 <xref:microsoft.quantum.canon.applytoeachca> 和陣列操作函式（例如 <xref:microsoft.quantum.arrays.zip>）表示，這會更短且更容易閱讀：

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

在本節的其餘部分，我們將提供一些範例，說明如何使用 canon 所提供的各種流程式控制製作業和函式來簡潔地 express 量副程式。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>在陣列和範圍上套用作業和函式 ##

Canon 所提供的其中一個主要抽象概念是反復專案的其中一個。
例如，假設有一個表單 $U \otimes U \otimes \cdots \otimes U $ 適用于單一 qubit 單一 $U $。
在 Q # 中，我們可能會使用 <xref:microsoft.quantum.arrays.indexrange>，將此視為透過暫存器的 `for` 迴圈：

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

然後，我們可以使用這個新作業做為 `HAll(register)`，以套用 $H \otimes H \otimes \cdots \otimes H $。

不過，這樣做很麻煩，特別是在較大的演算法中。
此外，這種方法專門用於我們想要套用至每個 qubit 的特定作業。
我們可以使用作業的第一方，更明確地表達此演算法概念：

```qsharp
ApplyToEachCA(H, register);
```

在這裡，後置詞 `CA` 表示呼叫 `ApplyToEach` 本身是 adjointable 且可控制的。
因此，如果 `U` 支援 `Adjoint` 和 `Controlled`，下列幾行就是相同的：

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

特別是，這表示 `ApplyToEachCA` 的呼叫可能會出現在自動產生 adjoint 特製化的作業中。
同樣地，<xref:microsoft.quantum.canon.applytoeachindex> 適用于代表表單 `U(0, targets[0]); U(1, targets[1]); ...`的模式，並為其輸入所支援的每個函子組合提供版本。

> [!TIP]
> `ApplyToEach` 是型別參數化，因此可以與接受 `Qubit`以外之輸入的作業搭配使用。
> 例如，假設 `codeBlocks` 是需要復原 <xref:microsoft.quantum.errorcorrection.logicalregister> 值的陣列。
> 然後 `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 會將錯誤更正程式碼套用 `code` 和復原功能，分別 `recoveryFn` 到每個區塊。
> 這甚至適用于傳統輸入： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 會將 $ \pi/$2 的旋轉套用至 $X $，後面接著 $Y $ 的 $pi/$3 旋轉。

問 # canon 也提供功能程式設計熟悉的傳統列舉模式的支援。
例如，<xref:microsoft.quantum.arrays.fold> 會實作用 $f （f （f （s\_{\text{initial}}，x\_0），x\_1），\dots .） $ 來減少清單上的函式。
此模式可以用來執行 sum、products、minima、maxima 和其他這類函數：

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同樣地，<xref:microsoft.quantum.arrays.mapped> 和 <xref:microsoft.quantum.arrays.mappedbyindex> 之類的函式可以用來表示 Q # 中的功能性程式設計概念。

## <a name="composing-operations-and-functions"></a>撰寫作業和函數 ##

Canon 所提供的控制流程結構會採用作業和函式做為其輸入，因此能夠將數個作業或函式組成單一可呼叫，是很有説明的。
比方說，模式 $UVU ^ {\dagger} $ 在量副程式設計中非常常見，因此 canon 會提供作業 <xref:microsoft.quantum.canon.applywith> 做為此模式的抽象概念。
此抽象層也可讓您以更有效率的方式 compliation 到線路，因為 `Controlled` 的順序 `U(qubit); V(qubit); Adjoint U(qubit);` 不需要對每個 `U`採取行動。
若要查看此情況，請讓 $c （U） $ 是代表 `Controlled U([control], target)` 的單一，並讓 $c （V） $ 以相同的方式定義。
然後適用于任意狀態 $ \ket{\psi} $、\begin{align} c （u） c （V） c （U） ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes （UVU ^ {\dagger} \ket{\psi}） \\\\ & = （\boldone \otimes u）（c （V））（\boldone \otimes U ^ \dagger） \ket{1} \otimes \ket{\psi}。
由 `Controlled`的定義 \end{align}。
另一方面，\begin{align} c （U） c （V） c （U） ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes （UU ^ \dagger \ket{\psi}） \\\\ & = （\boldone \otimes u）（\boldone \otimes U ^ \dagger） \ket{0} \otimes \ket{\psi}。
藉由線性 \end{align}，我們可以讓我們以這種方式將所有輸入狀態的 $U $ out 納入考慮。
也就是 $c （UVU ^ \dagger） = U c （V） U ^ \dagger $。
由於控制作業通常會耗用很多資源，因此使用受控制的變異，例如 `WithC` 和 `WithCA` 有助於減少需要套用的控制項函子數目。

> [!NOTE]
> 分解 $U $ 的另一個結果是，我們甚至不知道如何將 `Controlled` 仿函數套用至 `U`。
> 因此，`ApplyWithCA` 的簽章會比預期的更弱：
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同樣地，<xref:microsoft.quantum.canon.bound> 會產生作業，這會依次套用其他作業的順序。
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
這種比喻是精確的辨識，因為單一運算子會完全對應到呼叫作業的副作用，因此任何單一運算子的分解會對應到特定的傳統副程式的呼叫順序，會發出指示做為特定的單一運算子。
在此視圖下，`Bound` 精確地表示矩陣產品，因為 `Bound([A, B])(target)` 相當於 `A(target); B(target);`，而後者則是對應至 $BA $ 的呼叫序列。

更複雜的範例是[Trotter – plat'home co. 擴充](https://arxiv.org/abs/math-ph/0506007v1)。
如[資料結構](xref:microsoft.quantum.libraries.data-structures)的 Dynamical 產生器表示一節中所述，Trotter – plat'home co. 擴充提供特別有用的方式來表達矩陣指數。
例如，以最低順序套用擴充，會產生適用于任何運算子 $A $ 和 $B $，因此 $A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-plat'home co.-0} \exp （i [A + B] t） = \ lim_ {n\to\infty} \left （\exp （i A t/n） \exp （i B t/n） \right） ^ n。
\end{align} 堆疊，這表示我們可以在 $A $ 和 $B $ 獨立的情況下，在 $A + B $ 之下，進一步演變狀態。
如果我們以 $e ^ {i t} $ 的作業 `A : (Double, Qubit[]) => Unit` 來表示 $A $ 之下的演進，則 Trotter – Plat'home co. 擴充在重新排列呼叫序列方面的標記法會變得很清楚。
具體而言，假設有一項作業 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` 這樣 `A = U(0, _, _)` 和 `B = U(1, _, _)`，我們就可以藉由產生格式的順序，定義一個代表 `U` 的整數 $t $ 的新運算

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

到目前為止，我們現在可以 Trotter – Plat'home co. 擴充，*完全不需要參考量子機制*。
擴充實際上是一個由 $ \eqref{eq： trotter-plat'home co.-0} $ 所積極的特別反復專案模式。
這個反復專案模式是由 <xref:microsoft.quantum.canon.decomposeintotimestepsca>來執行：

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

`DecomposeIntoTimeStepsCA` 的簽章遵循 Q # 中的常見模式，其中的集合可能會由陣列所支援，或由動態運算元素所代表的專案，由其第一個元素為 `Int` 值的元組來表示其長度。

## <a name="putting-it-together-controlling-operations"></a>將它放在一起：控制作業 ##

最後，canon 是以 `Controlled` 仿函數為基礎，藉由提供其他方法來進行條件配量作業。
通常是在量子算術中，對 $ \ket{0\cdots 0} $ 以外的計算基礎狀態進行條件運算。
使用上述的控制作業和函式，我們可以在單一語句中進行更一般的配量條件。
讓我們來看看 <xref:microsoft.quantum.canon.controlledonbitstring> 如何執行（san 型別參數），然後逐一細分各部分。
我們要做的第一件事，就是定義一項作業，此作業實際上會在任意計算基礎狀態上執行大量的控制項。
不過，我們不會直接呼叫這項作業，因此我們會將 `_` 新增至名稱的開頭，以指出它是其他位置的另一個結構。

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

請注意，我們會採用以 `Bool` 陣列表示的位字串，讓我們用來指定要套用至作業 `oracle` 所提供的調節。
因為此作業實際上會直接執行應用程式，所以我們也需要將控制項和目標暫存器（在此以 `Qubit[]`表示）。

接下來，我們會注意到，您可以藉由將 $ \ket{\vec{s}} $ 轉換成 $ \ket{0\cdots 0} $，來控制計算基礎狀態 $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots . s\_{n-1}} $ for a bit string $ \vec{s} $。
具體而言，$ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $。
由於 $X ^ {\dagger} = X $，這表示 $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $。
因此，我們可以套用 $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $，套用 `Controlled oracle`並轉換回 $ \vec{s} $。
這項結構會精確 `ApplyWith`，因此我們會據此撰寫新作業的本文：

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

在這裡，我們使用 <xref:microsoft.quantum.canon.applypaulifrombitstring> 來套用 $P $，部分套用在其目標上，以用於 `ApplyWith`。
不過，請注意，我們需要將*控制項*暫存器轉換成所需的表單，因此我們會在*目標*上部分套用內部作業 `(Controlled oracle)`。
這會讓 `ApplyWith` 以 $P $ 來括住控制項暫存器，完全如我們所需。

此時，我們可以完成，但有一點回答，我們的新作業不會像套用 `Controlled` 仿函數一樣「感覺」。
因此，我們會撰寫一個函式，此函式會接受 oracle 的控制，並傳回新的作業，藉此定義新的控制流程概念。
如此一來，我們的新函式看起來就像 `Controlled`，說明我們可以使用 Q # 和 canon，輕鬆地定義強大的新控制流程結構：

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
