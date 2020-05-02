---
title: '執行沒有驅動程式和主機語言的 Q # 程式'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706796"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="ac9f6-102">Q # 命令列應用程式</span><span class="sxs-lookup"><span data-stu-id="ac9f6-102">Q# Command Line Applications</span></span>

<span data-ttu-id="ac9f6-103">問 # 程式可以自己執行，而不需要像 c #、F # 或 Python 等主機語言的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="ac9f6-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="ac9f6-104">Pre-requisites</span></span>

- [<span data-ttu-id="ac9f6-105">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ac9f6-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="ac9f6-106">安裝</span><span class="sxs-lookup"><span data-stu-id="ac9f6-106">Installation</span></span>

<span data-ttu-id="ac9f6-107">雖然您可以在任何 IDE 中建立 Q # 命令列應用程式，但我們強烈建議您針對您的 Q # 應用程式使用 Visual Studio Code （VS Code）或 Visual Studio IDE。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="ac9f6-108">藉由使用 VS Code 或 Visual Studio 和 QDK Visual Studio Code 延伸模組，您可以存取更豐富的功能。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="ac9f6-109">安裝[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="ac9f6-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="ac9f6-110">安裝[適用于 VS Code 或的 QDK 擴充](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)功能</span><span class="sxs-lookup"><span data-stu-id="ac9f6-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="ac9f6-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3，並已啟用 .NET Core 跨平台開發工作負載</span><span class="sxs-lookup"><span data-stu-id="ac9f6-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="ac9f6-112">下載並安裝[Visual Studio 擴充](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)功能</span><span class="sxs-lookup"><span data-stu-id="ac9f6-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="ac9f6-113">使用 Q # 進行開發 VS Code</span><span class="sxs-lookup"><span data-stu-id="ac9f6-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="ac9f6-114">安裝 Quantum 專案範本：</span><span class="sxs-lookup"><span data-stu-id="ac9f6-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="ac9f6-115">移至**View** -> **命令**選擇區</span><span class="sxs-lookup"><span data-stu-id="ac9f6-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="ac9f6-116">選取 [ **Q #：安裝專案範本**]</span><span class="sxs-lookup"><span data-stu-id="ac9f6-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="ac9f6-117">您現已安裝好 Quantum Development Kit，並已準備好用於您自己的應用程式和程式庫中。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="ac9f6-118">建立新專案：</span><span class="sxs-lookup"><span data-stu-id="ac9f6-118">Create a new project:</span></span>
  - <span data-ttu-id="ac9f6-119">移至**View** -> **命令**選擇區</span><span class="sxs-lookup"><span data-stu-id="ac9f6-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="ac9f6-120">選取 [ **Q #：建立新專案**]</span><span class="sxs-lookup"><span data-stu-id="ac9f6-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="ac9f6-121">選取**獨立主控台應用程式**</span><span class="sxs-lookup"><span data-stu-id="ac9f6-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="ac9f6-122">瀏覽至您要建立應用程式的檔案系統位置</span><span class="sxs-lookup"><span data-stu-id="ac9f6-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="ac9f6-123">專案建立好之後，請按一下 [開啟新專案...]\*\*\*\* 按鈕</span><span class="sxs-lookup"><span data-stu-id="ac9f6-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="ac9f6-124">檢查專案</span><span class="sxs-lookup"><span data-stu-id="ac9f6-124">Inspect the project</span></span>
  - <span data-ttu-id="ac9f6-125">您應該會看到名`Program.qs`為 [已建立] 的檔案，這是一個 Q # 程式，可定義簡單的作業，以將訊息列印至主控台。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="ac9f6-126">執行應用程式：</span><span class="sxs-lookup"><span data-stu-id="ac9f6-126">Run the application:</span></span>
  - <span data-ttu-id="ac9f6-127">移至**終端** -> 機**新終端**機</span><span class="sxs-lookup"><span data-stu-id="ac9f6-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="ac9f6-128">輸入 `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="ac9f6-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="ac9f6-129">您應該會看到下列文字出現在輸出視窗中 `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="ac9f6-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="ac9f6-130">Visual Studio Code 擴充功能目前不支援具有多個根資料夾的工作區。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="ac9f6-131">如果您在一個 VS Code 工作區中有多個專案，則所有專案都必須包含在相同的根資料夾內。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="ac9f6-132">使用 Q # 進行開發 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ac9f6-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="ac9f6-133">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="ac9f6-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="ac9f6-134">建立新的 C# 應用程式</span><span class="sxs-lookup"><span data-stu-id="ac9f6-134">Create a new Q# application</span></span>
  - <span data-ttu-id="ac9f6-135">移至**File** -> [檔案] [**新增** -> **專案**]</span><span class="sxs-lookup"><span data-stu-id="ac9f6-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="ac9f6-136">在搜尋方塊中輸入 `Q#`</span><span class="sxs-lookup"><span data-stu-id="ac9f6-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="ac9f6-137">選取 [Q# 應用程式]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ac9f6-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="ac9f6-138">選取**下一步**</span><span class="sxs-lookup"><span data-stu-id="ac9f6-138">Select **Next**</span></span>
  - <span data-ttu-id="ac9f6-139">選擇應用程式的名稱和位置</span><span class="sxs-lookup"><span data-stu-id="ac9f6-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="ac9f6-140">選取 [**建立**]</span><span class="sxs-lookup"><span data-stu-id="ac9f6-140">Select **Create**</span></span>

- <span data-ttu-id="ac9f6-141">檢查專案</span><span class="sxs-lookup"><span data-stu-id="ac9f6-141">Inspect the project</span></span>
  - <span data-ttu-id="ac9f6-142">您應該會看到名`Program.qs`為的檔案已建立，這是一個 Q # 程式，定義將訊息列印至主控台的簡單操作。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="ac9f6-143">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="ac9f6-143">Run the application</span></span>
  - <span data-ttu-id="ac9f6-144">選取 [不進行調試的**Debug** -> **啟動**]</span><span class="sxs-lookup"><span data-stu-id="ac9f6-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="ac9f6-145">您應該會看到 `Hello quantum world!` 文字已列印到主控台視窗。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="ac9f6-146">如果您在一個 Visual Studio 解決方案內放入了多個專案，則解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="ac9f6-147">下一步</span><span class="sxs-lookup"><span data-stu-id="ac9f6-147">What's next?</span></span>

<span data-ttu-id="ac9f6-148">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="ac9f6-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
