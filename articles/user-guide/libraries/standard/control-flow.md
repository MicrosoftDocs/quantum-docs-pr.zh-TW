---
title: 標準 libararies 中的 Flow 控制項 Q#
description: 深入瞭解 Microsoft 標準程式庫中的流程式控制製作業和功能 Q# 。
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8f4b69250ed49bd56c3066d5cd40db4b8abfc9cb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858710"
---
# <a name="higher-order-control-flow"></a>Higher-Order 控制流程 #

標準程式庫的其中一個主要角色，是讓您更輕鬆地以 [量副程式](https://en.wikipedia.org/wiki/Quantum_programming)表示高階演算法的概念。
因此， Q# canon 會提供各種不同的流程式控制制結構，每個都使用函式和作業的部分應用程式來執行。
立即跳到範例中，請考慮要在註冊上建立「CNOT 階梯」的案例：

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

以 <xref:Microsoft.Quantum.Canon.ApplyToEachCA> 和陣列操作函式（例如）表示， <xref:Microsoft.Quantum.Arrays.Zipped> 這樣做會更短且更容易閱讀：

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

在本節的其餘部分，我們將提供一些範例，說明如何使用 canon 所提供的各種流程式控制製作業和函式來簡潔地快速量副程式。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>針對陣列和範圍套用作業和函數 ##

Canon 所提供的其中一個主要抽象概念是反覆運算的。
例如，假設有一個表單 $U \otimes U \otimes \cdots \otimes U $，適用于單一量子位的單一 $U $。
在中 Q# ，我們可能會使用將它表示為在暫存器 <xref:Microsoft.Quantum.Arrays.IndexRange> `for` 上的迴圈：

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

接著，我們可以使用這個新的作業， `HAll(register)` 將 $H \Otimes h \otimes \cdots \Otimes h $。

不過，這種做法很繁瑣，特別是在較大的演算法中。
此外，這個方法是專門針對我們想要套用至每個量子位的特定作業。
我們可以使用這類作業的第一種事實，更明確地表達此演算法概念：

```qsharp
ApplyToEachCA(H, register);
```

在這裡，尾碼 `CA` 表示的呼叫 `ApplyToEach` 本身是 adjointable 且可控制的。
因此，如果 `U` 支援 `Adjoint` 和 `Controlled` ，下列程式程式碼會是相等的：

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

特別是，這表示呼叫 `ApplyToEachCA` 可以出現在自動產生 adjoint 特製化的作業中。
同樣地，適用 <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> 于表示表單的模式 `U(0, targets[0]); U(1, targets[1]); ...` ，並針對其輸入所支援的每個函子組合提供版本。

> [!TIP]
> `ApplyToEach` 是型別參數化，因此可以搭配使用以外輸入的作業來使用 `Qubit` 。
> 例如，假設 `codeBlocks` 是 <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> 需要復原的值陣列。
> 然後， `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 會將錯誤更正程式碼和復原函式 `code` 個別套用 `recoveryFn` 至每個區塊。
> 這甚至適用于傳統的輸入： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 會套用 $ \pi/$2 的旋轉大約 $X $，後面接著 $pi/$3 $Y $ 的旋轉。

Q#Canon 也提供對功能性程式設計熟悉之傳統列舉模式的支援。
例如，會 <xref:Microsoft.Quantum.Arrays.Fold> 將模式 $f (f (f (s \_ {\text{initial}}，x \_ 0) ，x \_ 1) ，\dots ..) $ 以減少清單上的函式。
此模式可用來執行 sum、products、最小值、maxima 和其他這類函數：

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同樣地， <xref:Microsoft.Quantum.Arrays.Mapped> 和等函式 <xref:Microsoft.Quantum.Arrays.MappedByIndex> 可以用來在中表達功能性程式設計概念 Q# 。

## <a name="composing-operations-and-functions"></a>撰寫作業和函數 ##

Canon 所提供的控制流程結構會將作業和函式作為其輸入，因此可將數個作業或函式組合成單一可呼叫的功能。
比方說，在量副程式設計中，模式 $UVU ^ {\dagger} $ 非常常見，因此 canon 會將作業提供 <xref:Microsoft.Quantum.Canon.ApplyWith> 為此模式的抽象概念。
此抽象概念也可讓您以更有效率的方式編譯線路，因為 `Controlled` 在順序上 `U(qubit); V(qubit); Adjoint U(qubit);` 採取動作並不需要採取任何動作 `U` 。
若要查看這一點，請讓 $c (U) $ 成為單一代表 `Controlled U([control], target)` ，並讓 $c (V) $ 以相同方式定義。
然後，針對任意狀態 $ \ket{\psi} $、\begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (UVU ^ {\dagger} \ket{\psi} ) \\ \\ & = ( \boldone \otimes U)  (c (V) # A13 ( \boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\psi}。
由的定義 \end{align} `Controlled` 。
另一方面，\begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi} ) \\ \\ & = ( \Boldone \otimes U)  (c (V) # A13 ( \boldone \otimes U ^ \dagger) \ket {0} \otimes \ket{\psi}。
藉由線性 \end{align}，我們可以得出結論，我們可以針對所有輸入狀態，以這種方式將 $U $ out。
亦即 $c (UVU ^ \dagger) = U c (V) U ^ \dagger $。
由於控制作業的一般成本很高，因此使用受控制的變異（例如 `WithC` 和） `WithCA` 有助於減少需要套用的控制項函子數目。

> [!NOTE]
> 分解 $U $ 的另一個結果是，我們不需要知道如何將 `Controlled` 仿函數套用至 `U` 。
> `ApplyWithCA` 因此，簽章可能會比預期的更弱：
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同樣地，會 <xref:Microsoft.Quantum.Canon.Bound> 產生可依序套用一連串其他作業的作業。
例如，以下是相等的：

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

與反復專案模式結合可能會讓這特別有用：

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Time-Ordered 組合 ###

我們還可以在部分應用程式和傳統函式的角度考慮流量控制，也可以根據傳統流量控制來建立更複雜的量子概念模型。
這種比喻是由單一運算子精確對應至呼叫作業的副作用來精確地進行，例如，任何以其他單一運算子來分解的單一運算子，都對應于針對發出指示做為特定單一運算子的傳統副程式來建立特定的呼叫序列。
在此視圖下， `Bound` 是矩陣產品的標記法，因為 `Bound([A, B])(target)` 相當於 `A(target); B(target);` ，後者又是對應至 $BA $ 的呼叫順序。

更複雜的範例是 [Trotter – Suzuki 擴充](https://arxiv.org/abs/math-ph/0506007v1)。
如同 [資料結構](xref:microsoft.quantum.libraries.data-structures)的 Dynamical 產生器表示一節中所述，Trotter – Suzuki 擴充提供了一個特別有用的方式來表達矩陣指數。
例如，以最低順序套用擴充會產生任何運算子 $A $ 和 $B $，如此 $A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left ( \exp (i A t/n) \exp (i B t/n) \right) ^ n。
\end{align} 堆疊，這表示我們可以在 $A $ 和 $B $ 單獨演進的情況下，在 $A + B $ 下發展出狀態。
如果我們以 `A : (Double, Qubit[]) => Unit` 套用 $e ^ {i t A} $ 的作業 $A $ 來表示演進，則在重新排列呼叫序列的情況下，Trotter – Suzuki 擴充的表示會變得很清楚。
具體而言，假設有一項作業，因此 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` `B = U(1, _, _)` ，我們可以藉由產生格式的順序，來定義代表 `U` at time $t $ 整數的新運算

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

到目前為止，我們現在可以在 *沒有量子機制參考的情況* 下，Trotter – Suzuki 擴充的原因。
擴充實際上是由 $ \eqref{eq： trotter-suzuki-0} $ 所動機的一種非常特定的反復專案模式。
此反復專案模式的實作為 <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> ：

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

的簽章會 `DecomposeIntoTimeStepsCA` 遵循中常見的模式，也就是由 Q# 陣列所支援的集合，或是動態計算專案的集合，其第一個元素是 `Int` 表示其長度的值。

## <a name="putting-it-together-controlling-operations"></a>組合在一起：控制作業 ##

最後，canon 會藉 `Controlled` 由提供其他方式來進行量子運算的條件，以建立在仿函數上。
在計算基礎狀態（$ \ket{0\cdots 0} $）的情況下，這種情況通常很常見，尤其是在量子算術中。
使用上述的控制項作業和函式，我們可以在單一語句中使用更一般的量子條件。
讓我們來看看 <xref:Microsoft.Quantum.Canon.ControlledOnBitString> 它如何 (san 型別參數) ，然後逐一細分這些片段。
我們必須做的第一件事，是定義一項作業，以實際執行在任意計算基礎狀態中執行控制項的繁重工作。
不過，我們不會直接呼叫這項作業，因此我們要加入 `_` 名稱的開頭，以指出它是在其他位置的另一個結構。

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

請注意，我們會採用以陣列形式表示的位字串， `Bool` 以用來指定要套用至我們所提供之作業的調節 `oracle` 。
因為這項作業實際上會直接執行應用程式，所以我們也需要將控制項和目標暫存器（在此表示為） `Qubit[]` 。

接下來，我們要特別注意的是，在計算基礎狀態 $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots .. s \_ {n-1}} $ 上，將 $ \ket{\vec{s}} $ 轉換成 $ \ket{0\cdots 0} $ 可實現。
尤其是 $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $。
由於 $X ^ {\dagger} = X $，這表示 $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $。
因此，我們可以將 $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $、apply `Controlled oracle` ，然後轉換回 $ \vec{s} $。
這是精確的結構 `ApplyWith` ，因此我們會據以撰寫新作業的主體：

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

在這裡，我們用 <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> 來套用 $P $，部分套用至其目標，以搭配使用 `ApplyWith` 。
不過請注意，我們需要將 *控制項* 暫存器轉換成所需的表單，因此我們會 `(Controlled oracle)` 在 *目標* 上部分套用內部作業。
這會 `ApplyWith` 讓以 $P $ 的括弧括住控制項暫存器，就像我們所要的一樣。

到目前為止，我們可以完成這項作業，但 unsatisfying 新的作業不會像套用仿函數一樣「感覺」 `Controlled` 。
因此，我們藉由撰寫一個函式來定義新的控制流程概念，該函式會採用 oracle 來控制，並傳回新的作業。
如此一來，我們的新函式看起來非常類似 `Controlled` ，這表示我們可以輕鬆地使用和 canon 來定義功能強大的新控制流程結構 Q# ：

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
