---
title: 中的作業和函數 Q#
description: 如何定義和呼叫作業和函式，以及控制和 adjoint 作業特殊化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: c2ce999ea2a0fe7204f402fedb4cd3a3c15bd44b
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759419"
---
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="e78b3-103">中的作業和函數 Q#</span><span class="sxs-lookup"><span data-stu-id="e78b3-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="e78b3-104">定義新的作業</span><span class="sxs-lookup"><span data-stu-id="e78b3-104">Defining New Operations</span></span>

<span data-ttu-id="e78b3-105">作業是的核心 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="e78b3-106">宣告之後，您可以從傳統的 .NET 應用程式呼叫它們，例如使用模擬器或內的其他作業 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="e78b3-107">中定義的每個 Q# 作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="e78b3-108">定義這些內建作業的特定方式 Q# 取決於目的電腦。</span><span class="sxs-lookup"><span data-stu-id="e78b3-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="e78b3-109">編譯時，每項作業都會表示為可提供給目的電腦的 .NET 類別類型。</span><span class="sxs-lookup"><span data-stu-id="e78b3-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="e78b3-110">每個原始程式檔 Q# 都可以定義任何數目的作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="e78b3-111">作業名稱在命名空間中必須是唯一的，且不能與類型或函式名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="e78b3-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="e78b3-112">作業宣告由關鍵字組成 `operation` ，後面接著做為作業名稱的符號、定義作業引數的型別識別碼元組、冒號 `:` 、描述作業結果型別的型別批註、選擇性的注釋（具有作業特性）、左大括弧，以及作業宣告的主體（以大括弧括住） `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="e78b3-113">每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的實作為。</span><span class="sxs-lookup"><span data-stu-id="e78b3-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="e78b3-114">本文的不同章節將詳細說明可能的特製化，以及如何定義和呼叫它們。</span><span class="sxs-lookup"><span data-stu-id="e78b3-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="e78b3-115">現在，請考慮下列作業，此作業只會定義預設的本文特製化，並採用單一量子位作為其輸入，然後在該輸入上呼叫內建作業 <xref:microsoft.quantum.intrinsic.x> ：</span><span class="sxs-lookup"><span data-stu-id="e78b3-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="e78b3-116">關鍵字會 `operation` 開始作業定義，後面接著名稱，如下所示 `BitFlip` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="e78b3-117">接著，輸入的類型會定義 (`Qubit`) ，以及用來 `target` 參考新作業內之輸入的名稱。</span><span class="sxs-lookup"><span data-stu-id="e78b3-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="e78b3-118">最後， `Unit` 定義運算的輸出是空的。</span><span class="sxs-lookup"><span data-stu-id="e78b3-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="e78b3-119">`Unit` 的用法類似于 `void` c # 和其他命令式語言，相當於 `unit` F # 和其他功能性語言。</span><span class="sxs-lookup"><span data-stu-id="e78b3-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="e78b3-120">作業也會傳回比更有趣 `Unit` 的類型。</span><span class="sxs-lookup"><span data-stu-id="e78b3-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="e78b3-121">例如，此作業會傳回 <xref:microsoft.quantum.intrinsic.m> 類型的輸出 `Result` ，表示已執行度量。</span><span class="sxs-lookup"><span data-stu-id="e78b3-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="e78b3-122">您可以將作業從作業傳遞至另一個作業，或使用它搭配 `let` 關鍵字來定義新的變數。</span><span class="sxs-lookup"><span data-stu-id="e78b3-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="e78b3-123">這種方法可代表在低層級與量子作業互動的傳統計算，例如 [密集編碼](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)：</span><span class="sxs-lookup"><span data-stu-id="e78b3-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="e78b3-124">中的每個作業 Q# 都只會接受一個輸入，而且只會傳回一個輸出。</span><span class="sxs-lookup"><span data-stu-id="e78b3-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="e78b3-125">多個輸入和輸出是使用 *元組*表示，這會將多個值一起收集成單一值。</span><span class="sxs-lookup"><span data-stu-id="e78b3-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="e78b3-126">在這方面， Q# 是「元組即元組外」語言。</span><span class="sxs-lookup"><span data-stu-id="e78b3-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="e78b3-127">遵循這個概念之後，必須將一組空的括弧 `()` 視為具有類型的 "empty" 元組來讀取 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="e78b3-128">控制和 Adjoint 作業</span><span class="sxs-lookup"><span data-stu-id="e78b3-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="e78b3-129">如果作業會執行單一轉換（如同中許多作業的情況），則 Q# 可以在 *adjointed* 或 *控制*時定義作業的運作方式。</span><span class="sxs-lookup"><span data-stu-id="e78b3-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="e78b3-130">作業的 *adjoint* 特製化會指定作業的「反轉」運作方式，而 *受控制* 的特製化則會指定當作業的應用程式在特定量子暫存器的狀態時，如何運作。</span><span class="sxs-lookup"><span data-stu-id="e78b3-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="e78b3-131">量子運算的伴隨對於許多方面來說非常重要。</span><span class="sxs-lookup"><span data-stu-id="e78b3-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="e78b3-132">如需與實用的程式設計技巧一起討論的其中一種情況範例 Q# ，請參閱本文中的 [動詞變化或是](#conjugations) 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="e78b3-133">受控制的作業版本是一項新的作業，只有在所有控制項量子位都處於指定狀態時，才會有效地套用基底作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="e78b3-134">如果控制項量子位在迭加中，則會將基底作業時套用至迭加的適當部分。</span><span class="sxs-lookup"><span data-stu-id="e78b3-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="e78b3-135">因此，受控制的作業通常用來產生纏結。</span><span class="sxs-lookup"><span data-stu-id="e78b3-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="e78b3-136">當然， *控制的 adjoint* 特製化也可以存在，並指定作業 adjoint 的受控制應用程式。</span><span class="sxs-lookup"><span data-stu-id="e78b3-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="e78b3-137">如果 $U $ 是作業所執行的單一轉換 `U` ，則 `Adjoint U` 表示單一轉換 $U ^ \dagger $，這是複雜的下轉型。</span><span class="sxs-lookup"><span data-stu-id="e78b3-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="e78b3-138">連續套用作業，然後將其 adjoint 狀態保持不變，如 $UU ^ \dagger = U ^ \dagger U = \id $、身分識別矩陣的事實所述。</span><span class="sxs-lookup"><span data-stu-id="e78b3-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="e78b3-139">控制作業的單一標記法稍微差別細微，不過您可以在量子運算概念找到更多詳細資料 [：多個量子位](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="e78b3-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="e78b3-140">下一節描述如何在程式碼中呼叫這些不同的特製化 Q# ，以及如何定義作業來支援它們。</span><span class="sxs-lookup"><span data-stu-id="e78b3-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="e78b3-141">呼叫作業特製化</span><span class="sxs-lookup"><span data-stu-id="e78b3-141">Calling operation specializations</span></span>

