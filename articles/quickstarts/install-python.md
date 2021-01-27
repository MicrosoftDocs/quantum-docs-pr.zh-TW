---
title: 使用 Q# 和 Python 進行開發
description: 了解如何使用 Python 建立 Q# 應用程式。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ec40b6f1b7a8d9144860e3b8cfd554eb51bae81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844278"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="d177d-103">使用 Q# 和 Python 進行開發</span><span class="sxs-lookup"><span data-stu-id="d177d-103">Develop with Q# and Python</span></span>

<span data-ttu-id="d177d-104">安裝 QDK 以開發用來呼叫 Q# 作業的 Python 主機程式。</span><span class="sxs-lookup"><span data-stu-id="d177d-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="d177d-105">安裝 `qsharp` Python 套件</span><span class="sxs-lookup"><span data-stu-id="d177d-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="d177d-106">使用 conda 安裝 (建議做法)</span><span class="sxs-lookup"><span data-stu-id="d177d-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="d177d-107">安裝 [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 或 [Anaconda](https://www.anaconda.com/products/individual#Downloads)。</span><span class="sxs-lookup"><span data-stu-id="d177d-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="d177d-108">**注意：** 需要安裝 64 位元。</span><span class="sxs-lookup"><span data-stu-id="d177d-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="d177d-109">開啟 Anaconda 提示字元。</span><span class="sxs-lookup"><span data-stu-id="d177d-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="d177d-110">或者，您想要使用 PowerShell 或 pwsh：開啟命令介面、執行 `conda init powershell`，然後將命令介面關閉再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="d177d-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="d177d-111">執行下列命令，使用必要的套件 (包括 Jupyter Notebook 和 IQ#) 建立並啟動名為 `qsharp-env` 的新 conda 環境：</span><span class="sxs-lookup"><span data-stu-id="d177d-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="d177d-112">從相同的終端機執行 `python -c "import qsharp"`，以確認您的安裝，並將所有必要的 QDK 元件填入您的本機套件快取。</span><span class="sxs-lookup"><span data-stu-id="d177d-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="d177d-113">使用 .NET CLI 和 pip 安裝 (進階做法)</span><span class="sxs-lookup"><span data-stu-id="d177d-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="d177d-114">必要條件：</span><span class="sxs-lookup"><span data-stu-id="d177d-114">Prerequisites:</span></span>

    - <span data-ttu-id="d177d-115">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d177d-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="d177d-116">[PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員</span><span class="sxs-lookup"><span data-stu-id="d177d-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="d177d-117">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="d177d-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="d177d-118">安裝 `qsharp` 套件，此為允許 Q# 和 Python 之間互通的 Python 套件。</span><span class="sxs-lookup"><span data-stu-id="d177d-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="d177d-119">安裝 IQ#，此為 Jupyter 與 Python 所使用的核心，可提供用以編譯與執行 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="d177d-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="d177d-120">如果在進行 `dotnet iqsharp install` 步驟期間發生錯誤，請開啟新的終端機視窗，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="d177d-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="d177d-121">如果仍無法解決問題，請嘗試找到已安裝的 `dotnet-iqsharp` 工具 (在 Windows 上則為 `dotnet-iqsharp.exe`)，並執行：</span><span class="sxs-lookup"><span data-stu-id="d177d-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="d177d-122">其中的 `/path/to/dotnet-iqsharp` 應以您檔案系統中 `dotnet-iqsharp` 工具的絕對路徑加以取代。</span><span class="sxs-lookup"><span data-stu-id="d177d-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="d177d-123">此工具通常位於您使用者設定檔資料夾中 `.dotnet/tools` 的下方。</span><span class="sxs-lookup"><span data-stu-id="d177d-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="d177d-124">\*\*_</span><span class="sxs-lookup"><span data-stu-id="d177d-124">\*\*_</span></span>

<span data-ttu-id="d177d-125">就這麼簡單！</span><span class="sxs-lookup"><span data-stu-id="d177d-125">That's it!</span></span> <span data-ttu-id="d177d-126">您現在已有 `qsharp` Python 套件和適用於 Jupyter 的 IQ# 核心，可提供從 Python 編譯和執行 Q# 作業的核心功能，並可讓您使用 Q# Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="d177d-126">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="d177d-127">選擇您的整合式開發環境 (IDE)</span><span class="sxs-lookup"><span data-stu-id="d177d-127">Choose your IDE</span></span>

<span data-ttu-id="d177d-128">雖然您可以在任何 IDE 中將 Q# 搭配 Python 使用，但強烈建議使用 Q# + Python 應用程式適用的 Visual Studio Code (VS Code) IDE。</span><span class="sxs-lookup"><span data-stu-id="d177d-128">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="d177d-129">有了 QDK Visual Studio Code 擴充功能，您就可以存取更豐富的功能，例如警告、語法反白顯示、專案範本等等。</span><span class="sxs-lookup"><span data-stu-id="d177d-129">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="d177d-130">如果您想要使用 VS Code：</span><span class="sxs-lookup"><span data-stu-id="d177d-130">If you would like to use VS Code:</span></span>

- <span data-ttu-id="d177d-131">安裝 [VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac)。</span><span class="sxs-lookup"><span data-stu-id="d177d-131">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="d177d-132">安裝 [VS Code 適用的 QDK 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="d177d-132">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="d177d-133">如果您想要使用其他的編輯器，遵循上述指示就夠了。</span><span class="sxs-lookup"><span data-stu-id="d177d-133">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="d177d-134">撰寫您的第一個 Q# 程式</span><span class="sxs-lookup"><span data-stu-id="d177d-134">Write your first Q# program</span></span>

<span data-ttu-id="d177d-135">現在您已準備好要藉由撰寫和執行簡單的 Q# 程式來確認您的 `qsharp` Python 套件安裝。</span><span class="sxs-lookup"><span data-stu-id="d177d-135">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="d177d-136">建立名為 `Operation.qs` 的檔案，並新增下列程式碼，以建立最基本的 Q# 作業：</span><span class="sxs-lookup"><span data-stu-id="d177d-136">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="d177d-137">在與 `Operation.qs` 相同的資料夾中，建立名為 `host.py` 的 Python 程式以模擬 Q# `SampleQuantumRandomNumberGenerator()` 作業：</span><span class="sxs-lookup"><span data-stu-id="d177d-137">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="d177d-138">從您在安裝期間建立的環境中 (也就是您安裝 `qsharp` 的 conda 環境或 Python 環境) 執行程式：</span><span class="sxs-lookup"><span data-stu-id="d177d-138">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="d177d-139">您應該會看到您叫用作業的結果。</span><span class="sxs-lookup"><span data-stu-id="d177d-139">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="d177d-140">在此案例中，因為您的作業會產生隨機結果，所以您會看到螢幕上列印出 `0` 或 `1` 。</span><span class="sxs-lookup"><span data-stu-id="d177d-140">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="d177d-141">如果您重複執行程式，應該會看到這兩個結果大約是各一半的時間。</span><span class="sxs-lookup"><span data-stu-id="d177d-141">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> <span data-ttu-id="d177d-142">_ Python 程式碼只是一般的 Python 程式。</span><span class="sxs-lookup"><span data-stu-id="d177d-142">_ The Python code is just a normal Python program.</span></span> <span data-ttu-id="d177d-143">您可以使用任何 Python 環境 (包括以 Python 為基礎的 Jupyter Notebook) 來撰寫 Python 程式並呼叫 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="d177d-143">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="d177d-144">Python 程式可以從與 Python 程式碼本身相同的資料夾中包含的任何 .qs 檔案匯入 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="d177d-144">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d177d-145">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d177d-145">Next steps</span></span>

<span data-ttu-id="d177d-146">您已在慣用環境中測試了 Quantum 開發套件，接下來可以遵循此指南開始撰寫及執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="d177d-146">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
