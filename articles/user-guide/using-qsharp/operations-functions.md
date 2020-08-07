---
title: 中的作業和功能Q#
description: 如何定義和呼叫作業和函式，以及受控制和 adjoint 的操作特製化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 76437c83df894fa86409e680f961d97e267c6869
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867874"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="9f46d-103">中的作業和功能Q#</span><span class="sxs-lookup"><span data-stu-id="9f46d-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="9f46d-104">定義新的作業</span><span class="sxs-lookup"><span data-stu-id="9f46d-104">Defining New Operations</span></span>

<span data-ttu-id="9f46d-105">作業是的核心 Q# 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="9f46d-106">一旦宣告之後，即可從傳統 .NET 應用程式呼叫，例如，使用模擬器或內的其他作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="9f46d-107">在中定義的每個 Q# 作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建函式作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="9f46d-108">Q#定義這些內部作業的特定方式取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="9f46d-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="9f46d-109">在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。</span><span class="sxs-lookup"><span data-stu-id="9f46d-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="9f46d-110">每個 Q# 來源檔案都可以定義任何數目的作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="9f46d-111">作業名稱在命名空間中必須是唯一的，而且不能與類型或函數名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="9f46d-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="9f46d-112">作業宣告包含關鍵字 `operation` ，後面接著是作業名稱的符號、定義作業引數的具類型識別碼元組、冒號 `:` 、描述作業結果類型的類型注釋、選擇性具有作業特性的注釋、左括弧，以及作業宣告的主體，以大括弧括住 `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="9f46d-113">每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="9f46d-114">本文的不同章節會詳細說明可能的特製化，以及如何定義和呼叫這些特殊化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="9f46d-115">現在，請考慮下列作業，這項作業只會定義預設的本文特製化，並以單一 qubit 作為其輸入，然後在該輸入上呼叫內建作業 <xref:microsoft.quantum.intrinsic.x> ：</span><span class="sxs-lookup"><span data-stu-id="9f46d-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="9f46d-116">關鍵字會 `operation` 開始作業定義，後面接著名稱; 此處為 `BitFlip` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="9f46d-117">接下來，輸入的類型會 (`Qubit`) 中定義，以及用 `target` 來參考新作業內之輸入的名稱。</span><span class="sxs-lookup"><span data-stu-id="9f46d-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="9f46d-118">最後， `Unit` 會定義作業的輸出是空的。</span><span class="sxs-lookup"><span data-stu-id="9f46d-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="9f46d-119">`Unit``void`在 c # 和其他命令式語言中的用法類似，而且 `unit` 在 F # 和其他功能性語言中相當於。</span><span class="sxs-lookup"><span data-stu-id="9f46d-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="9f46d-120">作業也會傳回比更有趣 `Unit` 的類型。</span><span class="sxs-lookup"><span data-stu-id="9f46d-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="9f46d-121">例如，作業會傳回 <xref:microsoft.quantum.intrinsic.m> 類型的輸出 `Result` ，表示已執行測量。</span><span class="sxs-lookup"><span data-stu-id="9f46d-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="9f46d-122">您可以從作業將它傳遞至另一個作業，或將它與關鍵字搭配使用 `let` 以定義新的變數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="9f46d-123">這種方法可表示與較低層級的量子作業互動的傳統計算，例如[superdense 編碼](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：</span><span class="sxs-lookup"><span data-stu-id="9f46d-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="9f46d-124">中的每個作業 Q# 都只會採用一個輸入，並只傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="9f46d-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="9f46d-125">多個輸入和輸出會使用*元組*來表示，這會將多個值一起收集成單一值。</span><span class="sxs-lookup"><span data-stu-id="9f46d-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="9f46d-126">就這一點而言，是一種「元組元 Q# 組輸出」語言。</span><span class="sxs-lookup"><span data-stu-id="9f46d-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="9f46d-127">遵循這個概念之後，就應該將一組空括弧 `()` 視為具有類型的「空」元組 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="9f46d-128">控制和 Adjoint 作業</span><span class="sxs-lookup"><span data-stu-id="9f46d-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="9f46d-129">如果作業會執行單一轉換，就像中的許多作業一樣，您 Q# 可以在*adjointed*或*控制*時定義運算的運作方式。</span><span class="sxs-lookup"><span data-stu-id="9f46d-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="9f46d-130">作業的*adjoint*特製化會指定作業的「反向」運作方式，而*受控制*的特製化則會指定作業在其應用程式以特定量子暫存器的狀態為條件時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="9f46d-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="9f46d-131">量子運算的 Adjoints 對於量子計算的許多層面很重要。</span><span class="sxs-lookup"><span data-stu-id="9f46d-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="9f46d-132">如需與有用的程式設計技巧一起討論的其中一種情況的範例 Q# ，請參閱本文中的[動詞變化](#conjugations)。</span><span class="sxs-lookup"><span data-stu-id="9f46d-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="9f46d-133">作業的受控制版本是新的作業，只有在所有控制項 qubits 都處於指定的狀態時，才會有效地套用基底作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="9f46d-134">如果控制項 qubits 在重迭中，則會將基底作業套用 coherently 至重迭的適當部分。</span><span class="sxs-lookup"><span data-stu-id="9f46d-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="9f46d-135">因此，控制的作業通常用來產生會任何牽連。</span><span class="sxs-lookup"><span data-stu-id="9f46d-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="9f46d-136">當然，*控制的 adjoint*特製化也可能存在，指定受控制的作業 adjoint 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9f46d-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="9f46d-137">如果 $U $ 是作業所執行的單一轉換 `U` ，則 `Adjoint U` 代表單一轉換 $U ^ \dagger $，這是複雜的共軛轉型。</span><span class="sxs-lookup"><span data-stu-id="9f46d-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="9f46d-138">連續套用作業，然後其 adjoint 至狀態會使狀態保持不變，如 $UU ^ \dagger = U ^ \dagger U = \id $ （識別矩陣）的事實所示。</span><span class="sxs-lookup"><span data-stu-id="9f46d-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="9f46d-139">控制作業的單一標記法稍微差別細微，但您可以在量子計算概念中找到更多詳細資料[：多個 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="9f46d-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="9f46d-140">下一節說明如何在您的程式碼中呼叫這些特製化 Q# ，以及如何定義作業來支援它們。</span><span class="sxs-lookup"><span data-stu-id="9f46d-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="9f46d-141">呼叫作業特製化</span><span class="sxs-lookup"><span data-stu-id="9f46d-141">Calling operation specializations</span></span>

