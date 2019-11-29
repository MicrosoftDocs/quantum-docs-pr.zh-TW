---
title: 量子開發技術簡介 |Microsoft Docs
description: 量子開發技術簡介
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442561"
---
# <a name="q-program-overview"></a><span data-ttu-id="f4183-103">Q# 程式概觀</span><span class="sxs-lookup"><span data-stu-id="f4183-103">Q# program overview</span></span>

<span data-ttu-id="f4183-104">問 # 是一種可調整、多架構的領域專屬程式設計語言，適用于量子運算。</span><span class="sxs-lookup"><span data-stu-id="f4183-104">Q# is a scalable, multi-paradigm, domain-specific programming language for quantum computing.</span></span> <span data-ttu-id="f4183-105">問 # 是一種量副程式設計語言，它可以用來描述如何在量子機器上執行指令。</span><span class="sxs-lookup"><span data-stu-id="f4183-105">Q# is a quantum programming language in that it can be used to describe how instructions are executed on quantum machines.</span></span> <span data-ttu-id="f4183-106">可設為目標的電腦範圍從模擬器到實際的量子硬體。</span><span class="sxs-lookup"><span data-stu-id="f4183-106">The machines that can be targeted range from simulators to actual quantum hardware.</span></span> <span data-ttu-id="f4183-107">問 # 是可擴充的：它可以用來撰寫簡單的示範程式，像是在幾個 qubits 上執行的「傳送」，但也支援撰寫大型、複雜的程式，例如模擬複雜的分子驅使分子，這會需要含有數百萬 qubits 的大型機器。</span><span class="sxs-lookup"><span data-stu-id="f4183-107">Q# is scalable: it can be used to write simple demonstration programs like teleport that run on a few qubits, but also supports writing large, sophisticated programs such as simulations of complex molecules that will require large machines with millions of qubits.</span></span> <span data-ttu-id="f4183-108">雖然大型實體機器仍在未來，但問 # 可讓程式設計人員立即設計複雜的量子演算法。</span><span class="sxs-lookup"><span data-stu-id="f4183-108">Even though large physical machines are still in the future, Q# allows a programmer to program complex quantum algorithms now.</span></span> <span data-ttu-id="f4183-109">什麼是更多，Q # 支援以可擴充的方式進行各種工作，例如，偵錯工具、分析、資源估計和特定特殊用途的模擬。</span><span class="sxs-lookup"><span data-stu-id="f4183-109">What is more, Q# supports various tasks such as debugging, profiling, resource estimation, and certain special-purpose simulations in a scalable way.</span></span> 

