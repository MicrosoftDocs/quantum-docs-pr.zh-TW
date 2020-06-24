---
title: 對 Microsoft QDK 貢獻程式碼
description: 瞭解如何將範例和程式庫程式碼提供給 Microsoft Quantum Development Kit （QDK）。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274547"
---
# <a name="contributing-code"></a><span data-ttu-id="b0a98-103">提供程式碼</span><span class="sxs-lookup"><span data-stu-id="b0a98-103">Contributing Code</span></span>

<span data-ttu-id="b0a98-104">除了報告問題和改善檔外，將程式碼提供給量子開發工具組，是協助您的對等在「量副程式設計」小組中的直接方法。</span><span class="sxs-lookup"><span data-stu-id="b0a98-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="b0a98-105">藉由貢獻程式碼，您可以協助修正問題、提供新的範例、讓現有的程式庫更容易使用，甚至新增全新的功能。</span><span class="sxs-lookup"><span data-stu-id="b0a98-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="b0a98-106">在本指南中，我們將詳細說明我們在審查提取要求時所尋找的一些內容，以協助您的貢獻達到最佳效果。</span><span class="sxs-lookup"><span data-stu-id="b0a98-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="b0a98-107">我們所尋找的內容</span><span class="sxs-lookup"><span data-stu-id="b0a98-107">What We Look For</span></span>

<span data-ttu-id="b0a98-108">理想的程式碼貢獻是以「量子開發工具組」存放庫中的現有工作為基礎，以修正問題、擴充現有功能，或新增在存放庫範圍內的新功能。</span><span class="sxs-lookup"><span data-stu-id="b0a98-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="b0a98-109">當我們接受程式碼貢獻時，它會成為量子開發工具組本身的一部分，讓新功能的發行、維護和開發方式與其他的配量開發工具組相同。</span><span class="sxs-lookup"><span data-stu-id="b0a98-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="b0a98-110">因此，當投稿新增的功能經過妥善測試並記載時，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="b0a98-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="b0a98-111">單元測試</span><span class="sxs-lookup"><span data-stu-id="b0a98-111">Unit Tests</span></span>

