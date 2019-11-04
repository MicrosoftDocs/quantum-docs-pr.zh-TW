---
title: 了解如何安裝 Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 2a098d89f13278d7137bf182a184a74afb9393be
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462863"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ff445-102">安裝 Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="ff445-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ff445-103">了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="ff445-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="ff445-104">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="ff445-104">The QDK consists of:</span></span>

- <span data-ttu-id="ff445-105">Q# 程式設計語言</span><span class="sxs-lookup"><span data-stu-id="ff445-105">the Q# programming language</span></span>
- <span data-ttu-id="ff445-106">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="ff445-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="ff445-107">(以 Python 或 .NET 語言編寫的) 主應用程式，可執行以 Q# 編寫的量子操作。</span><span class="sxs-lookup"><span data-stu-id="ff445-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="ff445-108">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="ff445-108">tools to facilitate your development</span></span>

<span data-ttu-id="ff445-109">視您選擇的開發環境而定，安裝步驟會有所不同。</span><span class="sxs-lookup"><span data-stu-id="ff445-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="ff445-110">請從下列章節選擇您的環境。</span><span class="sxs-lookup"><span data-stu-id="ff445-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="ff445-111">使用 Python 來開發</span><span class="sxs-lookup"><span data-stu-id="ff445-111">Develop with Python</span></span>

