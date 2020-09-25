---
title: 使用 Q# Jupyter Notebook 進行開發
description: 了解如何使用 Jupyter Notebook 建立 Q# 應用程式。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51de510907ea087d1f23d3ff65d268d6d455a493
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834307"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="5696a-103">使用 Q# Jupyter Notebook 進行開發</span><span class="sxs-lookup"><span data-stu-id="5696a-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="5696a-104">安裝 QDK 以在 Q# Jupyter Notebook 上開發 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="5696a-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="5696a-105">Jupyter Notebook 允許就地程式碼計算，連同指示、備註與其他內容。</span><span class="sxs-lookup"><span data-stu-id="5696a-105">Jupyter Notebooks allow in-place code computation alongside instructions, notes, and other content.</span></span> <span data-ttu-id="5696a-106">此環境很適合用來撰寫含內嵌說明或配量運算互動式教學課程的 Q# 程式碼。</span><span class="sxs-lookup"><span data-stu-id="5696a-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="5696a-107">以下是您開始建立自己的 Q# 筆記本時所需執行的動作。</span><span class="sxs-lookup"><span data-stu-id="5696a-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="5696a-108">安裝 IQ# Jupyter 核心</span><span class="sxs-lookup"><span data-stu-id="5696a-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="5696a-109">IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，可提供編譯和模擬 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="5696a-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="5696a-110">使用 conda 安裝 (建議做法)</span><span class="sxs-lookup"><span data-stu-id="5696a-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="5696a-111">安裝 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。</span><span class="sxs-lookup"><span data-stu-id="5696a-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="5696a-112">**注意：** 需要安裝 64 位元。</span><span class="sxs-lookup"><span data-stu-id="5696a-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="5696a-113">開啟 Anaconda 提示字元。</span><span class="sxs-lookup"><span data-stu-id="5696a-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="5696a-114">或者，您想要使用 PowerShell 或 pwsh：開啟命令介面、執行 `conda init powershell`，然後將命令介面關閉再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="5696a-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="5696a-115">執行下列命令，使用必要的套件 (包括 Jupyter Notebook 和 IQ#) 建立並啟動名為 `qsharp-env` 的新 conda 環境：</span><span class="sxs-lookup"><span data-stu-id="5696a-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="5696a-116">從相同的終端機執行 `python -c "import qsharp"`，以確認您的安裝，並將所有必要的 QDK 元件填入您的本機套件快取。</span><span class="sxs-lookup"><span data-stu-id="5696a-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="5696a-117">使用 .NET CLI 安裝 (進階做法)</span><span class="sxs-lookup"><span data-stu-id="5696a-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="5696a-118">必要條件：</span><span class="sxs-lookup"><span data-stu-id="5696a-118">Prerequisites:</span></span>

    - <span data-ttu-id="5696a-119">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="5696a-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="5696a-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="5696a-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="5696a-121">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="5696a-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="5696a-122">安裝 `Microsoft.Quantum.IQSharp` 套件。</span><span class="sxs-lookup"><span data-stu-id="5696a-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="5696a-123">如果在進行 `dotnet iqsharp install` 步驟期間發生錯誤，請開啟新的終端機視窗，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="5696a-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="5696a-124">如果仍無法解決問題，請嘗試找到已安裝的 `dotnet-iqsharp` 工具 (在 Windows 上則為 `dotnet-iqsharp.exe`)，並執行：</span><span class="sxs-lookup"><span data-stu-id="5696a-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="5696a-125">其中的 `/path/to/dotnet-iqsharp` 應以您檔案系統中 `dotnet-iqsharp` 工具的絕對路徑加以取代。</span><span class="sxs-lookup"><span data-stu-id="5696a-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="5696a-126">此工具通常位於您使用者設定檔資料夾中 `.dotnet/tools` 的下方。</span><span class="sxs-lookup"><span data-stu-id="5696a-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="5696a-127">就這麼簡單！</span><span class="sxs-lookup"><span data-stu-id="5696a-127">That's it!</span></span> <span data-ttu-id="5696a-128">您現在已有適用於 Jupyter 的 IQ# 核心，可提供從 Q# Jupyter Notebook 編譯和執行 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="5696a-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="5696a-129">建立您的第一個 Q# 筆記本</span><span class="sxs-lookup"><span data-stu-id="5696a-129">Create your first Q# notebook</span></span>

