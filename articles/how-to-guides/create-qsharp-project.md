---
title: '瞭解如何使用量子開發工具組（QDK）建立問 # 專案'
description: '使用您選擇的開發環境中的 QDK 和 Q #，初始化專案以進行量子開發'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444169"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="bdf23-103">在開發環境中建立 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="bdf23-104">瞭解如何使用 QDK 建立 Q # 專案。</span><span class="sxs-lookup"><span data-stu-id="bdf23-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="bdf23-105">Q # 專案包含包含量子代碼的 Q # 檔案，以及執行配量程式的主機程式。</span><span class="sxs-lookup"><span data-stu-id="bdf23-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="bdf23-106">您可以在 .NET 語言（例如C#）或 Python 中撰寫主機程式。</span><span class="sxs-lookup"><span data-stu-id="bdf23-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="bdf23-107">您也可以使用 IQ # kernel 在 Jupyter 筆記本中執行 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="bdf23-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="bdf23-108">從下列各節選擇您的開發環境和語言：</span><span class="sxs-lookup"><span data-stu-id="bdf23-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="bdf23-109">Python</span><span class="sxs-lookup"><span data-stu-id="bdf23-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="bdf23-110">Jupyter 筆記本</span><span class="sxs-lookup"><span data-stu-id="bdf23-110">Jupyter notebooks</span></span>](#create-a-jupyter-notebook-project)
* [<span data-ttu-id="bdf23-111">C#使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bdf23-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="bdf23-112">C#使用 VS Code</span><span class="sxs-lookup"><span data-stu-id="bdf23-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="bdf23-113">C#使用命令列</span><span class="sxs-lookup"><span data-stu-id="bdf23-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="bdf23-114">建立 Python 專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-114">Create a Python project</span></span>

1. <span data-ttu-id="bdf23-115">先決條件</span><span class="sxs-lookup"><span data-stu-id="bdf23-115">Pre-requisites</span></span>

     * <span data-ttu-id="bdf23-116">[適用于 Python 的量子開發工具組](xref:microsoft.quantum.install#develop-with-python)</span><span class="sxs-lookup"><span data-stu-id="bdf23-116">The [Quantum Development Kit for Python](xref:microsoft.quantum.install#develop-with-python)</span></span>

1. <span data-ttu-id="bdf23-117">為您的專案建立資料夾，並流覽至該資料夾</span><span class="sxs-lookup"><span data-stu-id="bdf23-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="bdf23-118">建立名為 `Operation.qs`的 Q # 檔案，並將您的 Q # 程式碼加入其中。</span><span class="sxs-lookup"><span data-stu-id="bdf23-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="bdf23-119">例如：</span><span class="sxs-lookup"><span data-stu-id="bdf23-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="bdf23-120">建立名為 `host.py` 的 python 主機檔案，以呼叫您的 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="bdf23-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="bdf23-121">例如：</span><span class="sxs-lookup"><span data-stu-id="bdf23-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="bdf23-122">執行程式：</span><span class="sxs-lookup"><span data-stu-id="bdf23-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="bdf23-123">驗證輸出。</span><span class="sxs-lookup"><span data-stu-id="bdf23-123">Verify the output.</span></span> <span data-ttu-id="bdf23-124">您的程式應該會輸出下列幾行：</span><span class="sxs-lookup"><span data-stu-id="bdf23-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="bdf23-125">您現在可以繼續開發您的「量子」程式。</span><span class="sxs-lookup"><span data-stu-id="bdf23-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-jupyter-notebook-project"></a><span data-ttu-id="bdf23-126">建立 Jupyter Notebook 專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-126">Create a Jupyter Notebook project</span></span>

1. <span data-ttu-id="bdf23-127">先決條件</span><span class="sxs-lookup"><span data-stu-id="bdf23-127">Pre-requisites</span></span>

    * <span data-ttu-id="bdf23-128">[適用于 Jupyter 筆記本的量子開發工具組](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span><span class="sxs-lookup"><span data-stu-id="bdf23-128">The [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span></span>

1. <span data-ttu-id="bdf23-129">執行下列命令以啟動筆記本伺服器：</span><span class="sxs-lookup"><span data-stu-id="bdf23-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="bdf23-130">瀏覽至命令列上顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="bdf23-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="bdf23-131">例如：[http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="bdf23-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="bdf23-132">Jupyter 頁面會出現在瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="bdf23-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="bdf23-133">在 檔案 索引卷**標上，** 選取 **新增** > **q #** ，以使用 Q # 核心來建立 Jupyter 筆記本。</span><span class="sxs-lookup"><span data-stu-id="bdf23-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="bdf23-134">將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="bdf23-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="bdf23-135">選取要執行筆記本的資料**格** > **執行的單元**格。</span><span class="sxs-lookup"><span data-stu-id="bdf23-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="bdf23-136">`SayHello` 很快就會顯示在資料格的輸出中：</span><span class="sxs-lookup"><span data-stu-id="bdf23-136">`SayHello` will soon appear in the cell output:</span></span>

    ![使用 Q # 程式碼的 Jupyter 筆記本儲存格](~/media/install-guide-jupyter.png)

    <span data-ttu-id="bdf23-138">在 Jupyter 筆記本中執行時，會編譯 Q # 程式碼，而筆記本會輸出找到的作業名稱。</span><span class="sxs-lookup"><span data-stu-id="bdf23-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="bdf23-139">在新的資料格中，使用 `%simulate` 魔術來模擬您剛才建立之作業的量子電腦中的執行：</span><span class="sxs-lookup"><span data-stu-id="bdf23-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![具有% 模擬魔術的 Jupyter 筆記本資料格](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="bdf23-141">您應該會在畫面上看到列印的訊息，以及您叫用之作業的結果（在此案例中為空白）。</span><span class="sxs-lookup"><span data-stu-id="bdf23-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="bdf23-142">您現在可以新增其他的 Q # 作業，以繼續進行您的量子開發。</span><span class="sxs-lookup"><span data-stu-id="bdf23-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="bdf23-143">使用 Visual Studio C#在 Windows 上建立專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="bdf23-144">先決條件</span><span class="sxs-lookup"><span data-stu-id="bdf23-144">Pre-requisites</span></span>

    * <span data-ttu-id="bdf23-145">[Visual Studio 的量子開發工具組](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="bdf23-145">The [Quantum Development Kit for Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span></span>

1. <span data-ttu-id="bdf23-146">建立新的 C# 應用程式</span><span class="sxs-lookup"><span data-stu-id="bdf23-146">Create a new Q# application</span></span>

    * <span data-ttu-id="bdf23-147">移至 [檔案] -> [新增] -> [專案]</span><span class="sxs-lookup"><span data-stu-id="bdf23-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="bdf23-148">在搜尋方塊中輸入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="bdf23-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="bdf23-149">選取 [Q# 應用程式]</span><span class="sxs-lookup"><span data-stu-id="bdf23-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="bdf23-150">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="bdf23-150">Select **Next**</span></span>
    * <span data-ttu-id="bdf23-151">選擇應用程式的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="bdf23-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="bdf23-152">選取 [建立]</span><span class="sxs-lookup"><span data-stu-id="bdf23-152">Select **Create**</span></span>

1. <span data-ttu-id="bdf23-153">檢查專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-153">Inspect the project</span></span>

    <span data-ttu-id="bdf23-154">您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。</span><span class="sxs-lookup"><span data-stu-id="bdf23-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="bdf23-155">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="bdf23-155">Run the application</span></span>

    * <span data-ttu-id="bdf23-156">選取 [偵錯] -> [啟動但不偵錯]</span><span class="sxs-lookup"><span data-stu-id="bdf23-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="bdf23-157">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="bdf23-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="bdf23-158">您現在可以使用 Visual Studio 繼續進行量子開發</span><span class="sxs-lookup"><span data-stu-id="bdf23-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="bdf23-159">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="bdf23-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="bdf23-160">使用 VS Code C#建立專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="bdf23-161">先決條件</span><span class="sxs-lookup"><span data-stu-id="bdf23-161">Pre-requisites</span></span>

    * <span data-ttu-id="bdf23-162">[VS Code 的量子開發工具組](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span><span class="sxs-lookup"><span data-stu-id="bdf23-162">The [Quantum Development Kit for VS Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span></span>

1. <span data-ttu-id="bdf23-163">建立新專案：</span><span class="sxs-lookup"><span data-stu-id="bdf23-163">Create a new project:</span></span>

    * <span data-ttu-id="bdf23-164">移至 [檢視] -> [命令選擇區]</span><span class="sxs-lookup"><span data-stu-id="bdf23-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="bdf23-165">選取 [ **Q #：建立新專案**]</span><span class="sxs-lookup"><span data-stu-id="bdf23-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="bdf23-166">瀏覽至您要建立應用程式的檔案系統位置</span><span class="sxs-lookup"><span data-stu-id="bdf23-166">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="bdf23-167">專案建立好之後，請按一下 [開啟新專案...] 按鈕</span><span class="sxs-lookup"><span data-stu-id="bdf23-167">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="bdf23-168">執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="bdf23-168">Run the application:</span></span>

    * <span data-ttu-id="bdf23-169">移至 [偵錯] -> [啟動但不偵錯]</span><span class="sxs-lookup"><span data-stu-id="bdf23-169">Go to **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="bdf23-170">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="bdf23-170">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="bdf23-171">您現在可以使用 Visual Studio Code 繼續進行量子開發。</span><span class="sxs-lookup"><span data-stu-id="bdf23-171">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="bdf23-172">Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="bdf23-172">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="bdf23-173">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="bdf23-173">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="bdf23-174">使用 `dotnet` C#命令列工具建立專案</span><span class="sxs-lookup"><span data-stu-id="bdf23-174">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="bdf23-175">先決條件</span><span class="sxs-lookup"><span data-stu-id="bdf23-175">Pre-requisites</span></span>

    * <span data-ttu-id="bdf23-176">[命令列的量子開發工具組](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span><span class="sxs-lookup"><span data-stu-id="bdf23-176">The [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span></span>

1. <span data-ttu-id="bdf23-177">建立新的應用程式</span><span class="sxs-lookup"><span data-stu-id="bdf23-177">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="bdf23-178">瀏覽至新的應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="bdf23-178">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="bdf23-179">您應該會看到系統建立了兩個檔案，以及應用程式的專案檔：Q# 檔案 (`Operation.qs`) 和 C# 主機檔案 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="bdf23-179">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="bdf23-180">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="bdf23-180">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="bdf23-181">您應該會看見下列輸出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="bdf23-181">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="bdf23-182">您現在可以使用命令列工具繼續進行您的量子開發。</span><span class="sxs-lookup"><span data-stu-id="bdf23-182">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="bdf23-183">接下來呢？</span><span class="sxs-lookup"><span data-stu-id="bdf23-183">What's next?</span></span>

<span data-ttu-id="bdf23-184">現在您已在慣用的環境中建立專案，您可以繼續進行您的量子開發。</span><span class="sxs-lookup"><span data-stu-id="bdf23-184">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