<span data-ttu-id="9f46d-142">中*functor*的仿函數 Q# 是從另一個作業定義新作業的 factory。</span><span class="sxs-lookup"><span data-stu-id="9f46d-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="9f46d-143">中的兩個標準函子 Q# 為 `Adjoint` 和 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="9f46d-144">函子在定義新作業的執行時，可以存取基底作業的執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="9f46d-145">因此，函子可以執行比傳統更高層級函數更複雜的函式。</span><span class="sxs-lookup"><span data-stu-id="9f46d-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="9f46d-146">函子在型別系統中沒有標記法 Q# 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="9f46d-147">因此目前無法將它們系結至變數，或將它們當做引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="9f46d-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="9f46d-148">將仿函數套用至會傳回新作業的作業，以使用它。</span><span class="sxs-lookup"><span data-stu-id="9f46d-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="9f46d-149">例如，將仿函數套用至作業會傳回 `Adjoint` `Y` 新的作業 `Adjoint Y` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="9f46d-150">您可以叫用新作業，就像任何其他作業一樣。</span><span class="sxs-lookup"><span data-stu-id="9f46d-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="9f46d-151">若要讓作業支援或函子的應用程式，它的傳回型別必須 `Adjoint` `Controlled` 是 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="9f46d-152">`Adjoint`仿函數</span><span class="sxs-lookup"><span data-stu-id="9f46d-152">`Adjoint` functor</span></span>

<span data-ttu-id="9f46d-153">因此， `Adjoint Y(q1)` 會將 `Adjoint` 仿函數套用至作業 `Y` ，以產生新的作業，並將該新作業套用至 `q1` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="9f46d-154">新作業的簽章和類型與基底作業相同 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="9f46d-155">特別是，新作業也支援 `Adjoint` ，而且 `Controlled` 只有在基底作業執行時，才支援。</span><span class="sxs-lookup"><span data-stu-id="9f46d-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="9f46d-156">`Adjoint`仿函數是它自己的反向，也就是 `Adjoint Adjoint Op` 一律與相同 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="9f46d-157">`Controlled`仿函數</span><span class="sxs-lookup"><span data-stu-id="9f46d-157">`Controlled` functor</span></span>