<span data-ttu-id="e78b3-142">中*functor*的仿函數 Q# 是用來從另一個作業定義新作業的 factory。</span><span class="sxs-lookup"><span data-stu-id="e78b3-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="e78b3-143">中的兩個標準函子 Q# 為 `Adjoint` 和 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="e78b3-144">在定義新作業的執行時，函子可以存取基底作業的執行。</span><span class="sxs-lookup"><span data-stu-id="e78b3-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="e78b3-145">因此，函子可以執行比傳統較高層級函數更複雜的函式。</span><span class="sxs-lookup"><span data-stu-id="e78b3-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="e78b3-146">函子沒有類型系統中的標記法 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="e78b3-147">因此目前無法將它們系結至變數，或將它們傳遞為引數。</span><span class="sxs-lookup"><span data-stu-id="e78b3-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="e78b3-148">將仿函數套用至作業（會傳回新的作業），以使用它。</span><span class="sxs-lookup"><span data-stu-id="e78b3-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="e78b3-149">例如，將仿函數套用至作業會傳回 `Adjoint` `Y` 新的作業 `Adjoint Y` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="e78b3-150">您可以叫用新的作業，就像任何其他作業一樣。</span><span class="sxs-lookup"><span data-stu-id="e78b3-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="e78b3-151">若要讓作業支援或函子的應用 `Adjoint` 程式 `Controlled` ，其傳回型別必須是 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="e78b3-152">`Adjoint` 函</span><span class="sxs-lookup"><span data-stu-id="e78b3-152">`Adjoint` functor</span></span>

<span data-ttu-id="e78b3-153">因此， `Adjoint Y(q1)` 會將仿函數套用至作業 `Adjoint` `Y` ，以產生新的作業，並將該新作業套用至 `q1` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="e78b3-154">新作業具有與基底作業相同的簽章和類型 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="e78b3-155">尤其是，新的作業也支援 `Adjoint` ，而且 `Controlled` 只有在基底作業執行時，才支援。</span><span class="sxs-lookup"><span data-stu-id="e78b3-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="e78b3-156">`Adjoint`仿函數本身是反向的，也就是， `Adjoint Adjoint Op` 一律與相同 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="e78b3-157">`Controlled` 函</span><span class="sxs-lookup"><span data-stu-id="e78b3-157">`Controlled` functor</span></span>

