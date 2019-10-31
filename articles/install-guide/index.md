---
title: 了解如何安裝 Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035290"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="4efc9-102">安裝 Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="4efc9-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="4efc9-103">了解如何安裝 Microsoft Quantum Development Kit (QDK)，以便開始進行量子程式設計。</span><span class="sxs-lookup"><span data-stu-id="4efc9-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="4efc9-104">QDK 是由下列各項所組成的：</span><span class="sxs-lookup"><span data-stu-id="4efc9-104">The QDK consists of:</span></span>

- <span data-ttu-id="4efc9-105">Q# 程式設計語言</span><span class="sxs-lookup"><span data-stu-id="4efc9-105">the Q# programming language</span></span>
- <span data-ttu-id="4efc9-106">可在 Q# 中抽象呈現複雜功能的一組程式庫</span><span class="sxs-lookup"><span data-stu-id="4efc9-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="4efc9-107">(以 Python 或 .NET 語言編寫的) 主應用程式，可執行以 Q# 編寫的量子操作。</span><span class="sxs-lookup"><span data-stu-id="4efc9-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="4efc9-108">用來協助您進行開發的工具</span><span class="sxs-lookup"><span data-stu-id="4efc9-108">tools to facilitate your development</span></span>

<span data-ttu-id="4efc9-109">視您選擇的開發環境而定，安裝步驟會有所不同。</span><span class="sxs-lookup"><span data-stu-id="4efc9-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="4efc9-110">請從下列章節選擇您的環境。</span><span class="sxs-lookup"><span data-stu-id="4efc9-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="4efc9-111">使用 Python 來開發</span><span class="sxs-lookup"><span data-stu-id="4efc9-111">Develop with Python</span></span>