<span data-ttu-id="9f46d-158">同樣地， `Controlled X(controls, target)` `Controlled` 會將仿函數套用至作業 `X` ，以產生新作業，並將該新作業套用至 `controls` 和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="9f46d-159">在中 Q# ，控制的版本一律會採用控制項 qubits 的陣列，而控制一律會以計算 (`PauliZ`) `One` 狀態，$ \ket $ 的所有控制項 qubits 為基礎 {1} 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="9f46d-160">在受控制的作業之前，將適當的單一作業套用至控制項 qubits，然後在受控制的作業之後套用單一作業的反轉，即可根據其他狀態進行控制。</span><span class="sxs-lookup"><span data-stu-id="9f46d-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="9f46d-161">例如，在受控制的作業前後，將作業套用 `X` 至控制項 qubit，會使作業控制 `Zero` 該 qubit 的狀態 ($ \ket {0} $) ; 在 `H` 狀態的控制項之前和之後套用作業 `PauliX` `One` ，也就是-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} ( \ket {0} -\ket {1}) /\sqrt {2} $ 而不是 `PauliZ` `One` 狀態。</span><span class="sxs-lookup"><span data-stu-id="9f46d-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="9f46d-162">假設有作業運算式，您可以使用仿函數來形成新的作業運算式 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="9f46d-163">新作業的簽章是以原始作業的簽章為基礎。</span><span class="sxs-lookup"><span data-stu-id="9f46d-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="9f46d-164">結果型別相同，但輸入型別是具有 qubit 陣列的兩個元組，它會將控制項 qubit (s) 做為第一個專案，並將原始作業的引數當做第二個元素。</span><span class="sxs-lookup"><span data-stu-id="9f46d-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="9f46d-165">新的作業支援 `Controlled` ，而且只有在原始作業執行時，才會支援 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="9f46d-166">如果原始作業只接受單一引數，則會在這裡播放[單一元組等價](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="9f46d-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="9f46d-167">例如，是作業的 `Controlled X` 受控制版本 `X` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="9f46d-168">`X`具有類型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有類型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 因為單一元組等價，所以這與相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="9f46d-169">如果基底作業接受數個引數，請記得將作業之受控制版本的對應引數括在括弧中，以將其轉換為元組。</span><span class="sxs-lookup"><span data-stu-id="9f46d-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="9f46d-170">例如，是作業的 `Controlled Rz` 受控制版本 `Rz` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="9f46d-171">`Rz`具有類型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有類型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="9f46d-172">因此，會 `Controlled Rz(controls, (0.1, target))` 是有效的調用 `Controlled Rz` (請注意) 周圍的括弧 `0.1, target` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="9f46d-173">另一個範例 `CNOT(control, target)` 是，可以實作為 `Controlled X([control], target)` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="9f46d-174">如果目標應該由兩個控制項 qubits 控制 (CCNOT) ，請使用 `Controlled X([control1, control2], target)` 語句。</span><span class="sxs-lookup"><span data-stu-id="9f46d-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="9f46d-175">`Controlled`和 `Adjoint` 函子的上下班，因此套用或之間沒有任何 `Controlled Adjoint Op` 差異 `Adjoint Controlled Op` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="9f46d-176">定義受控制和 Adjoint 的實作為</span><span class="sxs-lookup"><span data-stu-id="9f46d-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="9f46d-177">在先前範例中的第一個作業宣告中，會 `BitFlip` 分別使用簽章和來定義操作和 `DecodeSuperdense` `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="9f46d-178">如同 `DecodeSuperdense` 測量，這不是單一作業，因此不會有任何受控的 adjoint 特製化， (回想這類作業傳回) 的相關需求 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="9f46d-179">不過，只要 `BitFlip` 執行單一作業 <xref:microsoft.quantum.intrinsic.x> ，您就可以使用這兩個特殊化來定義它。</span><span class="sxs-lookup"><span data-stu-id="9f46d-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="9f46d-180">本節將詳細說明如何在您的作業宣告中包含特製化的存在 Q# ，進而讓他們能夠與或函子一起呼叫 `Adjoint` `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="9f46d-181">如需有效或無效以宣告特定特製化的某些情況的詳細資訊，請參閱本文中可有效[定義特殊化的狀況](#circumstances-for-validly-defining-specializations)。</span><span class="sxs-lookup"><span data-stu-id="9f46d-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="9f46d-182">作業特性會定義您可以套用至已宣告作業的函子種類，以及它們的效果。</span><span class="sxs-lookup"><span data-stu-id="9f46d-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="9f46d-183">這些特製化的存在可以宣告為作業簽章的一部分，特別是透過具有作業特性的注釋： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="9f46d-184">每個特製化的實際執行方式可以是*隱含*或*明確*定義的。</span><span class="sxs-lookup"><span data-stu-id="9f46d-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="9f46d-185">隱含指定實現</span><span class="sxs-lookup"><span data-stu-id="9f46d-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="9f46d-186">在此情況下，作業宣告的主體只會包含預設的實作為。</span><span class="sxs-lookup"><span data-stu-id="9f46d-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="9f46d-187">例如：</span><span class="sxs-lookup"><span data-stu-id="9f46d-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="9f46d-188">在這裡，編譯器會自動產生每個這類隱含宣告特製化的對應實作為，以在 `Adjoint` 使用或 `Controlled` 函子時執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="9f46d-189">因此，的呼叫 `Adjoint PrepareEntangledPair` 會導致編譯器先執行的 adjoint `CNOT` ，然後再進行的 adjoint `H` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="9f46d-190">這些個別的作業都是自我 adjoint，因此產生的作業 `Adjoint PrepareEntangledPair` 只會包含套用，然後才會套用 `CNOT(here, there)` `H(here)` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="9f46d-191">因此，您可以使用這個來撰寫 `DecodeSuperdense` 上一個範例中更簡潔地的，方法是使用的 adjoint， `PrepareEntangledPair` 將光子狀態轉換回 unentangled 對 qubits：</span><span class="sxs-lookup"><span data-stu-id="9f46d-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="9f46d-192">在宣告中具有作業特性的注釋，非常適合用來確保編譯器會根據預設執行自動產生其他特製化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="9f46d-193">設計要與函子搭配使用的作業時，有幾個重要的限制需要考慮。</span><span class="sxs-lookup"><span data-stu-id="9f46d-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="9f46d-194">最重要的是，使用任何其他作業的輸出值之作業的特製化，*不能*由編譯器自動產生，因為在這類作業中重新排序語句以取得相同的效果並不明確。</span><span class="sxs-lookup"><span data-stu-id="9f46d-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="9f46d-195">因此，明確指定各種不同的執行通常會很有用。</span><span class="sxs-lookup"><span data-stu-id="9f46d-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="9f46d-196">明確指定實現</span><span class="sxs-lookup"><span data-stu-id="9f46d-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="9f46d-197">在編譯器無法產生執行的情況下，您可以明確地指定它。</span><span class="sxs-lookup"><span data-stu-id="9f46d-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="9f46d-198">這類明確特製化宣告可以包含適當的*世代*指示詞或使用者定義的實作為。</span><span class="sxs-lookup"><span data-stu-id="9f46d-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="9f46d-199">以下是完整的各種可能性，並提供一些明確特製化的範例。</span><span class="sxs-lookup"><span data-stu-id="9f46d-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="9f46d-200">明確特製化宣告</span><span class="sxs-lookup"><span data-stu-id="9f46d-200">Explicit specialization declarations</span></span>

