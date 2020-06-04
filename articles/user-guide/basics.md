---
title: '問 # 基本概念'
description: Q 的基本概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: e77b52d1a6eb7e2f62ab12dedd75d00ac8fec4be
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327317"
---
# <a name="q-basics"></a><span data-ttu-id="78fa8-103">問 # 基本概念</span><span class="sxs-lookup"><span data-stu-id="78fa8-103">Q# Basics</span></span>

<span data-ttu-id="78fa8-104">在本節中，我們將簡短介紹 Q # 的基本組建區塊。</span><span class="sxs-lookup"><span data-stu-id="78fa8-104">In this section we present a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="78fa8-105">如需快速概覽問 # 是什麼，以及它如何融入作為量子開發工具組的基礎元件，您可以查看[什麼是問 #？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="78fa8-105">For a quick overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, you can check out [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="78fa8-106">什麼是量副程式？</span><span class="sxs-lookup"><span data-stu-id="78fa8-106">What is a quantum program?</span></span>

<span data-ttu-id="78fa8-107">從技術觀點來看，配量程式可視為一組特定的傳統副程式，在呼叫時，會在量子系統上執行某些作業。</span><span class="sxs-lookup"><span data-stu-id="78fa8-107">From a technical perspective, a quantum program can be seen as a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="78fa8-108">該觀點的重要結果是，以 Q # 撰寫的程式並不會直接 qubits 本身的模型，而是說明傳統的控制項電腦與這些 qubits 的互動方式。</span><span class="sxs-lookup"><span data-stu-id="78fa8-108">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="78fa8-109">根據設計，Q # 因此不會直接定義配量狀態或其他的量子機制屬性。</span><span class="sxs-lookup"><span data-stu-id="78fa8-109">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="78fa8-110">例如，請考慮「量子計算概念指南」中所討論的 state $ \ket{+} = \left （\ket {0} + \ket {1} \right）/\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="78fa8-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="78fa8-111">若要在 Q # 中準備此狀態，我們會使用 qubits 在 $ \ket $ 狀態中初始化的事實 {0} ，以及 $ \ket{+} = H\ket {0} $，其中 $H $ 是 Hadamard 轉換，其中的 [ `H` operation] （] （x：）會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="78fa8-111">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform, implemented by the [`H` operation](](xref:microsoft.quantum.intrinsic.h):</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a><span data-ttu-id="78fa8-112">Q 中的量子狀態#</span><span class="sxs-lookup"><span data-stu-id="78fa8-112">Quantum states in Q#</span></span>