<span data-ttu-id="5696a-130">現在您已準備好要藉由撰寫和執行簡單的 Q# 作業來驗證您的 Q# Jupyter Notebook 安裝。</span><span class="sxs-lookup"><span data-stu-id="5696a-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="5696a-131">從您在安裝期間建立的環境中 (也就是您所建立的 conda 環境，或安裝 Jupyter 時所使用的 Python 環境)，執行下列命令啟動 Jupyter Notebook 伺服器：</span><span class="sxs-lookup"><span data-stu-id="5696a-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="5696a-132">如果 Jupyter Notebook 沒有在您的瀏覽器中自動開啟，請將命令列所提供的 URL 複製並貼到瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="5696a-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="5696a-133">選擇 **[新增] →Q#** ，來使用 Q# 核心建立 Jupyter Notebook，並將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="5696a-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="5696a-134">執行筆記本的此一資料格：</span><span class="sxs-lookup"><span data-stu-id="5696a-134">Run this cell of the notebook:</span></span>

    ![Jupyter Notebook 資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

    <span data-ttu-id="5696a-136">您應該會在資料格的輸出中看到 `SampleQuantumRandomNumberGenerator`。</span><span class="sxs-lookup"><span data-stu-id="5696a-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="5696a-137">在 Jupyter Notebook 中執行時，系統會編譯 Q# 程式碼，且資料格會輸出其找到的任何作業名稱。</span><span class="sxs-lookup"><span data-stu-id="5696a-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="5696a-138">在新的資料格中，使用 `%simulate` 命令來執行您剛才建立的作業 (在模擬器中)：</span><span class="sxs-lookup"><span data-stu-id="5696a-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Jupyter Notebook 資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="5696a-140">您應該會看到您叫用作業的結果。</span><span class="sxs-lookup"><span data-stu-id="5696a-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="5696a-141">在此案例中，因為您的作業會產生隨機結果，所以您會看到螢幕上列印出 `Zero` 或 `One` 。</span><span class="sxs-lookup"><span data-stu-id="5696a-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="5696a-142">如果您重複執行資料格，應該會看到這兩個結果大約是各一半的時間。</span><span class="sxs-lookup"><span data-stu-id="5696a-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5696a-143">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5696a-143">Next steps</span></span>

<span data-ttu-id="5696a-144">您已安裝 Q# Jupyter Notebook 適用的 QDK，現在您可以直接在 Jupyter Notebook 環境中撰寫 Q# 程式碼，以撰寫並執行[第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="5696a-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="5696a-145">如需更多 Q# Jupyter Notebook 的使用範例，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5696a-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="5696a-146">[Q# 與 Jupyter Notebook 簡介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="5696a-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="5696a-147">您會在這裡找到一個 Q# Jupyter Notebook，其中提供如何在 Jupyter 環境中使用 Q# 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5696a-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="5696a-148">[Quantum Katas](xref:microsoft.quantum.overview.katas)，這是一系列開放原始碼的自學型教學課程，和一組以Q# Jupyter Notebook 格式呈現的程式設計練習。</span><span class="sxs-lookup"><span data-stu-id="5696a-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="5696a-149">[Quantum Katas 教學課程筆記本](https://github.com/microsoft/QuantumKatas#tutorial-topics)是很好的起點。</span><span class="sxs-lookup"><span data-stu-id="5696a-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="5696a-150">Quantum Katas 的目標是要同時讓您學會配量運算和 Q# 程式設計的要素。</span><span class="sxs-lookup"><span data-stu-id="5696a-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="5696a-151">這些要素可充分說明使用 Q# Jupyter Notebook 所能建立的內容種類。</span><span class="sxs-lookup"><span data-stu-id="5696a-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
