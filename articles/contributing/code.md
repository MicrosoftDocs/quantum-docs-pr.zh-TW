---
title: 參與程式碼 |Microsoft Docs
description: 貢獻程式碼
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: 3ff15a744bf15924564d5a8fee54f4fbce4c04ee
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864418"
---
# <a name="contributing-code"></a>提供程式碼 #

除了報告問題和改善檔外，將程式碼提供給量子開發工具組，是協助您的對等在「量副程式設計」小組中的直接方法。
藉由貢獻程式碼，您可以協助修正問題、提供新的範例、讓現有的程式庫更容易使用，甚至新增全新的功能。

在本指南中，我們將詳細說明我們在審查提取要求時所尋找的一些內容，以協助您的貢獻達到最佳效果。

## <a name="what-we-look-for"></a>我們所尋找的內容 ##

理想的程式碼貢獻是以「量子開發工具組」存放庫中的現有工作為基礎，以修正問題、擴充現有功能，或新增在存放庫範圍內的新功能。
當我們接受程式碼貢獻時，它會成為量子開發工具組本身的一部分，讓新功能的發行、維護和開發方式與其他的配量開發工具組相同。
因此，當投稿新增的功能經過妥善測試並記載時，這會很有説明。

### <a name="unit-tests"></a>單元測試 ###

組成程式庫（例如 canon）的 Q # 函數、作業和使用者定義類型，會在[**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)存放庫的開發過程中自動進行測試。
例如，當新的提取要求開啟時，我們的[Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/)設定會檢查提取要求中的變更是否不會中斷任何與量副程式設計人員所相依的現有功能。

使用最新的 Q # 版本，單元測試是使用 `@Test("QuantumSimulator")` 屬性來定義。 引數可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"，或指定執行目標的任何完整限定名稱。 定義不同執行目標的數個屬性可能會附加至相同的可呼叫。 我們的一些測試仍會使用已被取代的[Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/)套件，它會公開所有的 Q # 函式和作業，並以 `Test` 至[Xunit](https://xunit.github.io/)架構。 定義單元測試不再需要此封裝。 

下列函數是用來確保 <xref:microsoft.quantum.canon.fst> 和 <xref:microsoft.quantum.canon.snd> 函式都會在代表性範例中傳回正確的輸出。
如果 `Fst` 或 `Snd` 的輸出不正確，則會使用 `fail` 語句來使測試失敗。

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

使用標準程式庫指南的[測試一節](xref:microsoft.quantum.libraries.diagnostics)中的技術，可以檢查更複雜的條件。
例如，下列測試會檢查 `H(q); X(q); H(q);` 如 <xref:microsoft.quantum.canon.applywith> 所呼叫的動作，與 `Z(q)`的做法相同。

```qsharp
@Test("QuantumSimulator")
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

新增新功能時，最好也加入新的測試，以確保您的投稿會執行其所需的工作。
這可協助其餘的社區維護和開發您的功能，特別是協助其他開發人員瞭解他們可以依賴您的功能。

> [!NOTE]
> 這也是以另一種方式運作！
> 如果現有的功能遺失某些測試，協助我們新增測試涵蓋範圍會對該社區產生絕佳的貢獻。

在本機上，可以使用 [Visual Studio Test Explorer] 或 [`dotnet test`] 命令來執行單元測試，讓您可以在開啟提取要求之前檢查您的貢獻。

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>當我們拒絕提取要求時 ##

有時候，我們會拒絕投稿的提取要求。
如果您發生這種情況，這並不表示它是壞的，因為我們可能會因為許多原因而無法接受特定的投稿。
最常見的情況是，配量程式設計小組的貢獻是一個很好的工具，但是量子開發工具組存放庫並不是開發的正確位置。
在這種情況下，我們強烈建議您讓自己的存放庫---配量開發工具組的優勢之一，那就是使用 GitHub 和 NuGet.org 輕鬆地建立和散佈您自己的程式庫，這與我們散發 canon 和化學的方式相同今天的程式庫。

在其他時候，我們可能會因為尚未準備維護和開發，而拒絕良好的貢獻。
這麼做可能很難以完成所有作業，因此我們計畫最能以藍圖的形式來處理的功能。
這可能是另一種將功能當做協力廠商程式庫發行的情況，可能會有很大的意義。
或者，我們可能會要求您協助修改某項功能，使其更符合我們的藍圖，讓我們可以執行最佳的工作。

如果提取要求有更多的檔或單元測試可協助我們使用它，或者它的樣式與問 # 程式庫的其餘部分有足夠的風格，讓使用者更難以找到您的功能，我們也會要求您變更要求。
在這些情況下，我們會嘗試在程式碼審查中提供一些建議，告訴您可以新增或變更哪些專案，讓我們更容易納入您的貢獻。

最後，我們無法接受造成損害「量子計算」的貢獻，如[Microsoft 開放原始碼](https://opensource.microsoft.com/codeofconduct/)管理辦法中所述。
我們想要確保貢獻的是整個量子運算的群體，在其目前的絕佳多樣性中，而且未來隨著成長而變得更具其成果。
我們非常感謝您實現此目標的協助。

## <a name="next-steps"></a>後續步驟 ##

感謝您協助讓量子開發工具組成為整個量副程式設計小組的絕佳資源！
若要深入瞭解，請繼續進行 Q # 樣式的下列指南。

> [!div class="nextstepaction"]
> [瞭解問 # 樣式指導方針](xref:microsoft.quantum.contributing.style)
