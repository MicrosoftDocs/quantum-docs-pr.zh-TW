---
title: Q 中的作業和函數#
description: 如何定義和呼叫作業和函式，以及受控制和 adjoint 的操作特製化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431065"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="5e844-103">Q 中的作業和函數#</span><span class="sxs-lookup"><span data-stu-id="5e844-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="5e844-104">定義新的作業</span><span class="sxs-lookup"><span data-stu-id="5e844-104">Defining New Operations</span></span>

<span data-ttu-id="5e844-105">作業是 Q # 的核心。</span><span class="sxs-lookup"><span data-stu-id="5e844-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="5e844-106">一旦宣告之後，您可以從傳統 .NET 應用程式（例如，使用模擬器），或由 Q # 中的其他作業呼叫。</span><span class="sxs-lookup"><span data-stu-id="5e844-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="5e844-107">在 Q # 中定義的每個作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建函式作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="5e844-108">定義這些內部作業的特定方式取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="5e844-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="5e844-109">在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。</span><span class="sxs-lookup"><span data-stu-id="5e844-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="5e844-110">每個 Q # 來源檔案都可以定義任何數目的作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="5e844-111">作業名稱在命名空間中必須是唯一的，而且可能不會與類型或函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="5e844-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="5e844-112">作業宣告包含關鍵字 `operation` ，後面接著是作業名稱的符號、定義作業引數的具類型識別碼元組、冒號 `:` 、描述作業結果類型的類型注釋、選擇性具有作業特性的注釋、左括弧、作業宣告 `{` 的主體，以及最後的右大括弧 `}` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="5e844-113">每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="5e844-114">以下詳細說明可能的特製化，以及如何定義/呼叫它們。</span><span class="sxs-lookup"><span data-stu-id="5e844-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="5e844-115">現在，請考慮下列作業，這項作業只會定義預設的本文特製化，並以單一 qubit 作為其輸入，然後在該輸入上呼叫內建作業 <xref:microsoft.quantum.intrinsic.x> ：</span><span class="sxs-lookup"><span data-stu-id="5e844-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="5e844-116">關鍵字 `operation` 會開始作業定義，後面接著名稱; 此處為 `BitFlip` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="5e844-117">接下來，輸入的類型會定義為 `Qubit` ，並使用名稱 `target` 來參考新作業中的輸入。</span><span class="sxs-lookup"><span data-stu-id="5e844-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="5e844-118">同樣地， `Unit` 會定義作業的輸出是空的。</span><span class="sxs-lookup"><span data-stu-id="5e844-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="5e844-119">這 `void` 在 c # 和其他命令式語言中的用法類似，相當於 `unit` F # 和其他功能性語言。</span><span class="sxs-lookup"><span data-stu-id="5e844-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="5e844-120">作業也會傳回比更有趣 `Unit` 的類型。</span><span class="sxs-lookup"><span data-stu-id="5e844-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="5e844-121">例如，作業會傳回 <xref:microsoft.quantum.intrinsic.m> 類型的輸出 `Result` ，表示已執行測量。</span><span class="sxs-lookup"><span data-stu-id="5e844-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="5e844-122">我們可以將作業的輸出傳遞至另一個作業，或可搭配 `let` 關鍵字來定義新的變數。</span><span class="sxs-lookup"><span data-stu-id="5e844-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="5e844-123">這可代表在較低層級與量子作業互動的傳統計算，例如[superdense 編碼](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：</span><span class="sxs-lookup"><span data-stu-id="5e844-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="5e844-124">Q # 中的每個作業都只接受一個輸入，並只傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="5e844-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="5e844-125">接著會使用*元組*來表示多個輸入和輸出，這會將多個值一起收集成單一值。</span><span class="sxs-lookup"><span data-stu-id="5e844-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="5e844-126">非正式地說，問 # 是一種「元組輸出」語言。</span><span class="sxs-lookup"><span data-stu-id="5e844-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="5e844-127">遵循此概念之後， `()` 應該會讀取為具有類型的「空」元組 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="5e844-128">控制和 Adjoint 作業</span><span class="sxs-lookup"><span data-stu-id="5e844-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="5e844-129">如果作業會執行單一轉換，如同在 Q # 中的許多作業，則可以在*adjointed*或*控制*時定義操作的運作方式。</span><span class="sxs-lookup"><span data-stu-id="5e844-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="5e844-130">作業的*adjoint*特製化會指定作業的「反向」運作方式，而*受控制*的特製化則會指定作業在其應用程式以特定量子暫存器的狀態為條件時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="5e844-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="5e844-131">量子運算的 Adjoints 對於量子計算的許多層面很重要。</span><span class="sxs-lookup"><span data-stu-id="5e844-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="5e844-132">接下來，在 [[動詞變化](#conjugations)] 區段中，您會發現其中一個這類情況會與有用的 Q # 程式設計技術一起討論。</span><span class="sxs-lookup"><span data-stu-id="5e844-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="5e844-133">作業的受控制版本是新的作業，只有在所有控制項 qubits 都處於指定的狀態時，才會有效地套用基底作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="5e844-134">如果控制項 qubits 在重迭中，則會將基底作業套用 coherently 至重迭的適當部分。</span><span class="sxs-lookup"><span data-stu-id="5e844-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="5e844-135">因此，控制的作業通常用來產生會任何牽連。</span><span class="sxs-lookup"><span data-stu-id="5e844-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="5e844-136">當然，*控制的 adjoint*特製化也可能存在，指定受控制的作業 adjoint 應用程式。</span><span class="sxs-lookup"><span data-stu-id="5e844-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="5e844-137">如果 $U $ 是作業所執行的單一轉換 `U` ，則 `Adjoint U` 代表單一轉換 $U ^ \dagger $，這是複雜的共軛轉型。</span><span class="sxs-lookup"><span data-stu-id="5e844-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="5e844-138">連續套用作業，然後其 adjoint 至狀態會使狀態保持不變，如 $UU ^ \dagger = U ^ \dagger U = \id $ （識別矩陣）的事實所示。</span><span class="sxs-lookup"><span data-stu-id="5e844-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="5e844-139">控制作業的單一標記法稍微差別細微，但您可以在量子計算概念中找到更多詳細資料[：多個 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="5e844-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="5e844-140">下一節說明如何在您的 Q # 程式碼中呼叫這些特殊化。</span><span class="sxs-lookup"><span data-stu-id="5e844-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="5e844-141">在下面，我們將詳細說明如何定義作業來支援它們。</span><span class="sxs-lookup"><span data-stu-id="5e844-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="5e844-142">呼叫作業特製化</span><span class="sxs-lookup"><span data-stu-id="5e844-142">Calling operation specializations</span></span>

