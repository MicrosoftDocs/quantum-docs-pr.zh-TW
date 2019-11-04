---
title: 瞭解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463293"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c0796-102">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="c0796-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c0796-103">瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。</span><span class="sxs-lookup"><span data-stu-id="c0796-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c0796-104">本文假設您已安裝 QDK。</span><span class="sxs-lookup"><span data-stu-id="c0796-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c0796-105">如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="c0796-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="c0796-106">更新 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="c0796-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="c0796-107">首先，安裝最新版本的[.NET Core SDK 3.0](https://dotnet.microsoft.com/download) ，並在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0796-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="c0796-108">確認輸出為3.0.100 或更高版本，然後根據您的設定遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="c0796-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="c0796-109">在 Visual Studio 中</span><span class="sxs-lookup"><span data-stu-id="c0796-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="c0796-110">更新至最新版本的 Visual Studio 2019，如需指示，請參閱[這裡](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)</span><span class="sxs-lookup"><span data-stu-id="c0796-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="c0796-111">在 Visual Studio 中開啟您的方案</span><span class="sxs-lookup"><span data-stu-id="c0796-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="c0796-112">從功能表中，選取 [組建] > [清除方案]</span><span class="sxs-lookup"><span data-stu-id="c0796-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="c0796-113">將您的每個 .csproj 檔案中[的目標 Framework 更新](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework)為 netcoreapp 3.0 （如果它是程式庫專案，則為 netstandard 2.1）</span><span class="sxs-lookup"><span data-stu-id="c0796-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="c0796-114">儲存並關閉方案中的所有檔案</span><span class="sxs-lookup"><span data-stu-id="c0796-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="c0796-115">選取 [工具] > 命令列 > 開發人員命令提示字元</span><span class="sxs-lookup"><span data-stu-id="c0796-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="c0796-116">針對方案中的每個專案，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0796-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="c0796-117">如果您的專案使用任何其他的 Microsoft 量子套件，也請針對這些封裝執行命令。</span><span class="sxs-lookup"><span data-stu-id="c0796-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="c0796-118">關閉命令提示字元，然後選取 [組建 > 組建方案] （*請勿選取 [* 重建方案]，因為重建將一開始就會失敗）</span><span class="sxs-lookup"><span data-stu-id="c0796-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="c0796-119">在 Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c0796-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="c0796-120">在 Visual Studio Code 中，開啟包含要更新之專案的資料夾</span><span class="sxs-lookup"><span data-stu-id="c0796-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="c0796-121">選取 [終端機] > 新的終端機</span><span class="sxs-lookup"><span data-stu-id="c0796-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="c0796-122">遵循使用命令列進行更新的指示</span><span class="sxs-lookup"><span data-stu-id="c0796-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="c0796-123">使用命令列</span><span class="sxs-lookup"><span data-stu-id="c0796-123">Using the command line</span></span>

1. <span data-ttu-id="c0796-124">流覽至包含您專案檔的資料夾</span><span class="sxs-lookup"><span data-stu-id="c0796-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="c0796-125">執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c0796-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="c0796-126">將您的每個 .csproj 檔案中[的目標 Framework 更新](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)為 netcoreapp 3.0 （如果它是程式庫專案，則為 netstandard 2.1）</span><span class="sxs-lookup"><span data-stu-id="c0796-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="c0796-127">執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c0796-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="c0796-128">如果您的專案使用任何其他的 Microsoft 量子套件，也請對這些封裝執行命令。</span><span class="sxs-lookup"><span data-stu-id="c0796-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="c0796-129">儲存並關閉所有檔案</span><span class="sxs-lookup"><span data-stu-id="c0796-129">Save and close all files</span></span>
6. <span data-ttu-id="c0796-130">針對每個專案相依性重複1-4，然後流覽回到包含主要專案的資料夾，並執行：</span><span class="sxs-lookup"><span data-stu-id="c0796-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="c0796-131">更新適用于 Python 的 IQ #</span><span class="sxs-lookup"><span data-stu-id="c0796-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="c0796-132">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="c0796-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c0796-133">確認 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="c0796-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c0796-134">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c0796-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="c0796-135">更新 `qsharp` 封裝</span><span class="sxs-lookup"><span data-stu-id="c0796-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="c0796-136">確認 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="c0796-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="c0796-137">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c0796-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="c0796-138">從 `.qs` 檔案的位置執行下列命令</span><span class="sxs-lookup"><span data-stu-id="c0796-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="c0796-139">您現在可以使用更新的 QDK 版本來執行現有的量副程式。</span><span class="sxs-lookup"><span data-stu-id="c0796-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="c0796-140">更新 Jupyter 筆記本的 IQ #</span><span class="sxs-lookup"><span data-stu-id="c0796-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="c0796-141">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="c0796-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c0796-142">確認 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="c0796-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c0796-143">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c0796-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="c0796-144">從您 Jupyter Notebook 中的儲存格執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0796-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="c0796-145">您現在可以開啟現有的 Jupyter 筆記本，並使用更新的 QDK 加以執行。</span><span class="sxs-lookup"><span data-stu-id="c0796-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="c0796-146">更新 Visual Studio QDK 延伸模組</span><span class="sxs-lookup"><span data-stu-id="c0796-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="c0796-147">更新 Q # Visual Studio 延伸模組</span><span class="sxs-lookup"><span data-stu-id="c0796-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c0796-148">Visual Studio 會提示您接受[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)模組的更新</span><span class="sxs-lookup"><span data-stu-id="c0796-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c0796-149">接受更新</span><span class="sxs-lookup"><span data-stu-id="c0796-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0796-150">專案範本會以擴充功能更新。</span><span class="sxs-lookup"><span data-stu-id="c0796-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="c0796-151">更新的範本僅適用于新建立的專案。</span><span class="sxs-lookup"><span data-stu-id="c0796-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c0796-152">更新延伸模組時，不會更新現有專案的程式碼。</span><span class="sxs-lookup"><span data-stu-id="c0796-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="c0796-153">更新 VS Code QDK 延伸模組</span><span class="sxs-lookup"><span data-stu-id="c0796-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="c0796-154">更新 VS Code 延伸模組的量子</span><span class="sxs-lookup"><span data-stu-id="c0796-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c0796-155">重新開機 VS Code</span><span class="sxs-lookup"><span data-stu-id="c0796-155">Restart VS Code</span></span>
    - <span data-ttu-id="c0796-156">流覽至 [**擴充**功能] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="c0796-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c0796-157">選取 Visual Studio Code 延伸模組的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="c0796-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c0796-158">重載擴充功能</span><span class="sxs-lookup"><span data-stu-id="c0796-158">Reload the extension</span></span>

1. <span data-ttu-id="c0796-159">更新 [量子] 專案範本：</span><span class="sxs-lookup"><span data-stu-id="c0796-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c0796-160">移至 [檢視] -> [命令選擇區]</span><span class="sxs-lookup"><span data-stu-id="c0796-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c0796-161">選取 [ **Q #：安裝專案範本**]</span><span class="sxs-lookup"><span data-stu-id="c0796-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c0796-162">C#，使用 `dotnet` 命令列工具</span><span class="sxs-lookup"><span data-stu-id="c0796-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c0796-163">更新 .NET 的量子專案範本</span><span class="sxs-lookup"><span data-stu-id="c0796-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="c0796-164">接下來呢？</span><span class="sxs-lookup"><span data-stu-id="c0796-164">What's next?</span></span>

<span data-ttu-id="c0796-165">既然您已在慣用的環境中更新配量開發工具組，您可以繼續開發和執行您的量副程式。</span><span class="sxs-lookup"><span data-stu-id="c0796-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="c0796-166">如果您尚未撰寫程式，您可以開始使用[第一個量副程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="c0796-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
