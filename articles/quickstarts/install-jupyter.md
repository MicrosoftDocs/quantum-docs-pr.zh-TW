---
title: 使用 Q# Jupyter Notebook 開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274033"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="1fae0-102">使用 Q# Jupyter Notebook 開發</span><span class="sxs-lookup"><span data-stu-id="1fae0-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="1fae0-103">安裝 QDK 以在 Q# Jupyter Notebook 上開發 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="1fae0-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="1fae0-104">Jupyter Notebook 允許就地執行指示、備註與其他內容旁的程式碼。</span><span class="sxs-lookup"><span data-stu-id="1fae0-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="1fae0-105">此環境適用於撰寫含內嵌說明或配量運算互動式教學課程的 Q# 程式碼。</span><span class="sxs-lookup"><span data-stu-id="1fae0-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="1fae0-106">以下是開始建立您自己的 Q# 筆記本所需的準備工作。</span><span class="sxs-lookup"><span data-stu-id="1fae0-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="1fae0-107">IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="1fae0-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="1fae0-108">在 Q# Jupyter Notebook 中，您只可以執行 Q# 程式碼，且無法從外部主機程式 (例如 Python 或 C# 檔案) 呼叫作業。</span><span class="sxs-lookup"><span data-stu-id="1fae0-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="1fae0-109">如果您的目標是將外部傳統主機程式與配量程式結合，則此環境不適合。</span><span class="sxs-lookup"><span data-stu-id="1fae0-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="1fae0-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="1fae0-110">Prerequisites</span></span>

    - <span data-ttu-id="1fae0-111">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="1fae0-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="1fae0-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="1fae0-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="1fae0-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="1fae0-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="1fae0-114">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="1fae0-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="1fae0-115">如果在進行 `dotnet iqsharp install` 步驟期間發生錯誤，請開啟新的終端機視窗，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="1fae0-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="1fae0-116">如果仍無法解決問題，請嘗試找到已安裝的 `dotnet-iqsharp` 工具 (在 Windows 上則為 `dotnet-iqsharp.exe`)，並執行：</span><span class="sxs-lookup"><span data-stu-id="1fae0-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="1fae0-117">其中的 `/path/to/dotnet-iqsharp` 應以您檔案系統中 `dotnet-iqsharp` 工具的絕對路徑加以取代。</span><span class="sxs-lookup"><span data-stu-id="1fae0-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="1fae0-118">此工具通常位於您使用者設定檔資料夾中 `.dotnet/tools` 的下方。</span><span class="sxs-lookup"><span data-stu-id="1fae0-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="1fae0-119">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="1fae0-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="1fae0-120">執行下列命令以啟動筆記本伺服器：</span><span class="sxs-lookup"><span data-stu-id="1fae0-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="1fae0-121">若要開啟 Jupyter Notebook，請複製命令列所提供的 URL，並貼到您的瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="1fae0-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="1fae0-122">使用 Q# 核心建立 Jupyter Notebook，並將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="1fae0-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="1fae0-123">執行筆記本的此一資料格：</span><span class="sxs-lookup"><span data-stu-id="1fae0-123">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook 資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

        <span data-ttu-id="1fae0-125">您應該會在資料格的輸出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="1fae0-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="1fae0-126">在 Jupyter Notebook 中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。</span><span class="sxs-lookup"><span data-stu-id="1fae0-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="1fae0-127">在新的資料格中，使用 `%simulate` 命令來執行您剛才建立的作業 (在模擬器中)：</span><span class="sxs-lookup"><span data-stu-id="1fae0-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter Notebook 資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="1fae0-129">您應該會在畫面上看見列印的訊息，以及所叫用作業的結果 (在此我們看到空白的元組 `()`，因作業只傳回 `Unit` 型別)。</span><span class="sxs-lookup"><span data-stu-id="1fae0-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1fae0-130">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1fae0-130">Next steps</span></span>

<span data-ttu-id="1fae0-131">您已安裝 Q# Jupyter Notebook 適用的 QDK，現在您可以撰寫並執行[第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)，方法是直接在 Jupyter Notebook 環境中撰寫您的 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="1fae0-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="1fae0-132">如需更多如何使用 Q# Jupyter Notebook 的範例，請參閱：</span><span class="sxs-lookup"><span data-stu-id="1fae0-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="1fae0-133">[Q# 與 Jupyter Notebook 簡介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) \(英文\)。</span><span class="sxs-lookup"><span data-stu-id="1fae0-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="1fae0-134">在此您將找到 Q# Jupyter Notebook，其中顯示如何在此環境中使用 Q#。</span><span class="sxs-lookup"><span data-stu-id="1fae0-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="1fae0-135">[Quantum Katas](xref:microsoft.quantum.overview.katas)，這是一系列開放原始碼的自學型教學課程，含一組程式設計練習，以 Q# Jupyter Notebook 格式呈現。</span><span class="sxs-lookup"><span data-stu-id="1fae0-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="1fae0-136">[Quantum Katas 教學課程筆記本](https://github.com/microsoft/QuantumKatas#tutorial-topics)是很好的起點。</span><span class="sxs-lookup"><span data-stu-id="1fae0-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="1fae0-137">Quantum Katas 的目標是要同時讓您學會配量運算和 Q# 程式設計的要素。</span><span class="sxs-lookup"><span data-stu-id="1fae0-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="1fae0-138">這些要素是使用 Q# Jupyter Notebook 所能建立內容種類的絕佳範例。</span><span class="sxs-lookup"><span data-stu-id="1fae0-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