<span data-ttu-id="e78b3-158">同樣地，將 `Controlled X(controls, target)` 仿函數套用至作業 `Controlled` `X` 以產生新的作業，並將該新作業套用至 `controls` 和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="e78b3-159">在中 Q# ，受控制的版本一律採用控制項量子位的陣列，且控制一律會根據 `PauliZ`) `One` 狀態、$ \ket $ 中計算 (的所有控制項量子位 {1} 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="e78b3-160">藉由在受控制的作業之前將適當的單一作業套用至控制項量子位，然後在受控制的作業之後套用單一作業的反轉，就可以達到以其他狀態為基礎的控制。</span><span class="sxs-lookup"><span data-stu-id="e78b3-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="e78b3-161">例如，將作業套用 `X` 至控制作業前後的控制項量子位，會讓作業控制 `Zero` 該量子位的狀態 ($ \ket {0} $) ; `H` 會在狀態的控制項之前和之後套用作業 `PauliX` `One` ，也就是-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} ( \ket \ket \sqrt {0} {1}) / {2} $ 而非 `PauliZ` `One` 狀態。</span><span class="sxs-lookup"><span data-stu-id="e78b3-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="e78b3-162">指定作業運算式之後，您就可以使用仿函數來形成新的作業運算式 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="e78b3-163">新作業的簽章是以原始作業的簽章為基礎。</span><span class="sxs-lookup"><span data-stu-id="e78b3-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="e78b3-164">結果類型是相同的，但輸入類型是具有量子位陣列的兩個元組，其中會將控制項量子位 () s 做為第一個專案，並將原始作業的引數做為第二個元素。</span><span class="sxs-lookup"><span data-stu-id="e78b3-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="e78b3-165">新作業支援 `Controlled` ，而且只有在原始作業執行時，才會支援 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="e78b3-166">如果原始作業只接受單一引數，則會在此處播放 [單一元組等價](xref:microsoft.quantum.guide.types) 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="e78b3-167">例如， `Controlled X` 是作業的受控制版本 `X` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="e78b3-168">`X` 有型別 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 有型別， `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` 因為單一元組相等，這與相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="e78b3-169">如果基底作業採用數個引數，請記得將受控制版本之作業的對應引數以括弧括住，以將它們轉換成元組。</span><span class="sxs-lookup"><span data-stu-id="e78b3-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="e78b3-170">例如， `Controlled Rz` 是作業的受控制版本 `Rz` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="e78b3-171">`Rz` 有型別 `((Double, Qubit) => Unit is Adj + Ctl)` ，所以 `Controlled Rz` 有型別 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="e78b3-172">因此，將 `Controlled Rz(controls, (0.1, target))` 會是 `Controlled Rz` (記下) 周圍括弧的有效調用 `0.1, target` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="e78b3-173">另一個範例 `CNOT(control, target)` 是，可以實作為 `Controlled X([control], target)` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="e78b3-174">如果目標應該由兩個控制項量子位控制 (CCNOT) ，請使用 `Controlled X([control1, control2], target)` 語句。</span><span class="sxs-lookup"><span data-stu-id="e78b3-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="e78b3-175">`Controlled`和 `Adjoint` 函子上，因此套用或時沒有任何差異 `Controlled Adjoint Op` `Adjoint Controlled Op` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="e78b3-176">定義受控和 Adjoint 的實作為</span><span class="sxs-lookup"><span data-stu-id="e78b3-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="e78b3-177">在上述範例中的第一個作業宣告中，會 `BitFlip` 分別使用簽章和來定義作業和 `DecodeSuperdense` `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="e78b3-178">例如 `DecodeSuperdense` ，它不是單一作業，因此不會有受控制的無法 adjoint 特製化 (回想這類作業傳回) 的相關需求 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="e78b3-179">不過，只要 `BitFlip` 執行單一作業 <xref:microsoft.quantum.intrinsic.x> ，您就可以使用這兩個特殊化來定義它。</span><span class="sxs-lookup"><span data-stu-id="e78b3-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="e78b3-180">本節將詳細說明如何在您的作業宣告中包含特製化的存在 Q# ，因此讓它們能夠與或函子一起呼叫 `Adjoint` `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="e78b3-181">如需有效或無效來宣告特定特製化的某些情況的詳細資訊，請參閱本文中有效定義特製化的 [狀況](#circumstances-for-validly-defining-specializations) 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="e78b3-182">作業特性會定義您可以套用至宣告作業的函子種類，以及它們的作用。</span><span class="sxs-lookup"><span data-stu-id="e78b3-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="e78b3-183">這些特製化的存在可以宣告為作業簽章的一部分，特別是透過具有作業特性的注釋： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="e78b3-184">每個特製化的實際執行可以是 *隱含* 或 *明確* 定義。</span><span class="sxs-lookup"><span data-stu-id="e78b3-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="e78b3-185">隱含指定實作為</span><span class="sxs-lookup"><span data-stu-id="e78b3-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="e78b3-186">在此情況下，作業宣告的主體只包含預設的實值。</span><span class="sxs-lookup"><span data-stu-id="e78b3-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="e78b3-187">例如：</span><span class="sxs-lookup"><span data-stu-id="e78b3-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="e78b3-188">在這種情況下，編譯器會自動產生每個這類隱含宣告特製化的對應執行，以 `Adjoint` 在 `Controlled` 使用或函子時執行。</span><span class="sxs-lookup"><span data-stu-id="e78b3-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="e78b3-189">因此，的呼叫 `Adjoint PrepareEntangledPair` 會導致編譯器執行的 adjoint `CNOT` ，然後是的 adjoint `H` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="e78b3-190">這些個別作業都是自我 adjoint，因此產生的作業 `Adjoint PrepareEntangledPair` 只會包含套用的 `CNOT(here, there)` 和 `H(here)` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="e78b3-191">因此，您可以使用這項功能 `DecodeSuperdense` ，利用的 adjoint `PrepareEntangledPair` 將纏結狀態轉換回 unentangled 對量子位，以更簡潔地的方式撰寫上述範例中的：</span><span class="sxs-lookup"><span data-stu-id="e78b3-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="e78b3-192">在宣告中具有作業特性的注釋，有助於確保編譯器會根據預設的執行自動產生其他特製化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="e78b3-193">設計與函子搭配使用的作業時，必須考慮幾個重要的限制。</span><span class="sxs-lookup"><span data-stu-id="e78b3-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="e78b3-194">最重要的是，使用任何其他作業的輸出值之作業的特製化， *無法* 由編譯器自動產生，因為這種方式不清楚如何在這類作業中重新排列語句，以取得相同的效果。</span><span class="sxs-lookup"><span data-stu-id="e78b3-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="e78b3-195">因此，明確指定各種不同的執行通常會很有用。</span><span class="sxs-lookup"><span data-stu-id="e78b3-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="e78b3-196">明確指定實現</span><span class="sxs-lookup"><span data-stu-id="e78b3-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="e78b3-197">在編譯器無法產生執行的情況下，您可以明確指定它。</span><span class="sxs-lookup"><span data-stu-id="e78b3-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="e78b3-198">這類明確特製化宣告可以包含適當的 *世代* 指示詞或使用者定義的執行。</span><span class="sxs-lookup"><span data-stu-id="e78b3-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="e78b3-199">以下是完整的可能性範圍，以及一些明確特製化的範例。</span><span class="sxs-lookup"><span data-stu-id="e78b3-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="e78b3-200">明確特製化宣告</span><span class="sxs-lookup"><span data-stu-id="e78b3-200">Explicit specialization declarations</span></span>