<span data-ttu-id="9f46d-201">Q#作業可以包含下列明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="9f46d-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="9f46d-202">特製 `body` 化會指定未套用任何函子之作業的執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="9f46d-203">特製 `adjoint` 化會指定已套用仿函數之作業的執行 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="9f46d-204">特製 `controlled` 化會指定已套用仿函數之作業的執行 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="9f46d-205">特製 `controlled adjoint` 化會指定同時套用和函子作業的執行 `Adjoint` `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="9f46d-206">這個特製化也可以命名為 `adjoint controlled` ，因為這兩個函子會向下。</span><span class="sxs-lookup"><span data-stu-id="9f46d-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="9f46d-207">作業特製化包含特製化標記 (例如， `body` 或 `adjoint`) 後面接著其中一個：</span><span class="sxs-lookup"><span data-stu-id="9f46d-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="9f46d-208">如下所述的明確宣告。</span><span class="sxs-lookup"><span data-stu-id="9f46d-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="9f46d-209">指示編譯器*如何*產生特製化*的指示詞，這是*下列其中一個：</span><span class="sxs-lookup"><span data-stu-id="9f46d-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="9f46d-210">`intrinsic`，表示目的電腦提供特製化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="9f46d-211">`distribute`，搭配和特製化使用 `controlled` `controlled adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="9f46d-212">與搭配使用時 `controlled` ，它會指出編譯器應該藉由套用 `Controlled` 至中的所有作業來計算特製化 `body` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="9f46d-213">與搭配使用時 `controlled adjoint` ，它會指出編譯器應該藉由套用至特製 `Controlled` 化中的所有作業來計算特製化 `adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="9f46d-214">`invert`，這表示編譯器應該藉由反轉來計算特製 `adjoint` 化 `body` ，例如，反轉作業的順序，並將 adjoint 套用至每一個。</span><span class="sxs-lookup"><span data-stu-id="9f46d-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="9f46d-215">與搭配使用時 `adjoint controlled` ，這表示編譯器應該藉由反轉特製化來計算特製化 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="9f46d-216">`self`，表示 adjoint 特製化與特製 `body` 化相同。</span><span class="sxs-lookup"><span data-stu-id="9f46d-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="9f46d-217">對於和特製化而言，使用 `self` 是合法的 `adjoint` `adjoint controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="9f46d-218">針對 `adjoint controlled` ，表示特製化與特製化 `self` `adjoint controlled` 相同 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="9f46d-219">`auto`，表示編譯器應該選取要套用的適當指示詞。</span><span class="sxs-lookup"><span data-stu-id="9f46d-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="9f46d-220">您不能將 `auto` 用於特製 `body` 化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="9f46d-221">指示詞和 `auto` 全部都需要結尾的分號 `;` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="9f46d-222">如果提供的明確宣告，指示詞 `auto` 會解析為下列產生的指示詞 `body` ：</span><span class="sxs-lookup"><span data-stu-id="9f46d-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="9f46d-223">特製 `adjoint` 化會根據指示詞產生 `invert` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="9f46d-224">特製 `controlled` 化會根據指示詞產生 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="9f46d-225">`adjoint controlled` `invert` 如果指定了的明確宣告 `controlled` ，而不是針對，則特製化會根據指示詞產生 `adjoint` ，否則為 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="9f46d-226">如果作業是自我 adjoint 的，請透過世代指示詞明確指定 adjoint 或受控制的 adjoint 特製化， `self` 以允許編譯器使用該資訊來進行優化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="9f46d-227">包含使用者定義之實作為的特製化宣告，是由引數元組後面接著語句區塊與執行特製 Q# 化的程式碼所組成。</span><span class="sxs-lookup"><span data-stu-id="9f46d-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="9f46d-228">在引數清單中， `...` 是用來代表整個作業所宣告的引數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="9f46d-229">針對 `body` 和 `adjoint` ，引數清單應一律為 `(...)` ; 針對 `controlled` 和 `adjoint controlled` ，引數清單應該是代表控制項 qubits 陣列的符號，後面接著 `...` 以括弧括住 `(controls,...)` ，例如。</span><span class="sxs-lookup"><span data-stu-id="9f46d-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="9f46d-230">範例</span><span class="sxs-lookup"><span data-stu-id="9f46d-230">Examples</span></span>

<span data-ttu-id="9f46d-231">作業宣告可能會像下面這樣簡單，其定義基本的 Pauli X 運算：</span><span class="sxs-lookup"><span data-stu-id="9f46d-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="9f46d-232">請注意，Pauli X 作業的 adjoint 是以指示詞定義， `self` 因為根據定義 `X` 是它自己的反向。</span><span class="sxs-lookup"><span data-stu-id="9f46d-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="9f46d-233">在先前的 `PrepareEntangledPair` 範例中，程式碼相當於包含明確特製化宣告的下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="9f46d-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="9f46d-234">關鍵字 `auto` 表示編譯器應該決定如何產生特製化執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="9f46d-235">使用者定義的特製化執行</span><span class="sxs-lookup"><span data-stu-id="9f46d-235">User-defined specialization implementation</span></span>

