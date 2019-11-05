---
title: 以 Q# 執行格羅弗搜尋演算法 - Quantum Development Kit
description: 建置一個 Q# 專案以示範格羅弗演算法，此為標準量子演算法之一。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443931"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="84875-103">快速入門：以 Q# 執行格羅弗搜尋演算法</span><span class="sxs-lookup"><span data-stu-id="84875-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="84875-104">在本快速入門中，您可以瞭解如何建立及執行格羅弗搜尋，以加速搜尋非結構化資料。</span><span class="sxs-lookup"><span data-stu-id="84875-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="84875-105">格羅弗搜尋是最受歡迎的量子運算演算法之一，而這個相對小型的 Q# 實作，可讓您使用高階的 Q# 量子程式設計語言來表達量子運算法，瞭解量子解決方案程式設計的一些優點。</span><span class="sxs-lookup"><span data-stu-id="84875-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="84875-106">在本指南最後，您會看到模擬輸出示範了如何在有序項目清單中成功地搜尋特定字串，且花費的時間比古典電腦搜尋所需的少了許多。</span><span class="sxs-lookup"><span data-stu-id="84875-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="84875-107">格羅弗演算法會搜尋特定項目的非結構化資料清單。</span><span class="sxs-lookup"><span data-stu-id="84875-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="84875-108">例如，它可以回答問題：從一副牌中抽出的這張牌是紅心 A 嗎？</span><span class="sxs-lookup"><span data-stu-id="84875-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="84875-109">為特定項目的加上標籤，稱為_標記輸入_。</span><span class="sxs-lookup"><span data-stu-id="84875-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="84875-110">使用格羅弗搜尋演算法，可保證量子電腦在執行此搜尋時所使用的步驟必定會比您搜尋清單中的項目數少 — 這是任何傳統演算法都做不到的。</span><span class="sxs-lookup"><span data-stu-id="84875-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="84875-111">以一副牌的案例來說，增加的速度並不多；但清單中若包含數百萬或數十億個項目，就會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="84875-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="84875-112">只要幾行程式碼，您就可以建置格羅弗搜尋演算法。</span><span class="sxs-lookup"><span data-stu-id="84875-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84875-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="84875-113">Prerequisites</span></span>

- <span data-ttu-id="84875-114">Microsoft [Quantum Development Kit][install]。</span><span class="sxs-lookup"><span data-stu-id="84875-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="84875-115">格羅弗搜尋演算法有哪些功能？</span><span class="sxs-lookup"><span data-stu-id="84875-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="84875-116">格羅弗演算法會詢問清單中的某個項目是否為我們要搜尋的項目。</span><span class="sxs-lookup"><span data-stu-id="84875-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="84875-117">其運作方式是，建構清單索引的量子疊加，並以每個係數 (或機率振幅) 代表該索引就是您要尋找之索引的機率。</span><span class="sxs-lookup"><span data-stu-id="84875-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="84875-118">此演算法的核心是兩個步驟，會以累加方式提高我們所尋找之索引的係數，直到該係數的機率振幅趨近於一。</span><span class="sxs-lookup"><span data-stu-id="84875-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="84875-119">遞增的數值會低於清單中的項目數。</span><span class="sxs-lookup"><span data-stu-id="84875-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="84875-120">正因如此，格羅弗搜尋演算法才能以比任何傳統演算法更少的步驟來執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="84875-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![格羅弗搜尋演算法的功能圖表](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="84875-122">撰寫程式碼</span><span class="sxs-lookup"><span data-stu-id="84875-122">Write the code</span></span>

1. <span data-ttu-id="84875-123">使用 Quantum Development Kit，在您選擇的開發環境中[建立新的 Q# 專案](xref:microsoft.quantum.howto.createproject) (名為 `Grover`)。</span><span class="sxs-lookup"><span data-stu-id="84875-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="84875-124">將下列程式碼新增至新專案中的 `Operations.qs` 檔案：</span><span class="sxs-lookup"><span data-stu-id="84875-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="84875-125">若要定義我們要搜尋的清單，請建立新檔案 `Reflections.qs`，並貼到下列程式碼中：</span><span class="sxs-lookup"><span data-stu-id="84875-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="84875-126">`ReflectAboutMarked` 作業會定義您要搜尋的標記輸入：替代零和一的字串。</span><span class="sxs-lookup"><span data-stu-id="84875-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="84875-127">此範例會進行標記輸入的硬式編碼，並且可進行擴充以搜尋不同的輸入，或進行一般化以搜尋任何輸入。</span><span class="sxs-lookup"><span data-stu-id="84875-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="84875-128">接著，執行新的 Q# 程式以尋找 `ReflectAboutMarked` 所標示的項目。</span><span class="sxs-lookup"><span data-stu-id="84875-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="84875-129">使用 Visual Studio Code 或命令列的 Python</span><span class="sxs-lookup"><span data-stu-id="84875-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="84875-130">若要從 Python 執行新的 Q# 程式，請將下列程式碼儲存為 `host.py`：</span><span class="sxs-lookup"><span data-stu-id="84875-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="84875-131">然後，您可以從命令列執行 Python 主機程式：</span><span class="sxs-lookup"><span data-stu-id="84875-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="84875-132">使用 Visual Studio Code 或命令列的 C#</span><span class="sxs-lookup"><span data-stu-id="84875-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="84875-133">若要從 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：</span><span class="sxs-lookup"><span data-stu-id="84875-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="84875-134">然後，您可以從命令列執行 C# 主機程式：</span><span class="sxs-lookup"><span data-stu-id="84875-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="84875-135">使用 Visual Studio 2019 的 C#</span><span class="sxs-lookup"><span data-stu-id="84875-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="84875-136">若要從 Visual Studio 中的 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：</span><span class="sxs-lookup"><span data-stu-id="84875-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="84875-137">然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示下列結果：</span><span class="sxs-lookup"><span data-stu-id="84875-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="84875-138">`ReflectAboutMarked` 作業僅呼叫了四次，但您的 Q# 程式就能從 $2^{5} = 32$ 個可能的輸入中找出 "01010" 輸入！</span><span class="sxs-lookup"><span data-stu-id="84875-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="84875-139">後續步驟</span><span class="sxs-lookup"><span data-stu-id="84875-139">Next steps</span></span>

<span data-ttu-id="84875-140">如果您喜歡本快速入門，請參閱下列一些資源，以深入了解如何使用 Q# 撰寫您自己的量子應用程式：</span><span class="sxs-lookup"><span data-stu-id="84875-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="84875-141">回到 QDK 使用者入門指南</span><span class="sxs-lookup"><span data-stu-id="84875-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="84875-142">試用較一般的格羅弗搜尋演算法[範例](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span><span class="sxs-lookup"><span data-stu-id="84875-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="84875-143">深入瞭解格羅弗搜尋與 Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="84875-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="84875-144">深入瞭解[振幅放大](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification)，格羅弗搜尋演算法背後的量子運算技術</span><span class="sxs-lookup"><span data-stu-id="84875-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="84875-145">量子運算概念</span><span class="sxs-lookup"><span data-stu-id="84875-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="84875-146">Quantum Development Kit 範例</span><span class="sxs-lookup"><span data-stu-id="84875-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