<span data-ttu-id="e78b3-201">Q# 作業可以包含下列明確的特製化宣告：</span><span class="sxs-lookup"><span data-stu-id="e78b3-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="e78b3-202">特製 `body` 化會指定未套用任何函子之作業的執行。</span><span class="sxs-lookup"><span data-stu-id="e78b3-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="e78b3-203">特製 `adjoint` 化會指定套用仿函數的作業執行 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="e78b3-204">特製 `controlled` 化會指定套用仿函數的作業執行 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="e78b3-205">特製 `controlled adjoint` 化會指定套用和函子的作業執行 `Adjoint` `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="e78b3-206">這種特製化也可以命名為 `adjoint controlled` ，因為這兩個函子的上一次。</span><span class="sxs-lookup"><span data-stu-id="e78b3-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="e78b3-207">作業特製化是由特製化標記 (例如， `body` 或 `adjoint`) 後面接著其中一個：</span><span class="sxs-lookup"><span data-stu-id="e78b3-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="e78b3-208">如下所述的明確宣告。</span><span class="sxs-lookup"><span data-stu-id="e78b3-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="e78b3-209">指示編譯器*如何*產生特製化*的指示詞*，其中一個：</span><span class="sxs-lookup"><span data-stu-id="e78b3-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="e78b3-210">`intrinsic`，表示目的電腦提供特製化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="e78b3-211">`distribute`，搭配和特製化使用 `controlled` `controlled adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="e78b3-212">搭配使用時 `controlled` ，表示編譯器應該套用至中的所有作業來計算特製化 `Controlled` `body` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="e78b3-213">搭配使用時 `controlled adjoint` ，表示編譯器應該套用 `Controlled` 至特製化中的所有作業，以計算特製化 `adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="e78b3-214">`invert`，這表示編譯器應該藉由反轉來計算特製 `adjoint` 化 `body` ，例如反轉作業的順序，並將 adjoint 套用至每一個。</span><span class="sxs-lookup"><span data-stu-id="e78b3-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="e78b3-215">搭配使用時 `adjoint controlled` ，表示編譯器應藉由反轉特製化來計算特製化 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="e78b3-216">`self`，表示 adjoint 特製化與特製 `body` 化相同。</span><span class="sxs-lookup"><span data-stu-id="e78b3-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="e78b3-217">使用對和特製化 `self` 是合法的 `adjoint` `adjoint controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="e78b3-218">若為，表示特製化與特製化 `adjoint controlled` `self` `adjoint controlled` 相同 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="e78b3-219">`auto`，表示編譯器應該選取適當的指示詞以套用。</span><span class="sxs-lookup"><span data-stu-id="e78b3-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="e78b3-220">您無法使用 `auto` 進行特製 `body` 化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="e78b3-221">指示詞和 `auto` 全部都需要右半冒號 `;` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="e78b3-222">如果提供了的明確宣告，則指示詞 `auto` 會解析為下列產生的指示詞 `body` ：</span><span class="sxs-lookup"><span data-stu-id="e78b3-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="e78b3-223">特製 `adjoint` 化會根據指示詞產生 `invert` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="e78b3-224">特製 `controlled` 化會根據指示詞產生 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="e78b3-225">`adjoint controlled` `invert` 如果指定的明確宣告，而非的明確宣告，則會根據指示詞產生特製化 `controlled` `adjoint` ，否則會產生 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="e78b3-226">如果作業是自我 adjoint，請透過世代指示詞明確指定 adjoint 或受控制的 adjoint 特製化， `self` 以允許編譯器將該資訊用於優化用途。</span><span class="sxs-lookup"><span data-stu-id="e78b3-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="e78b3-227">包含使用者定義之實作為的特製化宣告包含引數元組，後面接著語句區塊和執行特製 Q# 化的程式碼。</span><span class="sxs-lookup"><span data-stu-id="e78b3-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="e78b3-228">在引數清單中， `...` 是用來表示整個作業所宣告的引數。</span><span class="sxs-lookup"><span data-stu-id="e78b3-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="e78b3-229">若為 `body` 和 `adjoint` ，引數清單應一律為 `(...)` ; 針對 `controlled` 和 `adjoint controlled` ，引數清單應該是表示控制項量子位陣列的符號，後面接著 `...` 以括弧括住; 例如 `(controls,...)` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="e78b3-230">範例</span><span class="sxs-lookup"><span data-stu-id="e78b3-230">Examples</span></span>

<span data-ttu-id="e78b3-231">作業宣告可能會像下面這樣簡單，定義基本 Pauli X 作業：</span><span class="sxs-lookup"><span data-stu-id="e78b3-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="e78b3-232">請注意，Pauli X 作業的 adjoint 是使用指示詞所定義， `self` 因為根據定義 `X` 是它自己的反向。</span><span class="sxs-lookup"><span data-stu-id="e78b3-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="e78b3-233">在先前的 `PrepareEntangledPair` 範例中，程式碼相當於下列包含明確特製化宣告的程式碼：</span><span class="sxs-lookup"><span data-stu-id="e78b3-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="e78b3-234">關鍵字 `auto` 表示編譯器應該決定如何產生特製化的實作為。</span><span class="sxs-lookup"><span data-stu-id="e78b3-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="e78b3-235">使用者定義的特製化實作為</span><span class="sxs-lookup"><span data-stu-id="e78b3-235">User-defined specialization implementation</span></span>

