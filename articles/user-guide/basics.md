---
title: ':::no-loc(Q#)::: 基本概念'
description: '的基本概念 :::no-loc(Q#):::'
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: b3bc0841eabeac5d3968776f9dab3a02b1a1eef9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691625"
---
# <a name="no-locq-basics"></a><span data-ttu-id="572b7-103">:::no-loc(Q#)::: 基本概念</span><span class="sxs-lookup"><span data-stu-id="572b7-103">:::no-loc(Q#)::: Basics</span></span>

<span data-ttu-id="572b7-104">本文提供的基本組建區塊簡介 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="572b7-104">This article presents a brief introduction to the basic building blocks of :::no-loc(Q#):::.</span></span>

<span data-ttu-id="572b7-105">如需瞭解什麼是什麼， :::no-loc(Q#)::: 以及它如何納入作為量子開發工具組的基礎元件，請參閱 [何謂 :::no-loc(Q#)::: ？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="572b7-105">For an overview of what :::no-loc(Q#)::: is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is :::no-loc(Q#):::?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="572b7-106">什麼是量副程式？</span><span class="sxs-lookup"><span data-stu-id="572b7-106">What is a quantum program?</span></span>

<span data-ttu-id="572b7-107">從技術觀點來看，量副程式是一組特定的傳統副程式，在呼叫時，會在量子系統上執行某些作業。</span><span class="sxs-lookup"><span data-stu-id="572b7-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="572b7-108">該觀點的重要結果是，程式不 :::no-loc(Q#)::: 會直接建立量子位本身的模型，而是說明傳統方式控制的電腦如何與這些量子位互動。</span><span class="sxs-lookup"><span data-stu-id="572b7-108">An important consequence of that view is that a :::no-loc(Q#)::: program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="572b7-109">根據設計，不 :::no-loc(Q#)::: 會直接定義量子狀態或量子機制的其他屬性。</span><span class="sxs-lookup"><span data-stu-id="572b7-109">By design, :::no-loc(Q#)::: does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="572b7-110">比方說，請考慮「量子運算概念指南」中所討論的「狀態 $ \ket{+} = \left ( \ket {0} + \ket {1} \right) /\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="572b7-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="572b7-111">若要在中準備此狀態 :::no-loc(Q#)::: ，請從量子位在 $ \ket $ 狀態中初始化的事實開始， {0} 以及該 $ \ket{+} = H\ket {0} $，其中 $H $ 是[ `H` 作業所](xref:Microsoft.Quantum.Intrinsic.H)執行的[Hadamard 轉換](xref:microsoft.quantum.glossary#hadamard)。</span><span class="sxs-lookup"><span data-stu-id="572b7-111">To prepare this state in :::no-loc(Q#):::, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:Microsoft.Quantum.Intrinsic.H).</span></span> <span data-ttu-id="572b7-112">初始化和轉換量子位的基本程式碼，如下所 :::no-loc(Q#)::: 示：</span><span class="sxs-lookup"><span data-stu-id="572b7-112">The basic :::no-loc(Q#)::: code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="572b7-113">如需 *初始化或配置* 量子位的詳細資訊，請參閱 [使用量子位](xref:microsoft.quantum.guide.qubits)。</span><span class="sxs-lookup"><span data-stu-id="572b7-113">For more information on initializing, or *allocating* , qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="572b7-114">中的量子狀態 :::no-loc(Q#):::</span><span class="sxs-lookup"><span data-stu-id="572b7-114">Quantum states in :::no-loc(Q#):::</span></span>

<span data-ttu-id="572b7-115">重要的是，先前的程式並不會明確參考內的狀態， :::no-loc(Q#)::: 但會說明我們的程式如何 *轉換* 狀態。</span><span class="sxs-lookup"><span data-stu-id="572b7-115">Importantly, the previous program does not explicitly refer to the state within :::no-loc(Q#)::: but described how our program *transformed* the state.</span></span>
<span data-ttu-id="572b7-116">使用這種方法時，您可以完全無從確定每個目的電腦 *上的* 量子狀態為何，根據電腦而定，可能會有不同的解釋。</span><span class="sxs-lookup"><span data-stu-id="572b7-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="572b7-117">:::no-loc(Q#):::程式無法 introspect 至量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="572b7-117">A :::no-loc(Q#)::: program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="572b7-118">相反地，程式可以呼叫的作業（例如， [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 從量子位中學習資訊），然後呼叫和之類的作業 [`X`](xref:Microsoft.Quantum.Intrinsic.X) 來處理 [`H`](xref:Microsoft.Quantum.Intrinsic.H) 量子位的狀態。</span><span class="sxs-lookup"><span data-stu-id="572b7-118">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to learn information from a qubit, and call operations such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) to act on the state of a qubit.</span></span>
<span data-ttu-id="572b7-119">這些作業實際 *執行* 的動作，只會由用來執行特定程式的目的電腦來具體處理 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="572b7-119">What these operations actually *do* is only made concrete by the target machine used to run the particular :::no-loc(Q#)::: program.</span></span>
<span data-ttu-id="572b7-120">例如，如果在我們的 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器會對模擬的量子系統執行對應的數學運算。</span><span class="sxs-lookup"><span data-stu-id="572b7-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="572b7-121">但在未來，當目的電腦是真實量子電腦時，在中呼叫這類操作會 :::no-loc(Q#)::: 引導量子電腦在 *真正* 的量子系統上執行對應的 *實際* 操作，例如，精確地計時的雷射脈衝) 。</span><span class="sxs-lookup"><span data-stu-id="572b7-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in :::no-loc(Q#)::: directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="572b7-122">:::no-loc(Q#):::程式會 recombines 目的電腦所定義的這些作業，以建立新的較高層級作業來表示量子計算。</span><span class="sxs-lookup"><span data-stu-id="572b7-122">A :::no-loc(Q#)::: program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="572b7-123">如此一來，就能 :::no-loc(Q#)::: 輕鬆地表達基礎量子和混合式量子的邏輯，也就是目的電腦或模擬器的結構一般。</span><span class="sxs-lookup"><span data-stu-id="572b7-123">In this way, :::no-loc(Q#)::: makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="572b7-124">:::no-loc(Q#)::: 作業和函式</span><span class="sxs-lookup"><span data-stu-id="572b7-124">:::no-loc(Q#)::: operations and functions</span></span>

<span data-ttu-id="572b7-125">具體而言， :::no-loc(Q#)::: 套裝程式含 *作業* 、 *函數* 和任何使用者定義型別。</span><span class="sxs-lookup"><span data-stu-id="572b7-125">Concretely, a :::no-loc(Q#)::: program comprises *operations* , *functions* , and any user-defined types.</span></span> 

<span data-ttu-id="572b7-126">作業是用來描述量子系統的轉換，而且是最基本的程式組建區塊 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="572b7-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of :::no-loc(Q#)::: programs.</span></span> <span data-ttu-id="572b7-127">中定義的每個 :::no-loc(Q#)::: 作業都會呼叫任何數目的其他作業。</span><span class="sxs-lookup"><span data-stu-id="572b7-127">Each operation defined in :::no-loc(Q#)::: may then call any number of other operations.</span></span>

<span data-ttu-id="572b7-128">與作業不同的是，函式是用來描述純粹具 *決定性* 的傳統行為，而且除了計算傳統值之外，沒有任何影響。</span><span class="sxs-lookup"><span data-stu-id="572b7-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="572b7-129">例如，假設您想要測量程式結尾的量子位，並將測量結果新增至陣列。</span><span class="sxs-lookup"><span data-stu-id="572b7-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="572b7-130">在此情況下， `Measure` 是 *operation* 一項作業，會指示目的電腦對 (real 或模擬) 量子位進行測量。</span><span class="sxs-lookup"><span data-stu-id="572b7-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="572b7-131">同樣地，函式會處理將傳回的結果新增至陣列的 *傳統處理常式* 。</span><span class="sxs-lookup"><span data-stu-id="572b7-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="572b7-132">作業和函數統稱為 *callables* 。</span><span class="sxs-lookup"><span data-stu-id="572b7-132">Together, operations and functions are known as *callables* .</span></span> <span data-ttu-id="572b7-133">中導入了其基礎結構和行為，並詳細說明[中 :::no-loc(Q#)::: 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="572b7-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="572b7-134">:::no-loc(Q#)::: 語法總覽</span><span class="sxs-lookup"><span data-stu-id="572b7-134">:::no-loc(Q#)::: syntax overview</span></span>

<span data-ttu-id="572b7-135">語言的語法描述形成語法正確程式的不同符號組合。</span><span class="sxs-lookup"><span data-stu-id="572b7-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="572b7-136">在中 :::no-loc(Q#)::: ，語法元素會分類為三個不同的群組：類型、運算式和語句。</span><span class="sxs-lookup"><span data-stu-id="572b7-136">In :::no-loc(Q#):::, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="572b7-137">類型</span><span class="sxs-lookup"><span data-stu-id="572b7-137">Types</span></span>
<span data-ttu-id="572b7-138">:::no-loc(Q#)::: 是一種強型別語言，可讓編譯器在編譯時期提供程式的強大保證，以利使用類型 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="572b7-138">:::no-loc(Q#)::: is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about :::no-loc(Q#)::: programs at compile time.</span></span>
<span data-ttu-id="572b7-139">除了標準和量子特有的內建基本型別，例如、、 `Int` `Bool` `Qubit` 和 `Result` ，也 :::no-loc(Q#)::: 提供使用者定義類型的支援。</span><span class="sxs-lookup"><span data-stu-id="572b7-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, :::no-loc(Q#)::: provides support for user-defined types.</span></span>

<span data-ttu-id="572b7-140">如需所有基本型別、陣列和元組類型的詳細資訊，以及在檔案中定義新類型的步驟，請 :::no-loc(Q#)::: 參閱[中 :::no-loc(Q#)::: 的類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="572b7-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a :::no-loc(Q#)::: file, see [Types in :::no-loc(Q#):::](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="572b7-141">運算式</span><span class="sxs-lookup"><span data-stu-id="572b7-141">Expressions</span></span>
<span data-ttu-id="572b7-142">程式設計語言中的運算式結合了一或多個常數、變數、運算子和函式，程式語言會將這些常數、變數、運算子和函式轉譯為特定值。</span><span class="sxs-lookup"><span data-stu-id="572b7-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="572b7-143">最簡單的方法是，針對語言中的每個類型，該類型的運算式可以是系結至該類型值的 *常* 值或符號。</span><span class="sxs-lookup"><span data-stu-id="572b7-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="572b7-144">例如， `5` 是 `Int` 常值 (因此也是) 類型的運算式 `Int` ，如果符號系結 `count` 至整數值 `5` ，則 `count` 也是整數運算式。</span><span class="sxs-lookup"><span data-stu-id="572b7-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="572b7-145">此外，運算式也可以由某些運算子所合併的其他運算式所組成。</span><span class="sxs-lookup"><span data-stu-id="572b7-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="572b7-146">例如，另一個 `Int` 評估為的運算式 `5` `2+3` 。</span><span class="sxs-lookup"><span data-stu-id="572b7-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="572b7-147">如需中運算式和相容運算子的詳細資訊 :::no-loc(Q#)::: ，請參閱[中 :::no-loc(Q#)::: 的型別運算式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="572b7-147">For more information about expressions and compatible operators in :::no-loc(Q#):::, see [Type Expressions in :::no-loc(Q#):::](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="572b7-148">陳述式</span><span class="sxs-lookup"><span data-stu-id="572b7-148">Statements</span></span> 
<span data-ttu-id="572b7-149">語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與該語句中的運算式對比不會傳回結果，而且只會針對其副作用執行。</span><span class="sxs-lookup"><span data-stu-id="572b7-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are run solely for their side effects.</span></span> <span data-ttu-id="572b7-150">但是，運算式一律會傳回結果，而且通常沒有任何副作用。</span><span class="sxs-lookup"><span data-stu-id="572b7-150">Expressions, however, always return a result and often do not have any side effects.</span></span> <span data-ttu-id="572b7-151">簡單來說， :::no-loc(Q#)::: 語句是在評估運算式時執行。</span><span class="sxs-lookup"><span data-stu-id="572b7-151">In short, :::no-loc(Q#)::: statements are run, while expressions are evaluated.</span></span>

<span data-ttu-id="572b7-152">在中，語句的簡單範例 :::no-loc(Q#)::: 是將符號指派給運算式：</span><span class="sxs-lookup"><span data-stu-id="572b7-152">A simple example of a statement in :::no-loc(Q#)::: is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="572b7-153">比較有趣的範例是 `for` 支援反覆運算的語句，並包含 *語句區塊* 。</span><span class="sxs-lookup"><span data-stu-id="572b7-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block* .</span></span>
<span data-ttu-id="572b7-154">假設是系結至量子位之暫存器的 `qubits` 符號， (的型別或型別的 `Qubit[]` 陣列 `Qubit`) 。</span><span class="sxs-lookup"><span data-stu-id="572b7-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="572b7-155">結果為</span><span class="sxs-lookup"><span data-stu-id="572b7-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="572b7-156">這是逐一查看暫存器中的每個量子位，在每個上執行作業的語句 `H` 。</span><span class="sxs-lookup"><span data-stu-id="572b7-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="572b7-157">請注意，它 `H(qubit);` 本身也是語句。</span><span class="sxs-lookup"><span data-stu-id="572b7-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="572b7-158">您可以使用類型的任何呼叫運算式 `Unit` (`Unit` 類型不會傳回任何) 為語句的資訊。</span><span class="sxs-lookup"><span data-stu-id="572b7-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="572b7-159">這種類型的運算式在呼叫量子位上的作業時很有用， `Unit` 因為語句的目的是要修改隱含的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="572b7-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="572b7-160">運算式評估語句需要終止分號。</span><span class="sxs-lookup"><span data-stu-id="572b7-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="572b7-161">您可以使用語句來建立幾乎每個程式的各個層面 :::no-loc(Q#)::: ，而且沒有任何單一頁面可以包含與它們相關的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="572b7-161">You use statements to build nearly every aspect of a :::no-loc(Q#)::: program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="572b7-162">如需其詞法結構和格式的詳細資訊，請參閱檔案[ :::no-loc(Q#)::: 結構](xref:microsoft.quantum.guide.filestructure); 針對符號系結指派和範圍，請參閱[中 :::no-loc(Q#)::: 的變數](xref:microsoft.quantum.guide.variables)，以及如的控制流程迴圈（例如 `for` ），請參閱[中 :::no-loc(Q#)::: 的控制流程](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="572b7-162">For more information about their lexical structure and formatting, see [:::no-loc(Q#)::: File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in :::no-loc(Q#):::](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in :::no-loc(Q#):::](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="572b7-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="572b7-163">Next steps</span></span>

<span data-ttu-id="572b7-164">開始瞭解[中的 :::no-loc(Q#)::: 類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="572b7-164">Start learning about [Types in :::no-loc(Q#):::](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="572b7-165">如需背後基礎和動機的詳細背景 :::no-loc(Q#)::: ，請參閱 [為什麼我們需要 :::no-loc(Q#)::: ？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="572b7-165">For more background about the foundations and motivation behind :::no-loc(Q#):::, see [Why do we need :::no-loc(Q#):::?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