<span data-ttu-id="5e844-143">問 # 中的*仿函數*是從另一個作業定義新作業的 factory。</span><span class="sxs-lookup"><span data-stu-id="5e844-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="5e844-144">Q # 中的兩個標準函子為 `Adjoint` 和 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="5e844-145">函子在定義新作業的執行時，可以存取基底作業的執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="5e844-146">因此，函子可以執行比傳統更高層級函數更複雜的函式。</span><span class="sxs-lookup"><span data-stu-id="5e844-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="5e844-147">函子在 Q # 類型系統中沒有標記法。</span><span class="sxs-lookup"><span data-stu-id="5e844-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="5e844-148">因此目前無法將它們系結至變數，或將它們當做引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="5e844-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="5e844-149">仿函數的使用方式是將它套用至作業，並傳回新的作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="5e844-150">例如，將仿函數套用至作業所產生的作業 `Adjoint` `Y` 會寫入為 `Adjoint Y` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="5e844-151">接著就可以叫用新的作業，就像任何其他作業一樣。</span><span class="sxs-lookup"><span data-stu-id="5e844-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="5e844-152">如需支援和（或）函子之應用程式的作業 `Adjoint` `Controlled` ，其傳回型別必須是 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="5e844-153">`Adjoint`仿函數</span><span class="sxs-lookup"><span data-stu-id="5e844-153">`Adjoint` functor</span></span>

<span data-ttu-id="5e844-154">因此， `Adjoint Y(q1)` 會將 Adjoint 仿函數套用至作業 `Y` ，以產生新的作業，並將該新作業套用至 `q1` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="5e844-155">新作業的簽章和類型與基底作業相同 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="5e844-156">特別是，新作業也會允許 `Adjoint` ，而且 `Controlled` 只有在基底作業執行時，才允許。</span><span class="sxs-lookup"><span data-stu-id="5e844-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="5e844-157">Adjoint 仿函數是它自己的反向;也就是， `Adjoint Adjoint Op` 一律與相同 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="5e844-158">`Controlled`仿函數</span><span class="sxs-lookup"><span data-stu-id="5e844-158">`Controlled` functor</span></span>

