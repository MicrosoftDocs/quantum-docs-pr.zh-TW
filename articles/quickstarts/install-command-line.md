---
title: 以 Q# 命令列應用程式開發
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274066"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="97b62-102">以 Q# 命令列應用程式開發</span><span class="sxs-lookup"><span data-stu-id="97b62-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="97b62-103">Q# 程式可以自行執行，不需要如 C#、F# 或 Python 等主機語言中的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="97b62-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97b62-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="97b62-104">Prerequisites</span></span>

- [<span data-ttu-id="97b62-105">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="97b62-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="97b62-106">安裝</span><span class="sxs-lookup"><span data-stu-id="97b62-106">Installation</span></span>

<span data-ttu-id="97b62-107">雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但建議您為 Q # 應用程式使用 Visual Studio Code (VS Code) 或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="97b62-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="97b62-108">使用這些工具進行開發，可讓您存取豐富的功能。</span><span class="sxs-lookup"><span data-stu-id="97b62-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="97b62-109">若要設定 VS Code：</span><span class="sxs-lookup"><span data-stu-id="97b62-109">To configure VS Code:</span></span>

1. <span data-ttu-id="97b62-110">下載並安裝 [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)。</span><span class="sxs-lookup"><span data-stu-id="97b62-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="97b62-111">安裝 [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="97b62-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="97b62-112">若要設定 Visual Studio：</span><span class="sxs-lookup"><span data-stu-id="97b62-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="97b62-113">下載並安裝 [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 或更新版本，並已啟用 .NET Core 跨平台間工作負載。</span><span class="sxs-lookup"><span data-stu-id="97b62-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="97b62-114">下載並安裝 [Microsoft Azure CLI](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)。</span><span class="sxs-lookup"><span data-stu-id="97b62-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="97b62-115">透過 VS Code，使用 Q# 來開發</span><span class="sxs-lookup"><span data-stu-id="97b62-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="97b62-116">安裝 Q# 專案範本：</span><span class="sxs-lookup"><span data-stu-id="97b62-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="97b62-117">開啟 VS Code。</span><span class="sxs-lookup"><span data-stu-id="97b62-117">Open VS Code.</span></span>
2. <span data-ttu-id="97b62-118">按一下 [檢視] -> [命令選擇區]。</span><span class="sxs-lookup"><span data-stu-id="97b62-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="97b62-119">選取 [Q#:安裝專案範本]。</span><span class="sxs-lookup"><span data-stu-id="97b62-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="97b62-120">當顯示 [已成功專案範本] 時，QDK 已準備好搭配您自己的應用程式與程式庫使用。</span><span class="sxs-lookup"><span data-stu-id="97b62-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="97b62-121">若要建立新專案：</span><span class="sxs-lookup"><span data-stu-id="97b62-121">To create a new project:</span></span>

1. <span data-ttu-id="97b62-122">按一下 [檢視] -> [命令選擇區]，然後選取 [Q#:**建立新專案]** 。</span><span class="sxs-lookup"><span data-stu-id="97b62-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="97b62-123">按一下 [獨立主控台應用程式]。</span><span class="sxs-lookup"><span data-stu-id="97b62-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="97b62-124">瀏覽至要儲存專案的位置，然後按一下 [建立專案]。</span><span class="sxs-lookup"><span data-stu-id="97b62-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="97b62-125">成功建立專案後，按一下右下方的 [開啟新增專案...]。</span><span class="sxs-lookup"><span data-stu-id="97b62-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="97b62-126">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="97b62-126">Inspect the project.</span></span> <span data-ttu-id="97b62-127">您應該會看到名為 `Program.qs` 的原始程式檔，這是一個 Q # 程式，可定義將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="97b62-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="97b62-128">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="97b62-128">To run the application:</span></span>
1. <span data-ttu-id="97b62-129">按一下 [終端機] -> [新增終端機]。</span><span class="sxs-lookup"><span data-stu-id="97b62-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="97b62-130">在終端機提示中，輸入 `dotnet run`。</span><span class="sxs-lookup"><span data-stu-id="97b62-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="97b62-131">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="97b62-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="97b62-132">VS Code Q# 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="97b62-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="97b62-133">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="97b62-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="97b62-134">使用 Visual Studio，透過 Q# 開發</span><span class="sxs-lookup"><span data-stu-id="97b62-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="97b62-135">透過建立 Q # `Hello World` 應用程式來確認您的 Visual Studio 安裝。</span><span class="sxs-lookup"><span data-stu-id="97b62-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="97b62-136">若要建立新的 C# 應用程式：</span><span class="sxs-lookup"><span data-stu-id="97b62-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="97b62-137">開啟 Visual Studio，然後按一下 [檔案] -> [新增] -> [專案]。</span><span class="sxs-lookup"><span data-stu-id="97b62-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="97b62-138">在搜尋方塊中鍵入 `Q#`，選取 [Q# 應用程式]，然後按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="97b62-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="97b62-139">為應用程式輸入名稱和位置，然後按一下 [建立]。</span><span class="sxs-lookup"><span data-stu-id="97b62-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="97b62-140">檢查專案。</span><span class="sxs-lookup"><span data-stu-id="97b62-140">Inspect the project.</span></span> <span data-ttu-id="97b62-141">您應該會看到名為 `Program.qs` 的原始程式檔，這個 Q # 程式定義一個可將訊息列印至主控台的簡單作業。</span><span class="sxs-lookup"><span data-stu-id="97b62-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="97b62-142">若要執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="97b62-142">To run the application:</span></span>
1. <span data-ttu-id="97b62-143">選取 [偵錯] -> [啟動但不偵錯]。</span><span class="sxs-lookup"><span data-stu-id="97b62-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="97b62-144">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="97b62-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="97b62-145">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="97b62-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="97b62-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="97b62-146">Next steps</span></span>

<span data-ttu-id="97b62-147">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="97b62-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
