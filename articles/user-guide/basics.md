---
title: '問 # 基本概念'
description: Q 的基本概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415351"
---
# <a name="q-basics"></a><span data-ttu-id="a8799-103">問 # 基本概念</span><span class="sxs-lookup"><span data-stu-id="a8799-103">Q# Basics</span></span>

<span data-ttu-id="a8799-104">本文提供 Q # 基本構件的簡介。</span><span class="sxs-lookup"><span data-stu-id="a8799-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="a8799-105">如需瞭解問 # 是什麼，以及它如何融入作為量子開發工具組的基礎元件，請參閱[什麼是問 #？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="a8799-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="a8799-106">什麼是量副程式？</span><span class="sxs-lookup"><span data-stu-id="a8799-106">What is a quantum program?</span></span>

<span data-ttu-id="a8799-107">從技術觀點來看，配量程式是一組特定的傳統副程式，在被呼叫時，會在量子系統上執行某些作業。</span><span class="sxs-lookup"><span data-stu-id="a8799-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="a8799-108">該觀點的重要結果是，問 # 程式不會直接建立 qubits 本身的模型，而是描述傳統方式控管的電腦與這些 qubits 的互動方式。</span><span class="sxs-lookup"><span data-stu-id="a8799-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="a8799-109">根據設計，Q # 並不會直接定義配量狀態或其他的量子機制屬性。</span><span class="sxs-lookup"><span data-stu-id="a8799-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="a8799-110">例如，請考慮「量子計算概念指南」中所討論的 state $ \ket{+} = \left （\ket {0} + \ket {1} \right）/\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="a8799-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="a8799-111">若要在 Q # 中準備此狀態，請從以 $ \ket $ 狀態初始化 qubits 的事實開始， {0} 然後按 $ \ket{+} = H\ket {0} $，其中 $H $ 是由[ `H` 作業所](xref:microsoft.quantum.intrinsic.h)執行的[Hadamard 轉換](xref:microsoft.quantum.glossary#hadamard)。</span><span class="sxs-lookup"><span data-stu-id="a8799-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="a8799-112">用來初始化和轉換 qubit 的基本 Q # 程式碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a8799-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="a8799-113">如需有關*初始化或配置*qubits 的詳細資訊，請參閱[使用 qubits](xref:microsoft.quantum.guide.qubits)。</span><span class="sxs-lookup"><span data-stu-id="a8799-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-q"></a><span data-ttu-id="a8799-114">Q 中的量子狀態#</span><span class="sxs-lookup"><span data-stu-id="a8799-114">Quantum states in Q#</span></span>

<span data-ttu-id="a8799-115">重要的是，先前的程式並未明確參考 Q # 內的狀態，而是說明我們的程式如何*轉換*狀態。</span><span class="sxs-lookup"><span data-stu-id="a8799-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="a8799-116">使用這種方法，您可以完全找出每一部目的電腦*上的*量子狀態為何，這可能會有不同的解讀，視電腦而定。</span><span class="sxs-lookup"><span data-stu-id="a8799-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="a8799-117">Q # 程式無法 introspect 至 qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="a8799-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="a8799-118">相反地，程式可以呼叫作業（例如） [`Measure`](xref:microsoft.quantum.intrinsic.measure) 以從 qubit 中學習資訊，以及呼叫和之類的作業 [`X`](xref:microsoft.quantum.intrinsic.x) 來處理 [`H`](xref:microsoft.quantum.intrinsic.h) qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="a8799-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="a8799-119">這些作業實際*執行*的動作，只會由用來執行特定 Q # 程式的目的電腦進行具體處理。</span><span class="sxs-lookup"><span data-stu-id="a8799-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="a8799-120">例如，如果在我們的[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器會對模擬的量子系統執行對應的數學運算。</span><span class="sxs-lookup"><span data-stu-id="a8799-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="a8799-121">但在未來，當目的機器是實際的量子電腦時，在 Q # 中呼叫這類作業會引導量子電腦在*實際*的量子系統上執行對應的*實際*作業，例如，精確地計時雷射脈衝）。</span><span class="sxs-lookup"><span data-stu-id="a8799-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="a8799-122">Q # 程式會依照目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。</span><span class="sxs-lookup"><span data-stu-id="a8799-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="a8799-123">如此一來，Q # 可讓您輕鬆地表達基礎配量和混合式量子–傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。</span><span class="sxs-lookup"><span data-stu-id="a8799-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="a8799-124">Q # 作業和函數</span><span class="sxs-lookup"><span data-stu-id="a8799-124">Q# operations and functions</span></span>

