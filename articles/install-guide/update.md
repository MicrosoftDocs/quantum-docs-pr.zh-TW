---
title: 更新量子開發工具組（QDK）
description: '描述如何將您的 Q # 專案和 Microsoft Quantum Development Kit 更新為目前的版本。'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 53f72f1d49ae32a5a8572a1cf68a66a1d9b45e4a
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426916"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="762ea-103">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="762ea-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="762ea-104">瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。</span><span class="sxs-lookup"><span data-stu-id="762ea-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="762ea-105">本文假設您已安裝 QDK。</span><span class="sxs-lookup"><span data-stu-id="762ea-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="762ea-106">如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="762ea-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="762ea-107">我們建議您隨時掌握最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="762ea-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="762ea-108">遵循此更新指南以升級至最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="762ea-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="762ea-109">此套裝程式含兩個部分：</span><span class="sxs-lookup"><span data-stu-id="762ea-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="762ea-110">更新您現有的 Q # 檔案和專案，以將您的程式碼與任何更新的語法對齊</span><span class="sxs-lookup"><span data-stu-id="762ea-110">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="762ea-111">為您選擇的開發環境更新 QDK 本身</span><span class="sxs-lookup"><span data-stu-id="762ea-111">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="762ea-112">更新 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="762ea-112">Updating Q# Projects</span></span> 