<span data-ttu-id="f4183-110">從技術觀點來看，配量程式可視為一組特定的傳統函式，當呼叫這些函式時，會產生量子線路作為其副作用。</span><span class="sxs-lookup"><span data-stu-id="f4183-110">From a technical perspective, a quantum program can be seen as a particular set of classical functions which, when called, generate quantum circuits as their side effects.</span></span> <span data-ttu-id="f4183-111">該觀點的重要結果是，以 Q # 撰寫的程式並不會直接 qubits 本身的模型，而是說明傳統的控制項電腦與這些 qubits 的互動方式。</span><span class="sxs-lookup"><span data-stu-id="f4183-111">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="f4183-112">根據設計，Q # 因此不會直接定義配量狀態或其他量子機制的屬性，而是間接透過語言中所定義之各種副程式的動作來進行。</span><span class="sxs-lookup"><span data-stu-id="f4183-112">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly, but rather does so indirectly through the action of the various subroutines defined in the language.</span></span>
<span data-ttu-id="f4183-113">例如，請考慮 >量子計算概念指南》中所討論的狀態 $ \ket{+} = \left （\ket{0} + \ket{1}\right）/\sqrt{2}$。[](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="f4183-113">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="f4183-114">若要在 Q # 中準備此狀態，我們會使用 qubits 在 $ \ket{0}$ state 中初始化的事實，以及 $ \ket{+} = H\ket{0}$，其中 $H $ 是 Hadamard 轉換：</span><span class="sxs-lookup"><span data-stu-id="f4183-114">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a><span data-ttu-id="f4183-115">Tranformations 量子狀態的 Q #</span><span class="sxs-lookup"><span data-stu-id="f4183-115">Q# tranformations of quantum states</span></span>

<span data-ttu-id="f4183-116">重要的是，在撰寫上述程式時，我們並未明確參考 Q # 內的狀態，而是說明我們的程式如何*轉換*狀態。</span><span class="sxs-lookup"><span data-stu-id="f4183-116">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="f4183-117">因此，類似于圖形著色器程式如何為每個頂點累積轉換的描述，Q # 中的量副程式會累積轉換成配量狀態。</span><span class="sxs-lookup"><span data-stu-id="f4183-117">Thus, similar to how a graphics shader program accumulates a description of transformations to each vertex, a quantum program in Q# accumulates transformations to quantum states.</span></span>
<span data-ttu-id="f4183-118">這可讓我們完全無從得知每個目的電腦上的量子狀態為何，這*可能會有*不同的解讀，視電腦而定。</span><span class="sxs-lookup"><span data-stu-id="f4183-118">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="f4183-119">從 Q # 程式的角度來看，qubit 是對目的電腦內部結構的完全不透明參考。</span><span class="sxs-lookup"><span data-stu-id="f4183-119">From the perspective of a Q# program, a qubit is an entirely opaque reference to the internal structure of a target machine.</span></span>
<span data-ttu-id="f4183-120">Q # 程式無法 introspect 至 qubit 的狀態、其在目的電腦上的標記法，或甚至是與任何其他可供程式使用的 qubit 相同的 qubit。</span><span class="sxs-lookup"><span data-stu-id="f4183-120">A Q# program has no ability to introspect into the state of a qubit, its representation on a target machine, or even whether it is the same qubit as any other qubit available to the program.</span></span>
<span data-ttu-id="f4183-121">相反地，程式可以呼叫 `Measure` 之類的作業來從 qubit 中學習資訊，以及呼叫 `X` 和 `H` 等作業來處理 qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="f4183-121">Rather, a program can call operations such as `Measure` to learn information from a qubit, and call operations such as `X` and `H` to act on the state of a qubit.</span></span>
<span data-ttu-id="f4183-122">這些作業在此語言中沒有內建定義，而且只有用來執行特定 Q # 程式的目的電腦才有具體設定。</span><span class="sxs-lookup"><span data-stu-id="f4183-122">These operations have no intrinsic definition within the language, and are made concrete only by the target machine used to run a particular Q# program.</span></span>
<span data-ttu-id="f4183-123">Q # 程式會依照目的電腦的定義來 recombines 這些作業，以建立更高層級的新作業來表示量子計算。</span><span class="sxs-lookup"><span data-stu-id="f4183-123">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="f4183-124">如此一來，Q # 可讓您輕鬆地表達基礎配量和混合式量子-傳統演算法的邏輯，同時也會與目的機器或模擬器的結構有關。</span><span class="sxs-lookup"><span data-stu-id="f4183-124">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum-classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="f4183-125">Q # 作業和函數</span><span class="sxs-lookup"><span data-stu-id="f4183-125">Q# operations and functions</span></span>

<span data-ttu-id="f4183-126">具體而言，Q # 程式是由一或多個*作業*、一個或多個函*式，以及*使用者定義型別所組成。</span><span class="sxs-lookup"><span data-stu-id="f4183-126">Concretely, a Q# program is comprised of one or more *operations*, one or more *functions*, and user defined types.</span></span> <span data-ttu-id="f4183-127">作業是用來描述量子機器狀態的轉換，而且是 Q # 程式最基本的建立區塊。</span><span class="sxs-lookup"><span data-stu-id="f4183-127">Operations are used to describe the transformations of the state of a quantum machine and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="f4183-128">在 Q # 中定義的每個作業都可以呼叫任何數目的其他作業，包括目的電腦所執行的內建*內建函式*作業。</span><span class="sxs-lookup"><span data-stu-id="f4183-128">Each operation defined in Q# may then call any number of other operations, including the built-in *intrinsic* operations implemented by a target machine.</span></span>
<span data-ttu-id="f4183-129">在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。</span><span class="sxs-lookup"><span data-stu-id="f4183-129">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="f4183-130">相對於作業，函數是用來描述純粹的傳統行為，而且除了計算傳統輸出值之外，也不會有任何影響。</span><span class="sxs-lookup"><span data-stu-id="f4183-130">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span> <span data-ttu-id="f4183-131">問 # 是強型別語言，並隨附一組內建的基本型別，以及使用者定義型別的支援。</span><span class="sxs-lookup"><span data-stu-id="f4183-131">Q# is a strongly typed language and comes with a set of built-in primitive types as well as support for user defined types.</span></span> 

<span data-ttu-id="f4183-132">在本指南的其餘部分中，我們將瞭解如何使用不同的語言概念和結構，以協助我們透過作業、函式和類型的基本構件來定義複雜的配量程式。</span><span class="sxs-lookup"><span data-stu-id="f4183-132">Throughout the rest of this guide, we will see how to use different language concepts and constructs to help us define complex quantum programs through the basic building blocks of operations, functions, and types.</span></span> 

## <a name="structure-of-q-source-files"></a><span data-ttu-id="f4183-133">Q # 來源檔案的結構</span><span class="sxs-lookup"><span data-stu-id="f4183-133">Structure of Q# Source Files</span></span>

<span data-ttu-id="f4183-134">問 # 來源檔案至少包含*命名空間*宣告，此宣告會指定 .net 命名空間，其中包含來源檔案中的定義。</span><span class="sxs-lookup"><span data-stu-id="f4183-134">Minimally, a Q# source file consists of a *namespace declaration*, which specifies a .NET namespace which will contain the definitions in the source file.</span></span>
<span data-ttu-id="f4183-135">您可以使用 `open` 語句，來包含來自其他 Q # 來源檔案和程式庫的定義。</span><span class="sxs-lookup"><span data-stu-id="f4183-135">Definitions from other Q# source files and libraries can be included using the `open` statement.</span></span>
<span data-ttu-id="f4183-136">例如，定義基本閘道的大部分作業都是在 <xref:microsoft.quantum.intrinsic> 命名空間中定義。</span><span class="sxs-lookup"><span data-stu-id="f4183-136">For instance, most of the operations defining fundamental gates are defined in the <xref:microsoft.quantum.intrinsic> namespace.</span></span>
<span data-ttu-id="f4183-137">為了讓程式碼能夠使用這項功能，我們只要在每個檔案的頂端 `open` 該命名空間：</span><span class="sxs-lookup"><span data-stu-id="f4183-137">To make this available to our code, we simply `open` that namespace at the top of each file:</span></span>

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

<span data-ttu-id="f4183-138">在命名空間中，每個 Q # 來源檔案都可以定義*作業*、*函式*和*使用者定義類型*的任何組合。</span><span class="sxs-lookup"><span data-stu-id="f4183-138">Within a namespace, each Q# source file can define any combination of *operations*, *functions*, and *user-defined types*.</span></span>
<span data-ttu-id="f4183-139">在本節的其餘部分，我們將逐一說明每個專案，並提供如何在實務中使用它們來建立有用的量副程式的範例。</span><span class="sxs-lookup"><span data-stu-id="f4183-139">In the rest of this section, we will describe each in turn and provide examples of how they can be used in practice to make useful quantum programs.</span></span>
