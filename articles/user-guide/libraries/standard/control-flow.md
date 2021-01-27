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
# <a name="higher-order-control-flow"></a><span data-ttu-id="2d1fd-103">Higher-Order 控制流程</span><span class="sxs-lookup"><span data-stu-id="2d1fd-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="2d1fd-104">標準程式庫的其中一個主要角色，是讓您更輕鬆地以 [量副程式](https://en.wikipedia.org/wiki/Quantum_programming)表示高階演算法的概念。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="2d1fd-105">因此， Q# canon 會提供各種不同的流程式控制制結構，每個都使用函式和作業的部分應用程式來執行。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="2d1fd-106">立即跳到範例中，請考慮要在註冊上建立「CNOT 階梯」的案例：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="2d1fd-107">我們可以使用反復專案和迴圈來表示此模式 `for` ：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="2d1fd-108">以 <xref:Microsoft.Quantum.Canon.ApplyToEachCA> 和陣列操作函式（例如）表示， <xref:Microsoft.Quantum.Arrays.Zipped> 這樣做會更短且更容易閱讀：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-108">Expressed in terms of <xref:Microsoft.Quantum.Canon.ApplyToEachCA> and array manipulation functions such as <xref:Microsoft.Quantum.Arrays.Zipped>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="2d1fd-109">在本節的其餘部分，我們將提供一些範例，說明如何使用 canon 所提供的各種流程式控制製作業和函式來簡潔地快速量副程式。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="2d1fd-110">針對陣列和範圍套用作業和函數</span><span class="sxs-lookup"><span data-stu-id="2d1fd-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="2d1fd-111">Canon 所提供的其中一個主要抽象概念是反覆運算的。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="2d1fd-112">例如，假設有一個表單 $U \otimes U \otimes \cdots \otimes U $，適用于單一量子位的單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="2d1fd-113">在中 Q# ，我們可能會使用將它表示為在暫存器 <xref:Microsoft.Quantum.Arrays.IndexRange> `for` 上的迴圈：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-113">In Q#, we might use <xref:Microsoft.Quantum.Arrays.IndexRange> to represent this as as a `for` loop over a register:</span></span>

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

