---
title: '使用 Q # + 進行開發C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831013"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="47e07-102">使用 Q # + 進行開發C#</span><span class="sxs-lookup"><span data-stu-id="47e07-102">Develop with Q# + C#</span></span>

<span data-ttu-id="47e07-103">安裝 QDK 以開發C#主機程式，以呼叫 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="47e07-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="47e07-104">問 # 的設計可與 .NET 語言搭配使用，特別是C#。</span><span class="sxs-lookup"><span data-stu-id="47e07-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="47e07-105">您可以在不同的開發環境中使用此配對：</span><span class="sxs-lookup"><span data-stu-id="47e07-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="47e07-106">使用 Visual Studio 的C# Q # + （Windows）</span><span class="sxs-lookup"><span data-stu-id="47e07-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="47e07-107">使用 Visual Studio Code 的C# Q # + （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="47e07-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="47e07-108">使用 `dotnet` 命令C#行工具的 Q # +</span><span class="sxs-lookup"><span data-stu-id="47e07-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="47e07-109">使用 Visual Studio 的 Q # C# + 進行開發<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="47e07-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="47e07-110">Visual Studio 提供開發 Q # 程式的豐富環境。</span><span class="sxs-lookup"><span data-stu-id="47e07-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="47e07-111">Q # Visual Studio 延伸模組包含 Q # 檔案和專案的範本，以及語法醒目提示、程式碼完成和 IntelliSense 支援。</span><span class="sxs-lookup"><span data-stu-id="47e07-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="47e07-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="47e07-112">Pre-requisites</span></span>

    - <span data-ttu-id="47e07-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載</span><span class="sxs-lookup"><span data-stu-id="47e07-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="47e07-114">安裝 Q# Visual Studio 擴充功能</span><span class="sxs-lookup"><span data-stu-id="47e07-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="47e07-115">下載並安裝[Visual Studio 擴充](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)功能</span><span class="sxs-lookup"><span data-stu-id="47e07-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="47e07-116">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="47e07-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="47e07-117">建立新的 C# 應用程式</span><span class="sxs-lookup"><span data-stu-id="47e07-117">Create a new Q# application</span></span>

        - <span data-ttu-id="47e07-118">移至 [檔案] -> [新增] -> [專案]</span><span class="sxs-lookup"><span data-stu-id="47e07-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="47e07-119">在搜尋方塊中輸入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="47e07-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="47e07-120">選取 [Q# 應用程式]</span><span class="sxs-lookup"><span data-stu-id="47e07-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="47e07-121">選取 [**下一步**]</span><span class="sxs-lookup"><span data-stu-id="47e07-121">Select **Next**</span></span>
        - <span data-ttu-id="47e07-122">選擇應用程式的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="47e07-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="47e07-123">選取 [建立]</span><span class="sxs-lookup"><span data-stu-id="47e07-123">Select **Create**</span></span>

    - <span data-ttu-id="47e07-124">檢查專案</span><span class="sxs-lookup"><span data-stu-id="47e07-124">Inspect the project</span></span>

        <span data-ttu-id="47e07-125">您應該會看到系統建立了兩個檔案：`Driver.cs` (C# 主應用程式) 和 `Operation.qs` (Q# 程式，會定義用來將訊息列印至主控台的簡單操作)。</span><span class="sxs-lookup"><span data-stu-id="47e07-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="47e07-126">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="47e07-126">Run the application</span></span>

        - <span data-ttu-id="47e07-127">選取 [偵錯] -> [啟動但不偵錯]</span><span class="sxs-lookup"><span data-stu-id="47e07-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="47e07-128">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="47e07-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="47e07-129">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="47e07-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="47e07-130">使用 Visual Studio Code 的 Q # C# + 進行開發<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="47e07-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="47e07-131">Visual Studio Code （VS Code）提供豐富的環境，供您在 Windows、Linux 和 Mac 上開發 Q # 程式。</span><span class="sxs-lookup"><span data-stu-id="47e07-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="47e07-132">Q # VS Code 延伸模組包含 Q # 語法反白顯示、程式碼完成和 Q # 程式碼片段的支援。</span><span class="sxs-lookup"><span data-stu-id="47e07-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="47e07-133">必要條件</span><span class="sxs-lookup"><span data-stu-id="47e07-133">Pre-requisites</span></span>

   - [<span data-ttu-id="47e07-134">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="47e07-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="47e07-135">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="47e07-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="47e07-136">安裝 Quantum VS Code 擴充功能</span><span class="sxs-lookup"><span data-stu-id="47e07-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="47e07-137">安裝 [VS Code 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="47e07-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="47e07-138">安裝 Quantum 專案範本：</span><span class="sxs-lookup"><span data-stu-id="47e07-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="47e07-139">移至 [檢視] -> [命令選擇區]</span><span class="sxs-lookup"><span data-stu-id="47e07-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="47e07-140">選取 [ **Q #：安裝專案範本**]</span><span class="sxs-lookup"><span data-stu-id="47e07-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="47e07-141">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="47e07-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="47e07-142">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="47e07-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="47e07-143">建立新專案：</span><span class="sxs-lookup"><span data-stu-id="47e07-143">Create a new project:</span></span>

        - <span data-ttu-id="47e07-144">移至 [檢視] -> [命令選擇區]</span><span class="sxs-lookup"><span data-stu-id="47e07-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="47e07-145">選取 [ **Q #：建立新專案**]</span><span class="sxs-lookup"><span data-stu-id="47e07-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="47e07-146">選取**獨立主控台應用程式**</span><span class="sxs-lookup"><span data-stu-id="47e07-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="47e07-147">瀏覽至您要建立應用程式的檔案系統位置</span><span class="sxs-lookup"><span data-stu-id="47e07-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="47e07-148">專案建立好之後，請按一下 [開啟新專案...] 按鈕</span><span class="sxs-lookup"><span data-stu-id="47e07-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="47e07-149">如果您還沒有安裝 VS Code C#的延伸模組，將會顯示快顯視窗。</span><span class="sxs-lookup"><span data-stu-id="47e07-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="47e07-150">安裝延伸模組。</span><span class="sxs-lookup"><span data-stu-id="47e07-150">Install the extension.</span></span> 

    - <span data-ttu-id="47e07-151">執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="47e07-151">Run the application:</span></span>

        - <span data-ttu-id="47e07-152">移至**終端**機 -> **新的終端**機</span><span class="sxs-lookup"><span data-stu-id="47e07-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="47e07-153">輸入 `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="47e07-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="47e07-154">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="47e07-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="47e07-155">Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="47e07-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="47e07-156">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="47e07-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="47e07-157">使用 `dotnet` 命令列工具C#搭配 Q # + 進行開發<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="47e07-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="47e07-158">當然，您也可以從命令列建置並執行 Q# 程式，只要安裝 .NET Core SDK 和 QDK 專案範本即可。</span><span class="sxs-lookup"><span data-stu-id="47e07-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="47e07-159">必要條件</span><span class="sxs-lookup"><span data-stu-id="47e07-159">Pre-requisites</span></span>

    - [<span data-ttu-id="47e07-160">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="47e07-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="47e07-161">安裝適用於 .NET 的 Quantum 專案範本</span><span class="sxs-lookup"><span data-stu-id="47e07-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="47e07-162">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="47e07-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="47e07-163">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="47e07-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="47e07-164">建立新的應用程式</span><span class="sxs-lookup"><span data-stu-id="47e07-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="47e07-165">瀏覽至新的應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="47e07-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="47e07-166">您應該會看到系統建立了兩個檔案，以及應用程式的專案檔：Q# 檔案 (`Operation.qs`) 和 C# 主機檔案 (`Driver.cs`)。</span><span class="sxs-lookup"><span data-stu-id="47e07-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="47e07-167">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="47e07-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="47e07-168">您應該會看見下列輸出：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="47e07-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="47e07-169">接下來呢？</span><span class="sxs-lookup"><span data-stu-id="47e07-169">What's next?</span></span>

<span data-ttu-id="47e07-170">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="47e07-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