<span data-ttu-id="b0a98-112">組成程式庫（例如 canon）的 Q # 函數、作業和使用者定義類型，會在[**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)存放庫的開發過程中自動進行測試。</span><span class="sxs-lookup"><span data-stu-id="b0a98-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="b0a98-113">例如，當新的提取要求開啟時，我們的[Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/)設定會檢查提取要求中的變更是否不會中斷任何與量副程式設計人員所相依的現有功能。</span><span class="sxs-lookup"><span data-stu-id="b0a98-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="b0a98-114">使用最新的 Q # 版本，單元測試是使用屬性來定義 `@Test("QuantumSimulator")` 。</span><span class="sxs-lookup"><span data-stu-id="b0a98-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="b0a98-115">引數可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"，或指定執行目標的任何完整限定名稱。</span><span class="sxs-lookup"><span data-stu-id="b0a98-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="b0a98-116">定義不同執行目標的數個屬性可能會附加至相同的可呼叫。</span><span class="sxs-lookup"><span data-stu-id="b0a98-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="b0a98-117">我們的一些測試仍會使用已被取代的[Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/)套件，它會公開所有的 Q # 函式和所有以 `Test` [Xunit](https://xunit.github.io/) framework 結尾的作業。</span><span class="sxs-lookup"><span data-stu-id="b0a98-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="b0a98-118">定義單元測試不再需要此封裝。</span><span class="sxs-lookup"><span data-stu-id="b0a98-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="b0a98-119">下列函數是用來確保和函式 <xref:microsoft.quantum.canon.fst> <xref:microsoft.quantum.canon.snd> 都在代表性範例中傳回正確的輸出。</span><span class="sxs-lookup"><span data-stu-id="b0a98-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="b0a98-120">如果或的輸出 `Fst` `Snd` 不正確，則會 `fail` 使用語句來使測試失敗。</span><span class="sxs-lookup"><span data-stu-id="b0a98-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="b0a98-121">使用標準程式庫指南的[測試一節](xref:microsoft.quantum.libraries.diagnostics)中的技術，可以檢查更複雜的條件。</span><span class="sxs-lookup"><span data-stu-id="b0a98-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="b0a98-122">例如，下列測試會檢查所呼叫的是否與 `H(q); X(q); H(q);` <xref:microsoft.quantum.canon.applywith> 相同 `Z(q)` 。</span><span class="sxs-lookup"><span data-stu-id="b0a98-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="b0a98-123">新增新功能時，最好也加入新的測試，以確保您的投稿會執行其所需的工作。</span><span class="sxs-lookup"><span data-stu-id="b0a98-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="b0a98-124">這可協助其餘的社區維護和開發您的功能，特別是協助其他開發人員瞭解他們可以依賴您的功能。</span><span class="sxs-lookup"><span data-stu-id="b0a98-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="b0a98-125">這也是以另一種方式運作！</span><span class="sxs-lookup"><span data-stu-id="b0a98-125">This works the other way around, too!</span></span>
> <span data-ttu-id="b0a98-126">如果現有的功能遺失某些測試，協助我們新增測試涵蓋範圍會對該社區產生絕佳的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b0a98-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="b0a98-127">在本機上，可以使用 Visual Studio Test Explorer 或命令來執行單元測試 `dotnet test` ，讓您可以在開啟提取要求之前，先檢查您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b0a98-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="b0a98-128">當我們拒絕提取要求時</span><span class="sxs-lookup"><span data-stu-id="b0a98-128">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="b0a98-129">有時候，我們會拒絕投稿的提取要求。</span><span class="sxs-lookup"><span data-stu-id="b0a98-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="b0a98-130">如果您發生這種情況，這並不表示它是壞的，因為我們可能會因為許多原因而無法接受特定的投稿。</span><span class="sxs-lookup"><span data-stu-id="b0a98-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="b0a98-131">最常見的情況是，配量程式設計小組的貢獻是一個很好的工具，但是量子開發工具組存放庫並不是開發的正確位置。</span><span class="sxs-lookup"><span data-stu-id="b0a98-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="b0a98-132">在這種情況下，我們強烈建議您讓自己的存放庫---配量開發工具組的優勢之一，那就是使用 GitHub 和 NuGet.org 輕鬆地建立和散佈您自己的程式庫，這與我們目前散發 canon 和化學程式庫的方式相同。</span><span class="sxs-lookup"><span data-stu-id="b0a98-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="b0a98-133">在其他時候，我們可能會因為尚未準備維護和開發，而拒絕良好的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b0a98-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="b0a98-134">這麼做可能很難以完成所有作業，因此我們計畫最能以藍圖的形式來處理的功能。</span><span class="sxs-lookup"><span data-stu-id="b0a98-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="b0a98-135">這可能是另一種將功能當做協力廠商程式庫發行的情況，可能會有很大的意義。</span><span class="sxs-lookup"><span data-stu-id="b0a98-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="b0a98-136">或者，我們可能會要求您協助修改某項功能，使其更符合我們的藍圖，讓我們可以執行最佳的工作。</span><span class="sxs-lookup"><span data-stu-id="b0a98-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="b0a98-137">如果提取要求有更多的檔或單元測試可協助我們使用它，或者它的樣式與問 # 程式庫的其餘部分有足夠的風格，讓使用者更難以找到您的功能，我們也會要求您變更要求。</span><span class="sxs-lookup"><span data-stu-id="b0a98-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="b0a98-138">在這些情況下，我們會嘗試在程式碼審查中提供一些建議，告訴您可以新增或變更哪些專案，讓我們更容易納入您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b0a98-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="b0a98-139">最後，我們無法接受造成損害「量子計算」的貢獻，如[Microsoft 開放原始碼](https://opensource.microsoft.com/codeofconduct/)管理辦法中所述。</span><span class="sxs-lookup"><span data-stu-id="b0a98-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="b0a98-140">我們想要確保貢獻的是整個量子運算的群體，在其目前的絕佳多樣性中，而且未來隨著成長而變得更具其成果。</span><span class="sxs-lookup"><span data-stu-id="b0a98-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="b0a98-141">我們非常感謝您實現此目標的協助。</span><span class="sxs-lookup"><span data-stu-id="b0a98-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0a98-142">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b0a98-142">Next steps</span></span>

<span data-ttu-id="b0a98-143">感謝您協助讓量子開發工具組成為整個量副程式設計小組的絕佳資源！</span><span class="sxs-lookup"><span data-stu-id="b0a98-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="b0a98-144">若要深入瞭解，請繼續進行 Q # 樣式的下列指南。</span><span class="sxs-lookup"><span data-stu-id="b0a98-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b0a98-145">瞭解問 # 樣式指導方針</span><span class="sxs-lookup"><span data-stu-id="b0a98-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="b0a98-146">根據您所貢獻的程式碼類型而定，您可能需要記住其他事項，以協助您讓您的貢獻盡可能符合社區的最大目的。</span><span class="sxs-lookup"><span data-stu-id="b0a98-146">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b0a98-147">瞭解參與範例</span><span class="sxs-lookup"><span data-stu-id="b0a98-147">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
