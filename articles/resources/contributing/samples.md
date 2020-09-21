---
title: 參與 Microsoft QDK 的範例
description: 瞭解如何將範例程式碼提供給 Microsoft 量子開發工具組 (QDK) 。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: ae29614cc9c8bf965ea3cb373dc17470aec21252
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759181"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>參與量子開發工具組的範例

如果您有興趣參與 [範例存放庫](https://github.com/Microsoft/Quantum)的程式碼，感謝您讓量子開發小組成為更好的位置！

## <a name="the-quantum-development-kit-samples-repository"></a>量子開發工具組範例存放庫

為了協助您盡可能地準備您的貢獻，最好能夠快速查看範例存放庫的配置方式：

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

也就是說， [microsoft/量子存放庫](https://github.com/microsoft/Quantum) 中的範例會依主旨區域細分成不同的資料夾 `algorithms/` ，例如、 `arithmetic/` 或 `characterization/` 。
在每個主題區域的資料夾內，每個範例都是由單一資料夾所組成，該資料夾會收集使用者探索及使用該範例所需的所有專案。

## <a name="how-samples-are-structured"></a>範例的結構方式

查看組成每個資料夾的檔案，讓我們深入探索 [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) 範例。

| 檔案              | 描述                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# 使用 .NET Core SDK 建立範例的專案 |
| `Game.qs`         | Q# 範例的作業和函式                 |
| `Host.cs`         | 用來執行範例的 c # 主機程式                     |
| `host.py`         | 用來執行範例的 Python 主機程式                 |
| `README.md`       | 範例用途和使用方式的相關檔    |

並非所有範例都有完全相同的檔案集 (例如：某些範例可能僅限 c #，其他範例可能沒有 Python 主機，或某些範例可能需要輔助資料檔案才能運作) 。

## <a name="anatomy-of-a-helpful-readme-file"></a>實用的讀我檔案剖析

但是，其中一個特別重要的檔案是檔案 `README.md` ，因為這是使用者開始使用範例所需的內容！

每個都 `README.md` 應該以一些可協助 docs.microsoft.com/samples 找出您投稿的中繼資料開始。

> [!div class="nextstepaction"]
> [瞭解如何轉譯 chsh 遊戲範例](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

此中繼資料會以 [YAML 標頭](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) 的形式提供，指出您的範例所涵蓋的語言 (一般而言，這會是 `qsharp` 、 `csharp` 和 `python`) ，而您的範例所涵蓋的產品 (通常是 `qdk`) 。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`您的範例必須要有標頭中的索引鍵，您的範例才會出現在 docs.microsoft.com/samples 中。
> 同樣地， `product` 和索引 `language` 鍵對於協助使用者尋找並執行您的範例是不可或缺的。

之後，請提供簡短的簡介，說明新範例的作用：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

您範例的使用者也很樂意知道他們執行所需的工作 (例如：使用者只需要量子開發工具組本身，還是需要額外的軟體，例如 node.js？ ) ：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

一切就緒之後，您就可以告訴使用者如何執行您的範例：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

最後，告訴使用者您範例中的每個檔案所執行的動作，以及他們可以在何處取得詳細資訊，會很有説明：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> 請務必在此使用絕對 Url，因為在 docs.microsoft.com/samples 時，您的範例會出現在不同的 URL 上！
