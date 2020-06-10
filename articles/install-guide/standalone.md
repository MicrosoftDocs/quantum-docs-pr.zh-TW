---
title: '使用 Q # 命令列應用程式進行開發'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630265"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="c9115-102">使用 Q # 命令列應用程式進行開發</span><span class="sxs-lookup"><span data-stu-id="c9115-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="c9115-103">問 # 程式可以自己執行，而不需要像 c #、F # 或 Python 等主機語言的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="c9115-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9115-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="c9115-104">Prerequisites</span></span>

- [<span data-ttu-id="c9115-105">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="c9115-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="c9115-106">安裝</span><span class="sxs-lookup"><span data-stu-id="c9115-106">Installation</span></span>

<span data-ttu-id="c9115-107">雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但我們建議您為您的 Q # 應用程式使用 Visual Studio Code （VS Code）或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="c9115-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="c9115-108">在這些工具中進行開發，可讓您存取豐富的功能。</span><span class="sxs-lookup"><span data-stu-id="c9115-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="c9115-109">若要設定 VS Code：</span><span class="sxs-lookup"><span data-stu-id="c9115-109">To configure VS Code:</span></span>

1. <span data-ttu-id="c9115-110">下載並安裝[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）。</span><span class="sxs-lookup"><span data-stu-id="c9115-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="c9115-111">安裝[適用于 VS Code 的 MICROSOFT QDK](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="c9115-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="c9115-112">若要設定 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="c9115-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="c9115-113">下載並安裝[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並啟用 .net Core 跨平臺開發工作負載。</span><span class="sxs-lookup"><span data-stu-id="c9115-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="c9115-114">下載並安裝[MICROSOFT QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="c9115-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="c9115-115">使用 Q # 進行開發 VS Code</span><span class="sxs-lookup"><span data-stu-id="c9115-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="c9115-116">安裝 Q # 專案範本：</span><span class="sxs-lookup"><span data-stu-id="c9115-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="c9115-117">開啟 VS Code。</span><span class="sxs-lookup"><span data-stu-id="c9115-117">Open VS Code.</span></span>
2. <span data-ttu-id="c9115-118">按一下 [ **View**  ->  **Command 調色板**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="c9115-119">選取 [ **Q #：安裝專案範本**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="c9115-120">**成功安裝專案範本**時，QDK 就可以與您自己的應用程式和程式庫搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c9115-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="c9115-121">若要建立新的專案：</span><span class="sxs-lookup"><span data-stu-id="c9115-121">To create a new project:</span></span>

1. <span data-ttu-id="c9115-122">按一下 [**視圖**] [命令選擇區]  ->  **Command Palette** ，然後選取 [ **Q #：建立新專案**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="c9115-123">按一下 [**獨立主控台應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="c9115-124">流覽至要儲存專案的位置，然後按一下 [**建立專案**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="c9115-125">成功建立專案後，按一下右下方的 [**開啟新專案**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="c9115-126">檢查項目。</span><span class="sxs-lookup"><span data-stu-id="c9115-126">Inspect the project.</span></span> <span data-ttu-id="c9115-127">您應該會看到名為的原始 `Program.qs` 程式檔，這是定義簡單作業以將訊息列印至主控台的 Q # 程式。</span><span class="sxs-lookup"><span data-stu-id="c9115-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="c9115-128">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="c9115-128">To run the application:</span></span>
1. <span data-ttu-id="c9115-129">按一下 [**終端**機] [  ->  **新終端**機]。</span><span class="sxs-lookup"><span data-stu-id="c9115-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="c9115-130">在終端機提示中，輸入 `dotnet run` 。</span><span class="sxs-lookup"><span data-stu-id="c9115-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="c9115-131">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="c9115-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="c9115-132">VS Code Q # 延伸模組目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="c9115-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="c9115-133">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="c9115-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="c9115-134">使用 Q # 進行開發 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c9115-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="c9115-135">藉由建立 Q # 應用程式來驗證您的 Visual Studio 安裝 `Hello World` 。</span><span class="sxs-lookup"><span data-stu-id="c9115-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="c9115-136">若要建立新的 Q # 應用程式：</span><span class="sxs-lookup"><span data-stu-id="c9115-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="c9115-137">開啟 Visual Studio，然後**按一下 [** 檔案] [新增] [  ->  **New**  ->  **專案**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="c9115-138">`Q#`在搜尋方塊中輸入，選取 [ **Q # 應用程式**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9115-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="c9115-139">輸入應用程式的 [名稱] 和 [位置]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="c9115-140">檢查項目。</span><span class="sxs-lookup"><span data-stu-id="c9115-140">Inspect the project.</span></span> <span data-ttu-id="c9115-141">您應該會看到名為的原始 `Program.qs` 程式檔，這是定義簡單作業以將訊息列印至主控台的 Q # 程式。</span><span class="sxs-lookup"><span data-stu-id="c9115-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="c9115-142">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="c9115-142">To run the application:</span></span>
1. <span data-ttu-id="c9115-143">選取 **[** 在  ->  **不進行調試的情況下啟動**]。</span><span class="sxs-lookup"><span data-stu-id="c9115-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="c9115-144">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="c9115-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="c9115-145">如果您在一個 Visual Studio 方案中有多個專案，則方案中包含的所有專案都必須位於方案所在的相同資料夾中，或是在其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c9115-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="c9115-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c9115-146">Next steps</span></span>

<span data-ttu-id="c9115-147">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="c9115-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
