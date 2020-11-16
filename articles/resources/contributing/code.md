---
title: 參與 Microsoft QDK 的程式碼
description: 瞭解如何將範例和程式庫程式碼提供給 Microsoft 量子開發工具組 (QDK) 。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 47845c4f3520e8c50cf8aefd9bf9e8f086c42842
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691795"
---
# <a name="contributing-code"></a><span data-ttu-id="93cd8-103">提供程式碼</span><span class="sxs-lookup"><span data-stu-id="93cd8-103">Contributing Code</span></span>

<span data-ttu-id="93cd8-104">除了回報問題和改進檔之外，將程式碼提供給量子開發工具組，也是協助您參與量副程式設計團體的直接方式。</span><span class="sxs-lookup"><span data-stu-id="93cd8-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="93cd8-105">藉由貢獻程式碼，您可以協助修正問題、提供新的範例、讓現有的程式庫更容易使用，或甚至新增全新的功能。</span><span class="sxs-lookup"><span data-stu-id="93cd8-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="93cd8-106">在本指南中，我們將詳細說明我們在審視提取要求時所要尋找的內容，以協助您的投稿最妥善。</span><span class="sxs-lookup"><span data-stu-id="93cd8-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="93cd8-107">我們要尋找的內容</span><span class="sxs-lookup"><span data-stu-id="93cd8-107">What We Look For</span></span>

<span data-ttu-id="93cd8-108">理想的程式碼投稿建基於量子開發工具組存放庫中的現有工作，以修正問題、擴充現有的功能，或加入存放庫範圍內的新功能。</span><span class="sxs-lookup"><span data-stu-id="93cd8-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="93cd8-109">當我們接受程式碼投稿時，它會成為量子開發工具組本身的一部分，因此會以與其他量子開發工具組相同的方式來發行、維護及開發新功能。</span><span class="sxs-lookup"><span data-stu-id="93cd8-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="93cd8-110">因此，當投稿加入的功能經過妥善測試並記載時，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="93cd8-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="93cd8-111">單元測試</span><span class="sxs-lookup"><span data-stu-id="93cd8-111">Unit Tests</span></span>

<span data-ttu-id="93cd8-112">Q#組成程式庫（例如 canon）的函式、作業和使用者定義類型，會在 [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)儲存機制的開發過程中自動進行測試。</span><span class="sxs-lookup"><span data-stu-id="93cd8-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="93cd8-113">比方說，當新的提取要求開啟時，我們的 [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) 設定會確認提取要求中的變更不會中斷任何與量副程式設計社區相依的現有功能。</span><span class="sxs-lookup"><span data-stu-id="93cd8-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="93cd8-114">使用最新 Q# 版本，單元測試是使用屬性來定義 `@Test("QuantumSimulator")` 。</span><span class="sxs-lookup"><span data-stu-id="93cd8-114">With the latest Q# version, unit tests are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="93cd8-115">引數可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator" 或任何指定執行目標的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="93cd8-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the run target.</span></span> <span data-ttu-id="93cd8-116">有幾個屬性定義不同的執行目標可以附加到相同的可呼叫。</span><span class="sxs-lookup"><span data-stu-id="93cd8-116">Several attributes defining different run targets may be attached to the same callable.</span></span> <span data-ttu-id="93cd8-117">有些測試仍使用已被取代的 [Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) 套件，此封裝會公開所有 Q# `Test` 以 [Xunit](https://xunit.github.io/) framework 結尾的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="93cd8-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="93cd8-118">您不再需要此套件來定義單元測試。</span><span class="sxs-lookup"><span data-stu-id="93cd8-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="93cd8-119">下列函式是用來確保和函 <xref:Microsoft.Quantum.Canon.Fst> 式 <xref:Microsoft.Quantum.Canon.Snd> 都在代表性範例中傳回正確的輸出。</span><span class="sxs-lookup"><span data-stu-id="93cd8-119">The following function is used to ensure that the <xref:Microsoft.Quantum.Canon.Fst> and <xref:Microsoft.Quantum.Canon.Snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="93cd8-120">如果或的輸出 `Fst` `Snd` 不正確， `fail` 語句會用來導致測試失敗。</span><span class="sxs-lookup"><span data-stu-id="93cd8-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

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

<span data-ttu-id="93cd8-121">您可以使用標準程式庫指南的 [測試一節](xref:microsoft.quantum.libraries.diagnostics) 中的技巧來檢查更複雜的條件。</span><span class="sxs-lookup"><span data-stu-id="93cd8-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="93cd8-122">例如，下列測試會檢查所呼叫的是否與 `H(q); X(q); H(q);` <xref:Microsoft.Quantum.Canon.ApplyWith> 相同 `Z(q)` 。</span><span class="sxs-lookup"><span data-stu-id="93cd8-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:Microsoft.Quantum.Canon.ApplyWith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="93cd8-123">新增新功能時，建議您也要加入新的測試，以確保您的投稿內容符合預期。</span><span class="sxs-lookup"><span data-stu-id="93cd8-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="93cd8-124">這可協助其他小組維護及開發您的功能，特別是協助其他開發人員瞭解他們可以依賴您的功能。</span><span class="sxs-lookup"><span data-stu-id="93cd8-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="93cd8-125">這也是另一種方式</span><span class="sxs-lookup"><span data-stu-id="93cd8-125">This works the other way around, too!</span></span>
> <span data-ttu-id="93cd8-126">如果有現有的功能遺失某些測試，請協助我們新增測試涵蓋範圍，對該社區有很大的貢獻。</span><span class="sxs-lookup"><span data-stu-id="93cd8-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="93cd8-127">在本機，您可以使用 Visual Studio Test Explorer 或命令來執行單元測試 `dotnet test` ，讓您可以在開啟提取要求之前檢查您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="93cd8-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a><span data-ttu-id="93cd8-128">提取要求</span><span class="sxs-lookup"><span data-stu-id="93cd8-128">Pull Requests</span></span>

