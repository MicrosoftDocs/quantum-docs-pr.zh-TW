---
title: Q#操作
description: 的基本概念Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4f4a75cdaaa070fd763d7f75429b7c39357d25a5
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869642"
---
# <a name="no-locq-basics"></a><span data-ttu-id="cc06d-103">Q#操作</span><span class="sxs-lookup"><span data-stu-id="cc06d-103">Q# Basics</span></span>

<span data-ttu-id="cc06d-104">本文提供的基本組建組塊簡介 Q# 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="cc06d-105">如需瞭解其適用 Q# 于作為配量開發工具組的基本元件，以及其所在位置的總覽，請參閱[什麼是 Q# ？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="cc06d-106">什麼是量副程式？</span><span class="sxs-lookup"><span data-stu-id="cc06d-106">What is a quantum program?</span></span>

<span data-ttu-id="cc06d-107">從技術觀點來看，配量程式是一組特定的傳統副程式，在被呼叫時，會在量子系統上執行某些作業。</span><span class="sxs-lookup"><span data-stu-id="cc06d-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="cc06d-108">該觀點的重要結果是，程式不 Q# 會直接建立 qubits 本身的模型，而是描述傳統方式控制的電腦如何與這些 qubits 互動。</span><span class="sxs-lookup"><span data-stu-id="cc06d-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="cc06d-109">根據設計，不 Q# 會直接定義配量狀態或其他的量子機制屬性。</span><span class="sxs-lookup"><span data-stu-id="cc06d-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="cc06d-110">例如，請考慮「量子計算概念指南」中所討論的狀態 $ \ket{+} = \left ( \ket {0} + \ket {1} \right) /\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="cc06d-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="cc06d-111">若要在中準備此狀態 Q# ，請從 qubits 以 $ \ket $ 狀態初始化的事實開始， {0} 然後按 $ \ket{+} = H\ket {0} $，其中 $H $ 是由[ `H` 作業所](xref:microsoft.quantum.intrinsic.h)執行的[Hadamard 轉換](xref:microsoft.quantum.glossary#hadamard)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="cc06d-112">初始化和轉換 qubit 的基本程式碼，如下所示 Q# ：</span><span class="sxs-lookup"><span data-stu-id="cc06d-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="cc06d-113">如需有關*初始化或配置*qubits 的詳細資訊，請參閱[使用 qubits](xref:microsoft.quantum.guide.qubits)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="cc06d-114">中的量子狀態Q#</span><span class="sxs-lookup"><span data-stu-id="cc06d-114">Quantum states in Q#</span></span>

<span data-ttu-id="cc06d-115">重要的是，先前的程式並不會明確參考內的狀態，而是會 Q# 描述程式如何*轉換*狀態。</span><span class="sxs-lookup"><span data-stu-id="cc06d-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="cc06d-116">使用這種方法，您可以完全找出每一部目的電腦*上的*量子狀態為何，這可能會有不同的解讀，視電腦而定。</span><span class="sxs-lookup"><span data-stu-id="cc06d-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="cc06d-117">Q#程式無法 introspect 至 qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc06d-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="cc06d-118">相反地，程式可以呼叫作業（例如） [`Measure`](xref:microsoft.quantum.intrinsic.measure) 以從 qubit 中學習資訊，以及呼叫和之類的作業 [`X`](xref:microsoft.quantum.intrinsic.x) 來處理 [`H`](xref:microsoft.quantum.intrinsic.h) qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc06d-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="cc06d-119">這些作業實際*執行*的動作，只會由用來執行特定程式的目的電腦進行具體處理 Q# 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="cc06d-120">例如，如果在我們的[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器會對模擬的量子系統執行對應的數學運算。</span><span class="sxs-lookup"><span data-stu-id="cc06d-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="cc06d-121">但在未來，當目的機器是真實的量子電腦時，在中呼叫這類作業會 Q# 引導量子電腦在*實際*的量子系統上執行對應的*實際*作業，例如，精確地計時雷射脈衝) 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="cc06d-122">程式會依照 Q# 目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。</span><span class="sxs-lookup"><span data-stu-id="cc06d-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="cc06d-123">如此一來， Q# 您就可以輕鬆地表達基礎配量和混合式量子–傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。</span><span class="sxs-lookup"><span data-stu-id="cc06d-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="cc06d-124">Q#作業和函式</span><span class="sxs-lookup"><span data-stu-id="cc06d-124">Q# operations and functions</span></span>

<span data-ttu-id="cc06d-125">具體而言， Q# 套裝程式含*作業*、函*functions*式和任何使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="cc06d-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="cc06d-126">作業是用來描述量子系統的轉換，而且是最基本的程式建立組塊 Q# 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="cc06d-127">在中定義的每個 Q# 作業都會呼叫任何數目的其他作業。</span><span class="sxs-lookup"><span data-stu-id="cc06d-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="cc06d-128">相對於作業，函數是用來描述純粹具*決定性*的傳統行為，而且除了計算傳統值以外，也不會有任何影響。</span><span class="sxs-lookup"><span data-stu-id="cc06d-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="cc06d-129">例如，假設您想要測量程式結尾的 qubits，並將量測結果新增至陣列。</span><span class="sxs-lookup"><span data-stu-id="cc06d-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="cc06d-130">在此情況下， `Measure` 是指示目的電腦對 (real 或模擬) qubits 執行測量的*運算*。</span><span class="sxs-lookup"><span data-stu-id="cc06d-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="cc06d-131">同時 *，函*式會處理將傳回的結果新增至陣列的傳統程式。</span><span class="sxs-lookup"><span data-stu-id="cc06d-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="cc06d-132">作業和函數統稱為*callables*。</span><span class="sxs-lookup"><span data-stu-id="cc06d-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="cc06d-133">其基礎結構和行為會在中引進，並詳述于[中 Q# 的作業和功能](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="cc06d-134">Q#語法總覽</span><span class="sxs-lookup"><span data-stu-id="cc06d-134">Q# syntax overview</span></span>