<span data-ttu-id="9f46d-236">如果編譯器無法自動產生特定特製化的實作為，或者可以指定更有效率的執行，則您可以手動定義執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="9f46d-237">在上述範例中， `adjoint invert;` 表示 adjoint 特製化是藉由將主體實作為反轉而產生，並 `controlled adjoint invert;` 指出受控制的 adjoint 特製化是藉由反轉所控制特製化的指定實作為而產生的。</span><span class="sxs-lookup"><span data-stu-id="9f46d-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="9f46d-238">如果需要明確宣告預設主體以外的一個或多個特製化，則預設主體的執行也必須包裝為適當的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="9f46d-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="9f46d-239">有效定義特製化的情況</span><span class="sxs-lookup"><span data-stu-id="9f46d-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="9f46d-240">具有 adjoint/受控的作業宣告</span><span class="sxs-lookup"><span data-stu-id="9f46d-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="9f46d-241">指定不含 adjoint 或受控制版本的作業是合法的。</span><span class="sxs-lookup"><span data-stu-id="9f46d-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="9f46d-242">比方說，測量作業並不是因為不可逆或可控制的。</span><span class="sxs-lookup"><span data-stu-id="9f46d-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="9f46d-243">如果作業的宣告 `Adjoint` 包含個別特製化的隱含或明確宣告，則作業支援和 `Controlled` 函子。</span><span class="sxs-lookup"><span data-stu-id="9f46d-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="9f46d-244">明確宣告的 adjoint/控制特製化意味著存在 adjoint/控制特製化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="9f46d-245">如果作業的主體包含重複執行迴圈、set 語句、量值、傳回語句，或呼叫不支援仿函數的其他作業 `Adjoint` ， `invert` `auto` 則不能在或指示詞之後自動產生 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="9f46d-246">若作業的主體包含不支援仿函數的其他作業呼叫 `Controlled` ，就無法在或指示詞之後自動產生受控制的特製化 `distribute` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="9f46d-247">控制的 Adjoint</span><span class="sxs-lookup"><span data-stu-id="9f46d-247">Controlled Adjoint</span></span>

<span data-ttu-id="9f46d-248">作業的受控制 adjoint 版本會指定如何執行作業 adjoint 的量子控制版本。</span><span class="sxs-lookup"><span data-stu-id="9f46d-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="9f46d-249">指定沒有受控制 adjoint 版本的作業是合法的：比方說，測量作業沒有受控制的 adjoint 版本，因為它們都不是可控制也不可逆。</span><span class="sxs-lookup"><span data-stu-id="9f46d-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="9f46d-250">只有在 adjoint 和受控制的特製化都存在時，作業的受控制 adjoint 特製化才需要存在。</span><span class="sxs-lookup"><span data-stu-id="9f46d-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="9f46d-251">在此情況下，會推斷受控制的 adjoint 特製化是否存在。</span><span class="sxs-lookup"><span data-stu-id="9f46d-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="9f46d-252">如果未明確定義任何實作為，則編譯會產生適當的特製化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="9f46d-253">若作業的內文包含的呼叫不具有受控制 adjoint 版本的其他作業， `invert` 就無法在、或指示詞之後自動產生 adjoint 特製化 `distribute` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="9f46d-254">類型相容性</span><span class="sxs-lookup"><span data-stu-id="9f46d-254">Type Compatibility</span></span>

<span data-ttu-id="9f46d-255">如果您使用的作業具有較少的函子但具有相同的簽章，請使用具有其他函子支援的作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="9f46d-256">例如， `(Qubit => Unit is Adj)` 在您使用類型作業的任何位置使用類型的作業 `(Qubit => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="9f46d-257">Q#對於可呼叫的傳回型別而言是*協*變數的：傳回類型的可呼叫，與 `'A` 具有相同輸入類型的可呼叫，以及與相容的結果類型相容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="9f46d-258">Q#是相對於輸入類型的*逆變*性：接受類型做為輸入的可呼叫，與 `'A` 具有相同結果類型的可呼叫和與相容的輸入類型相容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="9f46d-259">也就是，假設有下列定義，</span><span class="sxs-lookup"><span data-stu-id="9f46d-259">That is, given the following definitions,</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="9f46d-260">您可以</span><span class="sxs-lookup"><span data-stu-id="9f46d-260">you can</span></span>

- <span data-ttu-id="9f46d-261">`ConjugateInvertWith`使用 `inner` 或的引數叫用函數 `Invert` `ApplyUnitary` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="9f46d-262">`ConjugateUnitaryWith`使用的引數叫用函式 `inner` `ApplyUnitary` ，但不叫用 `Invert` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="9f46d-263">從傳回類型的值 `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f46d-264">Q#0.3 在使用者定義型別的行為上引進了顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="9f46d-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="9f46d-265">使用者自訂類型會被視為基礎類型的包裝版本，而不是子類型。</span><span class="sxs-lookup"><span data-stu-id="9f46d-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="9f46d-266">這表示當您預期基礎類型的值為時，使用者自訂類型的值無法使用。</span><span class="sxs-lookup"><span data-stu-id="9f46d-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="9f46d-267">動詞變化</span><span class="sxs-lookup"><span data-stu-id="9f46d-267">Conjugations</span></span>

<span data-ttu-id="9f46d-268">相較于傳統的位，釋出配量記憶體會稍微複雜一點，因為如果 qubits 仍光子，則盲目重設 qubits 可能會對其餘的計算造成不想要的效果。</span><span class="sxs-lookup"><span data-stu-id="9f46d-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="9f46d-269">藉由適當地「復原」在釋放記憶體之前執行的計算，可以避免這些效果。</span><span class="sxs-lookup"><span data-stu-id="9f46d-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="9f46d-270">量子運算的常見模式如下：</span><span class="sxs-lookup"><span data-stu-id="9f46d-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="9f46d-271">從0.9 版開始， Q# 支援 conjugation 語句來執行先前的轉換。</span><span class="sxs-lookup"><span data-stu-id="9f46d-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="9f46d-272">使用該語句，可以透過 `ApplyWith` 下列方式來執行作業：</span><span class="sxs-lookup"><span data-stu-id="9f46d-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="9f46d-273">如果外部和內部轉換無法立即當做作業使用，這類 conjugation 語句就會變得更有用，但更方便由數個語句所組成的區塊描述。</span><span class="sxs-lookup"><span data-stu-id="9f46d-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="9f46d-274">在區塊內定義的語句的反向轉換會由編譯器自動產生，並在套用區塊完成後執行。</span><span class="sxs-lookup"><span data-stu-id="9f46d-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="9f46d-275">因為任何用來做為內部區塊一部分的可變變數無法在套用區塊中重新系結，所以產生的轉換保證會是在區塊內的計算 adjoint。</span><span class="sxs-lookup"><span data-stu-id="9f46d-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="9f46d-276">定義新函數</span><span class="sxs-lookup"><span data-stu-id="9f46d-276">Defining New Functions</span></span>

