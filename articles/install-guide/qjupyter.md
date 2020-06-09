---
title: 使用 Q# Jupyter Notebooks 來開發
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577815"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="5ba1c-102">使用 Q# Jupyter Notebooks 來開發</span><span class="sxs-lookup"><span data-stu-id="5ba1c-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="5ba1c-103">安裝 QDK 以在 Q # Jupyter 筆記本上開發 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="5ba1c-104">Jupyter 筆記本允許就地執行程式碼，連同指示、附注和其他內容。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="5ba1c-105">此環境適合用內嵌的說明或量子計算互動式教學課程來撰寫 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="5ba1c-106">以下是開始建立您自己的 Q# 筆記本所需的準備工作。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="5ba1c-107">IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="5ba1c-108">在 [Q # Jupyter 筆記本] 中，您只能執行 Q # 程式碼，而且無法從外部主機程式（例如 Python 或 c # 檔案）呼叫作業。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="5ba1c-109">如果您的目標是要將外部傳統主機程式與配量程式合併，則此環境不適用。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="5ba1c-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="5ba1c-110">Pre-requisites</span></span>

    - <span data-ttu-id="5ba1c-111">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="5ba1c-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="5ba1c-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="5ba1c-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="5ba1c-113">.NET Core SDK 3。1</span><span class="sxs-lookup"><span data-stu-id="5ba1c-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="5ba1c-114">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="5ba1c-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="5ba1c-115">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="5ba1c-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5ba1c-116">執行下列命令以啟動筆記本伺服器：</span><span class="sxs-lookup"><span data-stu-id="5ba1c-116">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="5ba1c-117">若要開啟 Jupyter Notebook，請將命令列所提供的 URL 複製並貼到您的瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="5ba1c-118">使用 Q # 核心建立 Jupyter Notebook，並將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="5ba1c-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="5ba1c-119">執行筆記本的此一資料格：</span><span class="sxs-lookup"><span data-stu-id="5ba1c-119">Run this cell of the notebook:</span></span>

        ![使用 Q # 程式碼 Jupyter Notebook 儲存格](~/media/install-guide-jupyter.png)

        <span data-ttu-id="5ba1c-121">您應該會在資料格的輸出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="5ba1c-122">在 Jupyter Notebook 中執行時，會編譯 Q # 程式碼，而筆記本會輸出找到的作業名稱。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="5ba1c-123">在新的資料格中，使用命令執行您剛才建立的作業（在模擬器中） `%simulate` ：</span><span class="sxs-lookup"><span data-stu-id="5ba1c-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![具有% 模擬魔術的 Jupyter Notebook 資料格](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="5ba1c-125">您應該會看到訊息印在畫面上，以及您叫用之作業的結果（在這裡，我們會看到空白的元組，因為我們的作業只會傳回 `()` `Unit` 類型）。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ba1c-126">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5ba1c-126">Next steps</span></span>

<span data-ttu-id="5ba1c-127">現在您已安裝了 Q # Jupyter 筆記本的 QDK，您可以撰寫並執行[您的第一個量副程式](xref:microsoft.quantum.quickstarts.qrng)，方法是直接在 Jupyter Notebook 環境中撰寫您的 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="5ba1c-128">如需如何使用 Q # Jupyter 筆記本的更多範例，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5ba1c-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="5ba1c-129">[問答 # 和 Jupyter Notebook 簡介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="5ba1c-130">您會在這裡找到一個 Q # Jupyter Notebook，說明如何在此環境中使用 Q #。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="5ba1c-131">[量子 Katas](xref:microsoft.quantum.overview.katas)，這是一個開放原始碼集合，可自主教學課程和一組程式設計練習，以 Q # Jupyter 筆記本形式呈現。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="5ba1c-132">[量子 Katas 教學課程筆記本](https://github.com/microsoft/QuantumKatas#tutorial-topics)是不錯的起點。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="5ba1c-133">量子 Katas 的目標在於教您同時進行量子運算和 Q # 程式設計的要素。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="5ba1c-134">這些是您可以使用 Q # Jupyter 筆記本建立之內容種類的絕佳範例。</span><span class="sxs-lookup"><span data-stu-id="5ba1c-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
