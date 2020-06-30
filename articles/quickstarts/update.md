---
title: 更新 Quantum Development Kit (QDK)
description: '描述如何將您的 Q # 專案和 Microsoft Quantum Development Kit 更新為目前的版本。'
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 8d39716c4d4c96ad87862b4b185895aab66cd210
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274028"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="66a66-103">更新 Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="66a66-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="66a66-104">深入了解如何將 Microsoft Quantum Development Kit (QDK) 更新為最新的版本。</span><span class="sxs-lookup"><span data-stu-id="66a66-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="66a66-105">本文假設您已經安裝 QDK。</span><span class="sxs-lookup"><span data-stu-id="66a66-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="66a66-106">如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="66a66-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="66a66-107">我們建議您保持最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="66a66-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="66a66-108">請遵循此更新指南升級至最新的 QDK 版本。</span><span class="sxs-lookup"><span data-stu-id="66a66-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="66a66-109">此流程由兩個部分組成：</span><span class="sxs-lookup"><span data-stu-id="66a66-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="66a66-110">更新您現有的 Q # 檔案和專案，讓您的程式碼與任何更新後的語法一致。</span><span class="sxs-lookup"><span data-stu-id="66a66-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="66a66-111">為您選擇的開發環境更新 QDK 本身。</span><span class="sxs-lookup"><span data-stu-id="66a66-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="66a66-112">更新 Q# 專案</span><span class="sxs-lookup"><span data-stu-id="66a66-112">Updating Q# Projects</span></span> 

