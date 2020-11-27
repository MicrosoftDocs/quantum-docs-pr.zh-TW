---
title: 在 IDE 中使用 Q# 應用程式進行開發
description: 了解如何建立從命令提示字元執行的 Q# 應用程式。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: eeb567dedc1b8123b32faf7ed3a42bb51f16a7d2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228724"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="f64d3-103">在 IDE 中使用 Q# 應用程式進行開發</span><span class="sxs-lookup"><span data-stu-id="f64d3-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="f64d3-104">Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f64d3-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="f64d3-105">您可以在 Visual Studio Code (VS Code)、Visual Studio、Visual Studio Codespaces 中開發 Q# 應用程式，或使用任何編輯器/IDE，以及從 .NET 主控台執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="f64d3-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="f64d3-106">所有環境的必要條件</span><span class="sxs-lookup"><span data-stu-id="f64d3-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="f64d3-107">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="f64d3-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="f64d3-108">安裝</span><span class="sxs-lookup"><span data-stu-id="f64d3-108">Installation</span></span>

<span data-ttu-id="f64d3-109">雖然您可以在任何 IDE 中建立 Q# 應用程式，但建議使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本機開發您的 Q# 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f64d3-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="f64d3-110">若要透過網頁瀏覽器在雲端中進行開發，建議使用 Visual Studio Codespaces。</span><span class="sxs-lookup"><span data-stu-id="f64d3-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="f64d3-111">在這些環境中進行的開發將利用 QDK 擴充功能的豐富功能，其中包括警告、語法反白顯示、專案範本等等。</span><span class="sxs-lookup"><span data-stu-id="f64d3-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="f64d3-112">若要為 VS Code 設定：</span><span class="sxs-lookup"><span data-stu-id="f64d3-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="f64d3-113">下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="f64d3-114">安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="f64d3-115">若要為 Visual Studio 設定：</span><span class="sxs-lookup"><span data-stu-id="f64d3-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="f64d3-116">下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。</span><span class="sxs-lookup"><span data-stu-id="f64d3-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="f64d3-117">下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="f64d3-118">若要為另一個環境設定：</span><span class="sxs-lookup"><span data-stu-id="f64d3-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="f64d3-119">在命令提示字元中，輸入以下：</span><span class="sxs-lookup"><span data-stu-id="f64d3-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="f64d3-120">若要為 Visual Studio Codespaces 設定：</span><span class="sxs-lookup"><span data-stu-id="f64d3-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="f64d3-121">建立 [Azure 帳戶](https://azure.microsoft.com/free/)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="f64d3-122">建立 Codespaces 環境。</span><span class="sxs-lookup"><span data-stu-id="f64d3-122">Create a Codespaces environment.</span></span> <span data-ttu-id="f64d3-123">遵循[快速入門](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="f64d3-124">建立 Codespace 時，建議您在 [Git 存放庫] 欄位中輸入 `microsoft/Quantum`，以載入 QDK 特定的設定。</span><span class="sxs-lookup"><span data-stu-id="f64d3-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="f64d3-125">您現在可以啟動新的環境，並透過 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)，在瀏覽器中開始進行開發。</span><span class="sxs-lookup"><span data-stu-id="f64d3-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="f64d3-126">或者，您也可以使用本機安裝的 VS Code，並使用 Codespaces 做為[遠端環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="f64d3-127">使用 Q# 進行開發</span><span class="sxs-lookup"><span data-stu-id="f64d3-127">Develop with Q#</span></span>

<span data-ttu-id="f64d3-128">依照對應至您開發環境索引標籤上的指示進行。</span><span class="sxs-lookup"><span data-stu-id="f64d3-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="f64d3-129">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="f64d3-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="f64d3-130">若要建立新專案：</span><span class="sxs-lookup"><span data-stu-id="f64d3-130">To create a new project:</span></span>

1. <span data-ttu-id="f64d3-131">按一下 [檢視] -> [命令選擇區]，然後選取 **[Q#：建立新專案]** 。</span><span class="sxs-lookup"><span data-stu-id="f64d3-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="f64d3-132">按一下 [獨立主控台應用程式]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="f64d3-133">瀏覽至要儲存專案的位置。</span><span class="sxs-lookup"><span data-stu-id="f64d3-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="f64d3-134">輸入專案名稱，並按一下 [建立專案]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="f64d3-135">成功建立專案後，按一下右下方的 [開啟新增專案...]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="f64d3-136">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="f64d3-136">Inspect the project.</span></span> <span data-ttu-id="f64d3-137">您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="f64d3-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="f64d3-138">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="f64d3-138">To run the application:</span></span>

1. <span data-ttu-id="f64d3-139">按一下 [終端機] -> [新增終端機]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="f64d3-140">在終端機提示中，輸入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="f64d3-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="f64d3-141">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f64d3-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="f64d3-142">VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="f64d3-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="f64d3-143">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="f64d3-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="f64d3-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f64d3-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="f64d3-145">藉由建立 Q# `Hello World` 應用程式來確認您的 Visual Studio 安裝。</span><span class="sxs-lookup"><span data-stu-id="f64d3-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="f64d3-146">若要建立新的 Q# 應用程式：</span><span class="sxs-lookup"><span data-stu-id="f64d3-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="f64d3-147">開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="f64d3-148">在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="f64d3-149">為應用程式輸入名稱和位置，然後按一下 [建立]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="f64d3-150">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="f64d3-150">Inspect the project.</span></span> <span data-ttu-id="f64d3-151">您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="f64d3-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="f64d3-152">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="f64d3-152">To run the application:</span></span>

1. <span data-ttu-id="f64d3-153">選取 [偵錯] -> [啟動但不偵錯]。</span><span class="sxs-lookup"><span data-stu-id="f64d3-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="f64d3-154">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="f64d3-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="f64d3-155">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f64d3-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="f64d3-156">其他有命令提示字元的編輯器</span><span class="sxs-lookup"><span data-stu-id="f64d3-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="f64d3-157">藉由建立 Q# `Hello World` 應用程式來確認您的安裝。</span><span class="sxs-lookup"><span data-stu-id="f64d3-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="f64d3-158">建立新的應用程式：</span><span class="sxs-lookup"><span data-stu-id="f64d3-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="f64d3-159">瀏覽至新的應用程式目錄：</span><span class="sxs-lookup"><span data-stu-id="f64d3-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="f64d3-160">此目錄中應該有一個 `Program.qs` 檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="f64d3-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="f64d3-161">您可以使用文字編輯器來修改此範本，使用自己的量子應用程式來覆寫它。</span><span class="sxs-lookup"><span data-stu-id="f64d3-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="f64d3-162">執行程式：</span><span class="sxs-lookup"><span data-stu-id="f64d3-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="f64d3-163">您應該會看到列印出下列文字：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="f64d3-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="f64d3-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f64d3-164">Next steps</span></span>

<span data-ttu-id="f64d3-165">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="f64d3-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