<span data-ttu-id="5e844-159">同樣地， `Controlled X(controls, target)` 會將受控制的仿函數套用至作業， `X` 以產生新的作業，並將該新作業套用至 `controls` 和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="5e844-160">在 Q # 中，受控制的版本一律接受控制項 qubits 的陣列，而且指定的狀態一律會讓所有控制項 qubits 都處於計算（ `PauliZ` ） `One` 狀態，$ \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="5e844-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="5e844-161">藉由將適當的單一作業套用至受控制的作業之前的控制項 qubits，然後在受控制的作業之後套用單一作業的反轉，即可達成根據其他狀態進行控制。</span><span class="sxs-lookup"><span data-stu-id="5e844-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="5e844-162">例如，在 `X` 受控制的作業前後將作業套用至控制項 qubit，會導致作業控制 `Zero` 該 qubit 的狀態（$ \ket {0} $）; 在 `H` 之前和之後套用作業將會控制 `PauliX` `One` 狀態，也就是-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} （\ket {0} -\ket {1} ）/\sqrt {2} $，而不是 `PauliZ` `One` 狀態。</span><span class="sxs-lookup"><span data-stu-id="5e844-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="5e844-163">給定作業運算式時，可以使用仿函數來形成新的作業運算式 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="5e844-164">新作業的簽章是以原始作業的簽章為基礎。</span><span class="sxs-lookup"><span data-stu-id="5e844-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="5e844-165">結果型別相同，但輸入型別是具有 qubit 陣列的兩個元組，其會將控制項 qubit 保存為第一個專案，並將原始運算的引數當做第二個元素。</span><span class="sxs-lookup"><span data-stu-id="5e844-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="5e844-166">新的作業支援 `Controlled` ，而且只有在原始作業執行時，才會支援 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="5e844-167">如果原始作業只接受單一引數，則會在這裡播放單一元組等價。</span><span class="sxs-lookup"><span data-stu-id="5e844-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="5e844-168">例如，是作業的 `Controlled X` 受控制版本 `X` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="5e844-169">`X`具有類型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有類型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 因為單一元組等價，所以這與相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="5e844-170">如果基底作業接受數個引數，請記得將作業之受控制版本的對應引數括在括弧中，以將其轉換為元組。</span><span class="sxs-lookup"><span data-stu-id="5e844-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="5e844-171">例如，是作業的 `Controlled Rz` 受控制版本 `Rz` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="5e844-172">`Rz`具有類型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有類型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="5e844-173">因此，會 `Controlled Rz(controls, (0.1, target))` 是的有效調用 `Controlled Rz` （請注意周圍的括弧 `0.1, target` ）。</span><span class="sxs-lookup"><span data-stu-id="5e844-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="5e844-174">另一個範例 `CNOT(control, target)` 是，可以實作為 `Controlled X([control], target)` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="5e844-175">如果目標應該由2個 control qubits （CCNOT）控制，我們可以使用 `Controlled X([control1, control2], target)` 語句。</span><span class="sxs-lookup"><span data-stu-id="5e844-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="5e844-176">`Controlled`和 `Adjoint` 函子的上下班，因此套用或之間沒有任何 `Controlled Adjoint Op` 差異 `Adjoint Controlled Op` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="5e844-177">定義受控制和 Adjoint 的實作為</span><span class="sxs-lookup"><span data-stu-id="5e844-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="5e844-178">在上述的第一個作業宣告範例中， `BitFlip` 會 `DecodeSuperdense` 分別使用簽章和來定義操作和 `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="5e844-179">`DecodeSuperdense`包含測量，這不是單一作業，因此不會有任何受控制的 adjoint 特製化可能存在（請重新叫用這類作業傳回的相關需求 `Unit` ）。</span><span class="sxs-lookup"><span data-stu-id="5e844-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="5e844-180">不過，只要 `BitFlip` 執行單一作業 <xref:microsoft.quantum.intrinsic.x> ，我們就可以使用這兩個特殊化來定義它。</span><span class="sxs-lookup"><span data-stu-id="5e844-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="5e844-181">在這裡，我們會詳細說明如何在您的 Q # 作業宣告中包含特製化的存在性，因此讓他們能夠與 `Adjoint` 和/或函子一起呼叫 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="5e844-182">接[下來，我們](#circumstances-for-validly-defining-specializations)將說明某些可能是有效或無效以宣告特定特製化的情況。</span><span class="sxs-lookup"><span data-stu-id="5e844-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="5e844-183">作業特性定義哪些類型的函子可套用至已宣告的作業，以及它們有何影響。</span><span class="sxs-lookup"><span data-stu-id="5e844-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="5e844-184">這些特製化的存在可以宣告為作業簽章的一部分，特別是透過具有作業特性的注釋： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="5e844-185">每個特製化的實際執行方式可以是*隱含*或*明確*定義的。</span><span class="sxs-lookup"><span data-stu-id="5e844-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="5e844-186">隱含指定實現</span><span class="sxs-lookup"><span data-stu-id="5e844-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="5e844-187">在此情況下，作業宣告的主體只會包含預設的實作為。</span><span class="sxs-lookup"><span data-stu-id="5e844-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="5e844-188">例如：</span><span class="sxs-lookup"><span data-stu-id="5e844-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="5e844-189">在這裡，編譯器會自動產生每個這類隱含宣告特製化的對應實作為，以在 `Adjoint` 使用或 `Controlled` 函子時執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="5e844-190">因此，的呼叫 `Adjoint PrepareEntangledPair` 會導致編譯器先執行的 adjoint `CNOT` ，然後再進行的 adjoint `H` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="5e844-191">這些個別的作業都是自我 adjoint，因此產生的作業 `Adjoint PrepareEntangledPair` 只會包含套用，然後才會套用 `CNOT(here, there)` `H(here)` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="5e844-192">因此，我們可以使用這 `DecodeSuperdense` 項資訊來撰寫上述範例更簡潔地，方法是使用的 adjoint，將 `PrepareEntangledPair` 光子狀態轉換回 unentangled 對 qubits：</span><span class="sxs-lookup"><span data-stu-id="5e844-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="5e844-193">在宣告中具有作業特性的注釋，非常適合用來確保編譯器會根據預設執行自動產生其他特製化。</span><span class="sxs-lookup"><span data-stu-id="5e844-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="5e844-194">設計要與函子搭配使用的作業時，有一些重要的限制需要考慮。</span><span class="sxs-lookup"><span data-stu-id="5e844-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="5e844-195">最重要的是，使用任何其他作業的輸出值之作業的特製化，*不能*由編譯器自動產生，因為在這類作業中重新排序語句以取得相同的效果並不明確。</span><span class="sxs-lookup"><span data-stu-id="5e844-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="5e844-196">因此，明確指定各種不同的執行通常會很有用。</span><span class="sxs-lookup"><span data-stu-id="5e844-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="5e844-197">明確指定實現</span><span class="sxs-lookup"><span data-stu-id="5e844-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="5e844-198">如果編譯器無法產生執行，則可以明確指定。</span><span class="sxs-lookup"><span data-stu-id="5e844-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="5e844-199">這類明確特製化宣告可以包含適當的*世代*指示詞或使用者定義的實作為。</span><span class="sxs-lookup"><span data-stu-id="5e844-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="5e844-200">在這裡，我們提供了完整的各種可能性，範例如下所示。</span><span class="sxs-lookup"><span data-stu-id="5e844-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="5e844-201">明確特製化宣告</span><span class="sxs-lookup"><span data-stu-id="5e844-201">Explicit specialization declarations</span></span>