1. <span data-ttu-id="4efc9-112">先決條件</span><span class="sxs-lookup"><span data-stu-id="4efc9-112">Pre-requisites</span></span>

    - <span data-ttu-id="4efc9-113">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4efc9-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="4efc9-114">[PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員</span><span class="sxs-lookup"><span data-stu-id="4efc9-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="4efc9-115">.NET Core SDK 2.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4efc9-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4efc9-116">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="4efc9-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="4efc9-117">安裝 `qsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="4efc9-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="4efc9-118">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="4efc9-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4efc9-119">建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="4efc9-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="4efc9-120">建立名為 `hello_world.py` 的 Python 程式，以呼叫 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="4efc9-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="4efc9-121">執行程式：</span><span class="sxs-lookup"><span data-stu-id="4efc9-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="4efc9-122">驗證輸出。</span><span class="sxs-lookup"><span data-stu-id="4efc9-122">Verify the output.</span></span> <span data-ttu-id="4efc9-123">您的程式應該會輸出下列幾行：</span><span class="sxs-lookup"><span data-stu-id="4efc9-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="4efc9-124">使用 Jupyter 筆記本來開發</span><span class="sxs-lookup"><span data-stu-id="4efc9-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="4efc9-125">先決條件</span><span class="sxs-lookup"><span data-stu-id="4efc9-125">Pre-requisites</span></span>

    - <span data-ttu-id="4efc9-126">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4efc9-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="4efc9-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="4efc9-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="4efc9-128">.NET Core SDK 2.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4efc9-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4efc9-129">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="4efc9-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="4efc9-130">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="4efc9-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4efc9-131">執行下列命令以啟動筆記本伺服器：</span><span class="sxs-lookup"><span data-stu-id="4efc9-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="4efc9-132">瀏覽至命令列上顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="4efc9-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="4efc9-133">例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="4efc9-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="4efc9-134">使用 Q# 核心建立 Jupyter 筆記本，並將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="4efc9-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="4efc9-135">執行筆記本的此一資料格：</span><span class="sxs-lookup"><span data-stu-id="4efc9-135">Run this cell of the notebook:</span></span>

        ![Jupyter 筆記本資料格](~/media/install-guide-jupyter.png)

        <span data-ttu-id="4efc9-137">您應該會在資料格的輸出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="4efc9-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="4efc9-138">在 Jupyter 筆記本中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。</span><span class="sxs-lookup"><span data-stu-id="4efc9-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="4efc9-139">透過 Visual Studio，在 Windows 上使用 C# 來開發</span><span class="sxs-lookup"><span data-stu-id="4efc9-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="4efc9-140">先決條件</span><span class="sxs-lookup"><span data-stu-id="4efc9-140">Pre-requisites</span></span>

    - <span data-ttu-id="4efc9-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載</span><span class="sxs-lookup"><span data-stu-id="4efc9-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="4efc9-142">安裝 Q# Visual Studio 擴充功能</span><span class="sxs-lookup"><span data-stu-id="4efc9-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="4efc9-143">下載 [Visual Studio 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="4efc9-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="4efc9-144">將擴充功能新增至 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4efc9-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="4efc9-145">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="4efc9-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4efc9-146">建立新的 C# 應用程式</span><span class="sxs-lookup"><span data-stu-id="4efc9-146">Create a new Q# application</span></span>

        - <span data-ttu-id="4efc9-147">移至 [檔案]   -> [新增]   -> [專案] </span><span class="sxs-lookup"><span data-stu-id="4efc9-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="4efc9-148">在搜尋方塊中輸入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="4efc9-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="4efc9-149">選取 [Q# 應用程式] </span><span class="sxs-lookup"><span data-stu-id="4efc9-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="4efc9-150">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="4efc9-150">Select **Next**</span></span>
        - <span data-ttu-id="4efc9-151">選擇應用程式的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="4efc9-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="4efc9-152">選取 [建立] </span><span class="sxs-lookup"><span data-stu-id="4efc9-152">Select **Create**</span></span>

    - <span data-ttu-id="4efc9-153">檢查專案</span><span class="sxs-lookup"><span data-stu-id="4efc9-153">Inspect the project</span></span>

        <span data-ttu-id="4efc9-154">您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。</span><span class="sxs-lookup"><span data-stu-id="4efc9-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="4efc9-155">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="4efc9-155">Run the application</span></span>

        - <span data-ttu-id="4efc9-156">選取 [偵錯]   -> [啟動但不偵錯] </span><span class="sxs-lookup"><span data-stu-id="4efc9-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4efc9-157">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="4efc9-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="4efc9-158">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="4efc9-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="4efc9-159">透過 VS Code，使用 C# 來開發</span><span class="sxs-lookup"><span data-stu-id="4efc9-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="4efc9-160">先決條件</span><span class="sxs-lookup"><span data-stu-id="4efc9-160">Pre-requisites</span></span>

   - [<span data-ttu-id="4efc9-161">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="4efc9-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="4efc9-162">.NET Core SDK 2.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4efc9-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4efc9-163">安裝 Quantum VS Code 擴充功能</span><span class="sxs-lookup"><span data-stu-id="4efc9-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="4efc9-164">安裝 [VS Code 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="4efc9-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="4efc9-165">安裝 Quantum 專案範本：</span><span class="sxs-lookup"><span data-stu-id="4efc9-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="4efc9-166">移至 [檢視]   -> [命令選擇區] </span><span class="sxs-lookup"><span data-stu-id="4efc9-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="4efc9-167">選取 [Q#:  安裝專案範本]</span><span class="sxs-lookup"><span data-stu-id="4efc9-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="4efc9-168">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="4efc9-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4efc9-169">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="4efc9-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4efc9-170">建立新專案：</span><span class="sxs-lookup"><span data-stu-id="4efc9-170">Create a new project:</span></span>

        - <span data-ttu-id="4efc9-171">移至 [檢視]   -> [命令選擇區] </span><span class="sxs-lookup"><span data-stu-id="4efc9-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="4efc9-172">選取 [Q#:  建立新專案]</span><span class="sxs-lookup"><span data-stu-id="4efc9-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="4efc9-173">瀏覽至您要建立應用程式的檔案系統位置</span><span class="sxs-lookup"><span data-stu-id="4efc9-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="4efc9-174">專案建立好之後，請按一下 [開啟新專案...]  按鈕</span><span class="sxs-lookup"><span data-stu-id="4efc9-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="4efc9-175">執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="4efc9-175">Run the application:</span></span>

        - <span data-ttu-id="4efc9-176">移至 [偵錯]   -> [啟動但不偵錯] </span><span class="sxs-lookup"><span data-stu-id="4efc9-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="4efc9-177">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4efc9-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="4efc9-178">Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="4efc9-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="4efc9-179">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="4efc9-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="4efc9-180">透過 `dotnet` 命令列工具，使用 C# 來開發</span><span class="sxs-lookup"><span data-stu-id="4efc9-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="4efc9-181">先決條件</span><span class="sxs-lookup"><span data-stu-id="4efc9-181">Pre-requisites</span></span>

    - [<span data-ttu-id="4efc9-182">.NET Core SDK 2.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4efc9-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="4efc9-183">安裝適用於 .NET 的 Quantum 專案範本</span><span class="sxs-lookup"><span data-stu-id="4efc9-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="4efc9-184">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="4efc9-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="4efc9-185">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="4efc9-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4efc9-186">建立新的應用程式</span><span class="sxs-lookup"><span data-stu-id="4efc9-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="4efc9-187">瀏覽至新的應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="4efc9-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="4efc9-188">您應該會看到系統建立了兩個檔案，以及應用程式的專案檔：Q# 檔案 (`Operation.qs`) 和 C# 主機檔案 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="4efc9-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="4efc9-189">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="4efc9-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="4efc9-190">您應該會看見下列輸出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4efc9-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="4efc9-191">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4efc9-191">What's next?</span></span>

<span data-ttu-id="4efc9-192">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="4efc9-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