<span data-ttu-id="a8799-125">具體而言，Q # 套裝程式含*作業* *、函式和任何*使用者定義的類型。</span><span class="sxs-lookup"><span data-stu-id="a8799-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="a8799-126">作業是用來描述量子系統的轉換，而且是 Q # 程式的最基本建立組塊。</span><span class="sxs-lookup"><span data-stu-id="a8799-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="a8799-127">在 Q # 中定義的每個作業，都可以呼叫任何數目的其他作業。</span><span class="sxs-lookup"><span data-stu-id="a8799-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="a8799-128">相對於作業，函數是用來描述純粹具*決定性*的傳統行為，而且除了計算傳統值以外，也不會有任何影響。</span><span class="sxs-lookup"><span data-stu-id="a8799-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="a8799-129">例如，假設您想要測量程式結尾的 qubits，並將量測結果新增至陣列。</span><span class="sxs-lookup"><span data-stu-id="a8799-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="a8799-130">在此情況下， `Measure` 是*operation*一項作業，會指示目的電腦對（實際或模擬） qubits 執行測量。</span><span class="sxs-lookup"><span data-stu-id="a8799-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="a8799-131">同時 *，函*式會處理將傳回的結果新增至陣列的傳統程式。</span><span class="sxs-lookup"><span data-stu-id="a8799-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="a8799-132">作業和函數統稱為*callables*。</span><span class="sxs-lookup"><span data-stu-id="a8799-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="a8799-133">其基礎結構和行為會在[Q # 的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式中引進和詳細說明。</span><span class="sxs-lookup"><span data-stu-id="a8799-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="a8799-134">Q # 語法總覽</span><span class="sxs-lookup"><span data-stu-id="a8799-134">Q# syntax overview</span></span>

