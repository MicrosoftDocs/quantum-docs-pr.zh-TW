---
title: Quantum 開發套件版本資訊
description: 深入了解 Microsoft Quantum Development Kit 預覽版的最新更新。
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: 61a91278ee2c77972ff12ed77b4f20c837b02643
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320694"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a><span data-ttu-id="74dfd-103">Microsoft Quantum Development Kit 版本資訊</span><span class="sxs-lookup"><span data-stu-id="74dfd-103">Microsoft Quantum Development Kit Release Notes</span></span>

<span data-ttu-id="74dfd-104">本文包含各個 Quantum Development Kit 版本的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="74dfd-104">This article contains information on each Quantum Development Kit release.</span></span>

<span data-ttu-id="74dfd-105">如需安裝指示，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-105">For installation instructions, please refer to the [install guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="74dfd-106">如需更新指示，請參閱[更新指南](xref:microsoft.quantum.update)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-106">For update instructions, please refer to the [update guide](xref:microsoft.quantum.update).</span></span>


## <a name="version-01020022610"></a><span data-ttu-id="74dfd-107">0\.10.2002.2610 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-107">Version 0.10.2002.2610</span></span>

<span data-ttu-id="74dfd-108">*發行日期：2020 年 2 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-108">*Release date: February 27th, 2020*</span></span>

<span data-ttu-id="74dfd-109">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-109">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-110">新的量子機器學習程式庫。如需詳細資訊，請移至我們的 [QML 文件頁面](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)</span><span class="sxs-lookup"><span data-stu-id="74dfd-110">New Quantum Machine Learning library, for more information go to our [QML docs page](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)</span></span>
- <span data-ttu-id="74dfd-111">IQ# 錯誤修正，可在載入 NuGet 套件時增加 10-20 倍的效能</span><span class="sxs-lookup"><span data-stu-id="74dfd-111">IQ# bug fixes, resulting in up to a 10-20x performance increase when loading NuGet packages</span></span>

<span data-ttu-id="74dfd-112">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-112">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020012831"></a><span data-ttu-id="74dfd-113">0\.10.2001.2831 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-113">Version 0.10.2001.2831</span></span>

<span data-ttu-id="74dfd-114">*發行日期：2020 年 1 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-114">*Release date: January 29th, 2020*</span></span>

<span data-ttu-id="74dfd-115">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-115">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-116">新的 Microsoft.Quantum.SDK NuGet 套件，將在建立新專案時取代 Microsoft.Quantum.Development.Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="74dfd-116">New Microsoft.Quantum.SDK NuGet package which will replace Microsoft.Quantum.Development.Kit NuGet package when creating new projects.</span></span> <span data-ttu-id="74dfd-117">現有專案將會繼續支援 Microsoft.Quantum.Development.Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="74dfd-117">Microsoft.Quantum.Development.Kit NuGet package will continue to be supported for existing projects.</span></span> 
- <span data-ttu-id="74dfd-118">由新 Microsoft.Quantum.SDK NuGet 套件啟用的 Q# 編譯器擴充功能支援，如需詳細資訊，請參閱 [Github 上的文件](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler)：[編譯器擴充功能範例](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions)及 [Q# 開發人員部落格](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span><span class="sxs-lookup"><span data-stu-id="74dfd-118">Support for Q# compiler extensions, enabled by the new Microsoft.Quantum.SDK NuGet packge, for more information see the [documentation on Github](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), the [compiler extensions sample](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) and the [Q# Dev Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span></span>
- <span data-ttu-id="74dfd-119">新增 .NET Core 3.1 支援，強烈建議您安裝 3.1.100 版，因為使用舊版 .NET Core SDK 版本可能會造成問題</span><span class="sxs-lookup"><span data-stu-id="74dfd-119">Added support for .NET Core 3.1, it is highly recommended to have version 3.1.100 installed since building with older .NET Core SDK versions may cause issues</span></span>
- <span data-ttu-id="74dfd-120">在 Microsoft.Quantum.QsCompiler.Experimental 下提供新的編譯器轉換</span><span class="sxs-lookup"><span data-stu-id="74dfd-120">New compiler transformations available under Microsoft.Quantum.QsCompiler.Experimental</span></span>
- <span data-ttu-id="74dfd-121">在 IQ# 中將輸出狀態向量以 HTML 公開的新功能</span><span class="sxs-lookup"><span data-stu-id="74dfd-121">New functionality to expose output state vectors as HTML in IQ#</span></span>
- <span data-ttu-id="74dfd-122">已將 EstimateFrequencyA 支援新增至適用於 Hadamard 和 SWAP 測試的 Microsoft.Quantum.Characterization</span><span class="sxs-lookup"><span data-stu-id="74dfd-122">Added support for EstimateFrequencyA to Microsoft.Quantum.Characterization for Hadamard and SWAP tests</span></span>
- <span data-ttu-id="74dfd-123">AmplitudeAmplification 命名空間現在使用 Q# 樣式指南</span><span class="sxs-lookup"><span data-stu-id="74dfd-123">AmplitudeAmplification namespace now uses Q# style guide</span></span>

<span data-ttu-id="74dfd-124">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-124">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019120501"></a><span data-ttu-id="74dfd-125">版本 0.10.1912.0501</span><span class="sxs-lookup"><span data-stu-id="74dfd-125">Version 0.10.1912.0501</span></span>

<span data-ttu-id="74dfd-126">*發行日期：2019 年 12 月 5 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-126">*Release date: December 5th, 2019*</span></span>

