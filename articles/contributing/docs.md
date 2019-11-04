---
title: 參與檔 |Microsoft Docs
description: 參與檔
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183670"
---
# <a name="improving-documentation"></a>改善檔 #

量子開發工具組的檔會採用數種不同的形式，讓量子開發人員可以立即使用該資訊。

遵循檔的原則[做為程式碼](https://www.writethedocs.org/guide/docs-as-code/)，所有的配量開發工具組檔都會格式化為程式碼，並使用 Git 進行管理，其方式與用來建立量子開發工具組的原始程式碼相同。
在大部分的情況下，程式碼支援檔是由各種形式的[Markdown](https://daringfireball.net/projects/markdown/)所組成，這是一種語言，用來以純文字格式寫出豐富格式的文字，可在命令列、ide 和原始檔控制中輕鬆使用。
我們同樣採用[MathJax](https://www.mathjax.org/)程式庫，以允許在檔中使用 LaTeX 語言來格式化數學法，如下所詳述。


話雖如此，每一種形式的檔都有不同的細節：

- **概念檔**包含發行至 https://docs.microsoft.com/quantum 的一系列文章，並說明從量子計算的基本概念到交換格式的技術規格等所有事項。 這些文章是以[DocFX-Flavored Markdown （DFM）](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)撰寫，這是用來建立豐富檔集的 Markdown 變體。
- **API 參考**是每個 Q # 函數、作業和使用者定義類型的一組頁面，已發行至 https://docs.microsoft.com/qsharp/api/ 。 這些頁面會記錄每個可呼叫的輸入和作業，以及範例和詳細資訊的連結。 API 參考會在每次發行時，從 Q # 原始程式碼中的小型 DFM 檔自動解壓縮。
- 包含在每個範例和 kata 中的**讀我檔案<!---->** ，說明如何使用該範例或 kata、它涵蓋的內容，以及它與其他的量子開發工具組的關係。 這些檔案是使用[GitHub Flavored Markdown （GFM）](https://github.github.com/gfm/)所撰寫，這是更輕量的替代方案，可將檔直接附加至程式碼存放庫。

## <a name="contributing-to-the-conceptual-documentation"></a>參與概念檔 ##

為了提供概念或讀我檔案的改進，在適當的情況下，您可以根據[**MicrosoftDocs/量子-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/量子**](https://github.com/Microsoft/Quantum)或[**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)，以提取要求開始。
我們將在下方說明提取要求的詳細資訊，但現在有幾件事可以在改善檔時記住：

- 讀者會從非常廣泛的背景，進入「量子開發工具組」檔。 來自高中學生的每個人，想要學習新功能和令人興奮的任職教職員執行量子運算研究時，應該能夠取得閱讀檔的相關內容。 在可能的範圍內，請不要對讀者的部分取得豐富的知識，因為它們可能只是從開始。如果您可以提供清楚且可存取的描述，或者可以提供其他資源的連結以取得詳細資訊，它最有説明。
- 檔集並不像書籍或論文一樣，而讀者會收到「中間」這類的內容。 例如，搜尋引擎可能不會建議索引，也可能是由朋友傳送連結來嘗試協助他們。請一律提供清楚的內容，以及適當的連結，以協助您的讀者。
- 有些讀者會發現抽象的語句和定義最有説明，而其他讀取器則是從具體範例中推斷的最佳做法。 同時提供一般案例和特定範例，可協助這兩個讀取器充分利用量副程式設計。
- 特別是當您也寫了記載的程式碼時，您可能會很明顯地得知您的讀者並不清楚。 沒有一種獨特的程式設計方法，因此無論讀者有多麼聰明或有經驗，他們都無法猜出您在程式碼中最有説明的設計模式。 清楚瞭解讀取器可以如何利用您的程式碼來協助提供該內容。
- 「量副程式設計」小組的許多成員都是學術研究人員，主要是透過對其投稿貢獻的引文來辨識。 除了協助讀者尋找額外的資料之外，也請務必適當地提及學術的輸出（例如論文、交談、blog 文章和軟體工具），以協助學術參與者繼續進行最佳的工作來改善社區。
- 「量副程式設計」小組是廣泛而 wonderfully 的多樣化團體。 使用協力廠商範例中的名詞代名詞（例如：「如果使用者 ...，他將 ...」）可以工作來排除而不是包含。 在引文和連結中 cognizant 人員名稱，以及正確包含非 ASCII 字元，可以藉由顯示其成員來提供社區的多樣性。 同樣地，英文語言中的許多單字通常會以 hateful 的方式使用，因此在技術檔中使用時，可能會對個別讀者和大型團體造成損害。

## <a name="contributing-to-the-api-references"></a>參與 API 參考 ##

若要改善 API 參考的效果，在記載的程式碼上直接開啟提取要求最有説明。
每個函數、作業或使用者自訂類型都支援檔批註（以 `///` 表示，而不是 `//`）。
當我們編譯每個版本的「配量」開發工具組時，這些批註會用來產生 https://docs.microsoft.com/qsharp/api/ 的 API 參考，包括每個可呼叫之輸入和輸出的詳細資訊、每個可呼叫的假設，以及如何使用它們的範例。

> [!IMPORTANT]
> 請務必不要手動編輯產生的 API 檔，因為每個新版本都會覆寫這些檔案。
> 我們將您對您的貢獻做為價值，並想要確保您的變更在發行後仍持續協助使用者發行。

例如，請考慮 `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`的作業。
檔批註應可協助使用者瞭解如何解讀 `angles`、作業假設 `register`的初始狀態、對 `register` 的影響等等。
您可以透過檔批註中特別命名的 Markdown 區段，將這些不同的資訊片段提供給 Q # 編譯器。
在 `PrepareTrialState`的範例中，我們可能會撰寫如下所示的內容：

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

除了撰寫檔的一般作法外，在撰寫 API 檔批註時，您可以記住一些事項：

- 每個檔批註的格式必須符合 Q # 編譯器所預期的檔，才能正確顯示。 某些區段（例如 `/// # Remarks` 允許自由格式內容），而 `/// # See Also` 區段之類的區段則較嚴格。
- 讀者可以在主要 API 參考網站上、每個命名空間的摘要，或甚至是透過使用暫留資訊，從其 IDE 中讀取您的 API 檔。 確定 `/// # Summary` 的長度不超過句子，可協助您的讀者快速地排序它們是否需要進一步閱讀或查看其他位置，並可協助快速透過命名空間摘要進行掃描。
- 您的檔可能會比程式碼本身更長，但也沒關係！ 即使是一小段程式碼，對不知道該程式碼所在內容的使用者，也可能會產生非預期的影響。 藉由提供具體的範例和清楚的說明，您可以協助使用者充分利用其所提供的程式碼。

<!-- ## LaTeX Formatting ##

**TODO** -->
