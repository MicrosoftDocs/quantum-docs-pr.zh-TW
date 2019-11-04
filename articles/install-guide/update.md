---
title: 瞭解如何更新 Microsoft Quantum Development Kit （QDK）
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185846"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c4cf0-102">更新 Microsoft Quantum Development Kit （QDK）</span><span class="sxs-lookup"><span data-stu-id="c4cf0-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c4cf0-103">瞭解如何將 Microsoft Quantum Development Kit （QDK）更新為最新版本。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c4cf0-104">本文假設您已安裝 QDK。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c4cf0-105">如果您是第一次安裝，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c4cf0-106">更新步驟取決於您的開發環境。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="c4cf0-107">從下列各節選擇您的環境。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="c4cf0-108">Python</span><span class="sxs-lookup"><span data-stu-id="c4cf0-108">Python</span></span>

1. <span data-ttu-id="c4cf0-109">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="c4cf0-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c4cf0-110">確認 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c4cf0-111">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c4cf0-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="c4cf0-112">更新 `qsharp` 封裝</span><span class="sxs-lookup"><span data-stu-id="c4cf0-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="c4cf0-113">確認 `qsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="c4cf0-114">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c4cf0-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="c4cf0-115">您現在可以使用更新的 QDK 版本來執行現有的量副程式。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="c4cf0-116">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="c4cf0-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="c4cf0-117">更新 `iqsharp` 核心</span><span class="sxs-lookup"><span data-stu-id="c4cf0-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="c4cf0-118">確認 `iqsharp` 版本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c4cf0-119">您應該會看見下列輸出：</span><span class="sxs-lookup"><span data-stu-id="c4cf0-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="c4cf0-120">您現在可以開啟現有的 Jupyter 筆記本，並使用更新的 QDK 加以執行。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="c4cf0-121">C#在 Windows 上，使用 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4cf0-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="c4cf0-122">更新 Q # Visual Studio 延伸模組</span><span class="sxs-lookup"><span data-stu-id="c4cf0-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c4cf0-123">Visual Studio 會提示您接受[Visual Studio 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)模組的更新</span><span class="sxs-lookup"><span data-stu-id="c4cf0-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c4cf0-124">接受更新</span><span class="sxs-lookup"><span data-stu-id="c4cf0-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4cf0-125">專案範本會以擴充功能更新。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="c4cf0-126">更新的範本僅適用于新建立的專案。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c4cf0-127">更新延伸模組時，不會更新現有專案的程式碼。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="c4cf0-128">更新 QDK 套件</span><span class="sxs-lookup"><span data-stu-id="c4cf0-128">Update the QDK packages</span></span>

    - <span data-ttu-id="c4cf0-129">開啟現有的應用程式</span><span class="sxs-lookup"><span data-stu-id="c4cf0-129">Open an existing application</span></span>
    - <span data-ttu-id="c4cf0-130">在 方案總管中選取 相依性</span><span class="sxs-lookup"><span data-stu-id="c4cf0-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="c4cf0-131">選取 [**管理 NuGet 套件**]</span><span class="sxs-lookup"><span data-stu-id="c4cf0-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="c4cf0-132">將**Microsoft 量子**套件更新為最新版本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="c4cf0-133">您現在可以使用最新的 QDK 來執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="c4cf0-134">C#，使用 VS Code</span><span class="sxs-lookup"><span data-stu-id="c4cf0-134">C#, using VS Code</span></span>

1. <span data-ttu-id="c4cf0-135">更新 VS Code 延伸模組的量子</span><span class="sxs-lookup"><span data-stu-id="c4cf0-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c4cf0-136">重新開機 VS Code</span><span class="sxs-lookup"><span data-stu-id="c4cf0-136">Restart VS Code</span></span>
    - <span data-ttu-id="c4cf0-137">流覽至 [**擴充**功能] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="c4cf0-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c4cf0-138">選取 Visual Studio Code 延伸模組的**Microsoft Quantum Development Kit**</span><span class="sxs-lookup"><span data-stu-id="c4cf0-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c4cf0-139">重載擴充功能</span><span class="sxs-lookup"><span data-stu-id="c4cf0-139">Reload the extension</span></span>

1. <span data-ttu-id="c4cf0-140">更新 [量子] 專案範本：</span><span class="sxs-lookup"><span data-stu-id="c4cf0-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c4cf0-141">移至**View** -> **命令**選擇區</span><span class="sxs-lookup"><span data-stu-id="c4cf0-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c4cf0-142">選取 [ **Q #：安裝專案範本**]</span><span class="sxs-lookup"><span data-stu-id="c4cf0-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="c4cf0-143">在 VS Code 中開啟現有的應用程式</span><span class="sxs-lookup"><span data-stu-id="c4cf0-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="c4cf0-144">編輯 .csproj 檔案以加入新的封裝版本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="c4cf0-145">如果您使用其他 `Microsoft.Quantum` 套件，也請加以更新。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="c4cf0-146">您現在可以使用更新的 QDK 來執行應用程式</span><span class="sxs-lookup"><span data-stu-id="c4cf0-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c4cf0-147">C#，使用 `dotnet` 命令列工具</span><span class="sxs-lookup"><span data-stu-id="c4cf0-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c4cf0-148">更新 .NET 的量子專案範本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="c4cf0-149">更新並執行現有的應用程式</span><span class="sxs-lookup"><span data-stu-id="c4cf0-149">Update and run an existing application</span></span>

    - <span data-ttu-id="c4cf0-150">更新您應用程式中的 QDK 套件版本</span><span class="sxs-lookup"><span data-stu-id="c4cf0-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="c4cf0-151">如果您的應用程式使用任何其他 `Microsoft.Quantum` 套件，也請加以更新。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="c4cf0-152">執行應用程式</span><span class="sxs-lookup"><span data-stu-id="c4cf0-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="c4cf0-153">您的應用程式將會以新的套件版本執行</span><span class="sxs-lookup"><span data-stu-id="c4cf0-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="c4cf0-154">接下來呢？</span><span class="sxs-lookup"><span data-stu-id="c4cf0-154">What's next?</span></span>

<span data-ttu-id="c4cf0-155">既然您已在慣用的環境中更新配量開發工具組，您可以繼續開發和執行您的量副程式。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="c4cf0-156">如果您尚未撰寫程式，您可以開始使用[第一個量副程式](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="c4cf0-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