<span data-ttu-id="5e844-202">Q # 作業可以包含下列明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="5e844-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="5e844-203">特製 `body` 化會指定未套用任何函子之作業的執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="5e844-204">特製 `adjoint` 化會指定已套用仿函數之作業的執行 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="5e844-205">特製 `controlled` 化會指定已套用仿函數之作業的執行 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="5e844-206">特製 `controlled adjoint` 化會指定同時套用和函子作業的執行 `Adjoint` `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="5e844-207">這個特製化也可以命名為 `adjoint controlled` ，因為這兩個函子會向下。</span><span class="sxs-lookup"><span data-stu-id="5e844-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="5e844-208">作業特製化包含特製化標記（例如 `body` 或 `adjoint` 等等），後面接著下列其中一個：</span><span class="sxs-lookup"><span data-stu-id="5e844-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="5e844-209">明確宣告，如下所述。</span><span class="sxs-lookup"><span data-stu-id="5e844-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="5e844-210">指示編譯器*如何*產生特製化*的指示詞，這是*下列其中一個：</span><span class="sxs-lookup"><span data-stu-id="5e844-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="5e844-211">`intrinsic`，這表示特製化是由目的電腦所提供。</span><span class="sxs-lookup"><span data-stu-id="5e844-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="5e844-212">`distribute`，可與和特製化搭配 `controlled` 使用 `controlled adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="5e844-213">與搭配使用時 `controlled` ，它會指出編譯器應該藉由套用 `Controlled` 至中的所有作業來計算特製化 `body` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="5e844-214">與搭配使用時 `controlled adjoint` ，它會指出編譯器應該藉由套用至特製 `Controlled` 化中的所有作業來計算特製化 `adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="5e844-215">`invert`，這表示編譯器應該藉由反轉來計算特製 `adjoint` 化 `body` ，亦即反轉作業順序，並將 adjoint 套用至每一個。</span><span class="sxs-lookup"><span data-stu-id="5e844-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="5e844-216">與搭配使用時 `adjoint controlled` ，這表示編譯器應該藉由反轉特製化來計算特製化 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="5e844-217">`self`，表示 adjoint 特製化與特製 `body` 化相同。</span><span class="sxs-lookup"><span data-stu-id="5e844-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="5e844-218">這對於和特製化而言是合法的 `adjoint` `adjoint controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="5e844-219">針對 `adjoint controlled` ，表示特製化與特製化 `self` `adjoint controlled` 相同 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="5e844-220">`auto`，表示編譯器應該選取要套用的適當指示詞。</span><span class="sxs-lookup"><span data-stu-id="5e844-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="5e844-221">`auto`不能用於特製 `body` 化。</span><span class="sxs-lookup"><span data-stu-id="5e844-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="5e844-222">指示詞和 `auto` 全部都需要結尾的分號 `;` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="5e844-223">如果提供的明確宣告，指示詞 `auto` 會解析為下列產生指示詞 `body` ：</span><span class="sxs-lookup"><span data-stu-id="5e844-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="5e844-224">特製 `adjoint` 化是根據指示詞所產生 `invert` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="5e844-225">特製 `controlled` 化是根據指示詞所產生 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="5e844-226">`adjoint controlled` `invert` 如果指定了的明確宣告 `controlled` ，而不是針對，則會根據指示詞產生特製化 `adjoint` ， `distribute` 否則為。</span><span class="sxs-lookup"><span data-stu-id="5e844-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="5e844-227">如果作業是自我 adjoint 的，請透過世代指示詞明確指定 adjoint 或受控制的 adjoint 特製化， `self` 以允許編譯器使用該資訊來進行優化。</span><span class="sxs-lookup"><span data-stu-id="5e844-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="5e844-228">包含使用者定義之實作為的特製化宣告，是由引數元組後面接著語句區塊，以及用來實行特製化的 Q # 程式碼所組成。</span><span class="sxs-lookup"><span data-stu-id="5e844-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="5e844-229">在引數清單中， `...` 是用來代表整個作業所宣告的引數。</span><span class="sxs-lookup"><span data-stu-id="5e844-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="5e844-230">針對 `body` 和 `adjoint` ，引數清單應一律為 `(...)` ; 針對 `controlled` 和 `adjoint controlled` ，引數清單應該是代表控制項 qubits 陣列的符號，後面接著 `...` 以括弧括住 `(controls,...)` ，例如。</span><span class="sxs-lookup"><span data-stu-id="5e844-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="5e844-231">範例</span><span class="sxs-lookup"><span data-stu-id="5e844-231">Examples</span></span>

<span data-ttu-id="5e844-232">作業宣告可能會像下面這樣簡單，其定義基本的 Pauli X 運算：</span><span class="sxs-lookup"><span data-stu-id="5e844-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="5e844-233">請注意，Pauli X 作業的 adjoint 是以指示詞定義， `self` 因為根據定義 `X` 是它自己的反向。</span><span class="sxs-lookup"><span data-stu-id="5e844-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="5e844-234">`PrepareEntangledPair`上述的程式碼相當於下列程式碼，其中包含明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="5e844-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="5e844-235">關鍵字 `auto` 表示編譯器應該決定如何產生特製化執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="5e844-236">使用者定義的特製化執行</span><span class="sxs-lookup"><span data-stu-id="5e844-236">User-defined specialization implementation</span></span>