<span data-ttu-id="e78b3-236">如果編譯器無法自動產生特定特製化的執行，或可以指定更有效率的執行，則您可以手動定義執行。</span><span class="sxs-lookup"><span data-stu-id="e78b3-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

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
<span data-ttu-id="e78b3-237">在上述範例中， `adjoint invert;` 表示 adjoint 特製化是藉由反轉主體實作為產生的， `controlled adjoint invert;` 表示要藉由反轉受控制特製化的指定實來產生受控制的 adjoint 特製化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="e78b3-238">如果有一或多個特製化（除了預設主體）必須明確宣告，則預設主體的實值也必須包裝到適當的特製化宣告中：</span><span class="sxs-lookup"><span data-stu-id="e78b3-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="e78b3-239">有效定義特製化的情況</span><span class="sxs-lookup"><span data-stu-id="e78b3-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="e78b3-240">使用 adjoint/受控制的作業聲明</span><span class="sxs-lookup"><span data-stu-id="e78b3-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="e78b3-241">指定沒有 adjoint 或受控制版本的作業是合法的。</span><span class="sxs-lookup"><span data-stu-id="e78b3-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="e78b3-242">比方說，測量作業不是因為它們無法反轉或可控制。</span><span class="sxs-lookup"><span data-stu-id="e78b3-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="e78b3-243">如果作業的宣告 `Adjoint` 包含個別特製化的隱含或明確宣告，則作業支援和 `Controlled` 函子。</span><span class="sxs-lookup"><span data-stu-id="e78b3-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="e78b3-244">明確宣告的 adjoint/受控制特製化意指 adjoint/受控制特製化是否存在。</span><span class="sxs-lookup"><span data-stu-id="e78b3-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="e78b3-245">若為主體包含重複直到成功迴圈、設定語句、測量、傳回語句或對不支援仿函數之其他作業的作業 `Adjoint` ，則無法在或指示詞之後自動產生 adjoint 特製化 `invert` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="e78b3-246">如果作業的主體包含不支援仿函數之其他作業的呼叫 `Controlled` ，就無法在或指示詞之後自動產生受控制的特製化 `distribute` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="e78b3-247">控制的 Adjoint</span><span class="sxs-lookup"><span data-stu-id="e78b3-247">Controlled Adjoint</span></span>

<span data-ttu-id="e78b3-248">作業的受控制 adjoint 版本會指定如何執行該作業之 adjoint 的量子控制版本。</span><span class="sxs-lookup"><span data-stu-id="e78b3-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="e78b3-249">指定沒有受控制 adjoint 版本的作業是合法的，比方說，測量作業沒有控制的 adjoint 版本，因為它們都不是可控制的，也不能反轉。</span><span class="sxs-lookup"><span data-stu-id="e78b3-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="e78b3-250">如果只有 adjoint 和受控制的特製化存在，則作業的受控制 adjoint 特製化必須存在。</span><span class="sxs-lookup"><span data-stu-id="e78b3-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="e78b3-251">在此情況下，會推斷受控制 adjoint 特製化是否存在。</span><span class="sxs-lookup"><span data-stu-id="e78b3-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="e78b3-252">如果未明確定義任何實作，編譯會產生適當的特製化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="e78b3-253">如果作業的主體包含其他沒有受控制 adjoint 版本之作業的呼叫， `invert` `distribute` 就不可能在、或指示詞之後自動產生 adjoint 特製化 `auto` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="e78b3-254">類型相容性</span><span class="sxs-lookup"><span data-stu-id="e78b3-254">Type Compatibility</span></span>

<span data-ttu-id="e78b3-255">在使用具有較少函子但相同簽章之作業的任何地方，使用具有其他函子支援的作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="e78b3-256">例如，在使用類型作業的任何地方使用類型的作業 `(Qubit => Unit is Adj)` `(Qubit => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="e78b3-257">Q# 對可呼叫的傳回型別而言是 *協* 變數：傳回型別的可呼叫，與 `'A` 具有相同輸入類型的可呼叫相容，以及與相容的結果型別相容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="e78b3-258">Q# 相對於輸入類型是 *逆變* 性：接受型別做為輸入的可呼叫，與 `'A` 具有相同結果型別和與相容的輸入類型的可呼叫相容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="e78b3-259">亦即，假設有下列定義，</span><span class="sxs-lookup"><span data-stu-id="e78b3-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="e78b3-260">您可以</span><span class="sxs-lookup"><span data-stu-id="e78b3-260">you can</span></span>

- <span data-ttu-id="e78b3-261">`ConjugateInvertWith`使用 `inner` 或的引數叫用函數 `Invert` `ApplyUnitary` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="e78b3-262">`ConjugateUnitaryWith`使用的引數叫用函數 `inner` `ApplyUnitary` ，但不叫用 `Invert` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="e78b3-263">從傳回型別的值 `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e78b3-264">Q# 0.3 在使用者自訂類型的行為上引進了顯著的差異。</span><span class="sxs-lookup"><span data-stu-id="e78b3-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="e78b3-265">使用者定義型別會被視為基礎型別的包裝版本，而不是做為子類型。</span><span class="sxs-lookup"><span data-stu-id="e78b3-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="e78b3-266">這表示，如果您預期基礎型別的值為，就無法使用使用者定義型別的值。</span><span class="sxs-lookup"><span data-stu-id="e78b3-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="e78b3-267">動詞變化或是</span><span class="sxs-lookup"><span data-stu-id="e78b3-267">Conjugations</span></span>

<span data-ttu-id="e78b3-268">相較于傳統的位，釋出量子記憶體稍微多一點，因為在量子位仍纏結的情況下，盲目重設量子位可能會對其餘的計算造成不想要的效果。</span><span class="sxs-lookup"><span data-stu-id="e78b3-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="e78b3-269">您可以在釋放記憶體之前適當地「復原」已執行的計算，以避免這些效果。</span><span class="sxs-lookup"><span data-stu-id="e78b3-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="e78b3-270">在量子運算中，常見的模式如下：</span><span class="sxs-lookup"><span data-stu-id="e78b3-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="e78b3-271">從0.9 版開始， Q# 支援結合語句來執行上述轉換。</span><span class="sxs-lookup"><span data-stu-id="e78b3-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="e78b3-272">使用該語句，可以透過 `ApplyWith` 下列方式來執行作業：</span><span class="sxs-lookup"><span data-stu-id="e78b3-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="e78b3-273">如果外部和內部轉換並未立即以作業的形式提供使用，這種結合語句會變得更有用，但是由數個語句所組成的區塊描述更方便描述。</span><span class="sxs-lookup"><span data-stu-id="e78b3-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="e78b3-274">在區塊內定義的語句反向轉換會由編譯器自動產生，並在套用區塊完成之後執行。</span><span class="sxs-lookup"><span data-stu-id="e78b3-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="e78b3-275">由於在區塊中使用的任何可變動變數都無法在套用區塊中重新綁定，因此產生的轉換保證會是在區塊內的計算 adjoint。</span><span class="sxs-lookup"><span data-stu-id="e78b3-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="e78b3-276">定義新函數</span><span class="sxs-lookup"><span data-stu-id="e78b3-276">Defining New Functions</span></span>