<span data-ttu-id="cc06d-135">語言的語法描述形成語法正確程式的不同符號組合。</span><span class="sxs-lookup"><span data-stu-id="cc06d-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="cc06d-136">在中 Q# ，語法元素會分類成三個不同的群組：類型、運算式和語句。</span><span class="sxs-lookup"><span data-stu-id="cc06d-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="cc06d-137">型別</span><span class="sxs-lookup"><span data-stu-id="cc06d-137">Types</span></span>
<span data-ttu-id="cc06d-138">Q#是強型別語言，因此謹慎使用型別可以協助編譯器在編譯時期提供有關程式的強式保證 Q# 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="cc06d-139">除了標準和量子特定的內建基本類型（例如、、 `Int` 和）之外， `Bool` `Qubit` 也 `Result` Q# 提供使用者定義類型的支援。</span><span class="sxs-lookup"><span data-stu-id="cc06d-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="cc06d-140">如需所有基本類型的描述、陣列和元組類型的詳細資料，以及在檔案中定義新類型的步驟， Q# 請參閱[中 Q# 的類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="cc06d-141">運算式</span><span class="sxs-lookup"><span data-stu-id="cc06d-141">Expressions</span></span>
<span data-ttu-id="cc06d-142">程式設計語言中的運算式是一或多個常數、變數、運算子和函式的組合，程式語言會將其解讀並評估為特定值。</span><span class="sxs-lookup"><span data-stu-id="cc06d-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="cc06d-143">最簡單的說，針對語言中的每個型別，該型別的運算式可以是*常*值或系結至該型別之值的符號。</span><span class="sxs-lookup"><span data-stu-id="cc06d-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="cc06d-144">例如， `5` 是常值 `Int` (因此也是) 類型的運算式 `Int` ，如果符號系結 `count` 至整數值 `5` ，則 `count` 也是一個整數運算式。</span><span class="sxs-lookup"><span data-stu-id="cc06d-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="cc06d-145">此外，運算式可以由特定運算子所結合的其他運算式所組成。</span><span class="sxs-lookup"><span data-stu-id="cc06d-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="cc06d-146">例如，另一個 `Int` 評估為的運算式 `5` 是 `2+3` 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="cc06d-147">如需中運算式和相容運算子的詳細資訊 Q# ，請參閱[中 Q# 的類型運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="cc06d-148">陳述式</span><span class="sxs-lookup"><span data-stu-id="cc06d-148">Statements</span></span> 
<span data-ttu-id="cc06d-149">語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與語句中的運算式對比不會傳回結果，而且只會針對其副作用執行。</span><span class="sxs-lookup"><span data-stu-id="cc06d-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects.</span></span> <span data-ttu-id="cc06d-150">不過，運算式一律會傳回結果，而且通常完全不會有副作用。</span><span class="sxs-lookup"><span data-stu-id="cc06d-150">Expressions, however, always return a result and often do not have side effects at all.</span></span> <span data-ttu-id="cc06d-151">簡言之， Q# 會執行語句，而運算式會進行評估。</span><span class="sxs-lookup"><span data-stu-id="cc06d-151">In short, Q# statements are executed, while expressions are evaluated.</span></span>

<span data-ttu-id="cc06d-152">在中，有一個簡單的語句範例 Q# ，就是將符號指派給運算式：</span><span class="sxs-lookup"><span data-stu-id="cc06d-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="cc06d-153">更有趣的範例是 `for` 支援反復專案並包含*語句區塊*的語句。</span><span class="sxs-lookup"><span data-stu-id="cc06d-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="cc06d-154">假設 `qubits` 是系結至 (qubits 的暫存器（類型為技術 `Qubit[]` ）的符號，或 `Qubit`) 的類型陣列。</span><span class="sxs-lookup"><span data-stu-id="cc06d-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="cc06d-155">結果為</span><span class="sxs-lookup"><span data-stu-id="cc06d-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="cc06d-156">這是一種語句，它會逐一查看暫存器中的每個 qubit，對每一個的執行作業 `H` 。</span><span class="sxs-lookup"><span data-stu-id="cc06d-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="cc06d-157">請注意， `H(qubit);` 本身也是語句。</span><span class="sxs-lookup"><span data-stu-id="cc06d-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="cc06d-158">您可以使用任何類型的呼叫運算式 `Unit` (`Unit` 類型不會傳回任何資訊) 作為語句。</span><span class="sxs-lookup"><span data-stu-id="cc06d-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="cc06d-159">在傳回的 qubits 上呼叫作業時，這種類型的運算式很有用， `Unit` 因為語句的目的是要修改隱含的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="cc06d-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="cc06d-160">運算式評估語句需要結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="cc06d-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="cc06d-161">您可以使用語句來建立幾乎每個程式的各個層面 Q# ，而且沒有任何單一頁面可以包含與它們相關的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="cc06d-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="cc06d-162">如需其詞法結構和格式的詳細資訊，請參閱檔案[ Q# 結構](xref:microsoft.quantum.guide.filestructure); 針對符號系結指派和範圍，請參閱[中 Q# 的變數](xref:microsoft.quantum.guide.variables); 如需控制流程迴圈，請參閱 `for` [中 Q# 的控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cc06d-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="cc06d-163">Next steps</span></span>

<span data-ttu-id="cc06d-164">開始瞭解[中的 Q# 類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="cc06d-165">如需更多關於基礎和動機背後的背景資訊 Q# ，請參閱[為什麼我們需要 Q# ？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="cc06d-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
