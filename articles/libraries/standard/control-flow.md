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
# <a name="higher-order-control-flow"></a><span data-ttu-id="eea6f-103">較高順序的控制流程</span><span class="sxs-lookup"><span data-stu-id="eea6f-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="eea6f-104">標準程式庫的主要角色之一，是為了讓高階演算法概念更容易表達為[量副程式](https://en.wikipedia.org/wiki/Quantum_programming)。</span><span class="sxs-lookup"><span data-stu-id="eea6f-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="eea6f-105">因此，Q # canon 會提供各種不同的流程式控制制結構，每個都是使用部分應用於函式和作業來執行。</span><span class="sxs-lookup"><span data-stu-id="eea6f-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="eea6f-106">立即跳入範例，請考慮要在暫存器上建立「CNOT-CONTAINS 階梯」的情況：</span><span class="sxs-lookup"><span data-stu-id="eea6f-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="eea6f-107">我們可以使用反復專案和 `for` 迴圈來表示此模式：</span><span class="sxs-lookup"><span data-stu-id="eea6f-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="eea6f-108">以 <xref:microsoft.quantum.canon.applytoeachca> 和陣列操作函式（例如 <xref:microsoft.quantum.arrays.zip>）表示，這會更短且更容易閱讀：</span><span class="sxs-lookup"><span data-stu-id="eea6f-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="eea6f-109">在本節的其餘部分，我們將提供一些範例，說明如何使用 canon 所提供的各種流程式控制製作業和函式來簡潔地 express 量副程式。</span><span class="sxs-lookup"><span data-stu-id="eea6f-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="eea6f-110">在陣列和範圍上套用作業和函式</span><span class="sxs-lookup"><span data-stu-id="eea6f-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="eea6f-111">Canon 所提供的其中一個主要抽象概念是反復專案的其中一個。</span><span class="sxs-lookup"><span data-stu-id="eea6f-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="eea6f-112">例如，假設有一個表單 $U \otimes U \otimes \cdots \otimes U $ 適用于單一 qubit 單一 $U $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="eea6f-113">在 Q # 中，我們可能會使用 <xref:microsoft.quantum.arrays.indexrange>，將此視為透過暫存器的 `for` 迴圈：</span><span class="sxs-lookup"><span data-stu-id="eea6f-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

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