<span data-ttu-id="e78b3-277">函式是純粹具決定性的傳統常式 Q# ，其與作業不同，因為它們不允許在計算輸出值之後產生任何影響。</span><span class="sxs-lookup"><span data-stu-id="e78b3-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="e78b3-278">尤其是，函數無法呼叫作業;act、配置或借用量子位;範例亂數字;或其他相依于函式的輸入值之外的狀態。</span><span class="sxs-lookup"><span data-stu-id="e78b3-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="e78b3-279">因此，函式 Q# 是 *純*虛擬的，因為它們一律會將相同的輸入值對應至相同的輸出值。</span><span class="sxs-lookup"><span data-stu-id="e78b3-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="e78b3-280">此行為可讓編譯器在產生作業特製化 Q# 時，安全地重新排列呼叫函式的方式和時機。</span><span class="sxs-lookup"><span data-stu-id="e78b3-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="e78b3-281">每個原始程式檔 Q# 都可以定義任何數目的函式。</span><span class="sxs-lookup"><span data-stu-id="e78b3-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="e78b3-282">函式名稱在命名空間中必須是唯一的，而且無法與作業或類型名稱衝突。</span><span class="sxs-lookup"><span data-stu-id="e78b3-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="e78b3-283">定義函式的運作方式類似于定義作業，但不能為函式定義任何 adjoint 或受控特製化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="e78b3-284">例如：</span><span class="sxs-lookup"><span data-stu-id="e78b3-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="e78b3-285">或</span><span class="sxs-lookup"><span data-stu-id="e78b3-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="e78b3-286">函數中的傳統邏輯 = = 良好</span><span class="sxs-lookup"><span data-stu-id="e78b3-286">Classical logic in functions == good</span></span>