<span data-ttu-id="ff445-112">適用於 Python 的 qsharp 套件可讓您輕鬆地從 Python 內模擬 Q# 作業和函式。</span><span class="sxs-lookup"><span data-stu-id="ff445-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="ff445-113">IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的擴充功能，提供編譯和模擬 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="ff445-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="ff445-114">先決條件</span><span class="sxs-lookup"><span data-stu-id="ff445-114">Pre-requisites</span></span>

    - <span data-ttu-id="ff445-115">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ff445-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="ff445-116">[PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員</span><span class="sxs-lookup"><span data-stu-id="ff445-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="ff445-117">.NET Core SDK 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ff445-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ff445-118">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="ff445-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ff445-119">安裝 `qsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="ff445-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="ff445-120">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="ff445-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff445-121">建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="ff445-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="ff445-122">建立名為 `hello_world.py` 的 Python 程式，以呼叫 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="ff445-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="ff445-123">執行程式：</span><span class="sxs-lookup"><span data-stu-id="ff445-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="ff445-124">驗證輸出。</span><span class="sxs-lookup"><span data-stu-id="ff445-124">Verify the output.</span></span> <span data-ttu-id="ff445-125">您的程式應該會輸出下列幾行：</span><span class="sxs-lookup"><span data-stu-id="ff445-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="ff445-126">使用 Jupyter 筆記本來開發</span><span class="sxs-lookup"><span data-stu-id="ff445-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="ff445-127">Jupyter Notebook 是學術環境、科學實驗室和線上共同作業程式設計的最愛，提供就地程式碼執行，包括 Q# 程式碼，以及各項指示、附註和其他內容。</span><span class="sxs-lookup"><span data-stu-id="ff445-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="ff445-128">以下是開始建立您自己的 Q# 筆記本所需的準備工作。</span><span class="sxs-lookup"><span data-stu-id="ff445-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="ff445-129">IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="ff445-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="ff445-130">先決條件</span><span class="sxs-lookup"><span data-stu-id="ff445-130">Pre-requisites</span></span>

    - <span data-ttu-id="ff445-131">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ff445-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="ff445-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ff445-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="ff445-133">.NET Core SDK 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ff445-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ff445-134">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="ff445-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ff445-135">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="ff445-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff445-136">執行下列命令以啟動筆記本伺服器：</span><span class="sxs-lookup"><span data-stu-id="ff445-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="ff445-137">瀏覽至命令列上顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="ff445-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="ff445-138">例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="ff445-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="ff445-139">使用 Q# 核心建立 Jupyter 筆記本，並將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="ff445-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="ff445-140">執行筆記本的此一資料格：</span><span class="sxs-lookup"><span data-stu-id="ff445-140">Run this cell of the notebook:</span></span>

        ![Jupyter 筆記本資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

        <span data-ttu-id="ff445-142">您應該會在資料格的輸出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="ff445-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="ff445-143">在 Jupyter 筆記本中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。</span><span class="sxs-lookup"><span data-stu-id="ff445-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="ff445-144">在新的資料格中，使用 `%simulate` magic 在剛剛建立的作業量子電腦中模擬執行：</span><span class="sxs-lookup"><span data-stu-id="ff445-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Jupyter 筆記本資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="ff445-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span><span class="sxs-lookup"><span data-stu-id="ff445-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="ff445-147">透過 Visual Studio，在 Windows 上使用 C# 來開發</span><span class="sxs-lookup"><span data-stu-id="ff445-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="ff445-148">Visual Studio 提供進階的環境來開發 Q# 程式，提供像是程式碼完成和語法反白顯示等實用功能，引導開發人員建置其應用程式。</span><span class="sxs-lookup"><span data-stu-id="ff445-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="ff445-149">Q# Visual Studio 擴充功能包含適用於 Q# 檔案的範本、專案以及語法反白顯示和 IntelliSense 支援。</span><span class="sxs-lookup"><span data-stu-id="ff445-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="ff445-150">先決條件</span><span class="sxs-lookup"><span data-stu-id="ff445-150">Pre-requisites</span></span>

    - <span data-ttu-id="ff445-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載</span><span class="sxs-lookup"><span data-stu-id="ff445-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="ff445-152">安裝 Q# Visual Studio 擴充功能</span><span class="sxs-lookup"><span data-stu-id="ff445-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ff445-153">下載 [Visual Studio 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="ff445-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="ff445-154">將擴充功能新增至 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff445-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="ff445-155">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="ff445-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff445-156">建立新的 C# 應用程式</span><span class="sxs-lookup"><span data-stu-id="ff445-156">Create a new Q# application</span></span>

        - <span data-ttu-id="ff445-157">移至 [檔案]   -> [新增]   -> [專案] </span><span class="sxs-lookup"><span data-stu-id="ff445-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="ff445-158">在搜尋方塊中輸入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="ff445-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="ff445-159">選取 [Q# 應用程式] </span><span class="sxs-lookup"><span data-stu-id="ff445-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="ff445-160">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="ff445-160">Select **Next**</span></span>
        - <span data-ttu-id="ff445-161">選擇應用程式的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="ff445-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="ff445-162">選取 [建立] </span><span class="sxs-lookup"><span data-stu-id="ff445-162">Select **Create**</span></span>

    - <span data-ttu-id="ff445-163">檢查專案</span><span class="sxs-lookup"><span data-stu-id="ff445-163">Inspect the project</span></span>

        <span data-ttu-id="ff445-164">您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。</span><span class="sxs-lookup"><span data-stu-id="ff445-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="ff445-165">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="ff445-165">Run the application</span></span>

        - <span data-ttu-id="ff445-166">選取 [偵錯]   -> [啟動但不偵錯] </span><span class="sxs-lookup"><span data-stu-id="ff445-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="ff445-167">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="ff445-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="ff445-168">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ff445-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="ff445-169">使用 Visual Studio Code，透過 C# 開發</span><span class="sxs-lookup"><span data-stu-id="ff445-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="ff445-170">Visual Studio Code (VS Code) 提供進階的環境跨多個電腦環境來開發 Q# 程式，包括 Windows、Linux 和 Mac，提供像是程式碼完成和語法反白顯示等實用功能，引導開發人員建置其應用程式。</span><span class="sxs-lookup"><span data-stu-id="ff445-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="ff445-171">Q# VS Code 擴充功能包含語法反白顯示，以及 Q# 程式碼片段。</span><span class="sxs-lookup"><span data-stu-id="ff445-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="ff445-172">先決條件</span><span class="sxs-lookup"><span data-stu-id="ff445-172">Pre-requisites</span></span>

   - [<span data-ttu-id="ff445-173">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="ff445-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="ff445-174">.NET Core SDK 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ff445-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ff445-175">安裝 Quantum VS Code 擴充功能</span><span class="sxs-lookup"><span data-stu-id="ff445-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ff445-176">安裝 [VS Code 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="ff445-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="ff445-177">安裝 Quantum 專案範本：</span><span class="sxs-lookup"><span data-stu-id="ff445-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="ff445-178">移至 [檢視]   -> [命令選擇區] </span><span class="sxs-lookup"><span data-stu-id="ff445-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ff445-179">選取 [Q#:  安裝專案範本]</span><span class="sxs-lookup"><span data-stu-id="ff445-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="ff445-180">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="ff445-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ff445-181">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="ff445-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff445-182">建立新專案：</span><span class="sxs-lookup"><span data-stu-id="ff445-182">Create a new project:</span></span>

        - <span data-ttu-id="ff445-183">移至 [檢視]   -> [命令選擇區] </span><span class="sxs-lookup"><span data-stu-id="ff445-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="ff445-184">選取 [Q#:  建立新專案]</span><span class="sxs-lookup"><span data-stu-id="ff445-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="ff445-185">瀏覽至您要建立應用程式的檔案系統位置</span><span class="sxs-lookup"><span data-stu-id="ff445-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="ff445-186">專案建立好之後，請按一下 [開啟新專案...]  按鈕</span><span class="sxs-lookup"><span data-stu-id="ff445-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="ff445-187">執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="ff445-187">Run the application:</span></span>

        - <span data-ttu-id="ff445-188">移至 [偵錯]   -> [啟動但不偵錯] </span><span class="sxs-lookup"><span data-stu-id="ff445-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="ff445-189">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ff445-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="ff445-190">Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="ff445-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="ff445-191">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="ff445-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="ff445-192">透過 `dotnet` 命令列工具，使用 C# 來開發</span><span class="sxs-lookup"><span data-stu-id="ff445-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="ff445-193">當然，您也可以從命令列建置並執行 Q# 程式，只要安裝 .NET Core SDK 和 QDK 專案範本即可。</span><span class="sxs-lookup"><span data-stu-id="ff445-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="ff445-194">先決條件</span><span class="sxs-lookup"><span data-stu-id="ff445-194">Pre-requisites</span></span>

    - [<span data-ttu-id="ff445-195">.NET Core SDK 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ff445-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ff445-196">安裝適用於 .NET 的 Quantum 專案範本</span><span class="sxs-lookup"><span data-stu-id="ff445-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="ff445-197">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="ff445-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ff445-198">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="ff445-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ff445-199">建立新的應用程式</span><span class="sxs-lookup"><span data-stu-id="ff445-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="ff445-200">瀏覽至新的應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="ff445-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="ff445-201">您應該會看到系統建立了兩個檔案，以及應用程式的專案檔：Q# 檔案 (`Operation.qs`) 和 C# 主機檔案 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="ff445-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="ff445-202">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="ff445-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="ff445-203">您應該會看見下列輸出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ff445-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="ff445-204">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ff445-204">What's next?</span></span>

<span data-ttu-id="ff445-205">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="ff445-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
