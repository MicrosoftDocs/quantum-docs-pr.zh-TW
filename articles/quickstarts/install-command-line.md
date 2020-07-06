---
title: 以 Q# 命令列應用程式開發
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884279"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="23795-102">以 Q# 命令列應用程式開發</span><span class="sxs-lookup"><span data-stu-id="23795-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="23795-103">Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="23795-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23795-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="23795-104">Prerequisites</span></span>

- [<span data-ttu-id="23795-105">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="23795-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="23795-106">安裝</span><span class="sxs-lookup"><span data-stu-id="23795-106">Installation</span></span>

<span data-ttu-id="23795-107">雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但建議您為 Q # 應用程式使用 Visual Studio Code (VS Code) 或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="23795-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="23795-108">在這些環境中進行的開發將包含 QDK 擴充功能的豐富功能，其中包括警告、語法反白顯示、專案範本等等。</span><span class="sxs-lookup"><span data-stu-id="23795-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="23795-109">若要設定 VS Code：</span><span class="sxs-lookup"><span data-stu-id="23795-109">To configure VS Code:</span></span>

1. <span data-ttu-id="23795-110">下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。</span><span class="sxs-lookup"><span data-stu-id="23795-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="23795-111">安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="23795-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="23795-112">若要設定 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="23795-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="23795-113">下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。</span><span class="sxs-lookup"><span data-stu-id="23795-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="23795-114">下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="23795-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="23795-115">若要為其他環境安裝 QDK，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="23795-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="23795-116">使用 Q# 進行開發</span><span class="sxs-lookup"><span data-stu-id="23795-116">Develop with Q#</span></span>

<span data-ttu-id="23795-117">遵循與您的環境對應的索引標籤中的指示。</span><span class="sxs-lookup"><span data-stu-id="23795-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="23795-118">VS 程式碼</span><span class="sxs-lookup"><span data-stu-id="23795-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="23795-119">安裝 Q# 專案範本：</span><span class="sxs-lookup"><span data-stu-id="23795-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="23795-120">開啟 VS Code。</span><span class="sxs-lookup"><span data-stu-id="23795-120">Open VS Code.</span></span>
2. <span data-ttu-id="23795-121">按一下 [檢視] -> [命令選擇區]。</span><span class="sxs-lookup"><span data-stu-id="23795-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="23795-122">選取 [Q#:安裝專案範本]。</span><span class="sxs-lookup"><span data-stu-id="23795-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="23795-123">當顯示 [已成功專案範本] 時，QDK 已準備好搭配您自己的應用程式與程式庫使用。</span><span class="sxs-lookup"><span data-stu-id="23795-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="23795-124">若要建立新專案：</span><span class="sxs-lookup"><span data-stu-id="23795-124">To create a new project:</span></span>

1. <span data-ttu-id="23795-125">按一下 [檢視] -> [命令選擇區]，然後選取 [Q#:**建立新專案]** 。</span><span class="sxs-lookup"><span data-stu-id="23795-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="23795-126">按一下 [獨立主控台應用程式]。</span><span class="sxs-lookup"><span data-stu-id="23795-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="23795-127">瀏覽至要儲存專案的位置，然後按一下 [建立專案]。</span><span class="sxs-lookup"><span data-stu-id="23795-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="23795-128">成功建立專案後，按一下右下方的 [開啟新增專案...]。</span><span class="sxs-lookup"><span data-stu-id="23795-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="23795-129">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="23795-129">Inspect the project.</span></span> <span data-ttu-id="23795-130">您應該會看到名為 `Program.qs` 的原始程式檔，這個 Q # 程式定義一個可將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="23795-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="23795-131">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="23795-131">To run the application:</span></span>
1. <span data-ttu-id="23795-132">按一下 [終端機] -> [新增終端機]。</span><span class="sxs-lookup"><span data-stu-id="23795-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="23795-133">在終端機提示中，輸入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="23795-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="23795-134">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="23795-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="23795-135">VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="23795-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="23795-136">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="23795-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="23795-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23795-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="23795-138">透過建立 Q # `Hello World` 應用程式來確認您的 Visual Studio 安裝。</span><span class="sxs-lookup"><span data-stu-id="23795-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="23795-139">若要建立新的 C# 應用程式：</span><span class="sxs-lookup"><span data-stu-id="23795-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="23795-140">開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。</span><span class="sxs-lookup"><span data-stu-id="23795-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="23795-141">在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="23795-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="23795-142">為應用程式輸入名稱和位置，然後按一下 [建立]。</span><span class="sxs-lookup"><span data-stu-id="23795-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="23795-143">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="23795-143">Inspect the project.</span></span> <span data-ttu-id="23795-144">您應該會看到名為 `Program.qs` 的原始程式檔，這個 Q # 程式定義一個可將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="23795-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="23795-145">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="23795-145">To run the application:</span></span>
1. <span data-ttu-id="23795-146">選取 [偵錯] -> [啟動但不偵錯]。</span><span class="sxs-lookup"><span data-stu-id="23795-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="23795-147">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="23795-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="23795-148">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="23795-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="23795-149">其他有命令列的編輯器</span><span class="sxs-lookup"><span data-stu-id="23795-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="23795-150">透過建立 Q# `Hello World` 應用程式來確認您的安裝。</span><span class="sxs-lookup"><span data-stu-id="23795-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="23795-151">建立新的應用程式：</span><span class="sxs-lookup"><span data-stu-id="23795-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="23795-152">瀏覽至新的應用程式目錄：</span><span class="sxs-lookup"><span data-stu-id="23795-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="23795-153">此目錄中應該有一個 `Program.qs` 檔案，這個 Q# 程式定義一個可將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="23795-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="23795-154">您可以使用文字編輯器來修改此範本，使用自己的量子應用程式來覆寫它。</span><span class="sxs-lookup"><span data-stu-id="23795-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="23795-155">執行程式：</span><span class="sxs-lookup"><span data-stu-id="23795-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="23795-156">您應該會看到列印出下列文字：`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="23795-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="23795-157">後續步驟</span><span class="sxs-lookup"><span data-stu-id="23795-157">Next steps</span></span>

<span data-ttu-id="23795-158">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="23795-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
