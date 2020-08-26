---
title: 在量子開發工具組中執行格羅弗的搜尋演算法 Q#
description: 建立一個 Q# 專案，以示範格羅弗的演算法，也就是其中一個標準量子演算法。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: f2ae56bdca893e8a317c16d0a993da15b9f021b5
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863112"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="d276d-103">教學課程：以 Q\# 執行格羅弗搜尋演算法</span><span class="sxs-lookup"><span data-stu-id="d276d-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="d276d-104">在本教學課程中，您可以了解如何建立及執行格羅弗搜尋，以加速搜尋非結構化資料。</span><span class="sxs-lookup"><span data-stu-id="d276d-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="d276d-105">格羅弗的搜尋是最受歡迎的量子運算演算法之一，而這種相對較小的 Q# 實，讓您瞭解使用高階 Q# 量副程式設計語言來表達量子演算法的程式設計量子解決方案的一些優點。</span><span class="sxs-lookup"><span data-stu-id="d276d-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="d276d-106">在本指南最後，您會看到模擬輸出示範了如何在有序項目清單中成功地搜尋特定字串，且花費的時間比古典電腦搜尋所需的少了許多。</span><span class="sxs-lookup"><span data-stu-id="d276d-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="d276d-107">格羅弗演算法會搜尋特定項目的非結構化資料清單。</span><span class="sxs-lookup"><span data-stu-id="d276d-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="d276d-108">例如，它可以回答問題：從一副牌中抽出的這張牌是紅心 A 嗎？</span><span class="sxs-lookup"><span data-stu-id="d276d-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="d276d-109">為特定項目的加上標籤，稱為_標記輸入_。</span><span class="sxs-lookup"><span data-stu-id="d276d-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="d276d-110">使用格羅弗搜尋演算法，可保證量子電腦在執行此搜尋時所使用的步驟必定會比您搜尋清單中的項目數少 — 這是任何傳統演算法都做不到的。</span><span class="sxs-lookup"><span data-stu-id="d276d-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="d276d-111">以一副牌的案例來說，增加的速度並不多；但清單中若包含數百萬或數十億個項目，就會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="d276d-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="d276d-112">只要幾行程式碼，您就可以建置格羅弗搜尋演算法。</span><span class="sxs-lookup"><span data-stu-id="d276d-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d276d-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="d276d-113">Prerequisites</span></span>

- <span data-ttu-id="d276d-114">Microsoft [Quantum Development Kit][install]。</span><span class="sxs-lookup"><span data-stu-id="d276d-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="d276d-115">格羅弗搜尋演算法有哪些功能？</span><span class="sxs-lookup"><span data-stu-id="d276d-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="d276d-116">格羅弗演算法會詢問清單中的某個項目是否為我們要搜尋的項目。</span><span class="sxs-lookup"><span data-stu-id="d276d-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="d276d-117">其運作方式是，建構清單索引的量子疊加，並以每個係數 (或機率振幅) 代表該索引就是您要尋找之索引的機率。</span><span class="sxs-lookup"><span data-stu-id="d276d-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="d276d-118">此演算法的核心是兩個步驟，會以累加方式提高我們所尋找之索引的係數，直到該係數的機率振幅趨近於一。</span><span class="sxs-lookup"><span data-stu-id="d276d-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="d276d-119">遞增的數值會低於清單中的項目數。</span><span class="sxs-lookup"><span data-stu-id="d276d-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="d276d-120">正因如此，格羅弗搜尋演算法才能以比任何傳統演算法更少的步驟來執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="d276d-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![格羅弗搜尋演算法的功能圖表](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="d276d-122">撰寫程式碼</span><span class="sxs-lookup"><span data-stu-id="d276d-122">Write the code</span></span>

1. <span data-ttu-id="d276d-123">使用量子開發工具組， [ Q# 為應用程式建立新專案](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="d276d-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="d276d-124">將專案標題命名為 `Grover`。</span><span class="sxs-lookup"><span data-stu-id="d276d-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="d276d-125">將下列程式碼新增至新專案中的 `Program.qs` 檔案：</span><span class="sxs-lookup"><span data-stu-id="d276d-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="d276d-126">若要定義我們要搜尋的清單，請建立新檔案 `Reflections.qs`，並貼到下列程式碼中：</span><span class="sxs-lookup"><span data-stu-id="d276d-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="d276d-127">`ReflectAboutMarked` 作業會定義您要搜尋的標記輸入：替代零和一的字串。</span><span class="sxs-lookup"><span data-stu-id="d276d-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="d276d-128">此範例會進行標記輸入的硬式編碼，並且可進行擴充以搜尋不同的輸入，或進行一般化以搜尋任何輸入。</span><span class="sxs-lookup"><span data-stu-id="d276d-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="d276d-129">接下來，執行您 Q# 的新程式來尋找標示為的專案 `ReflectAboutMarked` 。</span><span class="sxs-lookup"><span data-stu-id="d276d-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="d276d-130">Q# Visual Studio 或 Visual Studio Code 的應用程式</span><span class="sxs-lookup"><span data-stu-id="d276d-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="d276d-131">視專案設定和命令列選項而定，可執行檔將會在模擬器或資源估計工具上執行標記為 `@EntryPoint()` 屬性的作業或函式。</span><span class="sxs-lookup"><span data-stu-id="d276d-131">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="d276d-132">在 Visual Studio 中，只要按 Ctrl + F5 執行指令碼即可。</span><span class="sxs-lookup"><span data-stu-id="d276d-132">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="d276d-133">在 VS Code 中，透過在終端機中輸入下列命令，以第一次建立 `Program.qs`：</span><span class="sxs-lookup"><span data-stu-id="d276d-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="d276d-134">在後續的執行中，不需要重新建立。</span><span class="sxs-lookup"><span data-stu-id="d276d-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="d276d-135">若要執行，請輸入下列命令並按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="d276d-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="d276d-136">您應該會看到顯示在終端機中的下列訊息：</span><span class="sxs-lookup"><span data-stu-id="d276d-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="d276d-137">這是因為您未指定想要使用的 qubits 數目，所以終端機會告訴您可執行檔的命令。</span><span class="sxs-lookup"><span data-stu-id="d276d-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal tells you the commands available for the executable.</span></span> <span data-ttu-id="d276d-138">如果我們想要使用 5 個 qubits，則我們應該輸入：</span><span class="sxs-lookup"><span data-stu-id="d276d-138">If we want to use 5 qubits we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="d276d-139">按 Enter 後您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="d276d-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="d276d-140">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d276d-140">Next steps</span></span>

<span data-ttu-id="d276d-141">如果您喜歡本教學課程，請參閱下列資源以深入瞭解如何使用 Q# 來撰寫您自己的量子應用程式：</span><span class="sxs-lookup"><span data-stu-id="d276d-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="d276d-142">回到 QDK 使用者入門指南</span><span class="sxs-lookup"><span data-stu-id="d276d-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="d276d-143">試用較一般的格羅弗搜尋演算法[範例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span><span class="sxs-lookup"><span data-stu-id="d276d-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="d276d-144">深入瞭解格羅弗搜尋與 Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="d276d-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="d276d-145">深入瞭解[振幅放大][amplitude-amplification]，格羅弗搜尋演算法背後的量子運算技術</span><span class="sxs-lookup"><span data-stu-id="d276d-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="d276d-146">量子運算概念</span><span class="sxs-lookup"><span data-stu-id="d276d-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="d276d-147">Quantum Development Kit 範例</span><span class="sxs-lookup"><span data-stu-id="d276d-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