<span data-ttu-id="93cd8-129">當您準備好要參與工作時，請透過 GitHub 將提取要求傳送至對應的存放庫。</span><span class="sxs-lookup"><span data-stu-id="93cd8-129">When you are ready to contribute your work, please send a Pull Request via GitHub to the corresponding repository.</span></span>
<span data-ttu-id="93cd8-130">小組將會審查並提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="93cd8-130">The team will review and provide feedback.</span></span> <span data-ttu-id="93cd8-131">所有批註都必須經過回答和解決，而且所有的檢查都必須在程式碼合併至分支之前傳遞 `main` 。</span><span class="sxs-lookup"><span data-stu-id="93cd8-131">All comments need to be answered and resolved and all checks need to pass before the code is merged to the `main` branch.</span></span>

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="93cd8-132">當我們拒絕提取要求時</span><span class="sxs-lookup"><span data-stu-id="93cd8-132">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="93cd8-133">有時候，我們會拒絕投稿的提取要求。</span><span class="sxs-lookup"><span data-stu-id="93cd8-133">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="93cd8-134">如果發生這種情況，這並不表示它不正確，因為有許多原因可能無法接受特定的投稿。</span><span class="sxs-lookup"><span data-stu-id="93cd8-134">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="93cd8-135">最常見的情況是，量副程式設計團體的投稿是不錯的工具，但量子開發工具組存放庫並不是開發的正確位置。</span><span class="sxs-lookup"><span data-stu-id="93cd8-135">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="93cd8-136">在這種情況下，我們強烈建議您建立自己的存放庫，---量子開發工具組的優點之一，就是您可以使用 GitHub 和 NuGet.org 輕鬆地建立和散發您自己的程式庫，這與我們今天散發 canon 和化學程式庫的方式相同。</span><span class="sxs-lookup"><span data-stu-id="93cd8-136">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="93cd8-137">有時候，我們可能會拒絕良好的投稿，因為我們尚未準備好進行維護和開發。</span><span class="sxs-lookup"><span data-stu-id="93cd8-137">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="93cd8-138">執行所有動作可能很困難，因此我們規劃了我們最能作為藍圖的功能。</span><span class="sxs-lookup"><span data-stu-id="93cd8-138">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="93cd8-139">這可以是另一種將功能發行為協力廠商程式庫的情況，這種情況可能很合理。</span><span class="sxs-lookup"><span data-stu-id="93cd8-139">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="93cd8-140">另外，我們可能會要求您提供修改功能的協助，使其更符合我們的藍圖，讓我們可以執行最適合的工作。</span><span class="sxs-lookup"><span data-stu-id="93cd8-140">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="93cd8-141">如果提取要求需要更多檔或單元測試以協助我們使用它，或如果它的樣式與其他程式庫的樣式有所差異，讓 Q# 使用者更難找到您的功能，我們也會要求您變更提取要求。</span><span class="sxs-lookup"><span data-stu-id="93cd8-141">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="93cd8-142">在這些情況下，我們會嘗試在程式碼評論中提供一些建議，讓您可以新增或變更專案，讓我們更輕鬆地納入您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="93cd8-142">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="93cd8-143">最後，我們無法接受導致量子運算群體的投稿，如 [Microsoft 開放原始碼](https://opensource.microsoft.com/codeofconduct/)管理辦法所述。</span><span class="sxs-lookup"><span data-stu-id="93cd8-143">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="93cd8-144">我們想要確保貢獻能為整個量子運算群體提供最大的多樣性，並且在未來因為成長而變得更具包容性。</span><span class="sxs-lookup"><span data-stu-id="93cd8-144">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="93cd8-145">感謝您的協助以達成此目標。</span><span class="sxs-lookup"><span data-stu-id="93cd8-145">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93cd8-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="93cd8-146">Next steps</span></span>

<span data-ttu-id="93cd8-147">感謝您協助讓量子開發工具組成為整個量副程式設計團體的絕佳資源！</span><span class="sxs-lookup"><span data-stu-id="93cd8-147">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="93cd8-148">若要深入瞭解，請繼續進行下列樣式指南 Q# 。</span><span class="sxs-lookup"><span data-stu-id="93cd8-148">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="93cd8-149">瞭解 Q# 樣式指導方針</span><span class="sxs-lookup"><span data-stu-id="93cd8-149">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="93cd8-150">視您所參與的程式碼類型而定，可能會有其他事項要記住，這可協助您讓您的投稿更適合您的小組。</span><span class="sxs-lookup"><span data-stu-id="93cd8-150">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="93cd8-151">深入瞭解如何參與範例</span><span class="sxs-lookup"><span data-stu-id="93cd8-151">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