<span data-ttu-id="e78b3-287">只要有可能的話，就能以函式（而非作業）寫出傳統邏輯，讓作業可以更容易使用。</span><span class="sxs-lookup"><span data-stu-id="e78b3-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="e78b3-288">例如，如果您已撰寫先前的宣告 `Square` 做為作業*operation*，則編譯器無法保證以相同的輸入呼叫它會一致地產生相同的輸出。</span><span class="sxs-lookup"><span data-stu-id="e78b3-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="e78b3-289">若要底線函式和作業之間的差異，請考慮傳統方式從作業內取樣亂數字的問題 Q# ：</span><span class="sxs-lookup"><span data-stu-id="e78b3-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="e78b3-290">每次 `U` 呼叫時，會有不同的動作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="e78b3-291">尤其是，編譯器無法保證如果您將特製化宣告加入 `adjoint auto` 至 `U` ，則 `U(target); Adjoint U(target);` 會做為身分識別 (也就是無法運作的) 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="e78b3-292">這違反了 [向量和矩陣](xref:microsoft.quantum.concepts.vectors)中定義之 adjoint 的定義，因此可讓編譯器在您呼叫作業的作業中自動產生 adjoint 特製化，以 <xref:microsoft.quantum.math.randomreal> 中斷編譯器所提供的保證; <xref:microsoft.quantum.math.randomreal> 是沒有 adjoint 或受控制版本存在的作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="e78b3-293">另一方面，允許等函式呼叫 `Square` 是安全的，並確保編譯器只需要保留輸入，以 `Square` 保持其輸出穩定。</span><span class="sxs-lookup"><span data-stu-id="e78b3-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="e78b3-294">因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。</span><span class="sxs-lookup"><span data-stu-id="e78b3-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="e78b3-295">泛型 (類型參數化) Callables</span><span class="sxs-lookup"><span data-stu-id="e78b3-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="e78b3-296">您可能想要定義的許多函數和作業實際上不會依賴其輸入的類型，而只會透過其他函式或作業隱含地使用其類型。</span><span class="sxs-lookup"><span data-stu-id="e78b3-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="e78b3-297">例如，請考慮許多功能性語言通用的 *對應* 概念;假設函式 $f (x) $ 和值的集合 $ \{ x_1、x_2、\dots ..、x_n \} $、map 會傳回新的集合 $ \{ f (x_1) 、f (x_2) 、\dots ..、f (x_n \} $。</span><span class="sxs-lookup"><span data-stu-id="e78b3-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="e78b3-298">若要在中執行這項 Q# 功能，請利用函式是第一個類別的事實。</span><span class="sxs-lookup"><span data-stu-id="e78b3-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="e78b3-299">以下是在 `Map` `T` 您找出需要的型別時，使用做為預留位置的簡單範例。</span><span class="sxs-lookup"><span data-stu-id="e78b3-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="e78b3-300">請注意，無論您替代何種實際型別，此函式看起來非常類似。</span><span class="sxs-lookup"><span data-stu-id="e78b3-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="e78b3-301">例如，從整數到 Paulis 的對應，看起來與從浮點數到字串的對應很大：</span><span class="sxs-lookup"><span data-stu-id="e78b3-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="e78b3-302">基本上，您可以 `Map` 針對所遇到的每一組類型撰寫的版本，但這會帶來幾個難題。</span><span class="sxs-lookup"><span data-stu-id="e78b3-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="e78b3-303">比方說，如果您在中發現錯誤 `Map` ，則必須確保在所有版本的中都能一致地套用修正程式 `Map` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="e78b3-304">此外，如果您要建立新的元組或 UDT，您現在也必須同時建立新的 `Map` to go 以及新的類型。</span><span class="sxs-lookup"><span data-stu-id="e78b3-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="e78b3-305">雖然這是針對少數這類函式方便追蹤的，但當您收集更多和更多功能的相同表單時 `Map` ，引入新類型的成本會以相當短的順序過長大。</span><span class="sxs-lookup"><span data-stu-id="e78b3-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="e78b3-306">不過，這種困難的結果是因為您未提供編譯器所需的資訊，以辨識不同版本的 `Map` 相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e78b3-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="e78b3-307">實際上，您希望編譯器將 `Map` 類型的數學函式視為某種 Q# *類型* 的數學函數 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="e78b3-308">Q# 讓函式和作業具有 *型別參數*，以及它們的一般元組參數，以正規化這個概念。</span><span class="sxs-lookup"><span data-stu-id="e78b3-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="e78b3-309">在先前的範例中，您想要將 `Map` `Int, Pauli` 第一個案例和 `Double, String` 第二個案例中的型別參數視為有型別參數。</span><span class="sxs-lookup"><span data-stu-id="e78b3-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="e78b3-310">在大部分的情況下，請使用這些型別參數，就好像它們是一般型別一樣。</span><span class="sxs-lookup"><span data-stu-id="e78b3-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="e78b3-311">使用型別參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變動變數。</span><span class="sxs-lookup"><span data-stu-id="e78b3-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="e78b3-312">間接相依性最極端的情況是量子位，也就是 Q# 程式無法直接依賴型別的結構， `Qubit` 但 **必須** 將這類型別傳遞給其他作業和函式。</span><span class="sxs-lookup"><span data-stu-id="e78b3-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="e78b3-313">回到先前的範例，您會看到必須 `Map` 有型別參數，一個用來表示輸入，另一個代表 `fn` 輸出 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="e78b3-314">在中，這是藉由在宣告中的函式 Q# 或作業名稱後面加上角括弧 (，而 `<>` 非 brakets $ \braket {} $！ ) 來撰寫，並藉由列出每個類型參數。</span><span class="sxs-lookup"><span data-stu-id="e78b3-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="e78b3-315">每個類型參數的名稱都必須以刻度開頭 `'` ，表示它是型別參數，而不是一般型別 (也稱為 *實體* 型別) 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="e78b3-316">因此， `Map` 會寫入：</span><span class="sxs-lookup"><span data-stu-id="e78b3-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="e78b3-317">請注意，的定義 `Map<'Input, 'Output>` 看起來非常類似于 previoius 版本。</span><span class="sxs-lookup"><span data-stu-id="e78b3-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="e78b3-318">唯一的差別在於您已明確通知編譯器，其 `Map` 不會直接相依于哪些 `'Input` 專案 `'Output` ，但可透過間接使用它們來處理任何兩種類型 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="e78b3-319">`Map<'Input, 'Output>`以這種方式定義之後，您就可以呼叫它，就好像它是一般的函式一樣：</span><span class="sxs-lookup"><span data-stu-id="e78b3-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="e78b3-320">撰寫泛型函式和作業是一個位置，其中「元組-元組外」是一個非常實用的方法，可考慮函式 Q# 和作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="e78b3-321">由於每個函式只會接受一個輸入，而且只會傳回一個輸出，所以類型的輸入會 `'T -> 'U` 符合 *任何*函式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="e78b3-322">同樣地，您可以將任何作業傳遞至類型的輸入 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="e78b3-323">作為第二個範例，請考慮撰寫函數以傳回兩個其他函式組合的挑戰：</span><span class="sxs-lookup"><span data-stu-id="e78b3-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="e78b3-324">在這裡，您必須明確地指定 `A` 、 `B` 和是什麼， `C` 進而嚴格地限制新函式的公用程式 `Compose` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="e78b3-325">畢竟， `Compose` 只取決於 `A` 、和 `B` `C` *via* `innerFn` `outerFn` 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="e78b3-326">或者，您可以將型別參數加入至， `Compose` 這表示它適用于 *任何* `A` 、 `B` 和 `C` ，只要這些參數符合和所預期的參數即可 `innerFn` `outerFn` ：</span><span class="sxs-lookup"><span data-stu-id="e78b3-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="e78b3-327">Q#標準程式庫提供一系列的類型參數化作業和函式，讓高階控制流程更容易表達。</span><span class="sxs-lookup"><span data-stu-id="e78b3-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="e78b3-328">這些將在[ Q# 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。</span><span class="sxs-lookup"><span data-stu-id="e78b3-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="e78b3-329">Callables 為第一級值</span><span class="sxs-lookup"><span data-stu-id="e78b3-329">Callables as First-Class Values</span></span>