<span data-ttu-id="66a66-113">無論您使用的是 C# 或 Python 來裝載 Q# 作業，請遵循下列指示來更新您的 Q# 專案。</span><span class="sxs-lookup"><span data-stu-id="66a66-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="66a66-114">首先，檢查您是否有最新版的 [.NET Core SDK 3.1](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="66a66-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="66a66-115">在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="66a66-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="66a66-116">確認輸出為 `3.1.100` 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="66a66-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="66a66-117">如果不是，請安裝[最新版本](https://dotnet.microsoft.com/download)，然後再檢查一次。</span><span class="sxs-lookup"><span data-stu-id="66a66-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="66a66-118">接著，根據您的設定 (Visual Studio、Visual Studio Code 或直接使用命令列) 遵循下列指示進行。</span><span class="sxs-lookup"><span data-stu-id="66a66-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="66a66-119">更新 Visual Studio 中的 Q# 專案</span><span class="sxs-lookup"><span data-stu-id="66a66-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="66a66-120">更新為最新版的 Visual Studio 2019，請參閱[此處](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019)以取得指示。</span><span class="sxs-lookup"><span data-stu-id="66a66-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="66a66-121">在 Visual Studio 中開啟方案。</span><span class="sxs-lookup"><span data-stu-id="66a66-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="66a66-122">從功能表中選取 [組建] -> [清除方案]。</span><span class="sxs-lookup"><span data-stu-id="66a66-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="66a66-123">在每個 .csproj 檔案中，將目標框架變更為 `netcoreapp3.1` (若為程式庫專案，則變更為 `netstandard2.1`)。</span><span class="sxs-lookup"><span data-stu-id="66a66-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="66a66-124">亦即編輯表單的行：</span><span class="sxs-lookup"><span data-stu-id="66a66-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="66a66-125">您可以在[此處](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)取得更多關於指定目標框架的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="66a66-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="66a66-126">在每個 .csproj 檔案中，將 SDK 設定為 `Microsoft.Quantum.Sdk`，如下行所示。</span><span class="sxs-lookup"><span data-stu-id="66a66-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="66a66-127">請注意，版本號碼應該是最新可用的版本，您可以查看[版本資訊](https://docs.microsoft.com/quantum/relnotes/)來判斷。</span><span class="sxs-lookup"><span data-stu-id="66a66-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="66a66-128">儲存並關閉解決方案中所有的檔案。</span><span class="sxs-lookup"><span data-stu-id="66a66-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="66a66-129">選取 [工具] -> [命令列] -> [開發人員命令提示字元]。</span><span class="sxs-lookup"><span data-stu-id="66a66-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="66a66-130">或者，您可以使用 Visual Studio 中的封裝管理主控台。</span><span class="sxs-lookup"><span data-stu-id="66a66-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="66a66-131">針對解決方案中的每個專案，執行下列命令以**移除**此封裝：</span><span class="sxs-lookup"><span data-stu-id="66a66-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="66a66-132">如果您的專案使用任何其他的 Microsoft.Quantum 或 Microsoft.Azure.Quantum 封裝 (例如 Microsoft.Quantum.Numerics)，請為這些封裝執行 **add** 命令以更新所使用的版本。</span><span class="sxs-lookup"><span data-stu-id="66a66-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="66a66-133">關閉命令提示字元，然後選取 [組建] -> [組建方案] (請*勿*選取 [重建方案])。</span><span class="sxs-lookup"><span data-stu-id="66a66-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="66a66-134">您現在可以直接跳到[更新 Visual Studio QDK 擴充功能](#update-visual-studio-qdk-extension)。</span><span class="sxs-lookup"><span data-stu-id="66a66-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="66a66-135">更新 Visual Studio Code 中的 Q# 專案</span><span class="sxs-lookup"><span data-stu-id="66a66-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="66a66-136">在 Visual Studio Code 中，開啟包含所要更新專案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="66a66-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="66a66-137">選取 [終端機] -> [新增終端機]。</span><span class="sxs-lookup"><span data-stu-id="66a66-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="66a66-138">請遵循下列指示 (正下方) 以使用命令列進行更新。</span><span class="sxs-lookup"><span data-stu-id="66a66-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="66a66-139">使用命令列更新 Q # 專案</span><span class="sxs-lookup"><span data-stu-id="66a66-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="66a66-140">瀏覽至包含您主要專案檔的資料夾。</span><span class="sxs-lookup"><span data-stu-id="66a66-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="66a66-141">執行以下命令：</span><span class="sxs-lookup"><span data-stu-id="66a66-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="66a66-142">判斷 QDK 目前的版本。</span><span class="sxs-lookup"><span data-stu-id="66a66-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="66a66-143">若要找到它，您可以參閱[版本資訊](https://docs.microsoft.com/quantum/relnotes/)。</span><span class="sxs-lookup"><span data-stu-id="66a66-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="66a66-144">版本格式類似於 `0.11.2006.207`。</span><span class="sxs-lookup"><span data-stu-id="66a66-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="66a66-145">在您的每個 `.csproj` 檔案中，進行以下步驟：</span><span class="sxs-lookup"><span data-stu-id="66a66-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="66a66-146">將目標框架變更為 `netcoreapp3.1` (若為程式庫專案，則變更為 `netstandard2.1`)。</span><span class="sxs-lookup"><span data-stu-id="66a66-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="66a66-147">亦即編輯表單的行：</span><span class="sxs-lookup"><span data-stu-id="66a66-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="66a66-148">您可以在[此處](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)取得更多關於指定目標框架的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="66a66-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="66a66-149">取代專案定義中的 SDK 參考。</span><span class="sxs-lookup"><span data-stu-id="66a66-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="66a66-150">請確定版本號碼符合您在**步驟 3** 中判斷出的值。</span><span class="sxs-lookup"><span data-stu-id="66a66-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="66a66-151">移除封裝 `Microsoft.Quantum.Development.Kit` 的參考 (如果有的話)，這將在以下輸入中指定：</span><span class="sxs-lookup"><span data-stu-id="66a66-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="66a66-152">將所有 Microsoft Quantum 封裝的版本更新為最新發行 QDK 版本 (在**步驟 3** 中判斷的版本)。</span><span class="sxs-lookup"><span data-stu-id="66a66-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="66a66-153">這些封裝以下列模式命名：</span><span class="sxs-lookup"><span data-stu-id="66a66-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="66a66-154">封裝的參考格式如下：</span><span class="sxs-lookup"><span data-stu-id="66a66-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="66a66-155">儲存更新的檔案。</span><span class="sxs-lookup"><span data-stu-id="66a66-155">Save the updated file.</span></span>

    - <span data-ttu-id="66a66-156">執行下列動作還原專案的相依性：</span><span class="sxs-lookup"><span data-stu-id="66a66-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="66a66-157">瀏覽至包含您主要專案的資料夾，然後執行：</span><span class="sxs-lookup"><span data-stu-id="66a66-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="66a66-158">現在您的 Q # 專案已更新，請遵循下列指示來更新 QDK 本身。</span><span class="sxs-lookup"><span data-stu-id="66a66-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="66a66-159">更新 QDK</span><span class="sxs-lookup"><span data-stu-id="66a66-159">Updating the QDK</span></span>

<span data-ttu-id="66a66-160">更新 QDK 的流程會視開發語言和環境而有所不同。</span><span class="sxs-lookup"><span data-stu-id="66a66-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="66a66-161">於下方選取您的開發環境。</span><span class="sxs-lookup"><span data-stu-id="66a66-161">Select your development environment below.</span></span>

