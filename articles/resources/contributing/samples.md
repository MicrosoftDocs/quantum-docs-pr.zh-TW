---
title: 參與 Microsoft QDK 的範例
description: 瞭解如何將範例程式碼提供給 Microsoft Quantum Development Kit (QDK) 。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 20da0e1765a242c172cc595f03d7791a0e8b8d2d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867501"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>對量子開發工具組貢獻範例

如果您想要將程式碼提供給[範例存放庫](https://github.com/Microsoft/Quantum)，感謝您讓「量子開發」小組變得更好！

## <a name="the-quantum-development-kit-samples-repository"></a>量子開發工具組範例存放庫

為了協助您準備您的貢獻，盡可能地協助您，快速查看範例存放庫的配置方式會很有説明：

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

也就是說， [microsoft/量子存放庫](https://github.com/microsoft/Quantum)中的範例會依主題區域細分到不同的資料夾 `algorithms/` ，例如、 `arithmetic/` 或 `characterization/` 。
在每個主題區域的資料夾中，每個範例都包含一個單一資料夾，以收集使用者需要探索的所有內容，並利用該範例。

## <a name="how-samples-are-structured"></a>範例的結構

查看組成每個資料夾的檔案，讓我們深入瞭解 [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) 範例。

| 檔案              | 描述                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q#用來以 .NET Core SDK 建立範例的專案 |
| `Game.qs`         | Q#範例的作業和函式                 |
| `Host.cs`         | 用來執行範例的 c # 主機程式                     |
| `host.py`         | 用來執行範例的 Python 主機程式                 |
| `README.md`       | 範例用途和使用方式的相關檔    |

並非所有樣本都具有完全相同的檔案集合 (例如：有些範例可能僅限 c #，有些則可能沒有 Python 主機，或某些範例可能需要輔助的資料檔案才能) 。

## <a name="anatomy-of-a-helpful-readme-file"></a>有用的讀我檔案剖析

不過，其中一個特別重要的檔案是檔案 `README.md` ，因為這是使用者開始使用範例所需的內容！

每個都 `README.md` 應該從一些中繼資料開始，協助 docs.microsoft.com/samples 尋找您的貢獻。

> [!div class="nextstepaction"]
> [瞭解如何呈現 chsh 遊戲範例](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

此中繼資料會以[YAML 標頭](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header)的形式提供，以指出您的範例所涵蓋的語言 (一般，這會是 `qsharp` 、 `csharp` 和 `python`) ，而您的範例所涵蓋的產品 (通常只會 `qdk`) 。

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`必須要有標頭中的索引鍵，您的範例才會出現在 docs.microsoft.com/samples 中。
> 同樣地， `product` 和 `language` 金鑰組于協助使用者尋找並執行您的範例十分重要。

之後，提供簡短的簡介，告訴您新的範例有何作用：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

您的範例使用者也會知道他們需要哪些專案才能執行 (例如：使用者是否只需要量子開發工具組本身，或是否需要其他軟體，例如 node.js？ ) ：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

當您準備好時，可以告訴使用者如何執行您的範例：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

最後，告訴使用者您範例中的每個檔案有何用途，以及他們可以在何處取得詳細資訊，是很有説明的：

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> 請務必在此使用絕對 Url，因為您的範例會在轉譯為 docs.microsoft.com/samples 時出現在不同的 URL 上！