<span data-ttu-id="e78b3-330">使用函式（而非作業）來推理控制流程和傳統邏輯的一項重要技巧，是利用中的作業和函 Q# *式為第一類*。</span><span class="sxs-lookup"><span data-stu-id="e78b3-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="e78b3-331">亦即，它們本身就是語言中的每個值。</span><span class="sxs-lookup"><span data-stu-id="e78b3-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="e78b3-332">例如，以下是完全有效的程式 Q# 代碼，如果有一些間接的：</span><span class="sxs-lookup"><span data-stu-id="e78b3-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="e78b3-333">`ourH`前一個程式碼片段中的變數值接著是作業，如此一來， <xref:microsoft.quantum.intrinsic.h> 您就可以像任何其他作業一樣呼叫該值。</span><span class="sxs-lookup"><span data-stu-id="e78b3-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="e78b3-334">有了這項功能，您就可以撰寫作業，將作業當作輸入的一部分來執行，形成更高順序的控制流程概念。</span><span class="sxs-lookup"><span data-stu-id="e78b3-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="e78b3-335">比方說，您可能會想要「方形」作業，方法是將它套用至相同的目標量子位兩次。</span><span class="sxs-lookup"><span data-stu-id="e78b3-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="e78b3-336">從函式傳回作業</span><span class="sxs-lookup"><span data-stu-id="e78b3-336">Returning operations from a function</span></span>

<span data-ttu-id="e78b3-337">請務必強調，您也可以將作業當作輸出的一部分傳回，這樣您就可以將某些類型的傳統條件式邏輯隔離為傳統函式，以操作的形式傳回量副程式的描述。</span><span class="sxs-lookup"><span data-stu-id="e78b3-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="e78b3-338">簡單的範例，請考慮遙傳範例，在此範例中，接收兩位傳統訊息的合作物件需要使用訊息，將其量子位解碼為適當的傳送狀態。</span><span class="sxs-lookup"><span data-stu-id="e78b3-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="e78b3-339">您可以撰寫採用這兩個傳統位的函式，並傳回適當的解碼作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="e78b3-340">這個新函式確實是一個函式，如果您使用和相同的值來呼叫它， `hereBit` `thereBit` 就一定會取回相同的作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="e78b3-341">因此，此解碼器可以安全地在作業中執行，而不需要考慮解碼邏輯如何與不同作業特製化的定義互動。</span><span class="sxs-lookup"><span data-stu-id="e78b3-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="e78b3-342">也就是說，函式內的傳統邏輯是隔離的，保證編譯器可以使用 impunity 來重新排序函式呼叫，只要保留輸入即可。</span><span class="sxs-lookup"><span data-stu-id="e78b3-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="e78b3-343">部分應用程式</span><span class="sxs-lookup"><span data-stu-id="e78b3-343">Partial Application</span></span>

<span data-ttu-id="e78b3-344">您可以使用 *部分應用程式*來大幅增加傳回作業的函式，在此情況下，您可以提供一或多個部分的輸入給函數或作業，而不需要實際呼叫它。</span><span class="sxs-lookup"><span data-stu-id="e78b3-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="e78b3-345">在先前的 `ApplyTwice` 範例中，您可以指出您不想要立即指定應套用輸入作業的量子位：</span><span class="sxs-lookup"><span data-stu-id="e78b3-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="e78b3-346">在此情況下，本機變數會保存部分套用的作業 `twiceOp` `ApplyTwice(op, _)` ，其中 `_` 表示尚未指定的輸入部分。</span><span class="sxs-lookup"><span data-stu-id="e78b3-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="e78b3-347">當您 `twiceOp` 在下一行進行呼叫時，會以輸入的形式傳遞至部分套用的作業，並將輸入的其餘部分寫入至原始作業。</span><span class="sxs-lookup"><span data-stu-id="e78b3-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="e78b3-348">因此，先前的程式碼片段實際上與直接呼叫相同 `ApplyTwice(op, target)` ，請儲存您所引進的新區域變數，如此您就可以在提供輸入的某些部分時延遲呼叫。</span><span class="sxs-lookup"><span data-stu-id="e78b3-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="e78b3-349">由於已部分套用的作業在提供整個輸入之前，並不會實際呼叫，因此您可以安全地部分套用作業，即使是在函式內也一樣。</span><span class="sxs-lookup"><span data-stu-id="e78b3-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="e78b3-350">基本上，內的傳統邏輯 `SquareOperation` 可能更牽涉到許多，但它仍會與作業的其餘部分隔離，方法是編譯器可提供函數的保證。</span><span class="sxs-lookup"><span data-stu-id="e78b3-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="e78b3-351">Q#標準程式庫會在整個中使用這種方法，以量副程式可立即使用的方式來表示傳統控制流程。</span><span class="sxs-lookup"><span data-stu-id="e78b3-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="e78b3-352">遞迴</span><span class="sxs-lookup"><span data-stu-id="e78b3-352">Recursion</span></span>

<span data-ttu-id="e78b3-353">Q# callables 允許直接或間接遞迴。</span><span class="sxs-lookup"><span data-stu-id="e78b3-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="e78b3-354">也就是說，作業或函式可以呼叫本身，或呼叫另一個直接或間接呼叫可呼叫作業的調用。</span><span class="sxs-lookup"><span data-stu-id="e78b3-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="e78b3-355">使用遞迴有兩個重要的批註，不過：</span><span class="sxs-lookup"><span data-stu-id="e78b3-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="e78b3-356">在作業中使用遞迴可能會干擾某些優化。</span><span class="sxs-lookup"><span data-stu-id="e78b3-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="e78b3-357">這項干擾可能會對演算法的執行時間產生顯著的影響。</span><span class="sxs-lookup"><span data-stu-id="e78b3-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="e78b3-358">在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深層遞迴可能會導致執行階段錯誤。</span><span class="sxs-lookup"><span data-stu-id="e78b3-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="e78b3-359">尤其是， Q# 編譯器和執行時間不會識別並優化 tail 遞迴。</span><span class="sxs-lookup"><span data-stu-id="e78b3-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e78b3-360">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e78b3-360">Next steps</span></span>

<span data-ttu-id="e78b3-361">深入瞭解中的 [變數](xref:microsoft.quantum.guide.variables) Q# 。</span><span class="sxs-lookup"><span data-stu-id="e78b3-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>