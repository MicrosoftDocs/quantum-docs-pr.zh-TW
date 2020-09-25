---
title: 使用 Q# 應用程式進行開發
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
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834409"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="79573-103">使用 Q# 應用程式進行開發</span><span class="sxs-lookup"><span data-stu-id="79573-103">Develop with Q# applications</span></span>

<span data-ttu-id="79573-104">遵循與您的環境對應的索引標籤中的指示。</span><span class="sxs-lookup"><span data-stu-id="79573-104">Follow the instructions at the tab corresponding to your environment.</span></span>

<span data-ttu-id="79573-105">Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="79573-105">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79573-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="79573-106">Prerequisites</span></span>

- [<span data-ttu-id="79573-107">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="79573-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="79573-108">安裝</span><span class="sxs-lookup"><span data-stu-id="79573-108">Installation</span></span>

<span data-ttu-id="79573-109">雖然您可以在任何 IDE 中建立 Q# 應用程式，但建議使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本機開發您的 Q# 應用程式。</span><span class="sxs-lookup"><span data-stu-id="79573-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="79573-110">若要透過網頁瀏覽器在雲端中進行開發，建議使用 Visual Studio Codespaces。</span><span class="sxs-lookup"><span data-stu-id="79573-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="79573-111">在這些環境中進行的開發將包含 QDK 擴充功能的豐富功能，其中包括警告、語法反白顯示、專案範本等等。</span><span class="sxs-lookup"><span data-stu-id="79573-111">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="79573-112">若要設定 VS Code：</span><span class="sxs-lookup"><span data-stu-id="79573-112">To configure VS Code:</span></span>

1. <span data-ttu-id="79573-113">下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。</span><span class="sxs-lookup"><span data-stu-id="79573-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="79573-114">安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="79573-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="79573-115">若要設定 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="79573-115">To configure Visual Studio:</span></span>

1. <span data-ttu-id="79573-116">下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。</span><span class="sxs-lookup"><span data-stu-id="79573-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="79573-117">下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="79573-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="79573-118">設定 Visual Studio Codespaces：</span><span class="sxs-lookup"><span data-stu-id="79573-118">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="79573-119">建立 [Azure 帳戶](https://azure.microsoft.com/free/)。</span><span class="sxs-lookup"><span data-stu-id="79573-119">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="79573-120">建立 Codespaces 環境。</span><span class="sxs-lookup"><span data-stu-id="79573-120">Create a Codespaces environment.</span></span> <span data-ttu-id="79573-121">遵循[快速入門](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)。</span><span class="sxs-lookup"><span data-stu-id="79573-121">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="79573-122">建立 Codespace 時，建議您在 [Git 存放庫] 欄位中輸入 `microsoft/Quantum`，以載入 QDK 特定的設定。</span><span class="sxs-lookup"><span data-stu-id="79573-122">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="79573-123">您現在可以啟動新的環境，並透過 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)，在瀏覽器中開始進行開發。</span><span class="sxs-lookup"><span data-stu-id="79573-123">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="79573-124">或者，您也可以使用本機安裝的 VS Code，並使用 Codespaces 做為[遠端環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。</span><span class="sxs-lookup"><span data-stu-id="79573-124">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="79573-125">若要為其他環境安裝 QDK，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="79573-125">To install the QDK for another environment, enter the following at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="79573-126">使用 Q# 進行開發</span><span class="sxs-lookup"><span data-stu-id="79573-126">Develop with Q#</span></span>

<span data-ttu-id="79573-127">遵循與您的環境對應的索引標籤中的指示。</span><span class="sxs-lookup"><span data-stu-id="79573-127">Follow the instructions on the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="79573-128">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="79573-128">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="79573-129">若要建立新專案：</span><span class="sxs-lookup"><span data-stu-id="79573-129">To create a new project:</span></span>

1. <span data-ttu-id="79573-130">按一下 [檢視] -> [命令選擇區]，然後選取 **[Q#：建立新專案]** 。</span><span class="sxs-lookup"><span data-stu-id="79573-130">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="79573-131">按一下 [獨立主控台應用程式]。</span><span class="sxs-lookup"><span data-stu-id="79573-131">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="79573-132">瀏覽至要儲存專案的位置，然後按一下 [建立專案]。</span><span class="sxs-lookup"><span data-stu-id="79573-132">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="79573-133">成功建立專案後，按一下右下方的 [開啟新增專案...]。</span><span class="sxs-lookup"><span data-stu-id="79573-133">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="79573-134">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="79573-134">Inspect the project.</span></span> <span data-ttu-id="79573-135">您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="79573-135">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="79573-136">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="79573-136">To run the application:</span></span>

1. <span data-ttu-id="79573-137">按一下 [終端機] -> [新增終端機]。</span><span class="sxs-lookup"><span data-stu-id="79573-137">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="79573-138">在終端機提示中，輸入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="79573-138">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="79573-139">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="79573-139">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="79573-140">VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="79573-140">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="79573-141">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="79573-141">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="79573-142">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79573-142">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="79573-143">藉由建立 Q# `Hello World` 應用程式來確認您的 Visual Studio 安裝。</span><span class="sxs-lookup"><span data-stu-id="79573-143">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="79573-144">若要建立新的 Q# 應用程式：</span><span class="sxs-lookup"><span data-stu-id="79573-144">To create a new Q# application:</span></span>

1. <span data-ttu-id="79573-145">開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。</span><span class="sxs-lookup"><span data-stu-id="79573-145">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="79573-146">在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="79573-146">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="79573-147">為應用程式輸入名稱和位置，然後按一下 [建立]。</span><span class="sxs-lookup"><span data-stu-id="79573-147">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="79573-148">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="79573-148">Inspect the project.</span></span> <span data-ttu-id="79573-149">您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="79573-149">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="79573-150">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="79573-150">To run the application:</span></span>

1. <span data-ttu-id="79573-151">選取 [偵錯] -> [啟動但不偵錯]。</span><span class="sxs-lookup"><span data-stu-id="79573-151">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="79573-152">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="79573-152">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="79573-153">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="79573-153">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="79573-154">其他有命令提示字元的編輯器</span><span class="sxs-lookup"><span data-stu-id="79573-154">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="79573-155">藉由建立 Q# `Hello World` 應用程式來確認您的安裝。</span><span class="sxs-lookup"><span data-stu-id="79573-155">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="79573-156">安裝專案範本。</span><span class="sxs-lookup"><span data-stu-id="79573-156">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="79573-157">建立新的應用程式：</span><span class="sxs-lookup"><span data-stu-id="79573-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="79573-158">瀏覽至新的應用程式目錄：</span><span class="sxs-lookup"><span data-stu-id="79573-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="79573-159">此目錄中應該有一個 `Program.qs` 檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="79573-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="79573-160">您可以使用文字編輯器來修改此範本，使用自己的量子應用程式來覆寫它。</span><span class="sxs-lookup"><span data-stu-id="79573-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="79573-161">執行程式：</span><span class="sxs-lookup"><span data-stu-id="79573-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="79573-162">您應該會看到列印出下列文字：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="79573-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="79573-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="79573-163">Next steps</span></span>

<span data-ttu-id="79573-164">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="79573-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