<span data-ttu-id="74dfd-127">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-127">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-128">關於 Q# 單元測試的新測試屬性，請參閱[這裡](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)的更新 API 文件，以及[這裡](xref:microsoft.quantum.techniques.testing-and-debugging)的更新測試和偵錯手冊</span><span class="sxs-lookup"><span data-stu-id="74dfd-128">New Test attribute for Q# unit testing, see updated API documentation [here](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) and updated testing & debugging guide [here](xref:microsoft.quantum.techniques.testing-and-debugging)</span></span>
- <span data-ttu-id="74dfd-129">在 Q# 程式執行錯誤案例中新增了堆疊追蹤</span><span class="sxs-lookup"><span data-stu-id="74dfd-129">Added stack trace in the case of a Q# program execution error</span></span>
- <span data-ttu-id="74dfd-130">由於 [OmniSharp C# Visual Studio Code 延伸模組](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)更新，支援在 Visual Studio Code 中的中斷點</span><span class="sxs-lookup"><span data-stu-id="74dfd-130">Support for breakpoints in Visual Studio Code due to an update in the [OmniSharp C# Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span></span>

<span data-ttu-id="74dfd-131">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-131">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019111607"></a><span data-ttu-id="74dfd-132">版本 0.10.1911.1607</span><span class="sxs-lookup"><span data-stu-id="74dfd-132">Version 0.10.1911.1607</span></span>

<span data-ttu-id="74dfd-133">*發行日期：2019 年 11 月 17 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-133">*Release date: November 17th, 2019*</span></span>

<span data-ttu-id="74dfd-134">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-134">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-135">[Quantum Katas](https://github.com/Microsoft/QuantumKatas) 和 Jupyter 筆記本的效能修正</span><span class="sxs-lookup"><span data-stu-id="74dfd-135">Performance fix for [Quantum Katas](https://github.com/Microsoft/QuantumKatas) and Jupyter notebooks</span></span>

<span data-ttu-id="74dfd-136">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-136">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  


## <a name="version-0101911307"></a><span data-ttu-id="74dfd-137">版本 0.10.1911.307</span><span class="sxs-lookup"><span data-stu-id="74dfd-137">Version 0.10.1911.307</span></span>

<span data-ttu-id="74dfd-138">*發行日期：2019 年 11 月 1 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-138">*Release date: November 1st, 2019*</span></span>

<span data-ttu-id="74dfd-139">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-139">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-140">更新 Visual Studio Code 和 Visual Studio 擴充功能，將語言伺服器部署為獨立式可執行檔，以排除 .NET Core SDK 版本相依性</span><span class="sxs-lookup"><span data-stu-id="74dfd-140">Updates to Visual Studio Code & Visual Studio extensions to deploy language server as a self-contained executable, eliminating the .NET Core SDK version dependency</span></span>  
- <span data-ttu-id="74dfd-141">移轉到 .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="74dfd-141">Migration to .NET Core 3.0</span></span>
- <span data-ttu-id="74dfd-142">重大更新 - Microsoft.Quantum.Simulation.Core.IOperationFactory 引進新的 `Fail` 方法</span><span class="sxs-lookup"><span data-stu-id="74dfd-142">Breaking change to Microsoft.Quantum.Simulation.Core.IOperationFactory with introduction of new `Fail` method.</span></span> <span data-ttu-id="74dfd-143">此方法只會影響未擴充 SimulatorBase 的自訂模擬器。</span><span class="sxs-lookup"><span data-stu-id="74dfd-143">It affects only custom simulators that do not extend SimulatorBase.</span></span> <span data-ttu-id="74dfd-144">如需詳細資料，請[檢閱 GitHub 中的提取要求](https://github.com/microsoft/qsharp-runtime/pull/59)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-144">For more details, [view the pull request on GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).</span></span>
- <span data-ttu-id="74dfd-145">受取代屬性的新增支援</span><span class="sxs-lookup"><span data-stu-id="74dfd-145">New support for Deprecated attributes</span></span>

<span data-ttu-id="74dfd-146">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-146">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0919093002"></a><span data-ttu-id="74dfd-147">0\.9.1909.3002 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-147">Version 0.9.1909.3002</span></span>

<span data-ttu-id="74dfd-148">*發行日期：2019 年 9 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-148">*Release date: September 30th, 2019*</span></span>

<span data-ttu-id="74dfd-149">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-149">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-150">在 Visual Studio 2019 (16.3 版和更新版本) 和 Visual Studio Code 中完成 Q# 程式碼的新支援</span><span class="sxs-lookup"><span data-stu-id="74dfd-150">New support for Q# code completion in Visual Studio 2019 (versions 16.3 & later) & Visual Studio Code</span></span>
- <span data-ttu-id="74dfd-151">量子 adder 的新 [Quantum Kata](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="74dfd-151">New [Quantum Kata](https://github.com/Microsoft/QuantumKatas) for quantum adders</span></span>

<span data-ttu-id="74dfd-152">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-152">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-09-packagereference-0919082902"></a><span data-ttu-id="74dfd-153">0\.9 版 (*PackageReference 0.9.1908.2902*)</span><span class="sxs-lookup"><span data-stu-id="74dfd-153">Version 0.9 (*PackageReference 0.9.1908.2902*)</span></span>

<span data-ttu-id="74dfd-154">*發行日期：2019 年 8 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-154">*Release date: August 29th, 2019*</span></span>

<span data-ttu-id="74dfd-155">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-155">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-156">在 Q# 中對[結合陳述式](xref:microsoft.quantum.language.statements#conjugations)的新支援</span><span class="sxs-lookup"><span data-stu-id="74dfd-156">New support for [conjugation statements](xref:microsoft.quantum.language.statements#conjugations) in Q#</span></span>
- <span data-ttu-id="74dfd-157">編譯器中的新程式碼動作 (例如：「取代為」、「新增文件」)，以及簡單的陣列項目更新</span><span class="sxs-lookup"><span data-stu-id="74dfd-157">New code actions in the compiler, such as: "replace with", "add documentation", and simple array item update</span></span>
- <span data-ttu-id="74dfd-158">在 Visual Studio Code 延伸模組中新增了安裝範本和新的專案命令</span><span class="sxs-lookup"><span data-stu-id="74dfd-158">Added install template and new project commands to Visual Studio Code extension</span></span>
- <span data-ttu-id="74dfd-159">新增了 ApplyIf 結合器的新變體，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span><span class="sxs-lookup"><span data-stu-id="74dfd-159">Added new variants of ApplyIf combinator such as [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span></span>
- <span data-ttu-id="74dfd-160">有額外的 [Quantum Katas](https://github.com/Microsoft/QuantumKatas) 可轉換為 Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="74dfd-160">Additional [Quantum Katas](https://github.com/Microsoft/QuantumKatas) converted to Jupyter Notebooks</span></span>
- <span data-ttu-id="74dfd-161">Visual Studio 延伸模組現在需要 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="74dfd-161">Visual Studio Extension now requires Visual Studio 2019</span></span>

<span data-ttu-id="74dfd-162">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-162">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="74dfd-163">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="74dfd-163">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="74dfd-164">如需這些變更的詳細資訊，請參閱 [Q# 開發人員部落格](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-164">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

## <a name="version-08-packagereference-0819071701"></a><span data-ttu-id="74dfd-165">0\.8 版 (*PackageReference 0.8.1907.1701*)</span><span class="sxs-lookup"><span data-stu-id="74dfd-165">Version 0.8 (*PackageReference 0.8.1907.1701*)</span></span>

<span data-ttu-id="74dfd-166">*發行日期：2019 年 7 月 12 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-166">*Release date: July 12, 2019*</span></span>

<span data-ttu-id="74dfd-167">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-167">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-168">切割陣列的新索引位置；請[參閱語言參考](xref:microsoft.quantum.language.expressions#array-slices)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="74dfd-168">New indexing locations for slicing arrays, [see the language reference](xref:microsoft.quantum.language.expressions#array-slices) for more information.</span></span>
- <span data-ttu-id="74dfd-169">新增了裝載於 [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry) 上的 Dockerfile；請參閱 [IQ# 存放庫以取得詳細資訊](https://github.com/microsoft/iqsharp/blob/master/README.md)</span><span class="sxs-lookup"><span data-stu-id="74dfd-169">Added Dockerfile hosted on the [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry), see the [IQ# repository for more information](https://github.com/microsoft/iqsharp/blob/master/README.md)</span></span>
- <span data-ttu-id="74dfd-170">[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的重大變更、組態設定的更新、名稱變更；請參閱 [.NET API 瀏覽器以了解更新的名稱](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-170">Breaking change for [the trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), update to configuration settings, name changes; see the [.NET API Browser for the updated names](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).</span></span>

<span data-ttu-id="74dfd-171">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-171">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-07-packagereference-0719053109"></a><span data-ttu-id="74dfd-172">0\.7 版 (*PackageReference 0.7.1905.3109*)</span><span class="sxs-lookup"><span data-stu-id="74dfd-172">Version 0.7 (*PackageReference 0.7.1905.3109*)</span></span>

<span data-ttu-id="74dfd-173">*發行日期：2019 年 5 月 31 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-173">*Release date: May 31, 2019*</span></span>

<span data-ttu-id="74dfd-174">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-174">This release contains the following:</span></span>
- <span data-ttu-id="74dfd-175">Q# 語言的新增項目，</span><span class="sxs-lookup"><span data-stu-id="74dfd-175">additions to the Q# language,</span></span> 
- <span data-ttu-id="74dfd-176">化學程式庫的更新，</span><span class="sxs-lookup"><span data-stu-id="74dfd-176">updates to the chemistry library,</span></span> 
- <span data-ttu-id="74dfd-177">新的數值程式庫。</span><span class="sxs-lookup"><span data-stu-id="74dfd-177">a new numerics library.</span></span>

<span data-ttu-id="74dfd-178">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="74dfd-178">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="74dfd-179">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="74dfd-179">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="74dfd-180">如需這些變更的詳細資訊，請參閱 [Q# 開發人員部落格](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-180">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

### <a name="q-language-syntax"></a><span data-ttu-id="74dfd-181">Q# 語言語法</span><span class="sxs-lookup"><span data-stu-id="74dfd-181">Q# language syntax</span></span>
<span data-ttu-id="74dfd-182">此版本新增了 Q# 語言語法：</span><span class="sxs-lookup"><span data-stu-id="74dfd-182">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="74dfd-183">新增[使用者自訂類型](xref:microsoft.quantum.language.type-model#user-defined-types)的具名項目。</span><span class="sxs-lookup"><span data-stu-id="74dfd-183">Add named items for [user-defined types](xref:microsoft.quantum.language.type-model#user-defined-types).</span></span>  
* <span data-ttu-id="74dfd-184">使用者定義類型建構函式現在可以當作函式使用。</span><span class="sxs-lookup"><span data-stu-id="74dfd-184">User-defined type constructors can now be used as functions.</span></span>
* <span data-ttu-id="74dfd-185">在使用者定義類型中新增 [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) 和 [apply-and-reassign]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) 的支援。</span><span class="sxs-lookup"><span data-stu-id="74dfd-185">Add support for [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) and [apply-and-reassign]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) in user-defined types.</span></span>
* <span data-ttu-id="74dfd-186">[重複直到成功](xref:microsoft.quantum.language.statements#repeat-until-success-loop)迴圈的修復區塊現在是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="74dfd-186">Fixup-block for [repeat-until-success](xref:microsoft.quantum.language.statements#repeat-until-success-loop) loops is now optional.</span></span>
* <span data-ttu-id="74dfd-187">我們現在支援函式中 (而非作業中) 的 While 迴圈。</span><span class="sxs-lookup"><span data-stu-id="74dfd-187">We now support while loops in functions (not in operations).</span></span>

### <a name="library"></a><span data-ttu-id="74dfd-188">程式庫</span><span class="sxs-lookup"><span data-stu-id="74dfd-188">Library</span></span> 

<span data-ttu-id="74dfd-189">此版本新增了數值程式庫：請深入了解如何[使用新的數值程式庫](xref:microsoft.quantum.numerics.usage)，並試用[新範例](https://github.com/microsoft/quantum/tree/master/Numerics)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-189">This release adds a numerics library: Learn more about how to [use the new numerics library](xref:microsoft.quantum.numerics.usage) and try out the [new samples](https://github.com/microsoft/quantum/tree/master/Numerics).</span></span>  <span data-ttu-id="74dfd-190">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-190">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).</span></span>  

<span data-ttu-id="74dfd-191">此版本重組、擴充並更新了化學程式庫：</span><span class="sxs-lookup"><span data-stu-id="74dfd-191">This release reorganizes extends and updates the chemistry library:</span></span>
* <span data-ttu-id="74dfd-192">改善元件的模組化、擴充性、一般程式碼清除功能。</span><span class="sxs-lookup"><span data-stu-id="74dfd-192">Improves modularity of components, extensibility, general code cleanup.</span></span>  <span data-ttu-id="74dfd-193">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-193">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).</span></span>
* <span data-ttu-id="74dfd-194">新增[多重參考波函數](xref:microsoft.quantum.chemistry.concepts.multireference)的支援，包括疏鬆多重參考波函數和單一結合叢集。</span><span class="sxs-lookup"><span data-stu-id="74dfd-194">Add support for [multi-reference wavefunctions](xref:microsoft.quantum.chemistry.concepts.multireference), both sparse multi-reference wavefunctions and unitary coupled cluster.</span></span>  <span data-ttu-id="74dfd-195">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-195">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>
* <span data-ttu-id="74dfd-196">(謝謝！)[1QBit](https://1qbit.com) 參與者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用變分 ansatz 的能量評估。</span><span class="sxs-lookup"><span data-stu-id="74dfd-196">(Thank you!) [1QBit](https://1qbit.com) contributor ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energy evaluation using variational ansatz.</span></span> <span data-ttu-id="74dfd-197">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-197">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).</span></span>
* <span data-ttu-id="74dfd-198">將 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 結構描述更新為新的 [0.2 版](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，並新增單一結合叢集規格。</span><span class="sxs-lookup"><span data-stu-id="74dfd-198">Updating [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema to new [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), adding unitary coupled cluster specification.</span></span> <span data-ttu-id="74dfd-199">[問題 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-199">[Issue #65](https://github.com/microsoft/QuantumLibraries/issues/65).</span></span>
* <span data-ttu-id="74dfd-200">將 Python 互通性新增至化學程式庫函式。</span><span class="sxs-lookup"><span data-stu-id="74dfd-200">Adding Python interoperability to chemistry library functions.</span></span> <span data-ttu-id="74dfd-201">試著使用此[範例](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-201">Try out this [sample](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration).</span></span> <span data-ttu-id="74dfd-202">[問題 #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-202">[Issue #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>

## <a name="version-061905"></a><span data-ttu-id="74dfd-203">0\.6.1905 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-203">Version 0.6.1905</span></span>

<span data-ttu-id="74dfd-204">*發行日期：2019 年 5 月 3 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-204">*Release date: May 3, 2019*</span></span>

<span data-ttu-id="74dfd-205">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-205">This release contains the following:</span></span>
- <span data-ttu-id="74dfd-206">對 Q# 語言進行變更，</span><span class="sxs-lookup"><span data-stu-id="74dfd-206">makes changes to the Q# language,</span></span> 
- <span data-ttu-id="74dfd-207">重新建構 Quantum Development Kit 程式庫，</span><span class="sxs-lookup"><span data-stu-id="74dfd-207">restructures the Quantum Development Kit libraries,</span></span> 
- <span data-ttu-id="74dfd-208">新增範例，以及</span><span class="sxs-lookup"><span data-stu-id="74dfd-208">adds new samples, and</span></span> 
- <span data-ttu-id="74dfd-209">修正 Bug。</span><span class="sxs-lookup"><span data-stu-id="74dfd-209">fixes bugs.</span></span>  <span data-ttu-id="74dfd-210">[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的數個已關閉的 PR。</span><span class="sxs-lookup"><span data-stu-id="74dfd-210">Several closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="74dfd-211">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="74dfd-211">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="74dfd-212">您可以在 devblogs.microsoft.com/qsharp 上深入了解這些變更。</span><span class="sxs-lookup"><span data-stu-id="74dfd-212">You can read more about these changes on devblogs.microsoft.com/qsharp.</span></span>

### <a name="q-language-syntax"></a><span data-ttu-id="74dfd-213">Q# 語言語法</span><span class="sxs-lookup"><span data-stu-id="74dfd-213">Q# language syntax</span></span>
<span data-ttu-id="74dfd-214">此版本新增了 Q# 語言語法：</span><span class="sxs-lookup"><span data-stu-id="74dfd-214">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="74dfd-215">使用 `+` 運算子新增[用來表示量子作業特製化 (控制和伴隨) 的快速方法](xref:microsoft.quantum.language.type-model#functors)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-215">Add a [shorthand way to express specializations of quantum operations](xref:microsoft.quantum.language.type-model#functors) (control and adjoints) with `+` operators.</span></span>  <span data-ttu-id="74dfd-216">舊語法已被取代。</span><span class="sxs-lookup"><span data-stu-id="74dfd-216">The old syntax is deprecated.</span></span>  <span data-ttu-id="74dfd-217">使用舊語法的程式 (例如 `: adjoint`) 將可繼續運作，但會產生編譯時間警告。</span><span class="sxs-lookup"><span data-stu-id="74dfd-217">Programs that use the old syntax (e.g., `: adjoint`) will continue to work, but a compile time warning will be generated.</span></span>  
* <span data-ttu-id="74dfd-218">新增 [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) 的運算子 `w/`，可用來將陣列的建立表示為現有陣列的修改。</span><span class="sxs-lookup"><span data-stu-id="74dfd-218">Add a new operator for [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions), `w/`, can be used to express array creation as a modification of an existing array.</span></span>
* <span data-ttu-id="74dfd-219">新增一般 [apply-and-upate 陳述式](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)，例如 `+=`、`w/=`。</span><span class="sxs-lookup"><span data-stu-id="74dfd-219">Add the common [apply-and-upate statement](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols), e.g., `+=`, `w/=`.</span></span>
* <span data-ttu-id="74dfd-220">新增為[開放式指示詞](xref:microsoft.quantum.language.file-structure#open-directives)中的命名空間指定簡短名稱的方法。</span><span class="sxs-lookup"><span data-stu-id="74dfd-220">Add a way to specify a short name for namespaces in [open directives](xref:microsoft.quantum.language.file-structure#open-directives).</span></span>

<span data-ttu-id="74dfd-221">在此版本中，我們不再允許在 set 陳述式的左側指定陣列元素。</span><span class="sxs-lookup"><span data-stu-id="74dfd-221">With this release, we no longer allow an array element to be specified on the left side of a set statement.</span></span>  <span data-ttu-id="74dfd-222">這是因為該語法意味著陣列是可變動的，然而事實上，作業的結果一律是經由修改建立新陣列。</span><span class="sxs-lookup"><span data-stu-id="74dfd-222">This is because that syntax implies that arrays are mutable when in fact, the result of the operation has always been the creation of a new array with the modification.</span></span>  <span data-ttu-id="74dfd-223">系統將會產生編譯器錯誤，並建議使用新的 copy-and-update 運算子 `w/` 達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="74dfd-223">Instead, a compiler error will be generated with a suggestion to use the new copy-and-update operator, `w/`, to accomplish the same result.</span></span>  

### <a name="library-restructuring"></a><span data-ttu-id="74dfd-224">程式庫重建</span><span class="sxs-lookup"><span data-stu-id="74dfd-224">Library restructuring</span></span>
<span data-ttu-id="74dfd-225">此版本重組了程式庫，使其能以一致的方式擴展：</span><span class="sxs-lookup"><span data-stu-id="74dfd-225">This release reorganizes the libraries to enable their growth in a consistent way:</span></span>
* <span data-ttu-id="74dfd-226">將 Microsoft.Quantum.Primitive 命名空間重新命名為 Microsoft.Quantum.Intrinsic。</span><span class="sxs-lookup"><span data-stu-id="74dfd-226">Renames the Microsoft.Quantum.Primitive namespace  to Microsoft.Quantum.Intrinsic.</span></span>  <span data-ttu-id="74dfd-227">這些作業會由目標電腦實作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-227">These operations are implemented by the target machine.</span></span>  <span data-ttu-id="74dfd-228">Microsoft.Quantum.Primitive 命名空間已被取代。</span><span class="sxs-lookup"><span data-stu-id="74dfd-228">The Microsoft.Quantum.Primitive namespace is deprecated.</span></span>  <span data-ttu-id="74dfd-229">當程式使用已被取代的名稱呼叫作業和函式時，會有執行階段警告提出建議。</span><span class="sxs-lookup"><span data-stu-id="74dfd-229">A runtime warning will advise when programs call operations and functions using deprecated names.</span></span>

* <span data-ttu-id="74dfd-230">將 Microsoft.Quantum.Canon 套件重新命名為 Microsoft.Quantum.Standard。</span><span class="sxs-lookup"><span data-stu-id="74dfd-230">Renames the Microsoft.Quantum.Canon package to Microsoft.Quantum.Standard.</span></span>  <span data-ttu-id="74dfd-231">此套件包含大部分 Q# 程式通用的命名空間。</span><span class="sxs-lookup"><span data-stu-id="74dfd-231">This package contains namespaces that are common to most Q# programs.</span></span>  <span data-ttu-id="74dfd-232">這包括：</span><span class="sxs-lookup"><span data-stu-id="74dfd-232">This includes:</span></span>  
    - <span data-ttu-id="74dfd-233">一般作業的 Microsoft.Quantum.Canon</span><span class="sxs-lookup"><span data-stu-id="74dfd-233">Microsoft.Quantum.Canon for common operations</span></span>
    - <span data-ttu-id="74dfd-234">一般用途算術運算的 Microsoft.Quantum.Arithmetic</span><span class="sxs-lookup"><span data-stu-id="74dfd-234">Microsoft.Quantum.Arithmetic for general purpose arithmetic operations</span></span>
    - <span data-ttu-id="74dfd-235">作業用來準備量子位元狀態的 Microsoft.Quantum.Preparation</span><span class="sxs-lookup"><span data-stu-id="74dfd-235">Microsoft.Quantum.Preparation for operations used to prepare qubit state</span></span>
    - <span data-ttu-id="74dfd-236">模擬功能的 Microsoft.Quantum.Simulation</span><span class="sxs-lookup"><span data-stu-id="74dfd-236">Microsoft.Quantum.Simulation for simulation functionality</span></span>

<span data-ttu-id="74dfd-237">經過這項變更後，如果程式包含用於命名空間 Microsoft.Quatum.Canon 的單一 "open" 陳述式，且其參考的作業已移至其他三個新的命名空間，則可能會發生建置錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-237">With this change, programs that include a single "open" statement for the namespace Microsoft.Quatum.Canon may encounter build errors if the program references operations that were moved to the other three new namespaces.</span></span>  <span data-ttu-id="74dfd-238">為這三個新的命名空間新增額外的 open 陳述式，可直接了當地解決此問題。</span><span class="sxs-lookup"><span data-stu-id="74dfd-238">Adding the additional open statements for the three new namespaces is a straightforward way to resolve this issue.</span></span>  

* <span data-ttu-id="74dfd-239">有數個命名空間已被取代，因為其中的作業已重組至其他命名空間。</span><span class="sxs-lookup"><span data-stu-id="74dfd-239">Several namespaces have been deprecated as the operations within have been reorganized to other namespaces.</span></span> <span data-ttu-id="74dfd-240">使用這些命名空間的程式將可繼續運作，但會有編譯時間警告指出作業定義所在的命名空間。</span><span class="sxs-lookup"><span data-stu-id="74dfd-240">Programs that use these namespaces will continue to work, and a compile time warning will denote the namespace where the operation is defined.</span></span>  

* <span data-ttu-id="74dfd-241">Microsoft.Quantum.Arithmetic 命名空間已正規化為使用 <xref:microsoft.quantum.arithmetic.littleendian> 使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="74dfd-241">The Microsoft.Quantum.Arithmetic namespace has been normalized to use the <xref:microsoft.quantum.arithmetic.littleendian> user-defined type.</span></span> <span data-ttu-id="74dfd-242">需要轉換為 Little Endian 時，請使用函式 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-242">Use the function [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) when needed to convert to little endian.</span></span>  

* <span data-ttu-id="74dfd-243">有數個可呼叫項目 (函式和作業) 的名稱已變更，以符合 [Q# 樣式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-243">The names of several callables (functions and operations) have been changed to conform to the [Q# Style Guide](xref:microsoft.quantum.contributing.style).</span></span>  <span data-ttu-id="74dfd-244">舊的可呼叫名稱已被取代。</span><span class="sxs-lookup"><span data-stu-id="74dfd-244">The old callable names are deprecated.</span></span>  <span data-ttu-id="74dfd-245">使用舊有可呼叫項目的程式將可繼續運作，但會出現編譯時間警告。</span><span class="sxs-lookup"><span data-stu-id="74dfd-245">Programs that use the old callables will continue to work with a compile time warning.</span></span> 

### <a name="new-samples"></a><span data-ttu-id="74dfd-246">新範例</span><span class="sxs-lookup"><span data-stu-id="74dfd-246">New Samples</span></span>

<span data-ttu-id="74dfd-247">我們新增了[搭配使用 Q# 與 F# 驅動程式的範例](https://github.com/Microsoft/Quantum/pull/164)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-247">We added a [sample of using Q# with F# driver](https://github.com/Microsoft/Quantum/pull/164).</span></span>  

<span data-ttu-id="74dfd-248">**感謝**</span><span class="sxs-lookup"><span data-stu-id="74dfd-248">**Thank you!**</span></span> <span data-ttu-id="74dfd-249">下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。</span><span class="sxs-lookup"><span data-stu-id="74dfd-249">to the following contributor to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="74dfd-250">這些貢獻讓 Q# 程式碼的範例更加豐富：</span><span class="sxs-lookup"><span data-stu-id="74dfd-250">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="74dfd-251">Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函式合成。</span><span class="sxs-lookup"><span data-stu-id="74dfd-251">Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle function synthesis.</span></span> <span data-ttu-id="74dfd-252">[PR #135](https://github.com/Microsoft/Quantum/pull/135)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-252">[PR #135](https://github.com/Microsoft/Quantum/pull/135).</span></span>

### <a name="migrating-existing-projects-to-061905"></a><span data-ttu-id="74dfd-253">將現有的專案移轉至 0.6.1905。</span><span class="sxs-lookup"><span data-stu-id="74dfd-253">Migrating existing projects to 0.6.1905.</span></span>

<span data-ttu-id="74dfd-254">若要更新 QDK，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-254">See the [install guide](xref:microsoft.quantum.install) to update the QDK.</span></span>
  
<span data-ttu-id="74dfd-255">如果您有現有的 Q# 專案來自 0.5 版的 Quantum Development Kit，請依照下列步驟將這些專案移轉至最新版本。</span><span class="sxs-lookup"><span data-stu-id="74dfd-255">If you have existing Q# projects from version 0.5 of the Quantum Development Kit, the following are the steps to migrate those projects to the newest version.</span></span>

    1. <span data-ttu-id="74dfd-256">專案必須依序升級。</span><span class="sxs-lookup"><span data-stu-id="74dfd-256">Projects need to be upgraded in order.</span></span>  <span data-ttu-id="74dfd-257">如果您的解決方案有多個專案，請依照每個專案的參考順序加以更新。</span><span class="sxs-lookup"><span data-stu-id="74dfd-257">If you have a solution with multiple projects, update each project in the order they are referenced.</span></span>
    2. <span data-ttu-id="74dfd-258">從命令列執行 `dotnet clean`，以移除所有現有的二進位檔和中繼檔案。</span><span class="sxs-lookup"><span data-stu-id="74dfd-258">From a command line, Run `dotnet clean` to remove all existing binaries and intermediate files.</span></span>
    3. <span data-ttu-id="74dfd-259">在文字編輯器中編輯 .csproj 檔案，將所有 "Microsoft.Quantum" `PackageReference` 的版本變更為 0.6.1904 版，並將 "Microsoft.Quantum.Canon" 套件名稱變更為 "Microsoft.Quantum.Standard"，例如：</span><span class="sxs-lookup"><span data-stu-id="74dfd-259">In a text editor, edit the .csproj file to change the version of all the "Microsoft.Quantum" `PackageReference` to version 0.6.1904, and change the "Microsoft.Quantum.Canon" package name to "Microsoft.Quantum.Standard", for example:</span></span>

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. <span data-ttu-id="74dfd-260">從命令列執行下列命令：`dotnet msbuild`</span><span class="sxs-lookup"><span data-stu-id="74dfd-260">From the command line, run this command: `dotnet msbuild`</span></span>  
    5. <span data-ttu-id="74dfd-261">執行此命令後，您可能仍需手動解決因上述變更所造成的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-261">After running this, you might still need to manually address errors due to changes listed above.</span></span>  <span data-ttu-id="74dfd-262">在許多情況下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 也會報告這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-262">In many cases, these errors will also be reported by IntelliSense in Visual Studio or Visual Studio Code.</span></span>
        - <span data-ttu-id="74dfd-263">在 Visual Studio 2019 或 Visual Studio Code 中開啟專案或其所屬解決方案的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="74dfd-263">Open the root folder of the project or the containing solution in Visual Studio 2019 or Visual Studio Code.</span></span>
        - <span data-ttu-id="74dfd-264">在編輯器中開啟 .qs 檔案後，您應該會在輸出視窗中看到 Q# 語言延伸模組的輸出。</span><span class="sxs-lookup"><span data-stu-id="74dfd-264">After opening a .qs file in the editor, you should see the output of the Q# language extension in the output window.</span></span>
        - <span data-ttu-id="74dfd-265">成功載入專案後 (會在輸出視窗中指出)，請開啟每個檔案，並手動解決其餘的所有問題。</span><span class="sxs-lookup"><span data-stu-id="74dfd-265">After the project has loaded successfully (indicated in the output window) open each file and manually to address all remaining issues.</span></span>

> [!NOTE]
> * <span data-ttu-id="74dfd-266">對於 0.6 版本，隨附於 Quantum Development Kit 的語言伺服器不支援多個工作區。</span><span class="sxs-lookup"><span data-stu-id="74dfd-266">For the 0.6 release, the language server included with the Quantum Development Kit does not support multiple workspaces.</span></span>
> * <span data-ttu-id="74dfd-267">若要在 Visual Studio Code 中使用專案，請開啟包含專案本身和所有參考專案的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="74dfd-267">In order to work with a project in Visual Studio Code, open the root folder containing the project itself and all referenced projects.</span></span>   
> * <span data-ttu-id="74dfd-268">若要在 Visual Studio 中使用解決方案，解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="74dfd-268">In order to work with a solution in Visual Studio, all projects contained in the solution need to be in the same folder as the solution or in one of its subfolders.</span></span>  
> * <span data-ttu-id="74dfd-269">在專案間移轉至 0.6 和更新版本的參考，以及使用舊版套件的專案，均**不**受支援。</span><span class="sxs-lookup"><span data-stu-id="74dfd-269">References between projects migrated to 0.6 and higher and projects using older package versions are **not** supported.</span></span>

## <a name="version-051904"></a><span data-ttu-id="74dfd-270">0\.5.1904 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-270">Version 0.5.1904</span></span>

<span data-ttu-id="74dfd-271">*發行日期：2019 年 4 月 15 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-271">*Release date: April 15, 2019*</span></span>

<span data-ttu-id="74dfd-272">此版本包含 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="74dfd-272">This release contains bug fixes.</span></span>


## <a name="version-051903"></a><span data-ttu-id="74dfd-273">0\.5.1903 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-273">Version 0.5.1903</span></span>

<span data-ttu-id="74dfd-274">*發行日期：2019 年 3 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-274">*Release date: March 27, 2019*</span></span>

<span data-ttu-id="74dfd-275">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-275">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-276">新增 Jupyter Notebook 的支援，這可提供了解 Q# 的絕佳途徑。</span><span class="sxs-lookup"><span data-stu-id="74dfd-276">Adds support for Jupyter Notebook, which offers a great way to learn about Q#.</span></span>  <span data-ttu-id="74dfd-277">請[查看新的 Jupyter Notebook 範例，並了解如何撰寫您自己的 Notebook](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-277">[Check out new Jupyter Notebook samples and learn how to write your own Notebooks](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="74dfd-278">將整數 adder 演算法新增至 Quantum Canon 程式庫。</span><span class="sxs-lookup"><span data-stu-id="74dfd-278">Adds integer adder arithmetic to the Quantum Canon library.</span></span>  <span data-ttu-id="74dfd-279">另請參閱[說明如何使用新的整數 adder](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb) 的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="74dfd-279">See also a Jupyter Notebook that [describes how to use the new integer adders](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).</span></span>

- <span data-ttu-id="74dfd-280">社群回報的 DumpRegister 問題 ([#148](https://github.com/Microsoft/Quantum/issues/148)) 的 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="74dfd-280">Bug fix for DumpRegister issue reported by the community ([#148](https://github.com/Microsoft/Quantum/issues/148)).</span></span>

- <span data-ttu-id="74dfd-281">新增了從 [Using 陳述式](xref:microsoft.quantum.language.statements)傳回的功能。</span><span class="sxs-lookup"><span data-stu-id="74dfd-281">Added ability to return from within a [using statement](xref:microsoft.quantum.language.statements).</span></span>

- <span data-ttu-id="74dfd-282">全新設計的[使用者入門指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-282">Revamped [getting started guide](xref:microsoft.quantum.install).</span></span>


## <a name="version-051902"></a><span data-ttu-id="74dfd-283">0\.5.1902 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-283">Version 0.5.1902</span></span>

<span data-ttu-id="74dfd-284">*發行日期：2019 年 2 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-284">*Release date: February 27, 2019*</span></span>

<span data-ttu-id="74dfd-285">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-285">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-286">新增跨平台 Python 主機的支援。</span><span class="sxs-lookup"><span data-stu-id="74dfd-286">Adds support for a cross-platform Python host.</span></span>  <span data-ttu-id="74dfd-287">適用於 Python 的 `qsharp` 套件可讓您輕鬆地從 Python 內模擬 Q# 作業和函式。</span><span class="sxs-lookup"><span data-stu-id="74dfd-287">The `qsharp` package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="74dfd-288">深入了解 [Python 互通性](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-288">Learn more about [Python interoperability](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="74dfd-289">Visual Studio 和 Visual Studio Code 延伸模組現已支援符號 (例如函式和作業) 的重新命名。</span><span class="sxs-lookup"><span data-stu-id="74dfd-289">The Visual Studio and Visual Studio Code extensions now support renaming of symbols (e.g., functions and operations).</span></span>

- <span data-ttu-id="74dfd-290">Visual Studio 延伸模組現已可安裝在 Visual Studio 2019 上。</span><span class="sxs-lookup"><span data-stu-id="74dfd-290">The Visual Studio extension can now be installed on Visual Studio 2019.</span></span>

## <a name="version-041901"></a><span data-ttu-id="74dfd-291">0\.4.1901 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-291">Version 0.4.1901</span></span>

<span data-ttu-id="74dfd-292">*發行日期：2019 年 1 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-292">*Release date: January 30, 2019*</span></span>

<span data-ttu-id="74dfd-293">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="74dfd-293">This release contains the following:</span></span>

- <span data-ttu-id="74dfd-294">新增新的基本類型 BigInt 的支援，此類型代表任意大小帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="74dfd-294">adds support for a new primitive type, BigInt, which represents a signed integer of arbitrary size.</span></span>  <span data-ttu-id="74dfd-295">深入了解 [BigInt 類型](xref:microsoft.quantum.language.type-model)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-295">Learn more about [BigInt type](xref:microsoft.quantum.language.type-model).</span></span>
- <span data-ttu-id="74dfd-296">新增 Toffoli 模擬器，這是一種特殊用途的快速模擬器，可模擬具有大量量子位元的 X、CNOT 和多重受控 X 量子作業。</span><span class="sxs-lookup"><span data-stu-id="74dfd-296">adds new Toffoli simulator, a special purpose fast simulator that can simulate X, CNOT and multi-controlled X quantum operations with very large numbers of qubits.</span></span>  <span data-ttu-id="74dfd-297">深入了解 [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-297">Learn more about [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator).</span></span>
- <span data-ttu-id="74dfd-298">新增簡單的資源估算器，可估算在量子電腦上執行 Q# 作業的指定執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="74dfd-298">adds a simple resource estimator that estimates the resources required to run a given instancee of a Q# operation on a quantum computer.</span></span>  <span data-ttu-id="74dfd-299">深入了解[資源估算器](xref:microsoft.quantum.machines.resources-estimator)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-299">Learn more about the [Resource Estimator](xref:microsoft.quantum.machines.resources-estimator).</span></span>


## <a name="version-0318112802"></a><span data-ttu-id="74dfd-300">0\.3.1811.2802 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-300">Version 0.3.1811.2802</span></span>

<span data-ttu-id="74dfd-301">*發行日期：2018 年 11 月 28 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-301">*Release date: November 28, 2018*</span></span>

<span data-ttu-id="74dfd-302">此版本已在與 `event-stream` NPM 套件相關的[延伸模組清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)期間加上旗標，並從 Marketplace 中移除，但我們的 VS Code 延伸模組並未加以使用。</span><span class="sxs-lookup"><span data-stu-id="74dfd-302">Even though our VS Code extension was not using it, it was flagged and removed from the marketplace during [the extensions purge](https://code.visualstudio.com/blogs/2018/11/26/event-stream) related to the `event-stream` NPM package.</span></span> <span data-ttu-id="74dfd-303">此版本移除了所有可能致使延伸模組觸發任何紅色旗標的執行階段相依性。</span><span class="sxs-lookup"><span data-stu-id="74dfd-303">This version removes all runtime dependencies that could make the extension trigger any red flags.</span></span>

<span data-ttu-id="74dfd-304">如果您先前已安裝此延伸模組，您必須造訪 Visual Studio Marketplace 上的 [Visual Studio Code 延伸模組的 Microsoft Quantum Development Kit](vscode:extension/quantum.quantum-devkit-vscode)，並且按 [安裝] 重新加以安裝。</span><span class="sxs-lookup"><span data-stu-id="74dfd-304">If you had previously installed the extension you will need to install it again by visiting the [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) extension on the Visual Studio Marketplace and press Install.</span></span> <span data-ttu-id="74dfd-305">很抱歉造成您的不便。</span><span class="sxs-lookup"><span data-stu-id="74dfd-305">We are sorry about the inconvenience.</span></span>


## <a name="version-0318111511"></a><span data-ttu-id="74dfd-306">0\.3.1811.1511 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-306">Version 0.3.1811.1511</span></span>

<span data-ttu-id="74dfd-307">*發行日期：2018 年 11 月 20 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-307">*Release date: November 20, 2018*</span></span>

<span data-ttu-id="74dfd-308">此版本修正了導致某些使用者無法成功載入 Visual Studio 延伸模組的 Bug。</span><span class="sxs-lookup"><span data-stu-id="74dfd-308">This release fixes a bug that prevented some users to successfully load the Visual Studio extension.</span></span>

<span data-ttu-id="74dfd-309">如果您要從 0.2 版的 Quantum Development Kit 升級，請深入了解 [Q# 語言的變更和 Q# 程式的移轉](xref:microsoft.quantum.relnotes.migration-0-3)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-309">If you are upgrading from a 0.2 version of the Quantum Development Kit, learn more about [Q# language changes and migrating your Q# program](xref:microsoft.quantum.relnotes.migration-0-3).</span></span>

## <a name="version-031811203"></a><span data-ttu-id="74dfd-310">0\.3.1811.203 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-310">Version 0.3.1811.203</span></span>

<span data-ttu-id="74dfd-311">*發行日期：2018 年 11 月 2 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-311">*Release date: November 2, 2018*</span></span>

<span data-ttu-id="74dfd-312">此版本包含一些 Bug 修正，包括：</span><span class="sxs-lookup"><span data-stu-id="74dfd-312">This release includes a few bug fixes, including:</span></span>

* <span data-ttu-id="74dfd-313">在特定情況下，叫用 `DumpMachine` 可能會變更模擬器的狀態。</span><span class="sxs-lookup"><span data-stu-id="74dfd-313">Invoking `DumpMachine` could change the state of the simulator under certain situations.</span></span>
* <span data-ttu-id="74dfd-314">移除了在使用 2.1.403 之前的 .NET Core 版本建置專案時所產生的編譯警告。</span><span class="sxs-lookup"><span data-stu-id="74dfd-314">Removed compilation warnings when building projects using a version of .NET Core previous to 2.1.403.</span></span>
* <span data-ttu-id="74dfd-315">清除了文件，特別是在 VS Code 或 Visual Studio 中暫留滑鼠時所顯示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="74dfd-315">Clean up of documentation, specially the tooltips shown during mouse hover in VS Code or Visual Studio.</span></span>

<span data-ttu-id="74dfd-316">如果您要從 0.2 版的 Quantum Development Kit 升級，請深入了解 [Q# 語言的變更和 Q# 程式的移轉](xref:microsoft.quantum.relnotes.migration-0-3)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-316">If you are upgrading from a 0.2 version of the Quantum Development Kit, learn more about [Q# language changes and migrating your Q# program](xref:microsoft.quantum.relnotes.migration-0-3).</span></span>

## <a name="version-0318102508"></a><span data-ttu-id="74dfd-317">0\.3.1810.2508 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-317">Version 0.3.1810.2508</span></span>

<span data-ttu-id="74dfd-318">*發行日期：2018 年 10 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-318">*Release date: October 29, 2018*</span></span>

<span data-ttu-id="74dfd-319">此版本包含新的語言功能和改良的開發人員體驗：</span><span class="sxs-lookup"><span data-stu-id="74dfd-319">This release includes new language features and an improved developer experience:</span></span>

* <span data-ttu-id="74dfd-320">此版本包含 Q# 的語言伺服器，以及 Visual Studio 和 Visual Studio Code 的用戶端整合。</span><span class="sxs-lookup"><span data-stu-id="74dfd-320">This release includes a language server for Q#, as well as the client integrations for Visual Studio and Visual Studio Code.</span></span> <span data-ttu-id="74dfd-321">這會啟用一組新的 IntelliSense 功能，以及以波狀底線的形式輸入錯誤和警告的即時反饋。</span><span class="sxs-lookup"><span data-stu-id="74dfd-321">This enables a new set of IntelliSense features along with live feedback on typing in form of squiggly underlinings of errors and warnings.</span></span> 
* <span data-ttu-id="74dfd-322">整體而言，這項更新可讓您輕鬆瀏覽至精確的診斷範圍，並且在顯示的暫留資訊中提供其他詳細資料，而大幅改善了診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="74dfd-322">This update greatly improves diagnostic messages in general, with easy navigation to and precise ranges for diagnostics and additional details in the displayed hover information.</span></span>
* <span data-ttu-id="74dfd-323">Q# 語言已經過適當擴充，而統合了開發人員執行常見作業的方式，並且對語言功能進行了新的強化，以有效表達量子運算。</span><span class="sxs-lookup"><span data-stu-id="74dfd-323">The Q# language has been extended in ways that unifies the ways developers can do common operations and new enhancements to the language features to powerfully express quantum computation.</span></span>  <span data-ttu-id="74dfd-324">此版本的 Q# 語言有若干重大變更。</span><span class="sxs-lookup"><span data-stu-id="74dfd-324">There are a handful of breaking changes to the Q# language with this release.</span></span>   

<span data-ttu-id="74dfd-325">深入了解 [Q# 語言的變更和 Q# 程式的移轉](xref:microsoft.quantum.relnotes.migration-0-3)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-325">Learn more about [Q# language changes and migrating your Q# program](xref:microsoft.quantum.relnotes.migration-0-3).</span></span>

<span data-ttu-id="74dfd-326">此版本也包含新的量子化學程式庫：</span><span class="sxs-lookup"><span data-stu-id="74dfd-326">This release also includes a new quantum chemistry library:</span></span>

* <span data-ttu-id="74dfd-327">化學程式庫包含新的 Hamiltonian 模擬功能，包括：</span><span class="sxs-lookup"><span data-stu-id="74dfd-327">The chemistry library contains new Hamiltonian simulation features, including:</span></span>
    - <span data-ttu-id="74dfd-328">Trotter – 任意偶次的 Suzuki 整合器，用以改善模擬正確性。</span><span class="sxs-lookup"><span data-stu-id="74dfd-328">Trotter–Suzuki integrators of arbitrary even order for improved simulation accuracy.</span></span>
    - <span data-ttu-id="74dfd-329">採用化學專用最佳化的量子位元化模擬技術，用以降低 $T$ 閘道複雜度。</span><span class="sxs-lookup"><span data-stu-id="74dfd-329">Qubitization simulation technique with chemistry-specific optimizations for reducing $T$-gate complexity.</span></span>
* <span data-ttu-id="74dfd-330">導入了新的開放原始碼結構描述，名為 Broombridge 結構描述 (得名自被譽為 Hamiltonian 發源地的[地標](https://en.wikipedia.org/wiki/Broom_Bridge))，用以匯入分子的表示法及加以模擬。</span><span class="sxs-lookup"><span data-stu-id="74dfd-330">A new open source schema, called Broombridge Schema (in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) celebrated as a birthplace of Hamiltonians), is introduced for importing representations of molecules and simulating them.</span></span>
* <span data-ttu-id="74dfd-331">提供多個使用 Broombridge 結構描述定義的化學標記法。</span><span class="sxs-lookup"><span data-stu-id="74dfd-331">Multiple chemical representations defined using the Broombridge Schema are provided.</span></span>  <span data-ttu-id="74dfd-332">這些模型由 [NWChem](http://www.nwchem-sw.org/) (一種開放原始碼高效能運算化學工具) 所產生。</span><span class="sxs-lookup"><span data-stu-id="74dfd-332">These models were generated by [NWChem](http://www.nwchem-sw.org/), an open source high-performance computational chemistry tool.</span></span>
* <span data-ttu-id="74dfd-333">教學課程和範例會說明如何使用化學程式庫和 Broombridge 資料模型來：</span><span class="sxs-lookup"><span data-stu-id="74dfd-333">Tutorials and Samples describe how to use the chemistry library and the Broombridge data models to:</span></span>
    - <span data-ttu-id="74dfd-334">使用化學程式庫建構簡單的 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="74dfd-334">Construct simple Hamiltonians using the chemistry library</span></span>
    - <span data-ttu-id="74dfd-335">使用階段估算呈現氫化鋰的基態能量和激發態能量。</span><span class="sxs-lookup"><span data-stu-id="74dfd-335">Visualize ground and excited energies of Lithium Hydride using phase estimation.</span></span>
    - <span data-ttu-id="74dfd-336">執行量子化學模擬的資源估算。</span><span class="sxs-lookup"><span data-stu-id="74dfd-336">Perform resource estimates of quantum chemistry simulation.</span></span>
    - <span data-ttu-id="74dfd-337">對 Broombridge 結構描述所代表的分子估算能階。</span><span class="sxs-lookup"><span data-stu-id="74dfd-337">Estimate energy levels of molecules represented by the Broombridge schema.</span></span>
* <span data-ttu-id="74dfd-338">文件會說明如何使用 NWChem 產生 Q# 的量子模擬所適用的其他化學模型。</span><span class="sxs-lookup"><span data-stu-id="74dfd-338">Documentation describes how to use NWChem to generate additional chemical models for quantum simulation with Q#.</span></span>

<span data-ttu-id="74dfd-339">深入了解 [Quantum Development Kit 化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-339">Learn more about the [Quantum Development Kit chemistry library](xref:microsoft.quantum.chemistry.concepts.intro).</span></span>

<span data-ttu-id="74dfd-340">透過新的化學程式庫，我們將程式庫劃分到新的 GitHub 存放庫 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) 中。</span><span class="sxs-lookup"><span data-stu-id="74dfd-340">With the new chemistry library, we are separating out the libraries into a new GitHub repo, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).</span></span>  <span data-ttu-id="74dfd-341">範例仍保留在存放庫 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 中。</span><span class="sxs-lookup"><span data-stu-id="74dfd-341">The samples remain in the repo [Microsoft/Quantum](https://github.com/Microsoft/Quantum).</span></span>  <span data-ttu-id="74dfd-342">歡迎大家參與對這兩個存放庫的建構！</span><span class="sxs-lookup"><span data-stu-id="74dfd-342">We welcome contributions to both!</span></span>

<span data-ttu-id="74dfd-343">此版本包含針對社群回報的問題而提供的 Bug 修正和功能：</span><span class="sxs-lookup"><span data-stu-id="74dfd-343">This release includes bug fixes and features for issues reported by the community:</span></span>

* <span data-ttu-id="74dfd-344">Intellisense 適用於 Q# 嗎？</span><span class="sxs-lookup"><span data-stu-id="74dfd-344">Intellisense for Q#?</span></span> <span data-ttu-id="74dfd-345">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-345">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).</span></span>
* <span data-ttu-id="74dfd-346">.qs 檔案 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-346">.qs files ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).</span></span>
* <span data-ttu-id="74dfd-347">改善 If 陳述式中的大括弧節略時的錯誤訊息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-347">Improve error message when curly braces are abbreviated in if statement ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).</span></span>
* <span data-ttu-id="74dfd-348">支援可變動 (重新) 繫結上的元組解構 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-348">Support tuple deconstruction at mutable (re-)binding ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).</span></span>
* <span data-ttu-id="74dfd-349">執行提供的 BitFlipCode 時發生的錯誤 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-349">Error Running Provided BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>
* <span data-ttu-id="74dfd-350">H2SimulationGUI 有時會顯示大型尖峰 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-350">H2SimulationGUI displays big peaks sometimes ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="74dfd-351">社群貢獻</span><span class="sxs-lookup"><span data-stu-id="74dfd-351">Community Contributions</span></span>

<span data-ttu-id="74dfd-352">**感謝**</span><span class="sxs-lookup"><span data-stu-id="74dfd-352">**Thank you!**</span></span> <span data-ttu-id="74dfd-353">下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。</span><span class="sxs-lookup"><span data-stu-id="74dfd-353">to the following contributors to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="74dfd-354">這些貢獻讓 Q# 程式碼的範例更加豐富：</span><span class="sxs-lookup"><span data-stu-id="74dfd-354">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="74dfd-355">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman))：藉由建立從 QASM 到的 Q# 的轉譯程式，改善了 QASM/Q# 開發人員的體驗。</span><span class="sxs-lookup"><span data-stu-id="74dfd-355">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Improved the experience for QASM/Q# developers by creating a QASM to Q# translator.</span></span> <span data-ttu-id="74dfd-356">[PR #58](https://github.com/Microsoft/Quantum/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-356">[PR #58](https://github.com/Microsoft/Quantum/pull/58).</span></span>

* <span data-ttu-id="74dfd-357">Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了實作 CHSH 賽局的範例；這是與非定域性相關的量子賽局。</span><span class="sxs-lookup"><span data-stu-id="74dfd-357">Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Contributed a sample implementing the CHSH Game, a quantum game related to non-locality.</span></span>  <span data-ttu-id="74dfd-358">[PR #84](https://github.com/Microsoft/Quantum/pull/84)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-358">[PR #84](https://github.com/Microsoft/Quantum/pull/84).</span></span>

<span data-ttu-id="74dfd-359">同時感謝 Rohit Gupta ([@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90))、Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) 和 Lee James O'Riordan ([@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)) 為了改善我們所有人的內容，在文件、拼字和校對方面的努力付出！</span><span class="sxs-lookup"><span data-stu-id="74dfd-359">Thank you also to Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), and Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) for their work improving the content for all of us through documentation, spelling and typo corrections!</span></span> 

## <a name="version-021809701"></a><span data-ttu-id="74dfd-360">0\.2.1809.701 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-360">Version 0.2.1809.701</span></span>

<span data-ttu-id="74dfd-361">*發行日期：2018 年 9 月 10 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-361">*Release date: September 10, 2018*</span></span>

<span data-ttu-id="74dfd-362">此版本包含對社群回報的問題所做的 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="74dfd-362">This release includes bug fixes for issues reported by the community.</span></span> <span data-ttu-id="74dfd-363">其中包括：</span><span class="sxs-lookup"><span data-stu-id="74dfd-363">Including:</span></span>

* <span data-ttu-id="74dfd-364">無法使用移位運算子 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-364">Unable to use shift operator ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).</span></span>
* <span data-ttu-id="74dfd-365">在列印到主控台，`QCTraceSimulator` 上的 `DumpMachine` / `DumpRegister` 會失敗 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-365">`DumpMachine` / `DumpRegister` fails on `QCTraceSimulator` when printing to console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).</span></span>
* <span data-ttu-id="74dfd-366">允許配置 0 個量子位元 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-366">Allow allocating 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).</span></span>
* <span data-ttu-id="74dfd-367">`AssertQubitState` 需要明確的 Complex() 呼叫 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-367">`AssertQubitState` requires explicit Complex() call ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).</span></span>
* <span data-ttu-id="74dfd-368">macOS 上的 `Measure` 作業一律會傳回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="74dfd-368">`Measure` operation always returns `One` on macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>

<span data-ttu-id="74dfd-369">感謝您！</span><span class="sxs-lookup"><span data-stu-id="74dfd-369">Thanks!</span></span> 

## <a name="version-0218063001"></a><span data-ttu-id="74dfd-370">0\.2.1806.3001 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-370">Version 0.2.1806.3001</span></span>

<span data-ttu-id="74dfd-371">*發行日期：2018 年 6 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-371">*Release date: June 30, 2018*</span></span>

<span data-ttu-id="74dfd-372">此版本只是 [GitHub 上回報的問題 #48](https://github.com/Microsoft/Quantum/issues/48) (如果使用者名稱包含空格，Q# 編譯即會失敗) 的快速修正。</span><span class="sxs-lookup"><span data-stu-id="74dfd-372">This releases is just a quick fix for [issue #48 reported on GitHub](https://github.com/Microsoft/Quantum/issues/48) (Q# compilation fails if user name contains a blank space).</span></span> <span data-ttu-id="74dfd-373">使用對應的新版本 (`0.2.1806.3001-preview`) 時，請遵循與 `0.2.1806.1503` 相同的更新指示。</span><span class="sxs-lookup"><span data-stu-id="74dfd-373">Follow same update instructions as `0.2.1806.1503` with the corresponding new version (`0.2.1806.3001-preview`).</span></span>

## <a name="version-0218061503"></a><span data-ttu-id="74dfd-374">0\.2.1806.1503 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-374">Version 0.2.1806.1503</span></span>

<span data-ttu-id="74dfd-375">*發行日期：2018 年 6 月 22 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-375">*Release date: June 22, 2018*</span></span>

<span data-ttu-id="74dfd-376">此版本包含幾項社群貢獻，以及有所改善的偵錯體驗和增進的效能。</span><span class="sxs-lookup"><span data-stu-id="74dfd-376">This release includes several community contributions as well as an improved debugging experience and improved performance.</span></span>  <span data-ttu-id="74dfd-377">具體來說：</span><span class="sxs-lookup"><span data-stu-id="74dfd-377">Specifically:</span></span>

* <span data-ttu-id="74dfd-378">QuantumSimulator 目標電腦的小型和大型模擬的效能改進。</span><span class="sxs-lookup"><span data-stu-id="74dfd-378">Performance improvements on both small and large simulations for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="74dfd-379">改良的偵錯功能。</span><span class="sxs-lookup"><span data-stu-id="74dfd-379">Improved debugging functionality.</span></span>
* <span data-ttu-id="74dfd-380">社群在 Bug 修正、新的 Helper 函式、作業和新範例等方面的貢獻。</span><span class="sxs-lookup"><span data-stu-id="74dfd-380">Community contributions in bug fixes, new helper functions, operations and new samples.</span></span>

### <a name="performance-improvements"></a><span data-ttu-id="74dfd-381">效能改善</span><span class="sxs-lookup"><span data-stu-id="74dfd-381">Performance improvements</span></span>

<span data-ttu-id="74dfd-382">這項更新包括所有目標電腦的大量和少量量子位元模擬皆有顯著的效能改善。</span><span class="sxs-lookup"><span data-stu-id="74dfd-382">This update includes significant performance improvements for simulation of large and small numbers of qubits for all the target machines.</span></span>  <span data-ttu-id="74dfd-383">經由在 Quantum Development Kit 中作為標準範例的 H<sub>2</sub> 模擬，可發現改善的幅度顯而易見。</span><span class="sxs-lookup"><span data-stu-id="74dfd-383">This improvement is easily visible with the H<sub>2</sub> simulation that is a standard sample in the Quantum Development Kit.</span></span>

### <a name="improved-debugging-functionality"></a><span data-ttu-id="74dfd-384">改良的偵錯功能</span><span class="sxs-lookup"><span data-stu-id="74dfd-384">Improved debugging functionality</span></span>

<span data-ttu-id="74dfd-385">此更新新增了偵錯功能：</span><span class="sxs-lookup"><span data-stu-id="74dfd-385">This update adds new debugging functionality:</span></span>
* <span data-ttu-id="74dfd-386">新增了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 兩個新作業，可輸出目標量子電腦在某個時間點的波形函式相關資訊。</span><span class="sxs-lookup"><span data-stu-id="74dfd-386">Added two new operations,  @"microsoft.quantum.extensions.diagnostics.dumpmachine" and @"microsoft.quantum.extensions.diagnostics.dumpregister" that output wave function information about the target quantum machine at a point in time.</span></span>  
* <span data-ttu-id="74dfd-387">在 Visual Studio 中，對單一量子位元測量 $\ket{1}$ 的機率現在會自動顯示在 QuantumSimulator 目標電腦的偵錯視窗中。</span><span class="sxs-lookup"><span data-stu-id="74dfd-387">In Visual Studio, the probability of measuring a $\ket{1}$ on a single qubit is now automatically shown in the debugging window for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="74dfd-388">在 Visual Studio 中，變數屬性在 [自動變數]  和 [區域變數]  偵錯視窗中的顯示已有所改善。</span><span class="sxs-lookup"><span data-stu-id="74dfd-388">In Visual Studio, improved the display of variable properties in the **Autos** and **Locals** debug windows.</span></span> 

<span data-ttu-id="74dfd-389">深入了解[測試和偵錯](xref:microsoft.quantum.techniques.testing-and-debugging)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-389">Learn more about [Testing and Debugging](xref:microsoft.quantum.techniques.testing-and-debugging).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="74dfd-390">社群貢獻</span><span class="sxs-lookup"><span data-stu-id="74dfd-390">Community Contributions</span></span>

<span data-ttu-id="74dfd-391">Q# 編碼員社群正持續擴展中，我們十分樂見第一個由使用者參與內容建構的程式庫和範例已提交至我們的開放程式碼基底，位於 http://github.com/Microsoft/quantum 。</span><span class="sxs-lookup"><span data-stu-id="74dfd-391">The Q# coder community is growing and we are thrilled to see the first user contributed libraries and samples that were submitted to our open code base at http://github.com/Microsoft/quantum.</span></span>  <span data-ttu-id="74dfd-392">**非常感謝**</span><span class="sxs-lookup"><span data-stu-id="74dfd-392">**A big Thank you!**</span></span> <span data-ttu-id="74dfd-393">下列參與者：</span><span class="sxs-lookup"><span data-stu-id="74dfd-393">to the following contributors:</span></span>
* <span data-ttu-id="74dfd-394">Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一個範例，定義以轉換為基礎的邏輯合成方法，以建構用來實作指定排列的 Toffoli 網路。</span><span class="sxs-lookup"><span data-stu-id="74dfd-394">Mathias Soeken ([@msoeken](https://github.com/msoeken)):  contributed a sample defining a transformation based logic synthesis method that constructs Toffoli networks to implement a given permutation.</span></span> <span data-ttu-id="74dfd-395">其程式碼完全以 Q# 函式和作業撰寫。</span><span class="sxs-lookup"><span data-stu-id="74dfd-395">The code is written entirely in Q# functions and operations.</span></span>  <span data-ttu-id="74dfd-396">[PR #41](https://github.com/Microsoft/Quantum/pull/41)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-396">[PR #41](https://github.com/Microsoft/Quantum/pull/41).</span></span>
* <span data-ttu-id="74dfd-397">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman))：Microsoft MVP Rolf Huisman 提供了一個範例，可從 Q# 程式碼為不具傳統控制流程的限定程式類別和限定的量子作業產生一般 QASM 程式碼。</span><span class="sxs-lookup"><span data-stu-id="74dfd-397">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Microsoft MVP Rolf Huisman contributed a sample that generates flat QASM code from Q# code for a restricted class of programs that do not have classical control flow and restricted quantum operations.</span></span> [<span data-ttu-id="74dfd-398">PR #59</span><span class="sxs-lookup"><span data-stu-id="74dfd-398">PR #59</span></span>](https://github.com/Microsoft/Quantum/pull/59)
* <span data-ttu-id="74dfd-399">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：藉由提交受控作業適用的程式庫函式，協助我們改善程式碼基底。</span><span class="sxs-lookup"><span data-stu-id="74dfd-399">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): helped to improve our code base by submitting a library function for controlled operations.</span></span> [<span data-ttu-id="74dfd-400">PR #53</span><span class="sxs-lookup"><span data-stu-id="74dfd-400">PR #53</span></span>](https://github.com/Microsoft/Quantum/pull/53)
* <span data-ttu-id="74dfd-401">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修正 @"microsoft.quantum.canon.quantumphaseestimation" 並建立了新的單元測試。</span><span class="sxs-lookup"><span data-stu-id="74dfd-401">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): fixed @"microsoft.quantum.canon.quantumphaseestimation" and created new unit tests.</span></span>  [<span data-ttu-id="74dfd-402">PR #54</span><span class="sxs-lookup"><span data-stu-id="74dfd-402">PR #54</span></span>](https://github.com/Microsoft/Quantum/pull/54)
* <span data-ttu-id="74dfd-403">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：藉由確定 QuantumSimulator 執行個體已處置，清除了遙傳範例。</span><span class="sxs-lookup"><span data-stu-id="74dfd-403">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): cleaned the Teleportation sample by making sure the QuantumSimulator instance is disposed.</span></span> [<span data-ttu-id="74dfd-404">PR #20</span><span class="sxs-lookup"><span data-stu-id="74dfd-404">PR #20</span></span>](https://github.com/Microsoft/Quantum/pull/20)

<span data-ttu-id="74dfd-405">同時也**非常感謝**</span><span class="sxs-lookup"><span data-stu-id="74dfd-405">Additionally, a big **Thank You!**</span></span> <span data-ttu-id="74dfd-406">參與商業工程服務小組的 Microsoft 軟體工程師，他們在參加黑客松期間時對我們的文件做出了重要的變更。</span><span class="sxs-lookup"><span data-stu-id="74dfd-406">to these Microsoft Software Engineers from the Commercial Engineering Services team contributors who made valuable changes to our documentation during their Hackathon.</span></span>  <span data-ttu-id="74dfd-407">他們的變更我們所有人大幅提升了定義的明確性和上線體驗：</span><span class="sxs-lookup"><span data-stu-id="74dfd-407">Their changes vastly improved the clarity and onboarding experience for all of us:</span></span>
* <span data-ttu-id="74dfd-408">Sascha Corti</span><span class="sxs-lookup"><span data-stu-id="74dfd-408">Sascha Corti</span></span>
* <span data-ttu-id="74dfd-409">Mihaela Curmei</span><span class="sxs-lookup"><span data-stu-id="74dfd-409">Mihaela Curmei</span></span>
* <span data-ttu-id="74dfd-410">John Donnelly</span><span class="sxs-lookup"><span data-stu-id="74dfd-410">John Donnelly</span></span>
* <span data-ttu-id="74dfd-411">Kirill Logachev</span><span class="sxs-lookup"><span data-stu-id="74dfd-411">Kirill Logachev</span></span>
* <span data-ttu-id="74dfd-412">Jan Pospisil</span><span class="sxs-lookup"><span data-stu-id="74dfd-412">Jan Pospisil</span></span>
* <span data-ttu-id="74dfd-413">Anita Ramanan</span><span class="sxs-lookup"><span data-stu-id="74dfd-413">Anita Ramanan</span></span>
* <span data-ttu-id="74dfd-414">Frances Tibble</span><span class="sxs-lookup"><span data-stu-id="74dfd-414">Frances Tibble</span></span>
* <span data-ttu-id="74dfd-415">Alessandro Vozza</span><span class="sxs-lookup"><span data-stu-id="74dfd-415">Alessandro Vozza</span></span>

### <a name="update-existing-projects"></a><span data-ttu-id="74dfd-416">更新現有的專案</span><span class="sxs-lookup"><span data-stu-id="74dfd-416">Update existing projects</span></span>

<span data-ttu-id="74dfd-417">此版本具完整的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="74dfd-417">This release is fully backwards compatible.</span></span> <span data-ttu-id="74dfd-418">只要將專案中的 nuget 套件更新為 `0.2.1806.1503-preview` 版，並執行**完整重建**，即可確定所有中繼檔案都會重新產生。</span><span class="sxs-lookup"><span data-stu-id="74dfd-418">Just update the nuget pakages in your projects to version `0.2.1806.1503-preview` and do a **full rebuild** to make sure all intermediate files are regenerated.</span></span>

<span data-ttu-id="74dfd-419">在 Visual Studio 中，依照關於[更新套件](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的一般指示操作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-419">From Visual Studio, follow the normal instructions on how to [update a package](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).</span></span>

<span data-ttu-id="74dfd-420">若要更新命令列的專案範本，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="74dfd-420">To update project templates for the command line, run the following command:</span></span>
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

<span data-ttu-id="74dfd-421">執行此命令後，任何使用 `dotnet new <project-type> -lang Q#` 建立的新專案都會自動使用此版本的 Quantum Development Kit。</span><span class="sxs-lookup"><span data-stu-id="74dfd-421">After running this command, any new projects created using `dotnet new <project-type> -lang Q#` will automatically use this version of the Quantum Development Kit.</span></span>

<span data-ttu-id="74dfd-422">若要更新現有的專案以使用最新版本，請從各個專案的目錄中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="74dfd-422">To update an existing project to use the newest version, run the following command from within the directory for each project:</span></span>

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

<span data-ttu-id="74dfd-423">如果現有的專案也使用 XUnit 整合進行單元測試，則也可以使用類似的命令來更新該套件：</span><span class="sxs-lookup"><span data-stu-id="74dfd-423">If an existing project also uses XUnit integration for unit testing, then a similar command can be used to update that package as well:</span></span>
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

<span data-ttu-id="74dfd-424">根據您的測試專案所使用的 XUnit 版本，您可能也需要將 XUnit 更新為 2.3.1：</span><span class="sxs-lookup"><span data-stu-id="74dfd-424">Depending on the version of XUnit that your test project uses, you may also need to update XUnit to 2.3.1:</span></span>
```
dotnet add package xunit -v "2.3.1" 
```

<span data-ttu-id="74dfd-425">更新之後，請務必執行下列動作，以移除舊版所產生的所有暫存檔案：</span><span class="sxs-lookup"><span data-stu-id="74dfd-425">After the update, make sure you remove all temporary files generated by the previous version by doing:</span></span>
```
dotnet clean 
```

### <a name="known-issues"></a><span data-ttu-id="74dfd-426">已知問題</span><span class="sxs-lookup"><span data-stu-id="74dfd-426">Known Issues</span></span>

<span data-ttu-id="74dfd-427">沒有其他已知問題需要報告。</span><span class="sxs-lookup"><span data-stu-id="74dfd-427">No aditional known issues to report.</span></span>


## <a name="version-0218022202"></a><span data-ttu-id="74dfd-428">0\.2.1802.2202 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-428">Version 0.2.1802.2202</span></span>

<span data-ttu-id="74dfd-429">*發行日期：2018 年 2 月 26 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-429">*Release date: February 26, 2018*</span></span>

<span data-ttu-id="74dfd-430">此版本提供在更多平台上進行開發的支援、語言互通性，和效能的強化。</span><span class="sxs-lookup"><span data-stu-id="74dfd-430">This release brings support for development on more platforms, language interoperability, and performance enhancements.</span></span> <span data-ttu-id="74dfd-431">具體來說：</span><span class="sxs-lookup"><span data-stu-id="74dfd-431">Specifically:</span></span>

- <span data-ttu-id="74dfd-432">支援以 macOS 和 Linux 為基礎的開發。</span><span class="sxs-lookup"><span data-stu-id="74dfd-432">Support for macOS- and Linux-based development.</span></span> 
- <span data-ttu-id="74dfd-433">.NET Core 相容性，包括對 Visual Studio Code 的跨平台支援。</span><span class="sxs-lookup"><span data-stu-id="74dfd-433">.NET Core compatibility, including support for Visual Studio Code across platforms.</span></span>
- <span data-ttu-id="74dfd-434">Quantum Development Kit 程式庫的完整開放原始碼授權。</span><span class="sxs-lookup"><span data-stu-id="74dfd-434">A full Open Source license for the Quantum Development Kit Libraries.</span></span>
- <span data-ttu-id="74dfd-435">針對需要 20 個或更多量子位元的專案改善了模擬器效能。</span><span class="sxs-lookup"><span data-stu-id="74dfd-435">Improved simulator performance on projects requiring 20 or more qubits.</span></span>
- <span data-ttu-id="74dfd-436">與 Python 語言的互通性 (在 Windows 上可使用預覽版本)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-436">Interoperability with the Python language (preview release available on Windows).</span></span>

### <a name="net-editions"></a><span data-ttu-id="74dfd-437">.NET 版本</span><span class="sxs-lookup"><span data-stu-id="74dfd-437">.NET Editions</span></span>

<span data-ttu-id="74dfd-438">.NET 平台有兩種不同的版本可供使用：隨附於 Windows 的 .NET Framework，以及 Windows、macOS 和 Linux 上提供的開放原始碼 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="74dfd-438">The .NET platform is available through two different editions, the .NET Framework that is provided with Windows, and the open-source .NET Core that is available on Windows, macOS and Linux.</span></span>
<span data-ttu-id="74dfd-439">在此版本中，Quantum Development Kit 大部分的組件均以 .NET Standard 程式庫的形式提供，這是 Framework 和 Core 通用的一組類別。</span><span class="sxs-lookup"><span data-stu-id="74dfd-439">With this release, most parts of the Quantum Development Kit are provided as libraries for .NET Standard, the set of classes common to both Framework and Core.</span></span>
<span data-ttu-id="74dfd-440">這些程式庫因而可與最新版本的 .NET Framework 或 .NET Core 相容。</span><span class="sxs-lookup"><span data-stu-id="74dfd-440">These libraries are therefore compatible with recent versions of either .NET Framework or .NET Core.</span></span>

<span data-ttu-id="74dfd-441">因此，為了確保使用 Quantum Development Kit 撰寫的專案能有最高的可攜性，我們建議，使用 Quantum Development Kit 撰寫的程式庫專案應以 .NET Standard 為目標，而主控台應用程式則以 .NET Core 為目標。</span><span class="sxs-lookup"><span data-stu-id="74dfd-441">Thus, to help ensure that projects written using the Quantum Development Kit are as portable as possible, we recommend that library projects written using the Quantum Development Kit target .NET Standard, while console applications target .NET Core.</span></span>
<span data-ttu-id="74dfd-442">由於舊版的 Quantum Development Kit 僅支援 .NET Framework，因此您可能需要移轉現有的專案；如需如何執行此作業的詳細資訊，請參閱下文。</span><span class="sxs-lookup"><span data-stu-id="74dfd-442">Since previous releases of the Quantum Development Kit only supported .NET Framework, you may need to migrate your existing projects; see below for details on how to do this.</span></span>

### <a name="project-migration"></a><span data-ttu-id="74dfd-443">專案移轉</span><span class="sxs-lookup"><span data-stu-id="74dfd-443">Project Migration</span></span>

<span data-ttu-id="74dfd-444">使用舊版 Quantum Development Kit 建立的專案仍可運作，只要您未更新其中使用的 NuGet 套件即可。</span><span class="sxs-lookup"><span data-stu-id="74dfd-444">Projects created using previous versions of Quantum Development Kit will still work, as long as you don't update the NuGet packages used in them.</span></span> <span data-ttu-id="74dfd-445">若要將現有的程式碼移轉至新版本，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="74dfd-445">To migrate existing code to the new version, perform the following steps:</span></span>
1. <span data-ttu-id="74dfd-446">使用正確類型的 Q# 專案範本，建立新的 .NET Core 專案 (應用程式、程式庫或測試專案)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-446">Create a new .NET Core project using the right type of Q# project template (Application, Library or Test Project).</span></span>
2. <span data-ttu-id="74dfd-447">將舊專案中現有的 .qs 和 .cs/.fs 檔案複製到新專案 (使用 [新增] > [現有項目])。</span><span class="sxs-lookup"><span data-stu-id="74dfd-447">Copy existing .qs and .cs/.fs files from the old project to the new project (using Add > Existing Item).</span></span> <span data-ttu-id="74dfd-448">請勿複製 AssemblyInfo.cs 檔案。</span><span class="sxs-lookup"><span data-stu-id="74dfd-448">Do not copy the AssemblyInfo.cs file.</span></span>
3. <span data-ttu-id="74dfd-449">建置並執行新的專案。</span><span class="sxs-lookup"><span data-stu-id="74dfd-449">Build and run the new project.</span></span>

<span data-ttu-id="74dfd-450">請注意，命名空間 Microsoft.Quantum.Canon 中的作業 RandomWalkPhaseEstimation 已移至 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存放庫的命名空間 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 中。</span><span class="sxs-lookup"><span data-stu-id="74dfd-450">Please note that the operation RandomWalkPhaseEstimation from the namespace Microsoft.Quantum.Canon was moved into the namespace Microsoft.Research.Quantum.RandomWalkPhaseEstimation in the [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) repository.</span></span>

### <a name="known-issues"></a><span data-ttu-id="74dfd-451">已知問題</span><span class="sxs-lookup"><span data-stu-id="74dfd-451">Known Issues</span></span>

- <span data-ttu-id="74dfd-452">在以 Q# 撰寫的測試中，`dotnet test` 的 `--filter` 選項無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-452">The `--filter` option to `dotnet test` does not work correctly for tests written in Q#.</span></span>
  <span data-ttu-id="74dfd-453">因此，無法在 Visual Studio Code 中執行個別的單元測試；建議您在命令列上使用 `dotnet test` 重新執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="74dfd-453">As a result, individual unit tests cannot be run in Visual Studio Code; we recommend using `dotnet test` at the command line to re-run all tests.</span></span>

## <a name="version-0118011707"></a><span data-ttu-id="74dfd-454">0\.1.1801.1707 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-454">Version 0.1.1801.1707</span></span>

<span data-ttu-id="74dfd-455">*發行日期：2018 年 1 月 18 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-455">*Release date: January 18, 2018*</span></span>

<span data-ttu-id="74dfd-456">此版本修正了社群回報的某些問題。</span><span class="sxs-lookup"><span data-stu-id="74dfd-456">This release fixes some issues reported by the community.</span></span> <span data-ttu-id="74dfd-457">分別是：</span><span class="sxs-lookup"><span data-stu-id="74dfd-457">Namely:</span></span>

- <span data-ttu-id="74dfd-458">模擬器現已可與早期不具 AVX 功能的 CPU 搭配運作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-458">The simulator now works with early non-AVX-enabled CPUs.</span></span>
- <span data-ttu-id="74dfd-459">區域十進位設定不會導致 Q# 剖析器失敗。</span><span class="sxs-lookup"><span data-stu-id="74dfd-459">Regional decimal settings will not cause the Q# parser to fail.</span></span>
- <span data-ttu-id="74dfd-460">`SignD` 基本作業現在會傳回 `Int`，而不是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="74dfd-460">`SignD` primitive operation now returns `Int` rather than `Double`.</span></span>


## <a name="version-011712901"></a><span data-ttu-id="74dfd-461">0\.1.1712.901 版</span><span class="sxs-lookup"><span data-stu-id="74dfd-461">Version 0.1.1712.901</span></span>

<span data-ttu-id="74dfd-462">*發行日期：2017 年 12 月 11 日*</span><span class="sxs-lookup"><span data-stu-id="74dfd-462">*Release date: December 11, 2017*</span></span>

### <a name="known-issues"></a><span data-ttu-id="74dfd-463">已知問題</span><span class="sxs-lookup"><span data-stu-id="74dfd-463">Known Issues</span></span>

#### <a name="hardware-and-software-requirements"></a><span data-ttu-id="74dfd-464">硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="74dfd-464">Hardware and Software Requirements</span></span>

- <span data-ttu-id="74dfd-465">Quantum Development Kit 隨附的模擬器需要 Microsoft Windows 的 64 位元安裝才能執行。</span><span class="sxs-lookup"><span data-stu-id="74dfd-465">The simulator included with the Quantum Development Kit requires a 64-bit installation of Microsoft Windows to run.</span></span>
- <span data-ttu-id="74dfd-466">與 Quantum Development Kit 一起安裝的 Microsoft 量子模擬器會使用 Advance Vector Extensions (AVX)，且需要具有 AVX 功能的 CPU。</span><span class="sxs-lookup"><span data-stu-id="74dfd-466">Microsoft's quantum simulator, installed with the Quantum Development Kit, utilizes Advanced Vector Extensions (AVX), and requires an AVX-enabled CPU.</span></span> <span data-ttu-id="74dfd-467">2011 年第 1 季推出的 Intel 處理器 (Sandy Bridge) 或更新版本可支援 AVX。</span><span class="sxs-lookup"><span data-stu-id="74dfd-467">Intel processors shipped in Q1 2011 (Sandy Bridge) or later support AVX.</span></span> <span data-ttu-id="74dfd-468">我們正在評估對舊型 CPU 的支援，後續可能會發佈相關詳情。</span><span class="sxs-lookup"><span data-stu-id="74dfd-468">We are evaluating support for earlier CPUs and may announce details at a later time.</span></span>

#### <a name="project-creation"></a><span data-ttu-id="74dfd-469">專案建立</span><span class="sxs-lookup"><span data-stu-id="74dfd-469">Project Creation</span></span>

- <span data-ttu-id="74dfd-470">建立將使用 Q# 的解決方案 (.sln) 時，解決方案必須比其中的每個專案 (.csproj) 高一個目錄。</span><span class="sxs-lookup"><span data-stu-id="74dfd-470">When creating a solution (.sln) that will use Q#, the solution must be one directory higher than each project (.csproj) in the solution.</span></span> <span data-ttu-id="74dfd-471">在建立新的解決方案時，只要確實核取 [新增專案] 對話方塊上的 [建立解決方案的目錄] 核取方塊，即可符合此條件。</span><span class="sxs-lookup"><span data-stu-id="74dfd-471">When creating a new solution, this can be accomplished by making sure that the "Create directory for solution" checkbox on the "New Project" dialog box is checked.</span></span> <span data-ttu-id="74dfd-472">若未執行此動作，則必須手動安裝 Quantum Development Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="74dfd-472">If this is not done, the Quantum Development Kit NuGet packages will need to be installed manually.</span></span>

#### <a name="q"></a><span data-ttu-id="74dfd-473">Q#</span><span class="sxs-lookup"><span data-stu-id="74dfd-473">Q#</span></span>

- <span data-ttu-id="74dfd-474">Intellisense 不會針對 Q# 程式碼顯示適當的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-474">Intellisense does not display proper errors for Q# code.</span></span> <span data-ttu-id="74dfd-475">請確實在 Visual Studio 錯誤清單中顯示建置錯誤，以查看正確的 Q# 錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-475">Make sure that you are displaying Build errors in the Visual Studio Error List to see correct Q# errors.</span></span> <span data-ttu-id="74dfd-476">另請注意，必須在您完成建置後，才會顯示 Q# 錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-476">Also note that Q# errors will not show up until after you've done a build.</span></span>
- <span data-ttu-id="74dfd-477">在部分應用程式中使用可變動陣列可能會導致非預期的行為。</span><span class="sxs-lookup"><span data-stu-id="74dfd-477">Using a mutable array in a partial application may lead to unexpected behavior.</span></span>
- <span data-ttu-id="74dfd-478">將不可變陣列繫結至可變動陣列 (讓 a = b，其中 b 是可變動陣列)，可能會導致非預期的行為。</span><span class="sxs-lookup"><span data-stu-id="74dfd-478">Binding an immutable array to a mutable array (let a = b, where b is a mutable array) may lead to unexpected behavior.</span></span>
- <span data-ttu-id="74dfd-479">分析、程式碼涵蓋範圍和其他 VS 外掛程式不一定會正確計算 Q# 的行數和區塊數。</span><span class="sxs-lookup"><span data-stu-id="74dfd-479">Profiling, code coverage and other VS plugins may not always count Q# lines and blocks accurately.</span></span>
- <span data-ttu-id="74dfd-480">Q# 編譯器不會驗證差補字串。</span><span class="sxs-lookup"><span data-stu-id="74dfd-480">The Q# compiler does not validate interpolated strings.</span></span> <span data-ttu-id="74dfd-481">您可以藉由在 Q# 差補字串中拚寫錯誤的變數名稱或使用運算式，來建立 C# 編譯錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-481">It is possible to create C# compilation errors by misspelling variable names or using expressions in Q# interpolated strings.</span></span>

#### <a name="simulation"></a><span data-ttu-id="74dfd-482">模擬</span><span class="sxs-lookup"><span data-stu-id="74dfd-482">Simulation</span></span>

- <span data-ttu-id="74dfd-483">量子模擬器會使用 OpenMP 來平行處理所需的線性代數。</span><span class="sxs-lookup"><span data-stu-id="74dfd-483">The Quantum Simulator uses OpenMP to parallelize the linear algebra required.</span></span> <span data-ttu-id="74dfd-484">根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位元的程式常會執行緩慢，因為所需的協調會阻礙實際的工作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-484">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="74dfd-485">將環境變數 OMP_NUM_THREADS 設定為較小的數值，即可修正此問題。</span><span class="sxs-lookup"><span data-stu-id="74dfd-485">This can be fixed by setting the environment variable OMP_NUM_THREADS to a small number.</span></span> <span data-ttu-id="74dfd-486">一個非常粗略的經驗法則是，1 個執行緒最多可用於 4 個量子位元，而其後的每個量子位元則應使用一個額外的執行緒，但這主要取決於您的演算法。</span><span class="sxs-lookup"><span data-stu-id="74dfd-486">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

#### <a name="debugging"></a><span data-ttu-id="74dfd-487">偵錯</span><span class="sxs-lookup"><span data-stu-id="74dfd-487">Debugging</span></span>

- <span data-ttu-id="74dfd-488">F11 (逐步執行) 在 Q# 程式碼中無法運作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-488">F11 (step in) doesn't work in Q# code.</span></span>
- <span data-ttu-id="74dfd-489">在中斷點或單一步驟暫停時，Q# 程式碼中醒目提示的程式碼有時並不正確。</span><span class="sxs-lookup"><span data-stu-id="74dfd-489">Code highlighting in Q# code at a breakpoint or single-step pause is sometimes inaccurate.</span></span> <span data-ttu-id="74dfd-490">醒目提示的程式碼行是正確的，但有時候，醒目提示的開頭和結尾會位於行中不正確的資料行上。</span><span class="sxs-lookup"><span data-stu-id="74dfd-490">The correct line will be highlighted, but sometimes the highlight will start and end at incorrect columns on the line.</span></span>

#### <a name="testing"></a><span data-ttu-id="74dfd-491">測試</span><span class="sxs-lookup"><span data-stu-id="74dfd-491">Testing</span></span>

- <span data-ttu-id="74dfd-492">測試必須在 64 位元模式中執行。</span><span class="sxs-lookup"><span data-stu-id="74dfd-492">Tests must be executed in 64-bit mode.</span></span> <span data-ttu-id="74dfd-493">如果您的測試失敗並出現 BadImageFormatException，請移至 [測試] 功能表，然後選取 [測試設定] > [預設處理器架構] > [X64]。</span><span class="sxs-lookup"><span data-stu-id="74dfd-493">If your tests are failing with a BadImageFormatException, go to the Test menu and select Test Settings > Default Processor Architecture > X64.</span></span>
- <span data-ttu-id="74dfd-494">有些測試的執行會非常耗時 (最多可能需要 5 分鐘，視您的電腦而定)。</span><span class="sxs-lookup"><span data-stu-id="74dfd-494">Some tests take a long time (possibly as much as 5 minutes depending on your computer) to run.</span></span> <span data-ttu-id="74dfd-495">這是正常的，因為有些測試會使用超過 20 個量子位元；我們最大的測試目前以 23 個量子位元執行。</span><span class="sxs-lookup"><span data-stu-id="74dfd-495">This is normal, as some use over twenty qubits; our largest test currently runs on 23 qubits.</span></span>

#### <a name="samples"></a><span data-ttu-id="74dfd-496">範例</span><span class="sxs-lookup"><span data-stu-id="74dfd-496">Samples</span></span>

- <span data-ttu-id="74dfd-497">在某些電腦上，某些小型樣本可能會執行緩慢，除非環境變數 OMP_NUM_THREADS 設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="74dfd-497">On some machines, some small samples may run slowly unless the environment variable OMP_NUM_THREADS is set to "1".</span></span> <span data-ttu-id="74dfd-498">另請參閱「模擬」下的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="74dfd-498">See also the release note under "Simulation".</span></span>

#### <a name="libraries"></a><span data-ttu-id="74dfd-499">程式庫</span><span class="sxs-lookup"><span data-stu-id="74dfd-499">Libraries</span></span>

- <span data-ttu-id="74dfd-500">既有的隱含假設是，傳至作業中不同引數的量子位元是相異的。</span><span class="sxs-lookup"><span data-stu-id="74dfd-500">There is an implicit assumption that the qubits passed to an operation in different arguments are all distinct.</span></span> <span data-ttu-id="74dfd-501">例如，所有的程式庫作業 (以及所有模擬器) 都會假設傳至受控 NOT 的兩個量子位元是不同的。</span><span class="sxs-lookup"><span data-stu-id="74dfd-501">For instance, all of the library operations (and all of the simulators) assume that the two qubits passed to a controlled NOT are different qubits.</span></span> <span data-ttu-id="74dfd-502">若違反此假設，可能會導致無法預期的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74dfd-502">Violating this assumption may lead to unpredictable unexpected.</span></span> <span data-ttu-id="74dfd-503">您可以使用量子電腦追蹤模擬器來測試這種情況。</span><span class="sxs-lookup"><span data-stu-id="74dfd-503">It is possible to test for this using the quantum computer tracer simulator.</span></span>
- <span data-ttu-id="74dfd-504">Microsoft.Quantum.Bind 函式不一定在各種情況下都會如預期運作。</span><span class="sxs-lookup"><span data-stu-id="74dfd-504">The Microsoft.Quantum.Bind function may not act as expected in all cases.</span></span>
- <span data-ttu-id="74dfd-505">在 Microsoft.Quantum.Extensions.Math 命名空間中，SignD 函式會傳回雙精度浮點數 (而非整數)，但基礎 System.Math.Sign 函式則一律會傳回整數。</span><span class="sxs-lookup"><span data-stu-id="74dfd-505">In the Microsoft.Quantum.Extensions.Math namespace, the SignD function returns a Double rather than an Int, although the underlying System.Math.Sign function always returns an integer.</span></span> <span data-ttu-id="74dfd-506">您可以將結果與 1.0、-1.0 和 0.0 進行比較，因為這些雙精度浮點數具有相同的二進位表示法。</span><span class="sxs-lookup"><span data-stu-id="74dfd-506">It is safe to compare the result against 1.0, -1.0, and 0.0, since these doubles all have exact binary representations.</span></span>