* [<span data-ttu-id="66a66-162">Python：更新 IQ# 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="66a66-163">Jupyter Notebook：更新 IQ# 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="66a66-164">Visual Studio：更新 QDK 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="66a66-165">VS Code：更新 QDK 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="66a66-166">命令列和 C#：更新專案範本</span><span class="sxs-lookup"><span data-stu-id="66a66-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="66a66-167">更新 Python 的 IQ#</span><span class="sxs-lookup"><span data-stu-id="66a66-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="66a66-168">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="66a66-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="66a66-169">確認 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="66a66-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="66a66-170">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="66a66-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="66a66-171">如果您的 `iqsharp` 版本較新，不要擔心，它應該符合 [最新版本](xref:microsoft.quantum.relnotes)。</span><span class="sxs-lookup"><span data-stu-id="66a66-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="66a66-172">更新 `qsharp` 封裝</span><span class="sxs-lookup"><span data-stu-id="66a66-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="66a66-173">確認 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="66a66-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="66a66-174">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="66a66-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="66a66-175">從您 `.qs` 檔案的位置執行下列命令</span><span class="sxs-lookup"><span data-stu-id="66a66-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="66a66-176">現在您可以使用更新後的 QDK 版本來執行現有的配量程式。</span><span class="sxs-lookup"><span data-stu-id="66a66-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="66a66-177">更新 Jupyter Notebook 的 IQ#</span><span class="sxs-lookup"><span data-stu-id="66a66-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="66a66-178">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="66a66-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="66a66-179">確認 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="66a66-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="66a66-180">您的輸出應該類似如下範例：</span><span class="sxs-lookup"><span data-stu-id="66a66-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="66a66-181">如果您的 `iqsharp` 版本較新，不要擔心，它應該符合[最新版本](xref:microsoft.quantum.relnotes)。</span><span class="sxs-lookup"><span data-stu-id="66a66-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="66a66-182">從 Jupyter Notebook 中的資料格執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="66a66-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="66a66-183">您現在可以開啟現有的 Jupyter Notebook，並使用更新後的 QDK 加以執行。</span><span class="sxs-lookup"><span data-stu-id="66a66-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="66a66-184">更新 Visual Studio QDK 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="66a66-185">更新 Q# Visual Studio 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="66a66-186">Visual Studio 會提示您接受 [Quantum Visual Studio 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)的更新</span><span class="sxs-lookup"><span data-stu-id="66a66-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="66a66-187">接受更新</span><span class="sxs-lookup"><span data-stu-id="66a66-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="66a66-188">系統會以擴充功能更新專案範本。</span><span class="sxs-lookup"><span data-stu-id="66a66-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="66a66-189">更新後的範本只會套用到新建立的專案。</span><span class="sxs-lookup"><span data-stu-id="66a66-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="66a66-190">更新擴充模組時，不會更新現有專案的程式碼。</span><span class="sxs-lookup"><span data-stu-id="66a66-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="66a66-191">更新 VS Code QDK 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="66a66-192">更新 Quantum VS Code 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="66a66-193">重新啟動 VS Code</span><span class="sxs-lookup"><span data-stu-id="66a66-193">Restart VS Code</span></span>
    - <span data-ttu-id="66a66-194">瀏覽至 [擴充功能] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="66a66-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="66a66-195">選取 [Microsoft Quantum Development Kit for Visual Studio Code] 擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="66a66-196">重新載入擴充功能</span><span class="sxs-lookup"><span data-stu-id="66a66-196">Reload the extension</span></span>

2. <span data-ttu-id="66a66-197">更新 Quantum 專案範本：</span><span class="sxs-lookup"><span data-stu-id="66a66-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="66a66-198">移至 [檢視] -> [命令選擇區]</span><span class="sxs-lookup"><span data-stu-id="66a66-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="66a66-199">選取 [Q#:安裝專案範本]</span><span class="sxs-lookup"><span data-stu-id="66a66-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="66a66-200">幾秒鐘之後，您應該會看到一個快顯視窗確認「專案範本安裝成功」</span><span class="sxs-lookup"><span data-stu-id="66a66-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="66a66-201">C#，使用 `dotnet` 命令列工具</span><span class="sxs-lookup"><span data-stu-id="66a66-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="66a66-202">更新適用於 .NET 的 Quantum 專案範本</span><span class="sxs-lookup"><span data-stu-id="66a66-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
