---
title: 參與 Microsoft QDK 的範例
description: 瞭解如何將範例程式碼提供給 Microsoft Quantum Development Kit （QDK）。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024146"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="e374c-103">對量子開發工具組貢獻範例</span><span class="sxs-lookup"><span data-stu-id="e374c-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="e374c-104">如果您想要將程式碼提供給[範例存放庫](https://github.com/Microsoft/Quantum)，感謝您讓「量子開發」小組變得更好！</span><span class="sxs-lookup"><span data-stu-id="e374c-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="e374c-105">量子開發工具組範例存放庫</span><span class="sxs-lookup"><span data-stu-id="e374c-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="e374c-106">為了協助您準備您的貢獻，盡可能地協助您，快速查看範例存放庫的配置方式會很有説明：</span><span class="sxs-lookup"><span data-stu-id="e374c-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="e374c-107">也就是說， [microsoft/量子存放庫](https://github.com/microsoft/Quantum)中的範例會依主題區域細分到不同的資料夾，例如 `algorithms/`、`arithmetic/`或 `characterization/`。</span><span class="sxs-lookup"><span data-stu-id="e374c-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="e374c-108">在每個主題區域的資料夾中，每個範例都包含一個單一資料夾，以收集使用者需要探索的所有內容，並利用該範例。</span><span class="sxs-lookup"><span data-stu-id="e374c-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="e374c-109">範例的結構</span><span class="sxs-lookup"><span data-stu-id="e374c-109">How Samples are Structured</span></span>

<span data-ttu-id="e374c-110">查看組成每個資料夾的檔案，讓我們深入探討[`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game)範例。</span><span class="sxs-lookup"><span data-stu-id="e374c-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="e374c-111">檔案</span><span class="sxs-lookup"><span data-stu-id="e374c-111">File</span></span>              | <span data-ttu-id="e374c-112">描述</span><span class="sxs-lookup"><span data-stu-id="e374c-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="e374c-113">用來以 .NET Core SDK 建立範例的 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="e374c-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="e374c-114">範例的 Q # 作業和函式</span><span class="sxs-lookup"><span data-stu-id="e374c-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="e374c-115">C#用來執行範例的主機程式</span><span class="sxs-lookup"><span data-stu-id="e374c-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="e374c-116">用來執行範例的 Python 主機程式</span><span class="sxs-lookup"><span data-stu-id="e374c-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="e374c-117">範例用途和使用方式的相關檔</span><span class="sxs-lookup"><span data-stu-id="e374c-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="e374c-118">並非所有的範例都具有完全相同的檔案集合（例如：某些範例可能C#僅限、其他可能沒有 Python 主機，或有些範例可能需要輔助的資料檔案才能正常執行）。</span><span class="sxs-lookup"><span data-stu-id="e374c-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="e374c-119">有用的讀我檔案剖析</span><span class="sxs-lookup"><span data-stu-id="e374c-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="e374c-120">不過，其中一個特別重要的檔案是 `README.md` 檔案，因為這是使用者開始使用範例所需的內容！</span><span class="sxs-lookup"><span data-stu-id="e374c-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="e374c-121">每個 `README.md` 都應該從一些中繼資料開始，協助 docs.microsoft.com/samples 尋找您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="e374c-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e374c-122">瞭解如何呈現 chsh 遊戲範例</span><span class="sxs-lookup"><span data-stu-id="e374c-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="e374c-123">此中繼資料會以[YAML 標頭](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header)的形式提供，指出您的範例所涵蓋的語言（通常是 `qsharp`、`csharp`和 `python`），以及您的範例所涵蓋的產品（通常只是 `qdk`）。</span><span class="sxs-lookup"><span data-stu-id="e374c-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="e374c-124">必須要有標頭中的 `page_type: sample` 金鑰，您的範例才會出現在 docs.microsoft.com/samples 中。</span><span class="sxs-lookup"><span data-stu-id="e374c-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="e374c-125">同樣地，`product` 和 `language` 金鑰組于協助使用者尋找並執行您的範例十分重要。</span><span class="sxs-lookup"><span data-stu-id="e374c-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="e374c-126">之後，提供簡短的簡介，告訴您新的範例有何作用：</span><span class="sxs-lookup"><span data-stu-id="e374c-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="e374c-127">您的範例使用者也會知道他們需要執行的作業（例如：使用者是否只需要量子開發工具組本身，或需要其他軟體，例如 node.js？）：</span><span class="sxs-lookup"><span data-stu-id="e374c-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="e374c-128">當您準備好時，可以告訴使用者如何執行您的範例：</span><span class="sxs-lookup"><span data-stu-id="e374c-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="e374c-129">最後，告訴使用者您範例中的每個檔案有何用途，以及他們可以在何處取得詳細資訊，是很有説明的：</span><span class="sxs-lookup"><span data-stu-id="e374c-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="e374c-130">請務必在此使用絕對 Url，因為您的範例會在轉譯為 docs.microsoft.com/samples 時出現在不同的 URL 上！</span><span class="sxs-lookup"><span data-stu-id="e374c-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