<span data-ttu-id="5e844-237">如果編譯器無法自動產生特定特製化的實作為，或者可以指定更有效率的執行，則也可以手動定義執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="5e844-238">在上述範例中， `adjoint invert;` 表示 adjoint 特製化是藉由將主體實作為反轉而產生，並 `controlled adjoint invert;` 指出受控制的 adjoint 特製化是藉由反轉所控制特製化的指定實作為而產生的。</span><span class="sxs-lookup"><span data-stu-id="5e844-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="5e844-239">如果需要明確宣告預設主體以外的一個或多個特製化，則預設主體的執行也必須包裝為適當的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="5e844-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="5e844-240">有效定義特製化的情況</span><span class="sxs-lookup"><span data-stu-id="5e844-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="5e844-241">具有 adjoint/受控的作業宣告</span><span class="sxs-lookup"><span data-stu-id="5e844-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="5e844-242">指定不含 adjoint 或受控制版本的作業是合法的。</span><span class="sxs-lookup"><span data-stu-id="5e844-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="5e844-243">比方說，測量作業並不是，因為它們不是可反轉或可以控制的。</span><span class="sxs-lookup"><span data-stu-id="5e844-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="5e844-244">如果作業的宣告 `Adjoint` 包含個別特製化的隱含或明確宣告，則作業支援和/或 `Controlled` 函子。</span><span class="sxs-lookup"><span data-stu-id="5e844-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="5e844-245">明確宣告的 adjoint/控制特製化意味著存在 adjoint/控制特製化。</span><span class="sxs-lookup"><span data-stu-id="5e844-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="5e844-246">如果作業的主體包含重複執行迴圈、set 語句、量值、傳回語句，或呼叫不支援仿函數的其他作業 `Adjoint` ， `invert` `auto` 則不能在或指示詞之後自動產生 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="5e844-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="5e844-247">若作業的主體包含不支援仿函數的其他作業呼叫 `Controlled` ，就無法在或指示詞之後自動產生受控制的特製化 `distribute` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="5e844-248">控制的 Adjoint</span><span class="sxs-lookup"><span data-stu-id="5e844-248">Controlled Adjoint</span></span>

<span data-ttu-id="5e844-249">作業的受控制 adjoint 版本會指定如何實作為作業 adjoint 的配量控制版本。</span><span class="sxs-lookup"><span data-stu-id="5e844-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="5e844-250">指定沒有受控制 adjoint 版本的作業是合法的：比方說，測量作業沒有受控制的 adjoint 版本，因為它們都不是可控制也不可逆。</span><span class="sxs-lookup"><span data-stu-id="5e844-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="5e844-251">只有在 adjoint 和受控制的特製化都存在時，作業的受控制 adjoint 特製化才需要存在。</span><span class="sxs-lookup"><span data-stu-id="5e844-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="5e844-252">在這種情況下，系統會推斷受控制的 adjoint 特製化，而且編譯器會產生適當的特製化（如果未明確定義任何實作為）。</span><span class="sxs-lookup"><span data-stu-id="5e844-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="5e844-253">若作業的內文包含的呼叫不具有受控制 adjoint 版本的其他作業， `invert` 則無法在、或指示詞之後自動產生 adjoint 特製化 `distribute` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="5e844-254">類型相容性</span><span class="sxs-lookup"><span data-stu-id="5e844-254">Type Compatibility</span></span>

<span data-ttu-id="5e844-255">具有其他函子支援的作業可以在具有較少函子的作業中使用，但預期會有相同的簽章。</span><span class="sxs-lookup"><span data-stu-id="5e844-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="5e844-256">例如，類型的作業可以在 `(Qubit => Unit is Adj)` 預期為類型作業的任何位置使用 `(Qubit => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="5e844-257">Q # 是可呼叫傳回類型的*協*變數：傳回類型的可呼叫，與 `'A` 具有相同輸入類型和與相容之結果類型的可呼叫相容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="5e844-258">問 # 是相對於輸入類型的*逆變*性：接受類型做為輸入的可呼叫，與 `'A` 具有相同結果類型的可呼叫和與相容的輸入類型相容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="5e844-259">也就是，假設有下列定義：</span><span class="sxs-lookup"><span data-stu-id="5e844-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="5e844-260">下列為 true：</span><span class="sxs-lookup"><span data-stu-id="5e844-260">the following are true:</span></span>

- <span data-ttu-id="5e844-261">函數 `ConjugateInvertWith` 可以使用 `inner` 或的引數叫用 `Invert` `ApplyUnitary` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="5e844-262">函數 `ConjugateUnitaryWith` 可以使用 `inner` 的引數來叫用 `ApplyUnitary` ，但不能叫用 `Invert` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="5e844-263">`(Qubit[] => Unit is Adj + Ctl)`可能會從傳回類型的值 `ConjugateInvertWith` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e844-264">問 # 0.3 在使用者定義型別的行為上引進了顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="5e844-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="5e844-265">使用者自訂類型會被視為基礎類型的包裝版本，而不是子類型。</span><span class="sxs-lookup"><span data-stu-id="5e844-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="5e844-266">這表示在預期基礎類型的值時，使用者自訂類型的值無法使用。</span><span class="sxs-lookup"><span data-stu-id="5e844-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="5e844-267">動詞變化</span><span class="sxs-lookup"><span data-stu-id="5e844-267">Conjugations</span></span>

<span data-ttu-id="5e844-268">相較于傳統的位，釋出配量記憶體會稍微複雜一點，因為如果 qubits 仍光子，則盲目重設 qubits 可能會對其餘的計算造成不想要的效果。</span><span class="sxs-lookup"><span data-stu-id="5e844-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="5e844-269">在釋放記憶體之前，適當地「復原」執行的計算，可以避免這種情況。</span><span class="sxs-lookup"><span data-stu-id="5e844-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="5e844-270">量子運算的常見模式如下：</span><span class="sxs-lookup"><span data-stu-id="5e844-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="5e844-271">從0.9 版開始，我們支援 conjugation 語句來執行上述轉換。</span><span class="sxs-lookup"><span data-stu-id="5e844-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="5e844-272">使用該語句，可以透過 `ApplyWith` 下列方式來執行作業：</span><span class="sxs-lookup"><span data-stu-id="5e844-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="5e844-273">如果外部和內部轉換無法立即當做作業使用，這類 conjugation 語句會變得更有用，但以多個語句所組成的區塊來描述會更方便。</span><span class="sxs-lookup"><span data-stu-id="5e844-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="5e844-274">在區塊內定義的語句的反向轉換會由編譯器自動產生，並在套用區塊完成後執行。</span><span class="sxs-lookup"><span data-stu-id="5e844-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="5e844-275">因為任何用來做為內部區塊一部分的可變變數無法在套用區塊中重新系結，所以產生的轉換保證會是在區塊內的計算 adjoint。</span><span class="sxs-lookup"><span data-stu-id="5e844-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="5e844-276">定義新函數</span><span class="sxs-lookup"><span data-stu-id="5e844-276">Defining New Functions</span></span>