<span data-ttu-id="eea6f-114">然後，我們可以使用這個新作業做為 `HAll(register)`，以套用 $H \otimes H \otimes \cdots \otimes H $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="eea6f-115">不過，這樣做很麻煩，特別是在較大的演算法中。</span><span class="sxs-lookup"><span data-stu-id="eea6f-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="eea6f-116">此外，這種方法專門用於我們想要套用至每個 qubit 的特定作業。</span><span class="sxs-lookup"><span data-stu-id="eea6f-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="eea6f-117">我們可以使用作業的第一方，更明確地表達此演算法概念：</span><span class="sxs-lookup"><span data-stu-id="eea6f-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="eea6f-118">在這裡，後置詞 `CA` 表示呼叫 `ApplyToEach` 本身是 adjointable 且可控制的。</span><span class="sxs-lookup"><span data-stu-id="eea6f-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="eea6f-119">因此，如果 `U` 支援 `Adjoint` 和 `Controlled`，下列幾行就是相同的：</span><span class="sxs-lookup"><span data-stu-id="eea6f-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="eea6f-120">特別是，這表示 `ApplyToEachCA` 的呼叫可能會出現在自動產生 adjoint 特製化的作業中。</span><span class="sxs-lookup"><span data-stu-id="eea6f-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="eea6f-121">同樣地，<xref:microsoft.quantum.canon.applytoeachindex> 適用于代表表單 `U(0, targets[0]); U(1, targets[1]); ...`的模式，並為其輸入所支援的每個函子組合提供版本。</span><span class="sxs-lookup"><span data-stu-id="eea6f-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="eea6f-122">`ApplyToEach` 是型別參數化，因此可以與接受 `Qubit`以外之輸入的作業搭配使用。</span><span class="sxs-lookup"><span data-stu-id="eea6f-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="eea6f-123">例如，假設 `codeBlocks` 是需要復原 <xref:microsoft.quantum.errorcorrection.logicalregister> 值的陣列。</span><span class="sxs-lookup"><span data-stu-id="eea6f-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="eea6f-124">然後 `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 會將錯誤更正程式碼套用 `code` 和復原功能，分別 `recoveryFn` 到每個區塊。</span><span class="sxs-lookup"><span data-stu-id="eea6f-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="eea6f-125">這甚至適用于傳統輸入： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 會將 $ \pi/$2 的旋轉套用至 $X $，後面接著 $Y $ 的 $pi/$3 旋轉。</span><span class="sxs-lookup"><span data-stu-id="eea6f-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="eea6f-126">問 # canon 也提供功能程式設計熟悉的傳統列舉模式的支援。</span><span class="sxs-lookup"><span data-stu-id="eea6f-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="eea6f-127">例如，<xref:microsoft.quantum.arrays.fold> 會實作用 $f （f （f （s\_{\text{initial}}，x\_0），x\_1），\dots .） $ 來減少清單上的函式。</span><span class="sxs-lookup"><span data-stu-id="eea6f-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="eea6f-128">此模式可以用來執行 sum、products、minima、maxima 和其他這類函數：</span><span class="sxs-lookup"><span data-stu-id="eea6f-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="eea6f-129">同樣地，<xref:microsoft.quantum.arrays.mapped> 和 <xref:microsoft.quantum.arrays.mappedbyindex> 之類的函式可以用來表示 Q # 中的功能性程式設計概念。</span><span class="sxs-lookup"><span data-stu-id="eea6f-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="eea6f-130">撰寫作業和函數</span><span class="sxs-lookup"><span data-stu-id="eea6f-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="eea6f-131">Canon 所提供的控制流程結構會採用作業和函式做為其輸入，因此能夠將數個作業或函式組成單一可呼叫，是很有説明的。</span><span class="sxs-lookup"><span data-stu-id="eea6f-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="eea6f-132">比方說，模式 $UVU ^ {\dagger} $ 在量副程式設計中非常常見，因此 canon 會提供作業 <xref:microsoft.quantum.canon.applywith> 做為此模式的抽象概念。</span><span class="sxs-lookup"><span data-stu-id="eea6f-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="eea6f-133">此抽象層也可讓您以更有效率的方式 compliation 到線路，因為 `Controlled` 的順序 `U(qubit); V(qubit); Adjoint U(qubit);` 不需要對每個 `U`採取行動。</span><span class="sxs-lookup"><span data-stu-id="eea6f-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="eea6f-134">若要查看此情況，請讓 $c （U） $ 是代表 `Controlled U([control], target)` 的單一，並讓 $c （V） $ 以相同的方式定義。</span><span class="sxs-lookup"><span data-stu-id="eea6f-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="eea6f-135">然後適用于任意狀態 $ \ket{\psi} $、\begin{align} c （u） c （V） c （U） ^ \dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes （UVU ^ {\dagger} \ket{\psi}） \\\\ & = （\boldone \otimes u）（c （V））（\boldone \otimes U ^ \dagger） \ket{1} \otimes \ket{\psi}。</span><span class="sxs-lookup"><span data-stu-id="eea6f-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="eea6f-136">由 `Controlled`的定義 \end{align}。</span><span class="sxs-lookup"><span data-stu-id="eea6f-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="eea6f-137">另一方面，\begin{align} c （U） c （V） c （U） ^ \dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes （UU ^ \dagger \ket{\psi}） \\\\ & = （\boldone \otimes u）（\boldone \otimes U ^ \dagger） \ket{0} \otimes \ket{\psi}。</span><span class="sxs-lookup"><span data-stu-id="eea6f-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="eea6f-138">藉由線性 \end{align}，我們可以讓我們以這種方式將所有輸入狀態的 $U $ out 納入考慮。</span><span class="sxs-lookup"><span data-stu-id="eea6f-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="eea6f-139">也就是 $c （UVU ^ \dagger） = U c （V） U ^ \dagger $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="eea6f-140">由於控制作業通常會耗用很多資源，因此使用受控制的變異，例如 `WithC` 和 `WithCA` 有助於減少需要套用的控制項函子數目。</span><span class="sxs-lookup"><span data-stu-id="eea6f-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="eea6f-141">分解 $U $ 的另一個結果是，我們甚至不知道如何將 `Controlled` 仿函數套用至 `U`。</span><span class="sxs-lookup"><span data-stu-id="eea6f-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="eea6f-142">因此，`ApplyWithCA` 的簽章會比預期的更弱：</span><span class="sxs-lookup"><span data-stu-id="eea6f-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="eea6f-143">同樣地，<xref:microsoft.quantum.canon.bound> 會產生作業，這會依次套用其他作業的順序。</span><span class="sxs-lookup"><span data-stu-id="eea6f-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="eea6f-144">例如，下列是相同的：</span><span class="sxs-lookup"><span data-stu-id="eea6f-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="eea6f-145">結合反復專案模式可以讓此功能特別有用：</span><span class="sxs-lookup"><span data-stu-id="eea6f-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="eea6f-146">依時間排序的組合</span><span class="sxs-lookup"><span data-stu-id="eea6f-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="eea6f-147">我們還可以在部分應用程式和傳統函式的角度思考流量控制，也可以根據傳統流量控制來建立更複雜的量子概念模型。</span><span class="sxs-lookup"><span data-stu-id="eea6f-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="eea6f-148">這種比喻是精確的辨識，因為單一運算子會完全對應到呼叫作業的副作用，因此任何單一運算子的分解會對應到特定的傳統副程式的呼叫順序，會發出指示做為特定的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="eea6f-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="eea6f-149">在此視圖下，`Bound` 精確地表示矩陣產品，因為 `Bound([A, B])(target)` 相當於 `A(target); B(target);`，而後者則是對應至 $BA $ 的呼叫序列。</span><span class="sxs-lookup"><span data-stu-id="eea6f-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="eea6f-150">更複雜的範例是[Trotter – plat'home co. 擴充](https://arxiv.org/abs/math-ph/0506007v1)。</span><span class="sxs-lookup"><span data-stu-id="eea6f-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="eea6f-151">如[資料結構](xref:microsoft.quantum.libraries.data-structures)的 Dynamical 產生器表示一節中所述，Trotter – plat'home co. 擴充提供特別有用的方式來表達矩陣指數。</span><span class="sxs-lookup"><span data-stu-id="eea6f-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="eea6f-152">例如，以最低順序套用擴充，會產生適用于任何運算子 $A $ 和 $B $，因此 $A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-plat'home co.-0} \exp （i [A + B] t） = \ lim_ {n\to\infty} \left （\exp （i A t/n） \exp （i B t/n） \right） ^ n。</span><span class="sxs-lookup"><span data-stu-id="eea6f-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="eea6f-153">\end{align} 堆疊，這表示我們可以在 $A $ 和 $B $ 獨立的情況下，在 $A + B $ 之下，進一步演變狀態。</span><span class="sxs-lookup"><span data-stu-id="eea6f-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="eea6f-154">如果我們以 $e ^ {i t} $ 的作業 `A : (Double, Qubit[]) => Unit` 來表示 $A $ 之下的演進，則 Trotter – Plat'home co. 擴充在重新排列呼叫序列方面的標記法會變得很清楚。</span><span class="sxs-lookup"><span data-stu-id="eea6f-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="eea6f-155">具體而言，假設有一項作業 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` 這樣 `A = U(0, _, _)` 和 `B = U(1, _, _)`，我們就可以藉由產生格式的順序，定義一個代表 `U` 的整數 $t $ 的新運算</span><span class="sxs-lookup"><span data-stu-id="eea6f-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="eea6f-156">到目前為止，我們現在可以 Trotter – Plat'home co. 擴充，*完全不需要參考量子機制*。</span><span class="sxs-lookup"><span data-stu-id="eea6f-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="eea6f-157">擴充實際上是一個由 $ \eqref{eq： trotter-plat'home co.-0} $ 所積極的特別反復專案模式。</span><span class="sxs-lookup"><span data-stu-id="eea6f-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="eea6f-158">這個反復專案模式是由 <xref:microsoft.quantum.canon.decomposeintotimestepsca>來執行：</span><span class="sxs-lookup"><span data-stu-id="eea6f-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="eea6f-159">`DecomposeIntoTimeStepsCA` 的簽章遵循 Q # 中的常見模式，其中的集合可能會由陣列所支援，或由動態運算元素所代表的專案，由其第一個元素為 `Int` 值的元組來表示其長度。</span><span class="sxs-lookup"><span data-stu-id="eea6f-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="eea6f-160">將它放在一起：控制作業</span><span class="sxs-lookup"><span data-stu-id="eea6f-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="eea6f-161">最後，canon 是以 `Controlled` 仿函數為基礎，藉由提供其他方法來進行條件配量作業。</span><span class="sxs-lookup"><span data-stu-id="eea6f-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="eea6f-162">通常是在量子算術中，對 $ \ket{0\cdots 0} $ 以外的計算基礎狀態進行條件運算。</span><span class="sxs-lookup"><span data-stu-id="eea6f-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="eea6f-163">使用上述的控制作業和函式，我們可以在單一語句中進行更一般的配量條件。</span><span class="sxs-lookup"><span data-stu-id="eea6f-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="eea6f-164">讓我們來看看 <xref:microsoft.quantum.canon.controlledonbitstring> 如何執行（san 型別參數），然後逐一細分各部分。</span><span class="sxs-lookup"><span data-stu-id="eea6f-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="eea6f-165">我們要做的第一件事，就是定義一項作業，此作業實際上會在任意計算基礎狀態上執行大量的控制項。</span><span class="sxs-lookup"><span data-stu-id="eea6f-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="eea6f-166">不過，我們不會直接呼叫這項作業，因此我們會將 `_` 新增至名稱的開頭，以指出它是其他位置的另一個結構。</span><span class="sxs-lookup"><span data-stu-id="eea6f-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="eea6f-167">請注意，我們會採用以 `Bool` 陣列表示的位字串，讓我們用來指定要套用至作業 `oracle` 所提供的調節。</span><span class="sxs-lookup"><span data-stu-id="eea6f-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="eea6f-168">因為此作業實際上會直接執行應用程式，所以我們也需要將控制項和目標暫存器（在此以 `Qubit[]`表示）。</span><span class="sxs-lookup"><span data-stu-id="eea6f-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="eea6f-169">接下來，我們會注意到，您可以藉由將 $ \ket{\vec{s}} $ 轉換成 $ \ket{0\cdots 0} $，來控制計算基礎狀態 $ \ket{\vec{s}} = \ket{s\_0 s\_1 \dots . s\_{n-1}} $ for a bit string $ \vec{s} $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="eea6f-170">具體而言，$ \ket{\vec{s}} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="eea6f-171">由於 $X ^ {\dagger} = X $，這表示 $ \ket{0\dots 0} = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} \ket{\vec{s}} $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="eea6f-172">因此，我們可以套用 $P = X ^ {s\_0} \otimes X ^ {s\_1} \otimes \cdots \otimes X ^ {s\_{n-1}} $，套用 `Controlled oracle`並轉換回 $ \vec{s} $。</span><span class="sxs-lookup"><span data-stu-id="eea6f-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="eea6f-173">這項結構會精確 `ApplyWith`，因此我們會據此撰寫新作業的本文：</span><span class="sxs-lookup"><span data-stu-id="eea6f-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="eea6f-174">在這裡，我們使用 <xref:microsoft.quantum.canon.applypaulifrombitstring> 來套用 $P $，部分套用在其目標上，以用於 `ApplyWith`。</span><span class="sxs-lookup"><span data-stu-id="eea6f-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="eea6f-175">不過，請注意，我們需要將*控制項*暫存器轉換成所需的表單，因此我們會在*目標*上部分套用內部作業 `(Controlled oracle)`。</span><span class="sxs-lookup"><span data-stu-id="eea6f-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="eea6f-176">這會讓 `ApplyWith` 以 $P $ 來括住控制項暫存器，完全如我們所需。</span><span class="sxs-lookup"><span data-stu-id="eea6f-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="eea6f-177">此時，我們可以完成，但有一點回答，我們的新作業不會像套用 `Controlled` 仿函數一樣「感覺」。</span><span class="sxs-lookup"><span data-stu-id="eea6f-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="eea6f-178">因此，我們會撰寫一個函式，此函式會接受 oracle 的控制，並傳回新的作業，藉此定義新的控制流程概念。</span><span class="sxs-lookup"><span data-stu-id="eea6f-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="eea6f-179">如此一來，我們的新函式看起來就像 `Controlled`，說明我們可以使用 Q # 和 canon，輕鬆地定義強大的新控制流程結構：</span><span class="sxs-lookup"><span data-stu-id="eea6f-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
