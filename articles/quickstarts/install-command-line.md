---
title: 使用 Q# 應用程式進行開發
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6a287dd76162a05d72af7e9d1e46533425283e2a
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863653"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="a9570-102">使用 Q# 應用程式進行開發</span><span class="sxs-lookup"><span data-stu-id="a9570-102">Develop with Q# applications</span></span>

<span data-ttu-id="a9570-103">Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="a9570-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9570-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="a9570-104">Prerequisites</span></span>

- [<span data-ttu-id="a9570-105">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="a9570-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="a9570-106">安裝</span><span class="sxs-lookup"><span data-stu-id="a9570-106">Installation</span></span>

<span data-ttu-id="a9570-107">雖然您可以在任何 IDE 中建立 Q# 應用程式，但建議使用 Visual Studio Code (VS Code) 或 Visual Studio IDE 在本機開發您的 Q# 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a9570-107">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="a9570-108">若要透過網頁瀏覽器在雲端中進行開發，建議使用 Visual Studio Codespaces。</span><span class="sxs-lookup"><span data-stu-id="a9570-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="a9570-109">在這些環境中進行的開發將包含 QDK 擴充功能的豐富功能，其中包括警告、語法反白顯示、專案範本等等。</span><span class="sxs-lookup"><span data-stu-id="a9570-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="a9570-110">若要設定 VS Code：</span><span class="sxs-lookup"><span data-stu-id="a9570-110">To configure VS Code:</span></span>

1. <span data-ttu-id="a9570-111">下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。</span><span class="sxs-lookup"><span data-stu-id="a9570-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="a9570-112">安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="a9570-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="a9570-113">若要設定 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="a9570-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="a9570-114">下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。</span><span class="sxs-lookup"><span data-stu-id="a9570-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="a9570-115">下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="a9570-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="a9570-116">設定 Visual Studio Codespaces：</span><span class="sxs-lookup"><span data-stu-id="a9570-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="a9570-117">建立 [Azure 帳戶](https://azure.microsoft.com/free/)。</span><span class="sxs-lookup"><span data-stu-id="a9570-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="a9570-118">建立 Codespaces 環境。</span><span class="sxs-lookup"><span data-stu-id="a9570-118">Create a Codespaces environment.</span></span> <span data-ttu-id="a9570-119">遵循[快速入門](https://docs.microsoft.com/visualstudio/online/quickstarts/browser)。</span><span class="sxs-lookup"><span data-stu-id="a9570-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/online/quickstarts/browser).</span></span> <span data-ttu-id="a9570-120">建立 Codespace 時，建議您在 [Git 存放庫] 欄位中輸入 `microsoft/Quantum`，以載入 QDK 特定的設定。</span><span class="sxs-lookup"><span data-stu-id="a9570-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="a9570-121">您現在可以啟動新的環境，並透過 [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)，在瀏覽器中開始進行開發。</span><span class="sxs-lookup"><span data-stu-id="a9570-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="a9570-122">或者，您也可以使用本機安裝的 VS Code，並使用 Codespaces 做為[遠端環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)。</span><span class="sxs-lookup"><span data-stu-id="a9570-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="a9570-123">若要為其他環境安裝 QDK，請在命令提示字元中輸入：</span><span class="sxs-lookup"><span data-stu-id="a9570-123">To install the QDK for another environment, enter at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="a9570-124">使用 Q# 進行開發</span><span class="sxs-lookup"><span data-stu-id="a9570-124">Develop with Q#</span></span>

<span data-ttu-id="a9570-125">遵循與您的環境對應的索引標籤中的指示。</span><span class="sxs-lookup"><span data-stu-id="a9570-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="a9570-126">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="a9570-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="a9570-127">若要建立新專案：</span><span class="sxs-lookup"><span data-stu-id="a9570-127">To create a new project:</span></span>

1. <span data-ttu-id="a9570-128">按一下 [檢視] -> [命令選擇區]，然後選取 **[Q#：建立新專案]** 。</span><span class="sxs-lookup"><span data-stu-id="a9570-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="a9570-129">按一下 [獨立主控台應用程式]。</span><span class="sxs-lookup"><span data-stu-id="a9570-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="a9570-130">瀏覽至要儲存專案的位置，然後按一下 [建立專案]。</span><span class="sxs-lookup"><span data-stu-id="a9570-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="a9570-131">成功建立專案後，按一下右下方的 [開啟新增專案...]。</span><span class="sxs-lookup"><span data-stu-id="a9570-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="a9570-132">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="a9570-132">Inspect the project.</span></span> <span data-ttu-id="a9570-133">您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="a9570-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="a9570-134">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="a9570-134">To run the application:</span></span>
1. <span data-ttu-id="a9570-135">按一下 [終端機] -> [新增終端機]。</span><span class="sxs-lookup"><span data-stu-id="a9570-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="a9570-136">在終端機提示中，輸入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="a9570-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="a9570-137">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="a9570-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="a9570-138">VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="a9570-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="a9570-139">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="a9570-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="a9570-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a9570-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="a9570-141">藉由建立 Q# `Hello World` 應用程式來確認您的 Visual Studio 安裝。</span><span class="sxs-lookup"><span data-stu-id="a9570-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="a9570-142">若要建立新的 Q# 應用程式：</span><span class="sxs-lookup"><span data-stu-id="a9570-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="a9570-143">開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。</span><span class="sxs-lookup"><span data-stu-id="a9570-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="a9570-144">在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="a9570-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="a9570-145">為應用程式輸入名稱和位置，然後按一下 [建立]。</span><span class="sxs-lookup"><span data-stu-id="a9570-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="a9570-146">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="a9570-146">Inspect the project.</span></span> <span data-ttu-id="a9570-147">您應該會看到名為 `Program.qs` 的來源檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="a9570-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="a9570-148">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="a9570-148">To run the application:</span></span>
1. <span data-ttu-id="a9570-149">選取 [偵錯] -> [啟動但不偵錯]。</span><span class="sxs-lookup"><span data-stu-id="a9570-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="a9570-150">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="a9570-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="a9570-151">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a9570-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="a9570-152">其他有命令提示字元的編輯器</span><span class="sxs-lookup"><span data-stu-id="a9570-152">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="a9570-153">藉由建立 Q# `Hello World` 應用程式來確認您的安裝。</span><span class="sxs-lookup"><span data-stu-id="a9570-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="a9570-154">安裝專案範本。</span><span class="sxs-lookup"><span data-stu-id="a9570-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="a9570-155">建立新的應用程式：</span><span class="sxs-lookup"><span data-stu-id="a9570-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="a9570-156">瀏覽至新的應用程式目錄：</span><span class="sxs-lookup"><span data-stu-id="a9570-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="a9570-157">此目錄中應該有一個 `Program.qs` 檔案，這個 Q# 程式會定義一個將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="a9570-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="a9570-158">您可以使用文字編輯器來修改此範本，使用自己的量子應用程式來覆寫它。</span><span class="sxs-lookup"><span data-stu-id="a9570-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="a9570-159">執行程式：</span><span class="sxs-lookup"><span data-stu-id="a9570-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="a9570-160">您應該會看到列印出下列文字：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="a9570-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="a9570-161">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a9570-161">Next steps</span></span>

<span data-ttu-id="a9570-162">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="a9570-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