<span data-ttu-id="2d1fd-114">接著，我們可以使用這個新的作業， `HAll(register)` 將 $H \Otimes h \otimes \cdots \Otimes h $。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="2d1fd-115">不過，這種做法很繁瑣，特別是在較大的演算法中。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="2d1fd-116">此外，這個方法是專門針對我們想要套用至每個量子位的特定作業。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="2d1fd-117">我們可以使用這類作業的第一種事實，更明確地表達此演算法概念：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="2d1fd-118">在這裡，尾碼 `CA` 表示的呼叫 `ApplyToEach` 本身是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="2d1fd-119">因此，如果 `U` 支援 `Adjoint` 和 `Controlled` ，下列程式程式碼會是相等的：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="2d1fd-120">特別是，這表示呼叫 `ApplyToEachCA` 可以出現在自動產生 adjoint 特製化的作業中。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="2d1fd-121">同樣地，適用 <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> 于表示表單的模式 `U(0, targets[0]); U(1, targets[1]); ...` ，並針對其輸入所支援的每個函子組合提供版本。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-121">Similarly, <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="2d1fd-122">`ApplyToEach` 是型別參數化，因此可以搭配使用以外輸入的作業來使用 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="2d1fd-123">例如，假設 `codeBlocks` 是 <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> 需要復原的值陣列。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-123">For example, suppose that `codeBlocks` is an array of <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> values that need to be recovered.</span></span>
> <span data-ttu-id="2d1fd-124">然後， `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 會將錯誤更正程式碼和復原函式 `code` 個別套用 `recoveryFn` 至每個區塊。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="2d1fd-125">這甚至適用于傳統的輸入： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 會套用 $ \pi/$2 的旋轉大約 $X $，後面接著 $pi/$3 $Y $ 的旋轉。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="2d1fd-126">Q#Canon 也提供對功能性程式設計熟悉之傳統列舉模式的支援。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="2d1fd-127">例如，會 <xref:Microsoft.Quantum.Arrays.Fold> 將模式 $f (f (f (s \_ {\text{initial}}，x \_ 0) ，x \_ 1) ，\dots ..) $ 以減少清單上的函式。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-127">For instance, <xref:Microsoft.Quantum.Arrays.Fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="2d1fd-128">此模式可用來執行 sum、products、最小值、maxima 和其他這類函數：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="2d1fd-129">同樣地， <xref:Microsoft.Quantum.Arrays.Mapped> 和等函式 <xref:Microsoft.Quantum.Arrays.MappedByIndex> 可以用來在中表達功能性程式設計概念 Q# 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-129">Similarly, functions like <xref:Microsoft.Quantum.Arrays.Mapped> and <xref:Microsoft.Quantum.Arrays.MappedByIndex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="2d1fd-130">撰寫作業和函數</span><span class="sxs-lookup"><span data-stu-id="2d1fd-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="2d1fd-131">Canon 所提供的控制流程結構會將作業和函式作為其輸入，因此可將數個作業或函式組合成單一可呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="2d1fd-132">比方說，在量副程式設計中，模式 $UVU ^ {\dagger} $ 非常常見，因此 canon 會將作業提供 <xref:Microsoft.Quantum.Canon.ApplyWith> 為此模式的抽象概念。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:Microsoft.Quantum.Canon.ApplyWith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="2d1fd-133">此抽象概念也可讓您以更有效率的方式編譯線路，因為 `Controlled` 在順序上 `U(qubit); V(qubit); Adjoint U(qubit);` 採取動作並不需要採取任何動作 `U` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="2d1fd-134">若要查看這一點，請讓 $c (U) $ 成為單一代表 `Controlled U([control], target)` ，並讓 $c (V) $ 以相同方式定義。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="2d1fd-135">然後，針對任意狀態 $ \ket{\psi} $、\begin{align} c (U) c (V) c (U) ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES (UVU ^ {\dagger} \ket{\psi} ) \\ \\ & = ( \boldone \otimes U)  (c (V) # A13 ( \boldone \otimes U ^ \dagger) \ket {1} \otimes \ket{\psi}。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="2d1fd-136">由的定義 \end{align} `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="2d1fd-137">另一方面，\begin{align} c (U) c (V) c (U) ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes (UU ^ \dagger \ket{\psi} ) \\ \\ & = ( \Boldone \otimes U)  (c (V) # A13 ( \boldone \otimes U ^ \dagger) \ket {0} \otimes \ket{\psi}。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="2d1fd-138">藉由線性 \end{align}，我們可以得出結論，我們可以針對所有輸入狀態，以這種方式將 $U $ out。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="2d1fd-139">亦即 $c (UVU ^ \dagger) = U c (V) U ^ \dagger $。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="2d1fd-140">由於控制作業的一般成本很高，因此使用受控制的變異（例如 `WithC` 和） `WithCA` 有助於減少需要套用的控制項函子數目。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="2d1fd-141">分解 $U $ 的另一個結果是，我們不需要知道如何將 `Controlled` 仿函數套用至 `U` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="2d1fd-142">`ApplyWithCA` 因此，簽章可能會比預期的更弱：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="2d1fd-143">同樣地，會 <xref:Microsoft.Quantum.Canon.Bound> 產生可依序套用一連串其他作業的作業。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-143">Similarly, <xref:Microsoft.Quantum.Canon.Bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="2d1fd-144">例如，以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="2d1fd-145">與反復專案模式結合可能會讓這特別有用：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="2d1fd-146">Time-Ordered 組合</span><span class="sxs-lookup"><span data-stu-id="2d1fd-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="2d1fd-147">我們還可以在部分應用程式和傳統函式的角度考慮流量控制，也可以根據傳統流量控制來建立更複雜的量子概念模型。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="2d1fd-148">這種比喻是由單一運算子精確對應至呼叫作業的副作用來精確地進行，例如，任何以其他單一運算子來分解的單一運算子，都對應于針對發出指示做為特定單一運算子的傳統副程式來建立特定的呼叫序列。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="2d1fd-149">在此視圖下， `Bound` 是矩陣產品的標記法，因為 `Bound([A, B])(target)` 相當於 `A(target); B(target);` ，後者又是對應至 $BA $ 的呼叫順序。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="2d1fd-150">更複雜的範例是 [Trotter – Suzuki 擴充](https://arxiv.org/abs/math-ph/0506007v1)。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="2d1fd-151">如同 [資料結構](xref:microsoft.quantum.libraries.data-structures)的 Dynamical 產生器表示一節中所述，Trotter – Suzuki 擴充提供了一個特別有用的方式來表達矩陣指數。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="2d1fd-152">例如，以最低順序套用擴充會產生任何運算子 $A $ 和 $B $，如此 $A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left ( \exp (i A t/n) \exp (i B t/n) \right) ^ n。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="2d1fd-153">\end{align} 堆疊，這表示我們可以在 $A $ 和 $B $ 單獨演進的情況下，在 $A + B $ 下發展出狀態。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="2d1fd-154">如果我們以 `A : (Double, Qubit[]) => Unit` 套用 $e ^ {i t A} $ 的作業 $A $ 來表示演進，則在重新排列呼叫序列的情況下，Trotter – Suzuki 擴充的表示會變得很清楚。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="2d1fd-155">具體而言，假設有一項作業，因此 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` `B = U(1, _, _)` ，我們可以藉由產生格式的順序，來定義代表 `U` at time $t $ 整數的新運算</span><span class="sxs-lookup"><span data-stu-id="2d1fd-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="2d1fd-156">到目前為止，我們現在可以在 *沒有量子機制參考的情況* 下，Trotter – Suzuki 擴充的原因。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="2d1fd-157">擴充實際上是由 $ \eqref{eq： trotter-suzuki-0} $ 所動機的一種非常特定的反復專案模式。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="2d1fd-158">此反復專案模式的實作為 <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> ：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-158">This iteration pattern is implemented by <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="2d1fd-159">的簽章會 `DecomposeIntoTimeStepsCA` 遵循中常見的模式，也就是由 Q# 陣列所支援的集合，或是動態計算專案的集合，其第一個元素是 `Int` 表示其長度的值。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="2d1fd-160">組合在一起：控制作業</span><span class="sxs-lookup"><span data-stu-id="2d1fd-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="2d1fd-161">最後，canon 會藉 `Controlled` 由提供其他方式來進行量子運算的條件，以建立在仿函數上。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="2d1fd-162">在計算基礎狀態（$ \ket{0\cdots 0} $）的情況下，這種情況通常很常見，尤其是在量子算術中。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="2d1fd-163">使用上述的控制項作業和函式，我們可以在單一語句中使用更一般的量子條件。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="2d1fd-164">讓我們來看看 <xref:Microsoft.Quantum.Canon.ControlledOnBitString> 它如何 (san 型別參數) ，然後逐一細分這些片段。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-164">Let's jump in to how <xref:Microsoft.Quantum.Canon.ControlledOnBitString> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="2d1fd-165">我們必須做的第一件事，是定義一項作業，以實際執行在任意計算基礎狀態中執行控制項的繁重工作。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="2d1fd-166">不過，我們不會直接呼叫這項作業，因此我們要加入 `_` 名稱的開頭，以指出它是在其他位置的另一個結構。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="2d1fd-167">請注意，我們會採用以陣列形式表示的位字串， `Bool` 以用來指定要套用至我們所提供之作業的調節 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="2d1fd-168">因為這項作業實際上會直接執行應用程式，所以我們也需要將控制項和目標暫存器（在此表示為） `Qubit[]` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="2d1fd-169">接下來，我們要特別注意的是，在計算基礎狀態 $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots .. s \_ {n-1}} $ 上，將 $ \ket{\vec{s}} $ 轉換成 $ \ket{0\cdots 0} $ 可實現。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="2d1fd-170">尤其是 $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="2d1fd-171">由於 $X ^ {\dagger} = X $，這表示 $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ 1} \otimes \Cdots \otimes X ^ {s \_ {n-1}} \ket{\vec{s}} $。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="2d1fd-172">因此，我們可以將 $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $、apply `Controlled oracle` ，然後轉換回 $ \vec{s} $。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="2d1fd-173">這是精確的結構 `ApplyWith` ，因此我們會據以撰寫新作業的主體：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="2d1fd-174">在這裡，我們用 <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> 來套用 $P $，部分套用至其目標，以搭配使用 `ApplyWith` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-174">Here, we have used <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="2d1fd-175">不過請注意，我們需要將 *控制項* 暫存器轉換成所需的表單，因此我們會 `(Controlled oracle)` 在 *目標* 上部分套用內部作業。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="2d1fd-176">這會 `ApplyWith` 讓以 $P $ 的括弧括住控制項暫存器，就像我們所要的一樣。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="2d1fd-177">到目前為止，我們可以完成這項作業，但 unsatisfying 新的作業不會像套用仿函數一樣「感覺」 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="2d1fd-178">因此，我們藉由撰寫一個函式來定義新的控制流程概念，該函式會採用 oracle 來控制，並傳回新的作業。</span><span class="sxs-lookup"><span data-stu-id="2d1fd-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="2d1fd-179">如此一來，我們的新函式看起來非常類似 `Controlled` ，這表示我們可以輕鬆地使用和 canon 來定義功能強大的新控制流程結構 Q# ：</span><span class="sxs-lookup"><span data-stu-id="2d1fd-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