<span data-ttu-id="9f46d-277">函式在中純粹是具決定性的傳統常式 Q# ，這與作業不同，因為它們不允許超出計算輸出值的任何效果。</span><span class="sxs-lookup"><span data-stu-id="9f46d-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="9f46d-278">特別是，函數無法呼叫作業;採取行動、配置或借用 qubits;範例亂數字;或以其他方式相依于函式的輸入值以外的狀態。</span><span class="sxs-lookup"><span data-stu-id="9f46d-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="9f46d-279">因此， Q# 函數是*單純*的，因為它們一律會將相同的輸入值對應到相同的輸出值。</span><span class="sxs-lookup"><span data-stu-id="9f46d-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="9f46d-280">這種行為可讓編譯器在產生作業特製化 Q# 時，安全地重新排序呼叫函式的方式和時機。</span><span class="sxs-lookup"><span data-stu-id="9f46d-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="9f46d-281">每個 Q# 來源檔案都可以定義任何數目的函數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="9f46d-282">函數名稱在命名空間中必須是唯一的，而且不能與作業或類型名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="9f46d-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="9f46d-283">定義函式的運作方式類似于定義作業，不同之處在于無法為函式定義任何 adjoint 或受控特殊化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="9f46d-284">例如：</span><span class="sxs-lookup"><span data-stu-id="9f46d-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="9f46d-285">或</span><span class="sxs-lookup"><span data-stu-id="9f46d-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="9f46d-286">函數中的傳統邏輯 = = 良好</span><span class="sxs-lookup"><span data-stu-id="9f46d-286">Classical logic in functions == good</span></span>