<span data-ttu-id="5e844-277">函式在 Q # 中純粹是具決定性的傳統常式，這與作業不同，因為它們不允許超出計算輸出值的任何效果。</span><span class="sxs-lookup"><span data-stu-id="5e844-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="5e844-278">特別是，函數無法呼叫作業;採取行動、配置或借用 qubits;範例亂數字;或以其他方式相依于函式的輸入值以外的狀態。</span><span class="sxs-lookup"><span data-stu-id="5e844-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="5e844-279">因此，Q # 函式是*單純*的，因為它們一律會將相同的輸入值對應到相同的輸出值。</span><span class="sxs-lookup"><span data-stu-id="5e844-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="5e844-280">這可讓 Q # 編譯器在產生作業特製化時，安全地重新排序呼叫函式的方式和時機。</span><span class="sxs-lookup"><span data-stu-id="5e844-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="5e844-281">每個 Q # 來源檔案可能會定義任意數目的函數。</span><span class="sxs-lookup"><span data-stu-id="5e844-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="5e844-282">函數名稱在命名空間中必須是唯一的，而且可能不會與作業或類型名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="5e844-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="5e844-283">定義函式的運作方式類似于定義作業，不同之處在于無法為函式定義任何 adjoint 或受控特殊化。</span><span class="sxs-lookup"><span data-stu-id="5e844-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="5e844-284">例如：</span><span class="sxs-lookup"><span data-stu-id="5e844-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="5e844-285">或</span><span class="sxs-lookup"><span data-stu-id="5e844-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="5e844-286">函數中的傳統邏輯 = = 良好</span><span class="sxs-lookup"><span data-stu-id="5e844-286">Classical logic in functions == good</span></span>

