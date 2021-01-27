---
title: 參與 Microsoft QDK 的檔
description: 瞭解如何將概念或 API 內容投稿至 Microsoft 量子檔集。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8602705d2dd071e822e2ff58a9a44cd0684f77f1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857368"
---
# <a name="improving-documentation"></a>改善文件

量子開發工具組的檔採用數種不同的形式，因此量子開發人員可立即取得資訊。

遵循檔的原則即程式 [代碼](https://www.writethedocs.org/guide/docs-as-code/)，所有量子開發工具組檔都會格式化為程式碼，並使用 Git 來管理，方法與用來建立量子開發工具組的原始程式碼相同。
在大部分的情況下，程式碼支援檔是由各種形式的 [Markdown](https://daringfireball.net/projects/markdown/)所組成，這是一種以純文字格式寫出豐富格式文本的語言，在命令列、ide 和原始檔控制中都很容易使用。
同樣地，我們也採用 [MathJax](https://www.mathjax.org/) 程式庫，以便在檔中使用 LaTeX 語言來格式化數學，如下所述。


話雖如此，每一種形式的檔都有不同的詳細資料：

- **概念檔** 是由一組發行至的發行項所組成 https://docs.microsoft.com/quantum ，而且會從量子運算的基本概念，到交換格式的技術規格中說明所有專案。 這些文章是以 [DocFX-Flavored Markdown (DFM) ](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)，這是用來建立豐富檔集的 Markdown 變異。
- **API 參考** 是針對每個函 Q# 式、作業和使用者定義型別發行的一組頁面 https://docs.microsoft.com/qsharp/api/ 。 這些頁面會記錄每個可呼叫的輸入和作業，以及範例和詳細資訊的連結。 API 參考會自動從原始程式碼中的小型 DFM 檔中解壓縮， Q# 作為每個版本的一部分。
- 每個範例和 kata 中隨附的 Readme.txt 檔案會說明如何使用該範例或 kata、其涵蓋的內容，以及與量子開發工具組的其餘部分之間的關聯性 **<!----> 。** 這些檔案是使用 [GitHub Flavored Markdown (GFM) ](https://github.github.com/gfm/)所撰寫，這是 DFM 的較輕量替代方案，可直接將檔附加至程式碼存放庫。

## <a name="contributing-to-the-conceptual-documentation"></a>參與概念檔

為了提供概念或讀我檔案的改進，在適當的情況下，會從提取要求開始至 [**MicrosoftDocs/量子檔-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/量子**](https://github.com/Microsoft/Quantum)或 [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas)。
我們將在下面說明更多有關提取要求的資訊，但現在有幾件事在您改善檔時要牢記在心：

- 讀者從非常廣泛的背景進入量子開發工具組檔。 來自高中學生的每個人都想要學習任職的教職員，執行量子運算的教職員應該能夠從閱讀檔中取得一些東西。 在可能的範圍內，請不要對讀者的部分進行廣泛的知識，因為它們可能只是開始。如果您可以提供清楚且可存取的說明，也可以提供其他資源的連結，以取得詳細資訊。
- 檔集並不像書籍或論文一樣，讀者可能會在看起來像「中間」。 例如，搜尋引擎可能不會建議索引，或可能已傳送給 friend 的連結嘗試協助他們完成。請在適當的情況下，一律提供明確的內容以及適當的連結，以協助您的讀者。
- 某些讀者會尋找最有用的抽象語句和定義，而其他讀取器則是從具體範例中推斷來獲得最佳效果。 提供一般案例和特定範例，可協助這兩個讀者充分利用量副程式設計。
- 尤其是，如果您也撰寫了所記載的程式碼，您可能會很明顯地對讀者來說不太明顯。 沒有一個獨特的程式設計方法，所以無論讀者有多麼聰明或經驗，都不能猜到哪些設計模式最有助於您在程式碼中表達您的想法。 清楚瞭解讀者如何預期使用您的程式碼，可協助提供該內容。
- 量副程式設計團體的許多成員都是學術研究人員，主要是透過對社區投稿發表的引文來辨識。 除了協助讀者找出其他的材質之外，請務必適當地找出像是論文、演講、blog 文章和軟體工具等學術輸出，以協助學術的投稿人員繼續進行最佳的工作，以改善社區。
- 量副程式設計團體是廣泛且 wonderfully 的多樣化團體。 在協力廠商範例中使用名詞代名詞 (例如：「如果使用者 ...」，則 ) 可以在不包含的情況下使用。 在引文和連結中 cognizant 人員的姓名，以及包含非 ASCII 字元的正確包含，可以藉由顯示其成員的方式來提供該社區的多樣性。 同樣地，英文語言中的許多單字通常會以惡意的方式使用，因此在技術檔中使用時，可能會對個別讀者和大型團體造成損害。

### <a name="referencing-sample-code-from-conceptual-articles"></a>參考概念文章中的範例程式碼

如果您想要包含 [範例存放庫](https://github.com/Microsoft/Quantum)中的程式碼，您可以使用特殊的 DocFX-Flavored Markdown 命令來執行此作業：

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

此命令會[ `Game.qs` 從 `chsh-game` 範例](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)匯入檔案中的第4行到第8行，將它們標示為 Q# 程式碼以進行語法醒目提示。
使用這個命令，您可以避免在概念文章和範例存放庫之間複製程式碼，讓檔中的範例程式碼一律盡可能保持最新狀態。

### <a name="contributing-image-files"></a>參與影像檔案

**重要**：若要讓影像在深色模式中正確呈現，您必須避免使用投影片。

- 適用于 .jpg 檔案。 因為 .jpg 格式不支援透明元素，所以您不需要做任何動作。
- 若是 .png 檔案，您必須加入白色背景，或將 Alpha 色板的值變更為 **100**。 在 Windows 中最簡單的方式是在 **油漆** 中開啟檔案，並儲存檔案，覆寫原始檔案。
- 針對 svg 檔案，您必須在最低層中加入白色矩形。 您可以使用 **引導 inkscape** 來執行此動作：
  1. 開啟 svg 檔案。
  1. 選取 [正方形 maker] 工具，並在原始圖形上方繪製白色矩形。
  1. 選取工具，方法是按一下深色箭號或按 **F1** 鍵來 **選取和轉換物件**。
  1. 選取矩形之後，請按一下下方的工具列元素， **選取 [低於] (End)**。
  1. 以滑鼠或方向鍵調整矩形。

## <a name="contributing-to-the-api-references"></a>參與 API 參考

若要提升 API 參考的改進，請直接在所記載的程式碼上開啟提取要求是很有説明的。
每個函式、作業或使用者定義型別都支援以 (表示的檔批註， `///` 而不是 `//`) 。
當我們編譯量子開發工具組的每個版本時，會使用這些批註來產生 API 參考， https://docs.microsoft.com/qsharp/api/ 包括每個可呼叫之輸入和輸出的詳細資訊、每個可呼叫的假設，以及如何使用它們的範例。

> [!IMPORTANT]
> 請務必不要手動編輯產生的 API 檔，因為每個新版本都會覆寫這些檔案。
> 我們將您對您的投稿貢獻價值，並想要確保您的變更會繼續協助使用者在發行後發行。

例如，請考慮函數 `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` 。
檔批註應能協助使用者瞭解如何解讀和函式的 `bits` `oracle` 用途。
您可以透過 Q# 檔批註中的特殊命名 Markdown 區段，將這些不同的資訊片段提供給編譯器。
在的範例 `ControlledOnBitString` 中，我們可能會撰寫如下所示的內容：

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

您可以在函式的 API 檔中查看上述程式碼的轉譯版本。 [ `ControlledOnBitString` ](xref:Microsoft.Quantum.Canon.ControlledOnBitString)

除了撰寫檔的一般作法，撰寫 API 檔批註也有助於牢記一些事項：

- 每個檔批註的格式都必須符合 Q# 編譯器預期的檔顯示正確的內容。 某些區段（例如 `/// # Remarks` 允許自由格式的內容），而區段（例如 `/// # See Also` 區段）的限制較嚴格。
- 讀者可以在主要 API 參考網站、每個命名空間的摘要，或甚至是透過使用暫止資訊的 IDE 中讀取您的 API 檔。 確定 `/// # Summary` 不超過句子的長度，可協助您的讀者快速地排序他們是否需要進一步閱讀或查看其他位置，並可協助快速掃描命名空間摘要。
- 您的檔可能會比程式碼本身更長的時間，但沒關係！ 即使是一小段程式碼，對不知道該程式碼所在內容的使用者也可能會產生非預期的影響。 藉由提供具體範例和明確的說明，您可以協助使用者充分利用其可用的程式碼。

<!-- ## LaTeX Formatting ##

**TODO** -->