<span data-ttu-id="762ea-113">無論您使用的是 c # 或 Python 來裝載 Q # 作業，請遵循這些指示來更新您的 Q # 專案。</span><span class="sxs-lookup"><span data-stu-id="762ea-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="762ea-114">首先，檢查您是否有最新版本的[.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="762ea-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="762ea-115">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="762ea-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="762ea-116">確認輸出為 `3.1.100` 或更高。</span><span class="sxs-lookup"><span data-stu-id="762ea-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="762ea-117">如果不是，請安裝[最新版本](https://dotnet.microsoft.com/download)，然後再檢查一次。</span><span class="sxs-lookup"><span data-stu-id="762ea-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="762ea-118">然後根據您的設定（Visual Studio、Visual Studio Code 或直接命令列）遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="762ea-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="762ea-119">更新 Visual Studio 中的 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="762ea-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="762ea-120">更新至最新版本的 Visual Studio 2019，如需指示，請參閱[這裡](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)</span><span class="sxs-lookup"><span data-stu-id="762ea-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="762ea-121">在 Visual Studio 中開啟您的方案</span><span class="sxs-lookup"><span data-stu-id="762ea-121">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="762ea-122">從功能表中，選取 [**組建**] [  ->  **清除解決方案**]</span><span class="sxs-lookup"><span data-stu-id="762ea-122">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="762ea-123">在您的 .csproj 檔案中，將目標 framework 更新為 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是程式庫專案）。</span><span class="sxs-lookup"><span data-stu-id="762ea-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="762ea-124">也就是，編輯表單的行：</span><span class="sxs-lookup"><span data-stu-id="762ea-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="762ea-125">您可以在[這裡](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有關指定目標 framework 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="762ea-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="762ea-126">儲存並關閉方案中的所有檔案</span><span class="sxs-lookup"><span data-stu-id="762ea-126">Save and close all files in your solution</span></span>
6. <span data-ttu-id="762ea-127">選取**工具**  ->  **命令列**  ->  **開發人員命令提示字元**</span><span class="sxs-lookup"><span data-stu-id="762ea-127">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="762ea-128">針對方案中的每個專案，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="762ea-128">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="762ea-129">如果您的專案使用任何其他的 Microsoft 量子套件（例如，Microsoft 量子. 數值），請執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="762ea-129">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="762ea-130">關閉命令提示字元，然後選取 [**組建**  ->  **組建方案**] （請勿選取 [重建方案]） *not*</span><span class="sxs-lookup"><span data-stu-id="762ea-130">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="762ea-131">您現在可以直接跳至[更新您的 VISUAL STUDIO QDK 延伸](#update-visual-studio-qdk-extension)模組。</span><span class="sxs-lookup"><span data-stu-id="762ea-131">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="762ea-132">更新 Visual Studio Code 中的 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="762ea-132">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="762ea-133">在 Visual Studio Code 中，開啟包含要更新之專案的資料夾</span><span class="sxs-lookup"><span data-stu-id="762ea-133">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="762ea-134">選取 [**終端**機]  ->  **新終端**機</span><span class="sxs-lookup"><span data-stu-id="762ea-134">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="762ea-135">遵循使用命令列進行更新的指示（如下所示）</span><span class="sxs-lookup"><span data-stu-id="762ea-135">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="762ea-136">使用命令列更新 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="762ea-136">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="762ea-137">流覽至包含您專案檔的資料夾</span><span class="sxs-lookup"><span data-stu-id="762ea-137">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="762ea-138">執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="762ea-138">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="762ea-139">在您的 .csproj 檔案中，將目標 framework 更新為 `netcoreapp3.1` （或者， `netstandard2.1` 如果它是程式庫專案）。</span><span class="sxs-lookup"><span data-stu-id="762ea-139">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="762ea-140">也就是，編輯表單的行：</span><span class="sxs-lookup"><span data-stu-id="762ea-140">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="762ea-141">您可以在[這裡](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)找到有關指定目標 framework 的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="762ea-141">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="762ea-142">執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="762ea-142">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="762ea-143">如果您的專案使用任何其他的 Microsoft 量子套件（例如，Microsoft 量子. 數值），請同時執行命令。</span><span class="sxs-lookup"><span data-stu-id="762ea-143">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="762ea-144">儲存並關閉所有檔案。</span><span class="sxs-lookup"><span data-stu-id="762ea-144">Save and close all files.</span></span>
6. <span data-ttu-id="762ea-145">針對每個專案相依性重複1-4，然後流覽回到包含主要專案的資料夾，並執行：</span><span class="sxs-lookup"><span data-stu-id="762ea-145">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="762ea-146">現在您已更新您的 Q # 專案，請遵循下列指示來更新 QDK 本身。</span><span class="sxs-lookup"><span data-stu-id="762ea-146">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="762ea-147">更新 QDK</span><span class="sxs-lookup"><span data-stu-id="762ea-147">Updating the QDK</span></span>

<span data-ttu-id="762ea-148">更新 QDK 的程式會根據您的開發語言和環境而有所不同。</span><span class="sxs-lookup"><span data-stu-id="762ea-148">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="762ea-149">請在下方選取您的開發環境。</span><span class="sxs-lookup"><span data-stu-id="762ea-149">Select your development environment below.</span></span>

* [<span data-ttu-id="762ea-150">Python：更新 IQ # 擴充功能</span><span class="sxs-lookup"><span data-stu-id="762ea-150">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="762ea-151">Jupyter 筆記本：更新 IQ # 擴充功能</span><span class="sxs-lookup"><span data-stu-id="762ea-151">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="762ea-152">Visual Studio：更新 QDK 擴充功能</span><span class="sxs-lookup"><span data-stu-id="762ea-152">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="762ea-153">VS Code：更新 QDK 擴充功能</span><span class="sxs-lookup"><span data-stu-id="762ea-153">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="762ea-154">命令列和 c #：更新專案範本</span><span class="sxs-lookup"><span data-stu-id="762ea-154">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="762ea-155">更新適用于 Python 的 IQ #</span><span class="sxs-lookup"><span data-stu-id="762ea-155">Update IQ# for Python</span></span>

1. <span data-ttu-id="762ea-156">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="762ea-156">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="762ea-157">驗證 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="762ea-157">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="762ea-158">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="762ea-158">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="762ea-159">如果您的 `iqsharp` 版本較高，請不要擔心，它應該符合[最新版本](xref:microsoft.quantum.relnotes)。</span><span class="sxs-lookup"><span data-stu-id="762ea-159">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="762ea-160">更新 `qsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="762ea-160">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="762ea-161">驗證 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="762ea-161">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="762ea-162">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="762ea-162">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="762ea-163">從檔案的位置執行下列命令 `.qs`</span><span class="sxs-lookup"><span data-stu-id="762ea-163">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="762ea-164">您現在可以使用更新的 QDK 版本來執行現有的量副程式。</span><span class="sxs-lookup"><span data-stu-id="762ea-164">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="762ea-165">更新 Jupyter 筆記本的 IQ #</span><span class="sxs-lookup"><span data-stu-id="762ea-165">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="762ea-166">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="762ea-166">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="762ea-167">驗證 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="762ea-167">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="762ea-168">您的輸出應該類似如下範例：</span><span class="sxs-lookup"><span data-stu-id="762ea-168">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="762ea-169">如果您的 `iqsharp` 版本較高，請不要擔心，它應該符合[最新版本](xref:microsoft.quantum.relnotes)。</span><span class="sxs-lookup"><span data-stu-id="762ea-169">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="762ea-170">從您 Jupyter Notebook 中的儲存格執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="762ea-170">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="762ea-171">您現在可以開啟現有的 Jupyter 筆記本，並使用更新的 QDK 加以執行。</span><span class="sxs-lookup"><span data-stu-id="762ea-171">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="762ea-172">更新 Visual Studio QDK 延伸模組</span><span class="sxs-lookup"><span data-stu-id="762ea-172">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="762ea-173">更新 Q # Visual Studio 延伸模組</span><span class="sxs-lookup"><span data-stu-id="762ea-173">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="762ea-174">Visual Studio 會提示您接受[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)模組的更新</span><span class="sxs-lookup"><span data-stu-id="762ea-174">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="762ea-175">接受更新</span><span class="sxs-lookup"><span data-stu-id="762ea-175">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="762ea-176">專案範本會以擴充功能更新。</span><span class="sxs-lookup"><span data-stu-id="762ea-176">The project templates are updated with the extension.</span></span> <span data-ttu-id="762ea-177">更新的範本僅適用于新建立的專案。</span><span class="sxs-lookup"><span data-stu-id="762ea-177">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="762ea-178">更新延伸模組時，不會更新現有專案的程式碼。</span><span class="sxs-lookup"><span data-stu-id="762ea-178">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="762ea-179">更新 VS Code QDK 延伸模組</span><span class="sxs-lookup"><span data-stu-id="762ea-179">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="762ea-180">更新 VS Code 延伸模組的量子</span><span class="sxs-lookup"><span data-stu-id="762ea-180">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="762ea-181">重新開機 VS Code</span><span class="sxs-lookup"><span data-stu-id="762ea-181">Restart VS Code</span></span>
    - <span data-ttu-id="762ea-182">流覽至 [**擴充**功能] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="762ea-182">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="762ea-183">選取 Visual Studio Code 延伸模組的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="762ea-183">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="762ea-184">重載擴充功能</span><span class="sxs-lookup"><span data-stu-id="762ea-184">Reload the extension</span></span>

2. <span data-ttu-id="762ea-185">更新 [量子] 專案範本：</span><span class="sxs-lookup"><span data-stu-id="762ea-185">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="762ea-186">移至**View**  ->  **命令**選擇區</span><span class="sxs-lookup"><span data-stu-id="762ea-186">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="762ea-187">選取 [ **Q #：安裝專案範本**]</span><span class="sxs-lookup"><span data-stu-id="762ea-187">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="762ea-188">幾秒鐘之後，您應該會看到快顯確認「專案範本安裝成功」的快顯視窗</span><span class="sxs-lookup"><span data-stu-id="762ea-188">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="762ea-189">C #，使用 `dotnet` 命令列工具</span><span class="sxs-lookup"><span data-stu-id="762ea-189">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="762ea-190">更新 .NET 的量子專案範本</span><span class="sxs-lookup"><span data-stu-id="762ea-190">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```