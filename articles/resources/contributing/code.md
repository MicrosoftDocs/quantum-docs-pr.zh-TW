---
title: 參與 Microsoft QDK 的程式碼
description: 瞭解如何將範例和程式庫程式碼提供給 Microsoft 量子開發工具組 (QDK) 。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 54ef15db2b850e6a3bff38945c57129361517bfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856682"
---
# <a name="contributing-code"></a>提供程式碼

除了回報問題和改進檔之外，將程式碼提供給量子開發工具組，也是協助您參與量副程式設計團體的直接方式。
藉由貢獻程式碼，您可以協助修正問題、提供新的範例、讓現有的程式庫更容易使用，或甚至新增全新的功能。

在本指南中，我們將詳細說明我們在審視提取要求時所要尋找的內容，以協助您的投稿最妥善。

## <a name="what-we-look-for"></a>我們要尋找的內容

理想的程式碼投稿建基於量子開發工具組存放庫中的現有工作，以修正問題、擴充現有的功能，或加入存放庫範圍內的新功能。
當我們接受程式碼投稿時，它會成為量子開發工具組本身的一部分，因此會以與其他量子開發工具組相同的方式來發行、維護及開發新功能。
因此，當投稿加入的功能經過妥善測試並記載時，這會很有説明。

### <a name="unit-tests"></a>單元測試

Q#組成程式庫（例如 canon）的函式、作業和使用者定義類型，會在 [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)儲存機制的開發過程中自動進行測試。
比方說，當新的提取要求開啟時，我們的 [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) 設定會確認提取要求中的變更不會中斷任何與量副程式設計社區相依的現有功能。

使用最新 Q# 版本，單元測試是使用屬性來定義 `@Test("QuantumSimulator")` 。 引數可以是 "QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator" 或任何指定執行目標的完整名稱。 有幾個屬性定義不同的執行目標可以附加到相同的可呼叫。 有些測試仍使用已被取代的 [Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) 套件，此封裝會公開所有 Q# `Test` 以 [Xunit](https://xunit.github.io/) framework 結尾的函式和作業。 您不再需要此套件來定義單元測試。 

下列函式是用來確保和函 <xref:Microsoft.Quantum.Canon.Fst> 式 <xref:Microsoft.Quantum.Canon.Snd> 都在代表性範例中傳回正確的輸出。
如果或的輸出 `Fst` `Snd` 不正確， `fail` 語句會用來導致測試失敗。

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

您可以使用標準程式庫指南的 [測試一節](xref:microsoft.quantum.libraries.diagnostics) 中的技巧來檢查更複雜的條件。
例如，下列測試會檢查所呼叫的是否與 `H(q); X(q); H(q);` <xref:Microsoft.Quantum.Canon.ApplyWith> 相同 `Z(q)` 。

```qsharp
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

新增新功能時，建議您也要加入新的測試，以確保您的投稿內容符合預期。
這可協助其他小組維護及開發您的功能，特別是協助其他開發人員瞭解他們可以依賴您的功能。

> [!NOTE]
> 這也是另一種方式
> 如果有現有的功能遺失某些測試，請協助我們新增測試涵蓋範圍，對該社區有很大的貢獻。

在本機，您可以使用 Visual Studio Test Explorer 或命令來執行單元測試 `dotnet test` ，讓您可以在開啟提取要求之前檢查您的貢獻。

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a>提取要求

當您準備好要參與工作時，請透過 GitHub 將提取要求傳送至對應的存放庫。
小組將會審查並提供意見反應。 所有批註都必須經過回答和解決，而且所有的檢查都必須在程式碼合併至分支之前傳遞 `main` 。

## <a name="when-well-reject-a-pull-request"></a>當我們拒絕提取要求時

有時候，我們會拒絕投稿的提取要求。
如果發生這種情況，這並不表示它不正確，因為有許多原因可能無法接受特定的投稿。
最常見的情況是，量副程式設計團體的投稿是不錯的工具，但量子開發工具組存放庫並不是開發的正確位置。
在這種情況下，我們強烈建議您建立自己的存放庫，---量子開發工具組的優點之一，就是您可以使用 GitHub 和 NuGet.org 輕鬆地建立和散發您自己的程式庫，這與我們今天散發 canon 和化學程式庫的方式相同。

有時候，我們可能會拒絕良好的投稿，因為我們尚未準備好進行維護和開發。
執行所有動作可能很困難，因此我們規劃了我們最能作為藍圖的功能。
這可以是另一種將功能發行為協力廠商程式庫的情況，這種情況可能很合理。
另外，我們可能會要求您提供修改功能的協助，使其更符合我們的藍圖，讓我們可以執行最適合的工作。

如果提取要求需要更多檔或單元測試以協助我們使用它，或如果它的樣式與其他程式庫的樣式有所差異，讓 Q# 使用者更難找到您的功能，我們也會要求您變更提取要求。
在這些情況下，我們會嘗試在程式碼評論中提供一些建議，讓您可以新增或變更專案，讓我們更輕鬆地納入您的貢獻。

最後，我們無法接受導致量子運算群體的投稿，如 [Microsoft 開放原始碼](https://opensource.microsoft.com/codeofconduct/)管理辦法所述。
我們想要確保貢獻能為整個量子運算群體提供最大的多樣性，並且在未來因為成長而變得更具包容性。
感謝您的協助以達成此目標。

## <a name="next-steps"></a>後續步驟

感謝您協助讓量子開發工具組成為整個量副程式設計團體的絕佳資源！
若要深入瞭解，請繼續進行下列樣式指南 Q# 。

> [!div class="nextstepaction"]
> [瞭解 Q# 樣式指導方針](xref:microsoft.quantum.contributing.style)

視您所參與的程式碼類型而定，可能會有其他事項要記住，這可協助您讓您的投稿更適合您的小組。

> [!div class="nextstepaction"]
> [深入瞭解如何參與範例](xref:microsoft.quantum.contributing.samples)