<span data-ttu-id="9f46d-287">只要能夠這麼做，就能以函式而非作業的形式寫出傳統邏輯，以方便作業使用。</span><span class="sxs-lookup"><span data-stu-id="9f46d-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="9f46d-288">例如，如果您已將先前的宣告撰寫 `Square` 為作業*operation*，則編譯器無法保證以相同的輸入呼叫它，會一致地產生相同的輸出。</span><span class="sxs-lookup"><span data-stu-id="9f46d-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="9f46d-289">若要以底線表示函式和作業之間的差異，請考慮從作業內將亂數字取樣的傳統方式問題 Q# ：</span><span class="sxs-lookup"><span data-stu-id="9f46d-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="9f46d-290">每次 `U` 呼叫時，它會在上有不同的動作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="9f46d-291">特別是，編譯器無法保證如果您將特製化宣告加入 `adjoint auto` 至 `U` ，則會做為身分 `U(target); Adjoint U(target);` 識別 (也就是無作業) 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="9f46d-292">這會違反[向量和矩陣](xref:microsoft.quantum.concepts.vectors)中定義的 adjoint 定義，如此一來，在您呼叫作業的作業中，允許編譯器自動產生 adjoint 特製化， <xref:microsoft.quantum.math.randomreal> 會中斷編譯器所提供的保證; <xref:microsoft.quantum.math.randomreal> 是沒有 adjoint 或控制版本的作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="9f46d-293">相反地，允許函式呼叫（例如） `Square` 是安全的，而且會確保編譯器只需要保留輸入來 `Square` 保持其輸出穩定。</span><span class="sxs-lookup"><span data-stu-id="9f46d-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="9f46d-294">因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。</span><span class="sxs-lookup"><span data-stu-id="9f46d-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="9f46d-295">泛型 (類型參數化) Callables</span><span class="sxs-lookup"><span data-stu-id="9f46d-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="9f46d-296">許多您可能想要定義的函式和作業實際上並不會依賴其輸入的類型，而只會透過一些其他函式或運算，隱含地使用其類型。</span><span class="sxs-lookup"><span data-stu-id="9f46d-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="9f46d-297">例如，請考慮許多功能性語言通用的*地圖*概念;假設函式 $f (x) $ 和值 $ x_1 的集合， \{ x_2，\dots ..，x_n \} $，map 會傳回新的集合 $ \{ f (x_1) ，f (x_2) ，\dots ..，f (x_n) \} $。</span><span class="sxs-lookup"><span data-stu-id="9f46d-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="9f46d-298">若要在中執行此 Q# 功能，請利用函式為第一個類別的事實。</span><span class="sxs-lookup"><span data-stu-id="9f46d-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="9f46d-299">以下是的快速範例 `Map` ，在 `T` 您找出所需的類型時，使用做為預留位置。</span><span class="sxs-lookup"><span data-stu-id="9f46d-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="9f46d-300">請注意，無論您在什麼實際類型中替換，此函式看起來都一樣。</span><span class="sxs-lookup"><span data-stu-id="9f46d-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="9f46d-301">例如，從整數到 Paulis 的對應，與從浮點數到字串的對應大致相同：</span><span class="sxs-lookup"><span data-stu-id="9f46d-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="9f46d-302">原則上，您可以 `Map` 針對所遇到的每一對類型撰寫的版本，但這會導致幾個問題。</span><span class="sxs-lookup"><span data-stu-id="9f46d-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="9f46d-303">比方說，如果您在中發現錯誤 `Map` ，則必須確定已在所有版本的中統一套用修正程式 `Map` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="9f46d-304">此外，如果您要建立新的元組或 UDT，則您現在也必須建立新的 `Map` 來搭配新的類型。</span><span class="sxs-lookup"><span data-stu-id="9f46d-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="9f46d-305">雖然這只是針對少數這類函式所方便追蹤，但當您收集的函式與相同形式的多個函式相同時 `Map` ，引入新類型的成本會以相當短的順序過長龐大。</span><span class="sxs-lookup"><span data-stu-id="9f46d-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="9f46d-306">不過，這項困難的原因是您未指定編譯器所需的資訊，以辨識不同版本的 `Map` 關聯方式。</span><span class="sxs-lookup"><span data-stu-id="9f46d-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="9f46d-307">實際上，您希望編譯器視為 `Map` 某種類型的數學函式，從型別 Q# *types*到 Q# 函數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="9f46d-308">Q#藉由允許函式和作業具有型別*參數*，以及其一般的元組參數，來將此概念正規化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="9f46d-309">在先前的範例中，您想要 `Map` `Int, Pauli` 在第一個案例和 `Double, String` 第二個案例中將視為具有型別參數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="9f46d-310">在大部分的情況下，請使用這些類型參數，就像是一般類型一樣。</span><span class="sxs-lookup"><span data-stu-id="9f46d-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="9f46d-311">使用類型參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變變數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="9f46d-312">間接相依性最極端的情況，就是 qubits 的，其中 Q# 程式無法直接依賴類型的結構， `Qubit` 但**必須**將這類類型傳遞給其他作業和函式。</span><span class="sxs-lookup"><span data-stu-id="9f46d-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="9f46d-313">回到先前的範例，接著您會看到 `Map` 需要有型別參數，一個用來表示的輸入，另一個用 `fn` 來表示的輸出 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="9f46d-314">在中，這是藉由在其宣告中的函式 Q# 或作業名稱後面加上角括弧 (， `<>` 而不是 brakets $ \braket {} $！ ) 之後，並列出每個型別參數來撰寫。</span><span class="sxs-lookup"><span data-stu-id="9f46d-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="9f46d-315">每個型別參數的名稱都必須以滴答開頭 `'` ，表示它是型別參數，而不是一般型別 (也稱為*實體*型別) 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="9f46d-316">因此， `Map` 會寫入：</span><span class="sxs-lookup"><span data-stu-id="9f46d-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="9f46d-317">請注意，的定義 `Map<'Input, 'Output>` 看起來非常類似于 previoius 版本。</span><span class="sxs-lookup"><span data-stu-id="9f46d-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="9f46d-318">唯一的差別在於，您已明確告知編譯器，其 `Map` 不會直接相依于 `'Input` 和 `'Output` ，但可透過間接使用它們來處理任何兩種類型 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="9f46d-319">`Map<'Input, 'Output>`以這種方式定義之後，您就可以像一般函式一樣呼叫它：</span><span class="sxs-lookup"><span data-stu-id="9f46d-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="9f46d-320">撰寫泛型函式和作業是一個位置，其中「元組元組輸出」是一種很有用的方式來考慮 Q# 函數和作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="9f46d-321">因為每個函式只接受一個輸入，而且只會傳回一個輸出，所以類型的輸入會 `'T -> 'U` 符合*任何* Q# 函數。</span><span class="sxs-lookup"><span data-stu-id="9f46d-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="9f46d-322">同樣地，您可以將任何作業傳遞至類型的輸入 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="9f46d-323">作為第二個範例，請考慮撰寫會傳回兩個其他函式之組合的函式的挑戰：</span><span class="sxs-lookup"><span data-stu-id="9f46d-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="9f46d-324">在這裡，您必須指定、和的確切內容 `A` `B` `C` ，因此會嚴重限制新函式的公用程式 `Compose` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="9f46d-325">畢竟， `Compose` 只取決於 `A` 、 `B` 和 `C` *via* `innerFn` `outerFn` 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="9f46d-326">或者，您可以將型別參數新增至，以 `Compose` 表示它適用于*任何* `A` 、 `B` 和 `C` ，只要這些參數符合和所預期的參數即可 `innerFn` `outerFn` ：</span><span class="sxs-lookup"><span data-stu-id="9f46d-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="9f46d-327">Q#標準程式庫提供一系列這類類型參數化的作業和函式，讓您更容易表達更高順序的控制流程。</span><span class="sxs-lookup"><span data-stu-id="9f46d-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="9f46d-328">這些會在[ Q# 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。</span><span class="sxs-lookup"><span data-stu-id="9f46d-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="9f46d-329">Callables 為第一級值</span><span class="sxs-lookup"><span data-stu-id="9f46d-329">Callables as First-Class Values</span></span>

<span data-ttu-id="9f46d-330">使用函式而不是作業來推理控制流程和傳統邏輯的一項重要技巧，就是利用中的作業和函 Q# *式為第一類*。</span><span class="sxs-lookup"><span data-stu-id="9f46d-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="9f46d-331">也就是說，它們是語言中的每個值本身的許可權。</span><span class="sxs-lookup"><span data-stu-id="9f46d-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="9f46d-332">比方說，下列是完全有效的程式 Q# 代碼，如果有一些間接的：</span><span class="sxs-lookup"><span data-stu-id="9f46d-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="9f46d-333">`ourH`前一個程式碼片段中的變數值就是作業 <xref:microsoft.quantum.intrinsic.h> ，因此您可以像任何其他作業一樣呼叫該值。</span><span class="sxs-lookup"><span data-stu-id="9f46d-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="9f46d-334">有了這項功能，您就可以撰寫在其輸入過程中採取作業的作業，形成更高順序的控制流程概念。</span><span class="sxs-lookup"><span data-stu-id="9f46d-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="9f46d-335">例如，您可以想像想要「正方形」作業，方法是將它套用至相同的目標 qubit 兩次。</span><span class="sxs-lookup"><span data-stu-id="9f46d-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="9f46d-336">從函式傳回作業</span><span class="sxs-lookup"><span data-stu-id="9f46d-336">Returning operations from a function</span></span>