<span data-ttu-id="78fa8-113">重要的是，在撰寫上述程式時，我們並未明確參考 Q # 內的狀態，而是說明我們的程式如何*轉換*狀態。</span><span class="sxs-lookup"><span data-stu-id="78fa8-113">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="78fa8-114">這可讓我們完全無從得知每個目的電腦上的量子狀態為何，這*可能會有*不同的解讀，視電腦而定。</span><span class="sxs-lookup"><span data-stu-id="78fa8-114">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="78fa8-115">Q # 程式無法 introspect 至 qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="78fa8-115">A Q# program has no ability to introspect into the state of a qubit.</span></span>
<span data-ttu-id="78fa8-116">相反地，程式可以呼叫作業（例如） [`Measure`](xref:microsoft.quantum.intrinsic.measure) 以從 qubit 中學習資訊，以及呼叫和之類的作業 [`X`](xref:microsoft.quantum.intrinsic.x) 來處理 [`H`](xref:microsoft.quantum.intrinsic.h) qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="78fa8-116">Rather, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="78fa8-117">這些作業實際*執行*的動作，只會由我們用來執行特定 Q # 程式的目的電腦進行具體處理。</span><span class="sxs-lookup"><span data-stu-id="78fa8-117">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>
<span data-ttu-id="78fa8-118">例如，如果在我們的[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器上執行程式，模擬器將會對模擬的量子系統執行對應的數學運算。</span><span class="sxs-lookup"><span data-stu-id="78fa8-118">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator will perform the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="78fa8-119">但在未來，當目的機器是實際的量子電腦時，在 Q # 中呼叫這類作業會引導量子電腦在*實際*的量子系統上執行相對應的*實際*操作（例如，精確的時間間隔雷射脈衝）。</span><span class="sxs-lookup"><span data-stu-id="78fa8-119">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="78fa8-120">Q # 程式會依照目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。</span><span class="sxs-lookup"><span data-stu-id="78fa8-120">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="78fa8-121">如此一來，Q # 可讓您輕鬆地表達基礎配量和混合式量子–傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。</span><span class="sxs-lookup"><span data-stu-id="78fa8-121">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="78fa8-122">Q # 作業和函數</span><span class="sxs-lookup"><span data-stu-id="78fa8-122">Q# operations and functions</span></span>

<span data-ttu-id="78fa8-123">具體而言，Q # 程式是由*作業*、*函數*和任何使用者定義型別所組成。</span><span class="sxs-lookup"><span data-stu-id="78fa8-123">Concretely, a Q# program is comprised of *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="78fa8-124">作業是用來描述量子系統的轉換，而且是 Q # 程式的最基本建立區塊。</span><span class="sxs-lookup"><span data-stu-id="78fa8-124">Operations are used to describe the transformations of quantum systems and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="78fa8-125">在 Q # 中定義的每個作業，都可以呼叫任何數目的其他作業。</span><span class="sxs-lookup"><span data-stu-id="78fa8-125">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="78fa8-126">相對於作業，函數是用來描述純粹具*決定性*的傳統行為，而且除了計算傳統值以外，也不會有任何影響。</span><span class="sxs-lookup"><span data-stu-id="78fa8-126">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="78fa8-127">例如，假設我們想要測量程式結尾的 qubits，並將量測結果新增至陣列。</span><span class="sxs-lookup"><span data-stu-id="78fa8-127">For example, suppose we would like to measure our qubits at the end of a program, and add the measurement results to an array.</span></span>
<span data-ttu-id="78fa8-128">在此情況下，這項作業會 `Measure` 指示目的電腦對（real 或模擬） qubits 執行測量，而將傳回的結果新增至陣列的傳統程式將由函式處理。 *operation* *functions*</span><span class="sxs-lookup"><span data-stu-id="78fa8-128">In this case `Measure` is an *operation* which instructs the target machine to perform a measurement on the (real or simulated) qubits, and the classical process of adding the returned results to an array will be handled by *functions*.</span></span>

<span data-ttu-id="78fa8-129">作業和函式統稱為*callables*，且其基礎結構和行為會引進于[Q # 頁面中的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式。</span><span class="sxs-lookup"><span data-stu-id="78fa8-129">Together, operations and functions are referred to as *callables*, and their underlying structure and behavior is introduced on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) page.</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="78fa8-130">Q # 語法總覽</span><span class="sxs-lookup"><span data-stu-id="78fa8-130">Q# syntax overview</span></span>

<span data-ttu-id="78fa8-131">語言的語法描述形成語法正確程式的不同符號組合。</span><span class="sxs-lookup"><span data-stu-id="78fa8-131">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="78fa8-132">在 Q # 中，我們可以在三個不同的群組中，將其語法的元素分類：類型、運算式和語句。</span><span class="sxs-lookup"><span data-stu-id="78fa8-132">In Q# we can classify the elements of its syntax in three different groups: types, expressions and statements.</span></span>

### <a name="types"></a><span data-ttu-id="78fa8-133">類型</span><span class="sxs-lookup"><span data-stu-id="78fa8-133">Types</span></span>
<span data-ttu-id="78fa8-134">問 # 是強型別語言，因此謹慎使用型別可以協助編譯器在編譯時期提供有關 Q # 程式的強式保證。</span><span class="sxs-lookup"><span data-stu-id="78fa8-134">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="78fa8-135">除了標準和量子特定的內建基本類型（例如 `Int` 、、 `Bool` `Qubit` 和 `Result` ）之外，Q # 還提供使用者定義型別的支援。</span><span class="sxs-lookup"><span data-stu-id="78fa8-135">In addition to standard and quantum-specific built-in primitive types (e.g. `Int`, `Bool`, `Qubit`, and `Result`), Q# provides support for user-defined types.</span></span>
<span data-ttu-id="78fa8-136">Q # 中的 [[類型](xref:microsoft.quantum.guide.types)] 頁面上會描述所有 Q # 的各種基本類型，以及陣列和元組類型的詳細資料，以及如何在 q # 檔案中定義新的類型。</span><span class="sxs-lookup"><span data-stu-id="78fa8-136">All of Q#'s various primitive types are described on the [Types in Q#](xref:microsoft.quantum.guide.types) page, along with details on array and tuple types, as well as how to define new types within a Q# file.</span></span>

### <a name="expressions"></a><span data-ttu-id="78fa8-137">運算式</span><span class="sxs-lookup"><span data-stu-id="78fa8-137">Expressions</span></span>
<span data-ttu-id="78fa8-138">程式設計語言中的運算式是一或多個常數、變數、運算子和函式的組合，程式語言會將其解讀並評估為特定值。</span><span class="sxs-lookup"><span data-stu-id="78fa8-138">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="78fa8-139">最簡單的說，針對語言中的每個型別，該型別的運算式可以是*常*值或系結至該型別之值的符號。</span><span class="sxs-lookup"><span data-stu-id="78fa8-139">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="78fa8-140">例如， `5` 是 `Int` 常值（也是類型的運算式 `Int` ），而且如果符號系結 `count` 至整數值 `5` ，則 `count` 也是整數運算式。</span><span class="sxs-lookup"><span data-stu-id="78fa8-140">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="78fa8-141">此外，運算式可以包含與特定運算子結合的其他運算式。</span><span class="sxs-lookup"><span data-stu-id="78fa8-141">Additionally, an expression can consist of other expressions combined with certain operators.</span></span>
<span data-ttu-id="78fa8-142">因此，評估為的另一個 `Int` 運算式範例 `5` 是 `2+3` 。</span><span class="sxs-lookup"><span data-stu-id="78fa8-142">Hence another example of an `Int` expression which evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="78fa8-143">問 # 頁面中的[類型運算式](xref:microsoft.quantum.guide.expressions)會詳細說明 q # 中類型的可能運算式，以及可以用來形成它們的相容運算子。</span><span class="sxs-lookup"><span data-stu-id="78fa8-143">The possible expressions of types in Q#, as well as the compatible operators that can be used to form them, are detailed on the [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) page.</span></span> 

### <a name="statements"></a><span data-ttu-id="78fa8-144">陳述式</span><span class="sxs-lookup"><span data-stu-id="78fa8-144">Statements</span></span> 
<span data-ttu-id="78fa8-145">語句是命令式程式設計語言的語法單位，表示要執行的一些動作。語句與語句中的運算式對比不會傳回結果，而且只會針對其副作用執行，而運算式一律會傳回結果，而且通常不會有副作用。</span><span class="sxs-lookup"><span data-stu-id="78fa8-145">A statement is a syntactic unit of an imperative programming language that expresses some action to be carried out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects, while expressions always return a result and often do not have side effects at all.</span></span>
<span data-ttu-id="78fa8-146">這項區別經常會以用語來觀察：評估運算式，而執行語句。</span><span class="sxs-lookup"><span data-stu-id="78fa8-146">This distinction is frequently observed in wording: an expression is evaluated, whereas a statement is executed.</span></span>

<span data-ttu-id="78fa8-147">問 # 中的一個非常基本的語句範例，就是將符號指派給運算式：</span><span class="sxs-lookup"><span data-stu-id="78fa8-147">A very basic example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="78fa8-148">稍微有趣的範例是 `for` 支援反復專案並包含*語句區塊*的語句。</span><span class="sxs-lookup"><span data-stu-id="78fa8-148">A slightly more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="78fa8-149">假設是系結至 qubits 暫存器的 `qubits` 符號（技術上的類型，也就是 `Qubit[]` 類型的陣列 `Qubit` ）。</span><span class="sxs-lookup"><span data-stu-id="78fa8-149">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, i.e. an array of `Qubit` types).</span></span> <span data-ttu-id="78fa8-150">結果為</span><span class="sxs-lookup"><span data-stu-id="78fa8-150">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="78fa8-151">這是一種語句，會逐一查看暫存器中的每個 qubit，在 `H` 每個上執行作業。</span><span class="sxs-lookup"><span data-stu-id="78fa8-151">is a statement which iterates over each qubit in the register, performing the `H` operation on each.</span></span> <span data-ttu-id="78fa8-152">請注意， `H(qubit);` 本身也是語句。</span><span class="sxs-lookup"><span data-stu-id="78fa8-152">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="78fa8-153">事實上，任何類型的呼叫運算式 `Unit` （不會傳回任何資訊的 callables）都可以當做語句使用。</span><span class="sxs-lookup"><span data-stu-id="78fa8-153">In fact, any call expression of type `Unit` (those callables that do not return any information) may be used as a statement.</span></span>
<span data-ttu-id="78fa8-154">這主要是在傳回的 qubits 上呼叫作業時使用， `Unit` 因為語句的目的是要修改隱含的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="78fa8-154">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="78fa8-155">運算式評估語句需要結尾的分號。</span><span class="sxs-lookup"><span data-stu-id="78fa8-155">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="78fa8-156">幾乎所有的 Q # 程式層面都是使用語句來建立的，因此沒有任何單一頁面可以包含與它們相關的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="78fa8-156">Nearly every aspect of a Q# program is built using statements, so no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="78fa8-157">不過，其詞法結構和格式會在 [ [q # 檔案結構](xref:microsoft.quantum.guide.filestructure)] 頁面、[符號系結指派] 和 [q [# 中的變數](xref:microsoft.quantum.guide.variables)範圍] 和 [控制流程] 迴圈（例如 `for` [q # 中的控制流程](xref:microsoft.quantum.guide.controlflow)）中說明。</span><span class="sxs-lookup"><span data-stu-id="78fa8-157">However, their lexical structure and formatting is described on the [Q# File Structure](xref:microsoft.quantum.guide.filestructure) page, symbol binding assignment and scope at [Variables in Q#](xref:microsoft.quantum.guide.variables), and control flow loops such as `for` at [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="78fa8-158">下一步</span><span class="sxs-lookup"><span data-stu-id="78fa8-158">Next steps</span></span>
<span data-ttu-id="78fa8-159">在本指南的其餘部分中，我們將示範如何使用 Q #，透過作業、函式和類型的基本構件來建立複雜的配量程式。</span><span class="sxs-lookup"><span data-stu-id="78fa8-159">Throughout the rest of this guide, we will show you how to use Q# to construct complex quantum programs through the basic building blocks of operations, functions, and types.</span></span>

<span data-ttu-id="78fa8-160">若要開始使用，您可以開始瞭解[問 # 中的類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="78fa8-160">To get started, you can start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="78fa8-161">如果您有興趣深入瞭解問 # 背後的基礎和動機，請查看[為何需要問 #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="78fa8-161">If you are interested in learning more about the foundations and motivation behind Q#, check out [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
