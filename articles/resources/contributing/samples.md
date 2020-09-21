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
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="24ac1-103">參與量子開發工具組的範例</span><span class="sxs-lookup"><span data-stu-id="24ac1-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="24ac1-104">如果您有興趣參與 [範例存放庫](https://github.com/Microsoft/Quantum)的程式碼，感謝您讓量子開發小組成為更好的位置！</span><span class="sxs-lookup"><span data-stu-id="24ac1-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="24ac1-105">量子開發工具組範例存放庫</span><span class="sxs-lookup"><span data-stu-id="24ac1-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="24ac1-106">為了協助您盡可能地準備您的貢獻，最好能夠快速查看範例存放庫的配置方式：</span><span class="sxs-lookup"><span data-stu-id="24ac1-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="24ac1-107">也就是說， [microsoft/量子存放庫](https://github.com/microsoft/Quantum) 中的範例會依主旨區域細分成不同的資料夾 `algorithms/` ，例如、 `arithmetic/` 或 `characterization/` 。</span><span class="sxs-lookup"><span data-stu-id="24ac1-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="24ac1-108">在每個主題區域的資料夾內，每個範例都是由單一資料夾所組成，該資料夾會收集使用者探索及使用該範例所需的所有專案。</span><span class="sxs-lookup"><span data-stu-id="24ac1-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="24ac1-109">範例的結構方式</span><span class="sxs-lookup"><span data-stu-id="24ac1-109">How Samples are Structured</span></span>

<span data-ttu-id="24ac1-110">查看組成每個資料夾的檔案，讓我們深入探索 [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) 範例。</span><span class="sxs-lookup"><span data-stu-id="24ac1-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="24ac1-111">檔案</span><span class="sxs-lookup"><span data-stu-id="24ac1-111">File</span></span>              | <span data-ttu-id="24ac1-112">描述</span><span class="sxs-lookup"><span data-stu-id="24ac1-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="24ac1-113">Q# 使用 .NET Core SDK 建立範例的專案</span><span class="sxs-lookup"><span data-stu-id="24ac1-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="24ac1-114">Q# 範例的作業和函式</span><span class="sxs-lookup"><span data-stu-id="24ac1-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="24ac1-115">用來執行範例的 c # 主機程式</span><span class="sxs-lookup"><span data-stu-id="24ac1-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="24ac1-116">用來執行範例的 Python 主機程式</span><span class="sxs-lookup"><span data-stu-id="24ac1-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="24ac1-117">範例用途和使用方式的相關檔</span><span class="sxs-lookup"><span data-stu-id="24ac1-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="24ac1-118">並非所有範例都有完全相同的檔案集 (例如：某些範例可能僅限 c #，其他範例可能沒有 Python 主機，或某些範例可能需要輔助資料檔案才能運作) 。</span><span class="sxs-lookup"><span data-stu-id="24ac1-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="24ac1-119">實用的讀我檔案剖析</span><span class="sxs-lookup"><span data-stu-id="24ac1-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="24ac1-120">但是，其中一個特別重要的檔案是檔案 `README.md` ，因為這是使用者開始使用範例所需的內容！</span><span class="sxs-lookup"><span data-stu-id="24ac1-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="24ac1-121">每個都 `README.md` 應該以一些可協助 docs.microsoft.com/samples 找出您投稿的中繼資料開始。</span><span class="sxs-lookup"><span data-stu-id="24ac1-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="24ac1-122">瞭解如何轉譯 chsh 遊戲範例</span><span class="sxs-lookup"><span data-stu-id="24ac1-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="24ac1-123">此中繼資料會以 [YAML 標頭](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) 的形式提供，指出您的範例所涵蓋的語言 (一般而言，這會是 `qsharp` 、 `csharp` 和 `python`) ，而您的範例所涵蓋的產品 (通常是 `qdk`) 。</span><span class="sxs-lookup"><span data-stu-id="24ac1-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="24ac1-124">`page_type: sample`您的範例必須要有標頭中的索引鍵，您的範例才會出現在 docs.microsoft.com/samples 中。</span><span class="sxs-lookup"><span data-stu-id="24ac1-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="24ac1-125">同樣地， `product` 和索引 `language` 鍵對於協助使用者尋找並執行您的範例是不可或缺的。</span><span class="sxs-lookup"><span data-stu-id="24ac1-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="24ac1-126">之後，請提供簡短的簡介，說明新範例的作用：</span><span class="sxs-lookup"><span data-stu-id="24ac1-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="24ac1-127">您範例的使用者也很樂意知道他們執行所需的工作 (例如：使用者只需要量子開發工具組本身，還是需要額外的軟體，例如 node.js？ ) ：</span><span class="sxs-lookup"><span data-stu-id="24ac1-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="24ac1-128">一切就緒之後，您就可以告訴使用者如何執行您的範例：</span><span class="sxs-lookup"><span data-stu-id="24ac1-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="24ac1-129">最後，告訴使用者您範例中的每個檔案所執行的動作，以及他們可以在何處取得詳細資訊，會很有説明：</span><span class="sxs-lookup"><span data-stu-id="24ac1-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="24ac1-130">請務必在此使用絕對 Url，因為在 docs.microsoft.com/samples 時，您的範例會出現在不同的 URL 上！</span><span class="sxs-lookup"><span data-stu-id="24ac1-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