<span data-ttu-id="9f46d-337">請務必強調，您也可以將作業當做輸出的一部分傳回，讓您可以將一些傳統條件式邏輯隔離為傳統函式，以作業的形式傳回配量程式的描述。</span><span class="sxs-lookup"><span data-stu-id="9f46d-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="9f46d-338">做為簡單的範例，請考慮 teleportation 範例，其中接收兩個傳統訊息的合作物件需要使用訊息，將其 qubit 解碼為適當的傳送狀態。</span><span class="sxs-lookup"><span data-stu-id="9f46d-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="9f46d-339">您可以使用這兩個傳統位的函式來撰寫此程式，並傳回適當的解碼作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="9f46d-340">這個新函式確實是一個函式，在此情況下，如果您使用與相同的值來呼叫它 `hereBit` `thereBit` ，則一律會取回相同的作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="9f46d-341">因此，此解碼器可以安全地在作業內執行，而不需考慮解碼邏輯如何與不同作業特製化的定義互動。</span><span class="sxs-lookup"><span data-stu-id="9f46d-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="9f46d-342">也就是說，函式內的傳統邏輯是隔離的，只要保留輸入，就能保證編譯器可以將函式呼叫與 impunity 重新排序。</span><span class="sxs-lookup"><span data-stu-id="9f46d-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="9f46d-343">部分應用程式</span><span class="sxs-lookup"><span data-stu-id="9f46d-343">Partial Application</span></span>

<span data-ttu-id="9f46d-344">您可以透過使用*部分應用程式*來傳回作業的函式執行更多動作，在此情況下，您可以將輸入的一個或多個部分提供給函式或作業，而不需要實際呼叫它。</span><span class="sxs-lookup"><span data-stu-id="9f46d-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="9f46d-345">在先前的 `ApplyTwice` 範例中，您可以指出您不想要立即指定應套用輸入作業的 qubit：</span><span class="sxs-lookup"><span data-stu-id="9f46d-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="9f46d-346">在此情況下，本機變數會保存部分套用的作業 `twiceOp` `ApplyTwice(op, _)` ，其中 `_` 表示尚未指定的輸入部分。</span><span class="sxs-lookup"><span data-stu-id="9f46d-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="9f46d-347">當您 `twiceOp` 在下一行中呼叫時，您會將輸入的所有其餘部分當做原始作業，傳遞至部分套用的運算。</span><span class="sxs-lookup"><span data-stu-id="9f46d-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="9f46d-348">因此，先前的程式碼片段實際上與直接呼叫相同 `ApplyTwice(op, target)` ，請儲存您已引進新的區域變數，讓您可以延遲呼叫，同時提供輸入的某些部分。</span><span class="sxs-lookup"><span data-stu-id="9f46d-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="9f46d-349">由於已進行部分套用的作業，在提供完整的輸入之前，並不會實際呼叫，因此您甚至可以從函式中，安全地部分套用作業。</span><span class="sxs-lookup"><span data-stu-id="9f46d-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="9f46d-350">原則上，中的傳統邏輯 `SquareOperation` 可能更牽涉到，但它仍會與作業的其餘部分隔離，因為編譯器可以提供關於函數的保證。</span><span class="sxs-lookup"><span data-stu-id="9f46d-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="9f46d-351">Q#標準程式庫會在整個中使用此方法，以量副程式可輕易使用的方式來表示傳統控制流程。</span><span class="sxs-lookup"><span data-stu-id="9f46d-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="9f46d-352">遞迴</span><span class="sxs-lookup"><span data-stu-id="9f46d-352">Recursion</span></span>

<span data-ttu-id="9f46d-353">Q#callables 允許直接或間接遞迴。</span><span class="sxs-lookup"><span data-stu-id="9f46d-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="9f46d-354">也就是，作業或函式可以呼叫本身，也可以呼叫另一個可直接或間接呼叫可呼叫作業的調用。</span><span class="sxs-lookup"><span data-stu-id="9f46d-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="9f46d-355">使用遞迴有兩個重要的批註，不過：</span><span class="sxs-lookup"><span data-stu-id="9f46d-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="9f46d-356">在作業中使用遞迴可能會干擾特定的優化。</span><span class="sxs-lookup"><span data-stu-id="9f46d-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="9f46d-357">這項干擾可能會對演算法的執行時間產生重大影響。</span><span class="sxs-lookup"><span data-stu-id="9f46d-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="9f46d-358">在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深度遞迴可能會導致執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="9f46d-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="9f46d-359">特別是， Q# 編譯器和執行時間不會識別並優化尾遞迴。</span><span class="sxs-lookup"><span data-stu-id="9f46d-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9f46d-360">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9f46d-360">Next steps</span></span>

<span data-ttu-id="9f46d-361">瞭解中[Variables](xref:microsoft.quantum.guide.variables)的變數 Q# 。</span><span class="sxs-lookup"><span data-stu-id="9f46d-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>