<span data-ttu-id="a8799-135">語言的語法描述形成語法正確程式的不同符號組合。</span><span class="sxs-lookup"><span data-stu-id="a8799-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="a8799-136">在 Q # 中，語法元素會分類成三個不同的群組：類型、運算式和語句。</span><span class="sxs-lookup"><span data-stu-id="a8799-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="a8799-137">類型</span><span class="sxs-lookup"><span data-stu-id="a8799-137">Types</span></span>
<span data-ttu-id="a8799-138">問 # 是強型別語言，因此謹慎使用型別可以協助編譯器在編譯時期提供有關 Q # 程式的強式保證。</span><span class="sxs-lookup"><span data-stu-id="a8799-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="a8799-139">除了標準和量子特定的內建基本類型，例如、、 `Int` `Bool` `Qubit` 和 `Result` ，Q # 提供使用者定義類型的支援。</span><span class="sxs-lookup"><span data-stu-id="a8799-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="a8799-140">如需所有基本類型的描述、陣列和元組類型的詳細資料，以及在 Q # 檔案中定義新類型的步驟，請參閱[q # 中的類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="a8799-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="a8799-141">運算式</span><span class="sxs-lookup"><span data-stu-id="a8799-141">Expressions</span></span>
<span data-ttu-id="a8799-142">程式設計語言中的運算式是一或多個常數、變數、運算子和函式的組合，程式語言會將其解讀並評估為特定值。</span><span class="sxs-lookup"><span data-stu-id="a8799-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="a8799-143">最簡單的說，針對語言中的每個型別，該型別的運算式可以是*常*值或系結至該型別之值的符號。</span><span class="sxs-lookup"><span data-stu-id="a8799-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="a8799-144">例如， `5` 是 `Int` 常值（也是類型的運算式 `Int` ），而且如果符號系結 `count` 至整數值 `5` ，則 `count` 也是整數運算式。</span><span class="sxs-lookup"><span data-stu-id="a8799-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="a8799-145">此外，運算式可以由特定運算子所結合的其他運算式所組成。</span><span class="sxs-lookup"><span data-stu-id="a8799-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="a8799-146">例如，另一個 `Int` 評估為的運算式 `5` 是 `2+3` 。</span><span class="sxs-lookup"><span data-stu-id="a8799-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="a8799-147">如需 Q # 中運算式和相容運算子的詳細資訊，請參閱[q # 中的類型運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="a8799-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="a8799-148">陳述式</span><span class="sxs-lookup"><span data-stu-id="a8799-148">Statements</span></span> 
<span data-ttu-id="a8799-149">語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與語句中的運算式對比不會傳回結果，而且只會針對其副作用執行。</span><span class="sxs-lookup"><span data-stu-id="a8799-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects.</span></span> <span data-ttu-id="a8799-150">不過，運算式一律會傳回結果，而且通常完全不會有副作用。</span><span class="sxs-lookup"><span data-stu-id="a8799-150">Expressions, however, always return a result and often do not have side effects at all.</span></span> <span data-ttu-id="a8799-151">簡言之，會執行 Q # 語句，而運算式會進行評估。</span><span class="sxs-lookup"><span data-stu-id="a8799-151">In short, Q# statements are executed, while expressions are evaluated.</span></span>

<span data-ttu-id="a8799-152">在 Q # 中，語句的簡單範例是將符號指派給運算式：</span><span class="sxs-lookup"><span data-stu-id="a8799-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="a8799-153">更有趣的範例是 `for` 支援反復專案並包含*語句區塊*的語句。</span><span class="sxs-lookup"><span data-stu-id="a8799-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="a8799-154">假設是系結至 qubits 暫存器的 `qubits` 符號（技術上的類型 `Qubit[]` ，或類型的陣列 `Qubit` ）。</span><span class="sxs-lookup"><span data-stu-id="a8799-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="a8799-155">結果為</span><span class="sxs-lookup"><span data-stu-id="a8799-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="a8799-156">這是一種語句，它會逐一查看暫存器中的每個 qubit，對每一個的執行作業 `H` 。</span><span class="sxs-lookup"><span data-stu-id="a8799-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="a8799-157">請注意， `H(qubit);` 本身也是語句。</span><span class="sxs-lookup"><span data-stu-id="a8799-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="a8799-158">您可以將任何類型的呼叫運算式 `Unit` （ `Unit` 類型不會傳回任何資訊）當做語句使用。</span><span class="sxs-lookup"><span data-stu-id="a8799-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="a8799-159">在傳回的 qubits 上呼叫作業時，這種類型的運算式很有用， `Unit` 因為語句的目的是要修改隱含的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="a8799-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="a8799-160">運算式評估語句需要結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="a8799-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="a8799-161">您可以使用語句來建立一個 Q # 程式的幾乎每個層面，而且沒有任何一個頁面可以包含與它們相關的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="a8799-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="a8799-162">如需其詞法結構和格式的詳細資訊，請參閱[Q # 檔案結構](xref:microsoft.quantum.guide.filestructure);如需符號系結指派和範圍，請參閱[Q # 中的變數](xref:microsoft.quantum.guide.variables)。如需控制流程迴圈（例如 `for` ），請參閱[Q # 中的控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="a8799-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8799-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a8799-163">Next steps</span></span>

<span data-ttu-id="a8799-164">開始瞭解[問 # 中的類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="a8799-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="a8799-165">如需有關 Q # 背後的基礎和動機的背景資訊，請參閱[為什麼需要問 #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="a8799-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