<span data-ttu-id="5e844-287">只要能夠這麼做，就能以函式而非作業的形式寫出傳統邏輯，這會很有説明，可以更輕鬆地從作業中使用。</span><span class="sxs-lookup"><span data-stu-id="5e844-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="5e844-288">例如，如果我們將上述宣告撰寫 `Square` 為作業，則*operation*編譯器無法保證以相同的輸入呼叫它，會一致地產生相同的輸出。</span><span class="sxs-lookup"><span data-stu-id="5e844-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="5e844-289">若要以底線表示函式和作業之間的差異，請考慮傳統方式從 Q # 操作中取樣亂數字的問題：</span><span class="sxs-lookup"><span data-stu-id="5e844-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="5e844-290">每次 `U` 呼叫時，它會在上有不同的動作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="5e844-291">特別的是，編譯器無法保證如果我們將特製化宣告加入 `adjoint auto` 至 `U` ，則 `U(target); Adjoint U(target);` 會做為身分識別（也就是不需要 op）。</span><span class="sxs-lookup"><span data-stu-id="5e844-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="5e844-292">這會違反我們在[向量和矩陣](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定義，讓能夠在我們呼叫作業的作業中自動產生 adjoint 特製化，這 <xref:microsoft.quantum.math.randomreal> 會中斷編譯器所提供的保證; <xref:microsoft.quantum.math.randomreal> 是沒有 adjoint 或控制版本存在的作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="5e844-293">另一方面，允許函式呼叫（例如） `Square` 是安全的，因為編譯器可以確保它只需要保留的輸入，才能 `Square` 保持其輸出穩定。</span><span class="sxs-lookup"><span data-stu-id="5e844-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="5e844-294">因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。</span><span class="sxs-lookup"><span data-stu-id="5e844-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="5e844-295">泛型（型別參數化） Callables</span><span class="sxs-lookup"><span data-stu-id="5e844-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="5e844-296">我們可能會想要定義的許多函式和作業實際上並不會依賴其輸入的類型，而只會透過一些其他函式或運算，隱含地使用其類型。</span><span class="sxs-lookup"><span data-stu-id="5e844-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="5e844-297">例如，請考慮許多功能性語言通用的*地圖*概念;假設函數 $f （x） $ 和值 $ x_1 的集合 \{ ，x_2，\dots ..，x_n \} $，map 會傳回新的集合 $ \{ f （x_1）、f （x_2）、\dots ..、f （x_n） \} $。</span><span class="sxs-lookup"><span data-stu-id="5e844-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="5e844-298">若要在 Q # 中執行此功能，我們可以利用該函式是第一個類別。</span><span class="sxs-lookup"><span data-stu-id="5e844-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="5e844-299">讓我們寫出一個簡單的範例 `Map` ，使用★做為預留位置，同時瞭解我們所需的類型。</span><span class="sxs-lookup"><span data-stu-id="5e844-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="5e844-300">請注意，無論我們在什麼實際的型別中，此函式看起來都很相似。</span><span class="sxs-lookup"><span data-stu-id="5e844-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="5e844-301">例如，從整數到 Paulis 的對應，與從浮點數到字串的對應大致相同：</span><span class="sxs-lookup"><span data-stu-id="5e844-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="5e844-302">基本上，我們可以 `Map` 針對我們所遇到的每一對類型撰寫版本的，但這會造成一些問題。</span><span class="sxs-lookup"><span data-stu-id="5e844-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="5e844-303">比方說，如果我們在中發現錯誤 `Map` ，則必須確保在所有版本的中都已一致套用修正程式 `Map` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="5e844-304">此外，如果我們要建立新的元組或 UDT，我們現在也必須建立新的 `Map` 來搭配新的型別。</span><span class="sxs-lookup"><span data-stu-id="5e844-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="5e844-305">雖然這是少數這類函式的方便追蹤，但我們會收集與相同表單的多個函式，而 `Map` 新類型的成本會以相當短的順序變得過長龐大。</span><span class="sxs-lookup"><span data-stu-id="5e844-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="5e844-306">不過，大部分的困難之處在于，我們尚未提供編譯器所需的資訊，來辨識不同版本的 `Map` 關聯。</span><span class="sxs-lookup"><span data-stu-id="5e844-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="5e844-307">實際上，我們希望編譯器將 `Map` q #*類型*中的某種數學函式視為 q # 函式。</span><span class="sxs-lookup"><span data-stu-id="5e844-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="5e844-308">這種概念的正規化方式是讓函式和作業具有*型別參數*，以及它們的一般元組參數。</span><span class="sxs-lookup"><span data-stu-id="5e844-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="5e844-309">在上述範例中，我們想要 `Map` `Int, Pauli` 在第一個案例和 `Double, String` 第二個案例中將類型參數視為。</span><span class="sxs-lookup"><span data-stu-id="5e844-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="5e844-310">在大部分的情況下，這些類型參數可以用來當做一般類型使用：我們會使用類型參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變變數。</span><span class="sxs-lookup"><span data-stu-id="5e844-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="5e844-311">間接相依性最極端的情況，就是 qubits，其中 Q # 程式無法直接依賴類型的結構 `Qubit` ，但**必須**將這類類型傳遞給其他作業和函式。</span><span class="sxs-lookup"><span data-stu-id="5e844-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="5e844-312">回到上述範例，我們可以看到我們需要 `Map` 有型別參數，一個用來表示的輸入， `fn` 另一個用來表示的輸出 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="5e844-313">在 Q # 中，這是藉由在其宣告中的函式或作業名稱後面加上角括弧（也就是 `<>` 不是 brakets $ {} ！）來撰寫，並列出每個型別參數。</span><span class="sxs-lookup"><span data-stu-id="5e844-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="5e844-314">每個型別參數的名稱都必須以滴答開頭 `'` ，表示它是型別參數，而不是一般型別（也稱為*具體*型別）。</span><span class="sxs-lookup"><span data-stu-id="5e844-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="5e844-315">在 `Map` 中，我們會撰寫：</span><span class="sxs-lookup"><span data-stu-id="5e844-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="5e844-316">請注意，的定義 `Map<'Input, 'Output>` 看起來非常類似于之前寫出的版本。</span><span class="sxs-lookup"><span data-stu-id="5e844-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="5e844-317">唯一的差別在於，我們已明確告知編譯器，其 `Map` 不會直接相依于 `'Input` 和 `'Output` ，但可透過間接使用它們來處理任何兩種類型 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="5e844-318">一旦 `Map<'Input, 'Output>` 以這種方式定義，我們就可以像一般函式一樣呼叫它：</span><span class="sxs-lookup"><span data-stu-id="5e844-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="5e844-319">撰寫泛型函式和作業是一個位置，其中「元組元組輸出」是一種非常有用的方法，可以思考問 # 函式和作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="5e844-320">因為每個函式只接受一個輸入，而且只會傳回一個輸出，所以類型的輸入會 `'T -> 'U` 符合*任何*Q # 函數。</span><span class="sxs-lookup"><span data-stu-id="5e844-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="5e844-321">同樣地，任何作業都可以傳遞至類型的輸入 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="5e844-322">作為第二個範例，請考慮撰寫會傳回兩個其他函式之組合的函式的挑戰：</span><span class="sxs-lookup"><span data-stu-id="5e844-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="5e844-323">在這裡，我們必須確切地指定 `A` 、 `B` 和， `C` 因此會嚴重限制新函式的公用程式 `Compose` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="5e844-324">畢竟， `Compose` 只取決於 `A` 、 `B` 和 `C` *via* `innerFn` `outerFn` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="5e844-325">或者，我們可以將型別參數新增至，以 `Compose` 表示它適用于*任何* `A` 、 `B` 和 `C` ，只要這些參數符合和所預期的參數即可 `innerFn` `outerFn` ：</span><span class="sxs-lookup"><span data-stu-id="5e844-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="5e844-326">Q # 標準程式庫提供了這類類型參數化作業和函式的範圍，讓您更容易表達更高順序的控制流程。</span><span class="sxs-lookup"><span data-stu-id="5e844-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="5e844-327">這些會在[問答 # 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。</span><span class="sxs-lookup"><span data-stu-id="5e844-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="5e844-328">Callables 為第一級值</span><span class="sxs-lookup"><span data-stu-id="5e844-328">Callables as First-Class Values</span></span>

<span data-ttu-id="5e844-329">使用函式而不是作業來推理控制流程和傳統邏輯的一項重要技巧，就是利用 Q # 中的作業和函*式是第一類*。</span><span class="sxs-lookup"><span data-stu-id="5e844-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="5e844-330">也就是說，它們是語言中的每個值本身的許可權。</span><span class="sxs-lookup"><span data-stu-id="5e844-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="5e844-331">例如，下列是完全有效的 Q # 程式碼，如果有一點間接：</span><span class="sxs-lookup"><span data-stu-id="5e844-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="5e844-332">`ourH`上述程式碼片段中的變數值是作業 <xref:microsoft.quantum.intrinsic.h> ，因此我們可以像任何其他作業一樣呼叫該值。</span><span class="sxs-lookup"><span data-stu-id="5e844-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="5e844-333">這可讓我們撰寫在其輸入過程中採取作業的作業，形成更高順序的控制流程概念。</span><span class="sxs-lookup"><span data-stu-id="5e844-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="5e844-334">比方說，我們可以想像一下，將作業套用到相同的目標 qubit 兩次，以「正方形」作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="5e844-335">從函式傳回作業</span><span class="sxs-lookup"><span data-stu-id="5e844-335">Returning operations from a function</span></span>

<span data-ttu-id="5e844-336">我們強調，我們也可以將作業當做輸出的一部分傳回，讓我們可以將一些傳統條件式邏輯隔離為傳統函式，以作業的形式傳回量副程式的描述。</span><span class="sxs-lookup"><span data-stu-id="5e844-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="5e844-337">做為簡單的範例，請考慮 teleportation 範例，其中接收兩個傳統訊息的合作物件需要使用訊息，將其 qubit 解碼為適當的傳送狀態。</span><span class="sxs-lookup"><span data-stu-id="5e844-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="5e844-338">我們可以根據採用這兩個傳統位的函式撰寫此程式，並傳回適當的解碼作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="5e844-339">這個新函式確實是一個函式，在此情況下，如果我們使用和相同的值來呼叫它 `hereBit` `thereBit` ，我們一律會取回相同的作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="5e844-340">因此，可以安全地在作業內執行此解碼器，而不需考慮解碼邏輯如何與不同作業特製化的定義互動。</span><span class="sxs-lookup"><span data-stu-id="5e844-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="5e844-341">也就是，我們已將傳統邏輯隔離在函式內，並保證編譯器，只要保留輸入，函式呼叫就可以與 impunity 重新排序。</span><span class="sxs-lookup"><span data-stu-id="5e844-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="5e844-342">部分應用程式</span><span class="sxs-lookup"><span data-stu-id="5e844-342">Partial Application</span></span>

<span data-ttu-id="5e844-343">我們可以透過使用*部分應用程式*來傳回作業的函式執行更多動作，我們可以將輸入的一個或多個部分提供給函式或作業，而不需要實際呼叫它。</span><span class="sxs-lookup"><span data-stu-id="5e844-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="5e844-344">例如，若要重新叫 `ApplyTwice` 用上述範例，我們可以指出我們不想要對應套用輸入作業的 qubit 立即指定：</span><span class="sxs-lookup"><span data-stu-id="5e844-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="5e844-345">在此情況下，本機變數 `twiceOp` 會保存部分套用的作業 `ApplyTwice(op, _)` ，其中尚未指定的輸入部分會以表示 `_` 。</span><span class="sxs-lookup"><span data-stu-id="5e844-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="5e844-346">當我們 `twiceOp` 在下一行中實際呼叫時，會將輸入的所有剩餘部分當做原始作業傳遞給部分套用的作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="5e844-347">因此，上述程式碼片段實際上與直接呼叫相同 `ApplyTwice(op, target)` ，因此我們引進了新的區域變數，讓我們能夠延遲呼叫，同時提供輸入的某些部分。</span><span class="sxs-lookup"><span data-stu-id="5e844-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="5e844-348">由於已部分套用的作業並不會實際被呼叫，直到提供了完整的輸入為止，我們也可以安全地從函式內部分套用作業。</span><span class="sxs-lookup"><span data-stu-id="5e844-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="5e844-349">原則上，中的傳統邏輯 `SquareOperation` 可能更牽涉到，但它仍會與作業的其餘部分隔離，因為編譯器可以提供關於函數的保證。</span><span class="sxs-lookup"><span data-stu-id="5e844-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="5e844-350">這種方法會在整個 Q # 標準程式庫中用來以可在量副程式中輕鬆使用的方式來表示傳統控制流程。</span><span class="sxs-lookup"><span data-stu-id="5e844-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="5e844-351">遞迴</span><span class="sxs-lookup"><span data-stu-id="5e844-351">Recursion</span></span>

<span data-ttu-id="5e844-352">Q # callables 允許直接或間接遞迴。</span><span class="sxs-lookup"><span data-stu-id="5e844-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="5e844-353">也就是說，作業或函式可能會呼叫本身，或呼叫可直接或間接呼叫可呼叫作業的其他調用。</span><span class="sxs-lookup"><span data-stu-id="5e844-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="5e844-354">使用遞迴有兩個重要的批註，不過：</span><span class="sxs-lookup"><span data-stu-id="5e844-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="5e844-355">在作業中使用遞迴可能會干擾特定的優化。</span><span class="sxs-lookup"><span data-stu-id="5e844-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="5e844-356">這可能會對演算法的執行時間產生重大影響。</span><span class="sxs-lookup"><span data-stu-id="5e844-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="5e844-357">在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深度遞迴可能會導致執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="5e844-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="5e844-358">特別是，Q # 編譯器和執行時間不會識別並優化尾遞迴。</span><span class="sxs-lookup"><span data-stu-id="5e844-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="whats-next"></a><span data-ttu-id="5e844-359">下一步</span><span class="sxs-lookup"><span data-stu-id="5e844-359">What's Next?</span></span>
<span data-ttu-id="5e844-360">瞭解 Q # 中的[變數](xref:microsoft.quantum.guide.variables)。</span><span class="sxs-lookup"><span data-stu-id="5e844-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>