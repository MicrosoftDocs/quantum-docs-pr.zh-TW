---
title: Quantum 開發套件版本資訊
description: 深入了解 Microsoft Quantum Development Kit 預覽版的最新更新。
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: 4b5e7b657f0e11fb4a14308c20859f4007729146
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871547"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a><span data-ttu-id="49509-103">Microsoft Quantum Development Kit 版本資訊</span><span class="sxs-lookup"><span data-stu-id="49509-103">Microsoft Quantum Development Kit Release Notes</span></span>

<span data-ttu-id="49509-104">本文包含各個 Quantum Development Kit 版本的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="49509-104">This article contains information on each Quantum Development Kit release.</span></span>

<span data-ttu-id="49509-105">如需安裝指示，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="49509-105">For installation instructions, please refer to the [install guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="49509-106">如需更新指示，請參閱[更新指南](xref:microsoft.quantum.update)。</span><span class="sxs-lookup"><span data-stu-id="49509-106">For update instructions, please refer to the [update guide](xref:microsoft.quantum.update).</span></span>


## <a name="version-01220072031"></a><span data-ttu-id="49509-107">版本0.12.20072031</span><span class="sxs-lookup"><span data-stu-id="49509-107">Version 0.12.20072031</span></span>

<span data-ttu-id="49509-108">*發行日期：2020年7月21日*</span><span class="sxs-lookup"><span data-stu-id="49509-108">*Release date: July 21st, 2020*</span></span>

<span data-ttu-id="49509-109">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-109">This release contains the following:</span></span>

- <span data-ttu-id="49509-110">在 Q # 筆記本中開啟的命名空間現在可供未來所有的儲存格執行使用。</span><span class="sxs-lookup"><span data-stu-id="49509-110">Opened namespaces in Q# notebooks are now available for all future cell executions.</span></span> <span data-ttu-id="49509-111">例如，這可讓命名空間在筆記本頂端的資料格中開啟一次，而不需要在每個程式碼單元中開啟相關的命名空間。</span><span class="sxs-lookup"><span data-stu-id="49509-111">This allows, for example, namespaces to be opened once in a cell at the top of the notebook, rather than needing to open relevant namespaces in each code cell.</span></span> <span data-ttu-id="49509-112">新的 `%lsopen` 魔術命令會顯示目前開啟之命名空間的清單。</span><span class="sxs-lookup"><span data-stu-id="49509-112">A new `%lsopen` magic command displays the list of currently-opened namespaces.</span></span>

<span data-ttu-id="49509-113">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、[IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-113">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01220070124"></a><span data-ttu-id="49509-114">版本0.12.20070124</span><span class="sxs-lookup"><span data-stu-id="49509-114">Version 0.12.20070124</span></span>

<span data-ttu-id="49509-115">*發行日期：2020年7月2日*</span><span class="sxs-lookup"><span data-stu-id="49509-115">*Release date: July 2nd, 2020*</span></span>

<span data-ttu-id="49509-116">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-116">This release contains the following:</span></span>

- <span data-ttu-id="49509-117">`qdk-chem`將舊版電子結構問題序列化格式（例如： FCIDUMP）轉換成[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)的新工具</span><span class="sxs-lookup"><span data-stu-id="49509-117">New `qdk-chem` tool for converting legacy electronic structure problem serialization formats (e.g.: FCIDUMP) to [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)</span></span>
- <span data-ttu-id="49509-118">命名空間中的新函式和作業，可 [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) 用於 coherently 使用轉換和分解式合成演算法來套用傳統 oracles。</span><span class="sxs-lookup"><span data-stu-id="49509-118">New functions and operations in the [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) namespace for coherently applying classical oracles using transformation- and decomposition-based synthesis algorithms.</span></span>
- <span data-ttu-id="49509-119">IQ # 現在允許 `%simulate` 、 `%estimate` 和其他魔術命令的引數。</span><span class="sxs-lookup"><span data-stu-id="49509-119">IQ# now allows arguments to the `%simulate`, `%estimate`, and other magic commands.</span></span> <span data-ttu-id="49509-120">如需詳細資訊，請參閱[ `%simulate` 魔術命令參考](xref:microsoft.quantum.iqsharp.magic-ref.simulate)。</span><span class="sxs-lookup"><span data-stu-id="49509-120">See the [`%simulate` magic command reference](xref:microsoft.quantum.iqsharp.magic-ref.simulate) for more details.</span></span>
- <span data-ttu-id="49509-121">IQ # 中的新階段顯示選項。</span><span class="sxs-lookup"><span data-stu-id="49509-121">New phase display options in IQ#.</span></span> <span data-ttu-id="49509-122">如需詳細資訊，請參閱[ `%config` 魔術命令參考](xref:microsoft.quantum.iqsharp.magic-ref.config)。</span><span class="sxs-lookup"><span data-stu-id="49509-122">See the [`%config` magic command reference](xref:microsoft.quantum.iqsharp.magic-ref.config) for more details.</span></span>
- <span data-ttu-id="49509-123">`qsharp`現在透過 conda 套件（[qsharp](https://anaconda.org/quantum-engineering/qsharp)和[iqsharp](https://anaconda.org/quantum-engineering/iqsharp)）提供 IQ # 和 Python 套件，以簡化 Q # Jupyter 和 python 功能在 conda 環境中的本機安裝。</span><span class="sxs-lookup"><span data-stu-id="49509-123">IQ# and the `qsharp` Python package are now provided via conda packages ([qsharp](https://anaconda.org/quantum-engineering/qsharp) and [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) to simplify local installation of Q# Jupyter and Python functionality to a conda environment.</span></span> <span data-ttu-id="49509-124">如需詳細資訊，請參閱[Q # Jupyter 筆記本](xref:microsoft.quantum.install.jupyter)和[包含 Python 的 q #](xref:microsoft.quantum.install.python)安裝指南。</span><span class="sxs-lookup"><span data-stu-id="49509-124">See the [Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) and [Q# with Python](xref:microsoft.quantum.install.python) installation guides for more details.</span></span>
- <span data-ttu-id="49509-125">使用模擬器時，qubits 在發行時不再需要處於 | 0 ⟩狀態，但如果在釋放之前立即測量，則可以自動重設。</span><span class="sxs-lookup"><span data-stu-id="49509-125">When using the simulator, qubits no longer need to be in the |0⟩ state upon release, but can be automatically reset if they were measured immediately before releasing.</span></span>
- <span data-ttu-id="49509-126">更新可讓 IQ # 使用者更輕鬆地使用具有不同 QDK 版本的程式庫套件，只需要主要 & 次要版本號碼相符，而不是完全相同的版本</span><span class="sxs-lookup"><span data-stu-id="49509-126">Updates to make it easier for IQ# users to consume library packages with different QDK versions, requiring only major & minor version numbers match rather than the exact same version</span></span>
- <span data-ttu-id="49509-127">已移除取代的 `Microsoft.Quantum.Primitive.*` 命名空間</span><span class="sxs-lookup"><span data-stu-id="49509-127">Removed deprecated `Microsoft.Quantum.Primitive.*` namespace</span></span>
- <span data-ttu-id="49509-128">移動的作業：</span><span class="sxs-lookup"><span data-stu-id="49509-128">Moved operations:</span></span>
  - <span data-ttu-id="49509-129">`Microsoft.Quantum.Intrinsic.Assert` 現在為 `Microsoft.Quantum.Diagnostics.AssertMeasurement`</span><span class="sxs-lookup"><span data-stu-id="49509-129">`Microsoft.Quantum.Intrinsic.Assert` is now `Microsoft.Quantum.Diagnostics.AssertMeasurement`</span></span>
  - <span data-ttu-id="49509-130">`Microsoft.Quantum.Intrinsic.AssertProb` 現在為 `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`</span><span class="sxs-lookup"><span data-stu-id="49509-130">`Microsoft.Quantum.Intrinsic.AssertProb` is now `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`</span></span>
- <span data-ttu-id="49509-131">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="49509-131">Bug fixes</span></span> 

<span data-ttu-id="49509-132">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、[IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-132">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0112006403"></a><span data-ttu-id="49509-133">版本 0.11.2006.403</span><span class="sxs-lookup"><span data-stu-id="49509-133">Version 0.11.2006.403</span></span>

<span data-ttu-id="49509-134">*發行日期：2020 年 6 月 4 日*</span><span class="sxs-lookup"><span data-stu-id="49509-134">*Release date: June 4th, 2020*</span></span>

<span data-ttu-id="49509-135">這個版本會修正影響 Q # 專案編譯的錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-135">This release fixes a bug affecting compilation of Q# projects.</span></span>

## <a name="version-0112006207"></a><span data-ttu-id="49509-136">版本 0.11.2006.207</span><span class="sxs-lookup"><span data-stu-id="49509-136">Version 0.11.2006.207</span></span>

<span data-ttu-id="49509-137">*發行日期：2020 年 6 月 3 日*</span><span class="sxs-lookup"><span data-stu-id="49509-137">*Release date: June 3rd, 2020*</span></span>

<span data-ttu-id="49509-138">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-138">This release contains the following:</span></span>

- <span data-ttu-id="49509-139">當問 Q# 進入點存在時，Q# 筆記本和 Python 主機程式將不會再失敗</span><span class="sxs-lookup"><span data-stu-id="49509-139">Q# notebooks and Python host programs will no longer fail when a Q# entry point is present</span></span>
- <span data-ttu-id="49509-140">更新[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)以使用存取修飾詞</span><span class="sxs-lookup"><span data-stu-id="49509-140">Updates to [Standard library](xref:microsoft.quantum.libraries.standard.intro) to use access modifiers</span></span>
- <span data-ttu-id="49509-141">編譯器現在允許在內建重寫步驟之間進行重寫步驟的外掛程式</span><span class="sxs-lookup"><span data-stu-id="49509-141">Compiler now allows plug-in of rewrite steps between built-in rewrite steps</span></span>
- <span data-ttu-id="49509-142">已遵循我們的 [API 原則](xref:microsoft.quantum.contributing.api-design)中所述的排程，移除數個已遭取代的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="49509-142">Several deprecated functions and operations have been removed following the schedule described in our [API principles](xref:microsoft.quantum.contributing.api-design).</span></span> <span data-ttu-id="49509-143">在版本 0.11.2004.2825 中建立不含警告的 Q# 程式和程式庫，將會繼續以未修改的方式工作。</span><span class="sxs-lookup"><span data-stu-id="49509-143">Q# programs and libraries that build without warnings in version 0.11.2004.2825 will continue to work unmodified.</span></span>

<span data-ttu-id="49509-144">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、[IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) 和 [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-144">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

> [!NOTE]
> <span data-ttu-id="49509-145">此版本包含影響 Q # 專案編譯的錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-145">This version contains a bug affecting compilation of Q# projects.</span></span> <span data-ttu-id="49509-146">我們建議您升級至較新的版本。</span><span class="sxs-lookup"><span data-stu-id="49509-146">We recommend upgrading to a newer release.</span></span>

## <a name="version-01120042825"></a><span data-ttu-id="49509-147">0\.11.2004.2825 版</span><span class="sxs-lookup"><span data-stu-id="49509-147">Version 0.11.2004.2825</span></span>

<span data-ttu-id="49509-148">*發行日期：2020 年 4 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="49509-148">*Release date: April 30th, 2020*</span></span>

<span data-ttu-id="49509-149">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-149">This release contains the following:</span></span>

- <span data-ttu-id="49509-150">Q# 命令列應用程式的新支援，不再需要 C# 或 Python 主機檔案。</span><span class="sxs-lookup"><span data-stu-id="49509-150">New support for Q# command line applications, which no longer require a C# or Python host file.</span></span> <span data-ttu-id="49509-151">如需開始使用 Q # 命令列應用程式的詳細資訊，請參閱[這裡](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="49509-151">For more information on getting started with Q# command line applications, see [here](xref:microsoft.quantum.install.standalone).</span></span>
- <span data-ttu-id="49509-152">已更新的量子隨機數字產生器快速入門，不再需要 C# 或 Python 主機檔案。</span><span class="sxs-lookup"><span data-stu-id="49509-152">Updated quantum random number generator quickstart to no longer require a C# or Python host file.</span></span> <span data-ttu-id="49509-153">請參閱更新的[快速入門](xref:microsoft.quantum.quickstarts.qrng)</span><span class="sxs-lookup"><span data-stu-id="49509-153">See the updated  [Quickstart](xref:microsoft.quantum.quickstarts.qrng)</span></span>
- <span data-ttu-id="49509-154">IQ # Docker 映像的效能改進</span><span class="sxs-lookup"><span data-stu-id="49509-154">Performance improvements to IQ# Docker images</span></span>

> [!NOTE]
> <span data-ttu-id="49509-155">使用新 [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) 屬性的 Q # 命令列應用程式目前無法從 Python 或 .NET 主機程式呼叫。</span><span class="sxs-lookup"><span data-stu-id="49509-155">Q# command-line applications using the new [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) attribute currently cannot be called from Python or .NET host programs.</span></span>
> <span data-ttu-id="49509-156">如需詳細資訊，請參閱 [Python](xref:microsoft.quantum.install.python) 和 [.NET 互通性](xref:microsoft.quantum.install.cs) 指南。</span><span class="sxs-lookup"><span data-stu-id="49509-156">See the [Python](xref:microsoft.quantum.install.python) and [.NET interoperability](xref:microsoft.quantum.install.cs) guides for more information.</span></span>

## <a name="version-01120033107"></a><span data-ttu-id="49509-157">0\.11.2003.3107 版</span><span class="sxs-lookup"><span data-stu-id="49509-157">Version 0.11.2003.3107</span></span>

<span data-ttu-id="49509-158">*發行日期：2020 年 3 月 31 日*</span><span class="sxs-lookup"><span data-stu-id="49509-158">*Release date: March 31, 2020*</span></span>

<span data-ttu-id="49509-159">此版本包含版本 0.11.2003.2506 的次要錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="49509-159">This release contains minor bugfixes for version 0.11.2003.2506.</span></span>

## <a name="version-01120032506"></a><span data-ttu-id="49509-160">0\.11.2003.2506 版</span><span class="sxs-lookup"><span data-stu-id="49509-160">Version 0.11.2003.2506</span></span>

<span data-ttu-id="49509-161">*發行日期：2020 年 3 月 26 日*</span><span class="sxs-lookup"><span data-stu-id="49509-161">*Release date: March 26th, 2020*</span></span>

<span data-ttu-id="49509-162">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-162">This release contains the following:</span></span>

- <span data-ttu-id="49509-163">Q# 中存取修飾詞的新支援。如需詳細資訊，請參閱 [檔案結構](xref:microsoft.quantum.guide.filestructure)</span><span class="sxs-lookup"><span data-stu-id="49509-163">New support for access modifiers in Q#, for more information see [File Structures](xref:microsoft.quantum.guide.filestructure)</span></span>
- <span data-ttu-id="49509-164">已更新為 .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="49509-164">Updated to .NET Core SDK 3.1</span></span>

<span data-ttu-id="49509-165">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-165">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020022610"></a><span data-ttu-id="49509-166">0\.10.2002.2610 版</span><span class="sxs-lookup"><span data-stu-id="49509-166">Version 0.10.2002.2610</span></span>

<span data-ttu-id="49509-167">*發行日期：2020 年 2 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="49509-167">*Release date: February 27th, 2020*</span></span>

<span data-ttu-id="49509-168">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-168">This release contains the following:</span></span>

- <span data-ttu-id="49509-169">新的量子機器學習程式庫。如需詳細資訊，請移至我們的 [QML 文件頁面](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)</span><span class="sxs-lookup"><span data-stu-id="49509-169">New Quantum Machine Learning library, for more information go to our [QML docs page](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview)</span></span>
- <span data-ttu-id="49509-170">IQ# 錯誤修正，可在載入 NuGet 套件時增加 10-20 倍的效能</span><span class="sxs-lookup"><span data-stu-id="49509-170">IQ# bug fixes, resulting in up to a 10-20x performance increase when loading NuGet packages</span></span>

<span data-ttu-id="49509-171">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-171">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020012831"></a><span data-ttu-id="49509-172">0\.10.2001.2831 版</span><span class="sxs-lookup"><span data-stu-id="49509-172">Version 0.10.2001.2831</span></span>

<span data-ttu-id="49509-173">*發行日期：2020 年 1 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="49509-173">*Release date: January 29th, 2020*</span></span>

<span data-ttu-id="49509-174">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-174">This release contains the following:</span></span>

- <span data-ttu-id="49509-175">新的 Microsoft.Quantum.SDK NuGet 套件，將在建立新專案時取代 Microsoft.Quantum.Development.Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="49509-175">New Microsoft.Quantum.SDK NuGet package which will replace Microsoft.Quantum.Development.Kit NuGet package when creating new projects.</span></span> <span data-ttu-id="49509-176">現有專案將會繼續支援 Microsoft.Quantum.Development.Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="49509-176">Microsoft.Quantum.Development.Kit NuGet package will continue to be supported for existing projects.</span></span> 
- <span data-ttu-id="49509-177">由新 Microsoft.Quantum.SDK NuGet 套件啟用的 Q# 編譯器擴充功能支援，如需詳細資訊，請參閱 [Github 上的文件](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler)：[編譯器擴充功能範例](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions)及 [Q# 開發人員部落格](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span><span class="sxs-lookup"><span data-stu-id="49509-177">Support for Q# compiler extensions, enabled by the new Microsoft.Quantum.SDK NuGet packge, for more information see the [documentation on Github](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), the [compiler extensions sample](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) and the [Q# Dev Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span></span>
- <span data-ttu-id="49509-178">新增 .NET Core 3.1 支援，強烈建議您安裝 3.1.100 版，因為使用舊版 .NET Core SDK 版本可能會造成問題</span><span class="sxs-lookup"><span data-stu-id="49509-178">Added support for .NET Core 3.1, it is highly recommended to have version 3.1.100 installed since building with older .NET Core SDK versions may cause issues</span></span>
- <span data-ttu-id="49509-179">在 Microsoft.Quantum.QsCompiler.Experimental 下提供新的編譯器轉換</span><span class="sxs-lookup"><span data-stu-id="49509-179">New compiler transformations available under Microsoft.Quantum.QsCompiler.Experimental</span></span>
- <span data-ttu-id="49509-180">在 IQ# 中將輸出狀態向量以 HTML 公開的新功能</span><span class="sxs-lookup"><span data-stu-id="49509-180">New functionality to expose output state vectors as HTML in IQ#</span></span>
- <span data-ttu-id="49509-181">已將 EstimateFrequencyA 支援新增至適用於 Hadamard 和 SWAP 測試的 Microsoft.Quantum.Characterization</span><span class="sxs-lookup"><span data-stu-id="49509-181">Added support for EstimateFrequencyA to Microsoft.Quantum.Characterization for Hadamard and SWAP tests</span></span>
- <span data-ttu-id="49509-182">AmplitudeAmplification 命名空間現在使用 Q# 樣式指南</span><span class="sxs-lookup"><span data-stu-id="49509-182">AmplitudeAmplification namespace now uses Q# style guide</span></span>

<span data-ttu-id="49509-183">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-183">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019120501"></a><span data-ttu-id="49509-184">版本 0.10.1912.0501</span><span class="sxs-lookup"><span data-stu-id="49509-184">Version 0.10.1912.0501</span></span>

<span data-ttu-id="49509-185">*發行日期：2019 年 12 月 5 日*</span><span class="sxs-lookup"><span data-stu-id="49509-185">*Release date: December 5th, 2019*</span></span>

<span data-ttu-id="49509-186">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-186">This release contains the following:</span></span>

- <span data-ttu-id="49509-187">關於 Q# 單元測試的新測試屬性，請參閱[這裡](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)的更新 API 文件，以及[這裡](xref:microsoft.quantum.guide.testingdebugging)的更新測試和偵錯手冊</span><span class="sxs-lookup"><span data-stu-id="49509-187">New Test attribute for Q# unit testing, see updated API documentation [here](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) and updated testing & debugging guide [here](xref:microsoft.quantum.guide.testingdebugging)</span></span>
- <span data-ttu-id="49509-188">在 Q# 程式執行錯誤案例中新增了堆疊追蹤</span><span class="sxs-lookup"><span data-stu-id="49509-188">Added stack trace in the case of a Q# program execution error</span></span>
- <span data-ttu-id="49509-189">由於 [OmniSharp C# Visual Studio Code 延伸模組](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)更新，支援在 Visual Studio Code 中的中斷點</span><span class="sxs-lookup"><span data-stu-id="49509-189">Support for breakpoints in Visual Studio Code due to an update in the [OmniSharp C# Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span></span>

<span data-ttu-id="49509-190">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-190">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019111607"></a><span data-ttu-id="49509-191">版本 0.10.1911.1607</span><span class="sxs-lookup"><span data-stu-id="49509-191">Version 0.10.1911.1607</span></span>

<span data-ttu-id="49509-192">*發行日期：2019 年 11 月 17 日*</span><span class="sxs-lookup"><span data-stu-id="49509-192">*Release date: November 17th, 2019*</span></span>

<span data-ttu-id="49509-193">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-193">This release contains the following:</span></span>

- <span data-ttu-id="49509-194">[Quantum Katas](https://github.com/Microsoft/QuantumKatas) 和 Jupyter 筆記本的效能修正</span><span class="sxs-lookup"><span data-stu-id="49509-194">Performance fix for [Quantum Katas](https://github.com/Microsoft/QuantumKatas) and Jupyter notebooks</span></span>

<span data-ttu-id="49509-195">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-195">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  


## <a name="version-0101911307"></a><span data-ttu-id="49509-196">版本 0.10.1911.307</span><span class="sxs-lookup"><span data-stu-id="49509-196">Version 0.10.1911.307</span></span>

<span data-ttu-id="49509-197">*發行日期：2019 年 11 月 1 日*</span><span class="sxs-lookup"><span data-stu-id="49509-197">*Release date: November 1st, 2019*</span></span>

<span data-ttu-id="49509-198">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-198">This release contains the following:</span></span>

- <span data-ttu-id="49509-199">更新 Visual Studio Code 和 Visual Studio 擴充功能，將語言伺服器部署為獨立式可執行檔，以排除 .NET Core SDK 版本相依性</span><span class="sxs-lookup"><span data-stu-id="49509-199">Updates to Visual Studio Code & Visual Studio extensions to deploy language server as a self-contained executable, eliminating the .NET Core SDK version dependency</span></span>  
- <span data-ttu-id="49509-200">移轉到 .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49509-200">Migration to .NET Core 3.0</span></span>
- <span data-ttu-id="49509-201">重大更新 - Microsoft.Quantum.Simulation.Core.IOperationFactory 引進新的 `Fail` 方法</span><span class="sxs-lookup"><span data-stu-id="49509-201">Breaking change to Microsoft.Quantum.Simulation.Core.IOperationFactory with introduction of new `Fail` method.</span></span> <span data-ttu-id="49509-202">此方法只會影響未擴充 SimulatorBase 的自訂模擬器。</span><span class="sxs-lookup"><span data-stu-id="49509-202">It affects only custom simulators that do not extend SimulatorBase.</span></span> <span data-ttu-id="49509-203">如需詳細資料，請[檢閱 GitHub 中的提取要求](https://github.com/microsoft/qsharp-runtime/pull/59)。</span><span class="sxs-lookup"><span data-stu-id="49509-203">For more details, [view the pull request on GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).</span></span>
- <span data-ttu-id="49509-204">受取代屬性的新增支援</span><span class="sxs-lookup"><span data-stu-id="49509-204">New support for Deprecated attributes</span></span>

<span data-ttu-id="49509-205">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-205">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0919093002"></a><span data-ttu-id="49509-206">0\.9.1909.3002 版</span><span class="sxs-lookup"><span data-stu-id="49509-206">Version 0.9.1909.3002</span></span>

<span data-ttu-id="49509-207">*發行日期：2019 年 9 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="49509-207">*Release date: September 30th, 2019*</span></span>

<span data-ttu-id="49509-208">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-208">This release contains the following:</span></span>

- <span data-ttu-id="49509-209">在 Visual Studio 2019 (16.3 版和更新版本) 和 Visual Studio Code 中完成 Q# 程式碼的新支援</span><span class="sxs-lookup"><span data-stu-id="49509-209">New support for Q# code completion in Visual Studio 2019 (versions 16.3 & later) & Visual Studio Code</span></span>
- <span data-ttu-id="49509-210">量子 adder 的新 [Quantum Kata](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="49509-210">New [Quantum Kata](https://github.com/Microsoft/QuantumKatas) for quantum adders</span></span>

<span data-ttu-id="49509-211">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-211">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-09-packagereference-0919082902"></a><span data-ttu-id="49509-212">0\.9 版 (*PackageReference 0.9.1908.2902*)</span><span class="sxs-lookup"><span data-stu-id="49509-212">Version 0.9 (*PackageReference 0.9.1908.2902*)</span></span>

<span data-ttu-id="49509-213">*發行日期：2019 年 8 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="49509-213">*Release date: August 29th, 2019*</span></span>

<span data-ttu-id="49509-214">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-214">This release contains the following:</span></span>

- <span data-ttu-id="49509-215">在 Q# 中對[結合陳述式](xref:microsoft.quantum.guide.operationsfunctions#conjugations)的新支援</span><span class="sxs-lookup"><span data-stu-id="49509-215">New support for [conjugation statements](xref:microsoft.quantum.guide.operationsfunctions#conjugations) in Q#</span></span>
- <span data-ttu-id="49509-216">編譯器中的新程式碼動作 (例如：「取代為」、「新增文件」)，以及簡單的陣列項目更新</span><span class="sxs-lookup"><span data-stu-id="49509-216">New code actions in the compiler, such as: "replace with", "add documentation", and simple array item update</span></span>
- <span data-ttu-id="49509-217">在 Visual Studio Code 延伸模組中新增了安裝範本和新的專案命令</span><span class="sxs-lookup"><span data-stu-id="49509-217">Added install template and new project commands to Visual Studio Code extension</span></span>
- <span data-ttu-id="49509-218">新增了 ApplyIf 結合器的新變體，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span><span class="sxs-lookup"><span data-stu-id="49509-218">Added new variants of ApplyIf combinator such as [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span></span>
- <span data-ttu-id="49509-219">有額外的 [Quantum Katas](https://github.com/Microsoft/QuantumKatas) 可轉換為 Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="49509-219">Additional [Quantum Katas](https://github.com/Microsoft/QuantumKatas) converted to Jupyter Notebooks</span></span>
- <span data-ttu-id="49509-220">Visual Studio 延伸模組現在需要 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="49509-220">Visual Studio Extension now requires Visual Studio 2019</span></span>

<span data-ttu-id="49509-221">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-221">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="49509-222">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="49509-222">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="49509-223">如需這些變更的詳細資訊，請參閱 [Q# 開發人員部落格](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="49509-223">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

## <a name="version-08-packagereference-0819071701"></a><span data-ttu-id="49509-224">0\.8 版 (*PackageReference 0.8.1907.1701*)</span><span class="sxs-lookup"><span data-stu-id="49509-224">Version 0.8 (*PackageReference 0.8.1907.1701*)</span></span>

<span data-ttu-id="49509-225">*發行日期：2019 年 7 月 12 日*</span><span class="sxs-lookup"><span data-stu-id="49509-225">*Release date: July 12, 2019*</span></span>

<span data-ttu-id="49509-226">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-226">This release contains the following:</span></span>

- <span data-ttu-id="49509-227">切割陣列的新索引位置；請[參閱語言參考](xref:microsoft.quantum.guide.expressions#array-slices)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="49509-227">New indexing locations for slicing arrays, [see the language reference](xref:microsoft.quantum.guide.expressions#array-slices) for more information.</span></span>
- <span data-ttu-id="49509-228">新增了裝載於 [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry) 上的 Dockerfile；請參閱 [IQ# 存放庫以取得詳細資訊](https://github.com/microsoft/iqsharp/blob/master/README.md)</span><span class="sxs-lookup"><span data-stu-id="49509-228">Added Dockerfile hosted on the [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry), see the [IQ# repository for more information](https://github.com/microsoft/iqsharp/blob/master/README.md)</span></span>
- <span data-ttu-id="49509-229">[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的重大變更、組態設定的更新、名稱變更；請參閱 [.NET API 瀏覽器以了解更新的名稱](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="49509-229">Breaking change for [the trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), update to configuration settings, name changes; see the [.NET API Browser for the updated names](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).</span></span>

<span data-ttu-id="49509-230">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-230">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-07-packagereference-0719053109"></a><span data-ttu-id="49509-231">0\.7 版 (*PackageReference 0.7.1905.3109*)</span><span class="sxs-lookup"><span data-stu-id="49509-231">Version 0.7 (*PackageReference 0.7.1905.3109*)</span></span>

<span data-ttu-id="49509-232">*發行日期：2019 年 5 月 31 日*</span><span class="sxs-lookup"><span data-stu-id="49509-232">*Release date: May 31, 2019*</span></span>

<span data-ttu-id="49509-233">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-233">This release contains the following:</span></span>
- <span data-ttu-id="49509-234">Q# 語言的新增項目，</span><span class="sxs-lookup"><span data-stu-id="49509-234">additions to the Q# language,</span></span> 
- <span data-ttu-id="49509-235">化學程式庫的更新，</span><span class="sxs-lookup"><span data-stu-id="49509-235">updates to the chemistry library,</span></span> 
- <span data-ttu-id="49509-236">新的數值程式庫。</span><span class="sxs-lookup"><span data-stu-id="49509-236">a new numerics library.</span></span>

<span data-ttu-id="49509-237">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="49509-237">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="49509-238">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="49509-238">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="49509-239">如需這些變更的詳細資訊，請參閱 [Q# 開發人員部落格](https://devblogs.microsoft.com/qsharp)。</span><span class="sxs-lookup"><span data-stu-id="49509-239">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

### <a name="q-language-syntax"></a><span data-ttu-id="49509-240">Q# 語言語法</span><span class="sxs-lookup"><span data-stu-id="49509-240">Q# language syntax</span></span>
<span data-ttu-id="49509-241">此版本新增了 Q# 語言語法：</span><span class="sxs-lookup"><span data-stu-id="49509-241">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="49509-242">新增[使用者自訂類型](xref:microsoft.quantum.guide.types#user-defined-types)的具名項目。</span><span class="sxs-lookup"><span data-stu-id="49509-242">Add named items for [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>  
* <span data-ttu-id="49509-243">使用者定義類型建構函式現在可以當作函式使用。</span><span class="sxs-lookup"><span data-stu-id="49509-243">User-defined type constructors can now be used as functions.</span></span>
* <span data-ttu-id="49509-244">在使用者定義類型中新增 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 和 [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) 的支援。</span><span class="sxs-lookup"><span data-stu-id="49509-244">Add support for [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) and [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) in user-defined types.</span></span>
* <span data-ttu-id="49509-245">[重複直到成功](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)迴圈的修復區塊現在是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="49509-245">Fixup-block for [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) loops is now optional.</span></span>
* <span data-ttu-id="49509-246">我們現在支援函式中 (而非作業中) 的 While 迴圈。</span><span class="sxs-lookup"><span data-stu-id="49509-246">We now support while loops in functions (not in operations).</span></span>

### <a name="library"></a><span data-ttu-id="49509-247">程式庫</span><span class="sxs-lookup"><span data-stu-id="49509-247">Library</span></span> 

<span data-ttu-id="49509-248">此版本新增了數值程式庫：請深入了解如何[使用新的數值程式庫](xref:microsoft.quantum.numerics.usage)，並試用[新範例](https://github.com/microsoft/quantum/tree/master/Numerics)。</span><span class="sxs-lookup"><span data-stu-id="49509-248">This release adds a numerics library: Learn more about how to [use the new numerics library](xref:microsoft.quantum.numerics.usage) and try out the [new samples](https://github.com/microsoft/quantum/tree/master/Numerics).</span></span>  <span data-ttu-id="49509-249">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。</span><span class="sxs-lookup"><span data-stu-id="49509-249">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).</span></span>  

<span data-ttu-id="49509-250">此版本重組、擴充並更新了化學程式庫：</span><span class="sxs-lookup"><span data-stu-id="49509-250">This release reorganizes extends and updates the chemistry library:</span></span>
* <span data-ttu-id="49509-251">改善元件的模組化、擴充性、一般程式碼清除功能。</span><span class="sxs-lookup"><span data-stu-id="49509-251">Improves modularity of components, extensibility, general code cleanup.</span></span>  <span data-ttu-id="49509-252">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="49509-252">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).</span></span>
* <span data-ttu-id="49509-253">新增[多重參考波函數](xref:microsoft.quantum.chemistry.concepts.multireference)的支援，包括疏鬆多重參考波函數和單一結合叢集。</span><span class="sxs-lookup"><span data-stu-id="49509-253">Add support for [multi-reference wavefunctions](xref:microsoft.quantum.chemistry.concepts.multireference), both sparse multi-reference wavefunctions and unitary coupled cluster.</span></span>  <span data-ttu-id="49509-254">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="49509-254">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>
* <span data-ttu-id="49509-255">(謝謝！)[1QBit](https://1qbit.com) 參與者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用變分 ansatz 的能量評估。</span><span class="sxs-lookup"><span data-stu-id="49509-255">(Thank you!) [1QBit](https://1qbit.com) contributor ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energy evaluation using variational ansatz.</span></span> <span data-ttu-id="49509-256">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。</span><span class="sxs-lookup"><span data-stu-id="49509-256">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).</span></span>
* <span data-ttu-id="49509-257">將 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 結構描述更新為新的 [0.2 版](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，並新增單一結合叢集規格。</span><span class="sxs-lookup"><span data-stu-id="49509-257">Updating [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema to new [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), adding unitary coupled cluster specification.</span></span> <span data-ttu-id="49509-258">[問題 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。</span><span class="sxs-lookup"><span data-stu-id="49509-258">[Issue #65](https://github.com/microsoft/QuantumLibraries/issues/65).</span></span>
* <span data-ttu-id="49509-259">將 Python 互通性新增至化學程式庫函式。</span><span class="sxs-lookup"><span data-stu-id="49509-259">Adding Python interoperability to chemistry library functions.</span></span> <span data-ttu-id="49509-260">試著使用此[範例](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration)。</span><span class="sxs-lookup"><span data-stu-id="49509-260">Try out this [sample](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration).</span></span> <span data-ttu-id="49509-261">[問題 #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="49509-261">[Issue #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>

## <a name="version-061905"></a><span data-ttu-id="49509-262">0\.6.1905 版</span><span class="sxs-lookup"><span data-stu-id="49509-262">Version 0.6.1905</span></span>

<span data-ttu-id="49509-263">*發行日期：2019 年 5 月 3 日*</span><span class="sxs-lookup"><span data-stu-id="49509-263">*Release date: May 3, 2019*</span></span>

<span data-ttu-id="49509-264">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-264">This release contains the following:</span></span>
- <span data-ttu-id="49509-265">對 Q# 語言進行變更，</span><span class="sxs-lookup"><span data-stu-id="49509-265">makes changes to the Q# language,</span></span> 
- <span data-ttu-id="49509-266">重新建構 Quantum Development Kit 程式庫，</span><span class="sxs-lookup"><span data-stu-id="49509-266">restructures the Quantum Development Kit libraries,</span></span> 
- <span data-ttu-id="49509-267">新增範例，以及</span><span class="sxs-lookup"><span data-stu-id="49509-267">adds new samples, and</span></span> 
- <span data-ttu-id="49509-268">修正 Bug。</span><span class="sxs-lookup"><span data-stu-id="49509-268">fixes bugs.</span></span>  <span data-ttu-id="49509-269">[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的數個已關閉的 PR。</span><span class="sxs-lookup"><span data-stu-id="49509-269">Several closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="49509-270">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="49509-270">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="49509-271">您可以在 devblogs.microsoft.com/qsharp 上深入了解這些變更。</span><span class="sxs-lookup"><span data-stu-id="49509-271">You can read more about these changes on devblogs.microsoft.com/qsharp.</span></span>

### <a name="q-language-syntax"></a><span data-ttu-id="49509-272">Q# 語言語法</span><span class="sxs-lookup"><span data-stu-id="49509-272">Q# language syntax</span></span>
<span data-ttu-id="49509-273">此版本新增了 Q# 語言語法：</span><span class="sxs-lookup"><span data-stu-id="49509-273">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="49509-274">使用 `+` 運算子新增[用來表示量子作業特製化 (控制和伴隨) 的快速方法](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。</span><span class="sxs-lookup"><span data-stu-id="49509-274">Add a [shorthand way to express specializations of quantum operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (control and adjoints) with `+` operators.</span></span>  <span data-ttu-id="49509-275">舊語法已被取代。</span><span class="sxs-lookup"><span data-stu-id="49509-275">The old syntax is deprecated.</span></span>  <span data-ttu-id="49509-276">使用舊語法的程式 (例如 `: adjoint`) 將可繼續運作，但會產生編譯時間警告。</span><span class="sxs-lookup"><span data-stu-id="49509-276">Programs that use the old syntax (e.g., `: adjoint`) will continue to work, but a compile time warning will be generated.</span></span>  
* <span data-ttu-id="49509-277">新增 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 的運算子 `w/`，可用來將陣列的建立表示為現有陣列的修改。</span><span class="sxs-lookup"><span data-stu-id="49509-277">Add a new operator for [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, can be used to express array creation as a modification of an existing array.</span></span>
* <span data-ttu-id="49509-278">新增一般 [apply-and-update 陳述式](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols)，例如 `+=`、`w/=`。</span><span class="sxs-lookup"><span data-stu-id="49509-278">Add the common [apply-and-update statement](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), e.g., `+=`, `w/=`.</span></span>
* <span data-ttu-id="49509-279">新增為[開放式指示詞](xref:microsoft.quantum.guide.filestructure#open-directives)中的命名空間指定簡短名稱的方法。</span><span class="sxs-lookup"><span data-stu-id="49509-279">Add a way to specify a short name for namespaces in [open directives](xref:microsoft.quantum.guide.filestructure#open-directives).</span></span>

<span data-ttu-id="49509-280">在此版本中，我們不再允許在 set 陳述式的左側指定陣列元素。</span><span class="sxs-lookup"><span data-stu-id="49509-280">With this release, we no longer allow an array element to be specified on the left side of a set statement.</span></span>  <span data-ttu-id="49509-281">這是因為該語法意味著陣列是可變動的，然而事實上，作業的結果一律是經由修改建立新陣列。</span><span class="sxs-lookup"><span data-stu-id="49509-281">This is because that syntax implies that arrays are mutable when in fact, the result of the operation has always been the creation of a new array with the modification.</span></span>  <span data-ttu-id="49509-282">系統將會產生編譯器錯誤，並建議使用新的 copy-and-update 運算子 `w/` 達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="49509-282">Instead, a compiler error will be generated with a suggestion to use the new copy-and-update operator, `w/`, to accomplish the same result.</span></span>  

### <a name="library-restructuring"></a><span data-ttu-id="49509-283">程式庫重建</span><span class="sxs-lookup"><span data-stu-id="49509-283">Library restructuring</span></span>
<span data-ttu-id="49509-284">此版本重組了程式庫，使其能以一致的方式擴展：</span><span class="sxs-lookup"><span data-stu-id="49509-284">This release reorganizes the libraries to enable their growth in a consistent way:</span></span>
* <span data-ttu-id="49509-285">將 Microsoft.Quantum.Primitive 命名空間重新命名為 Microsoft.Quantum.Intrinsic。</span><span class="sxs-lookup"><span data-stu-id="49509-285">Renames the Microsoft.Quantum.Primitive namespace  to Microsoft.Quantum.Intrinsic.</span></span>  <span data-ttu-id="49509-286">這些作業會由目標電腦實作。</span><span class="sxs-lookup"><span data-stu-id="49509-286">These operations are implemented by the target machine.</span></span>  <span data-ttu-id="49509-287">Microsoft.Quantum.Primitive 命名空間已被取代。</span><span class="sxs-lookup"><span data-stu-id="49509-287">The Microsoft.Quantum.Primitive namespace is deprecated.</span></span>  <span data-ttu-id="49509-288">當程式使用已被取代的名稱呼叫作業和函式時，會有執行階段警告提出建議。</span><span class="sxs-lookup"><span data-stu-id="49509-288">A runtime warning will advise when programs call operations and functions using deprecated names.</span></span>

* <span data-ttu-id="49509-289">將 Microsoft.Quantum.Canon 套件重新命名為 Microsoft.Quantum.Standard。</span><span class="sxs-lookup"><span data-stu-id="49509-289">Renames the Microsoft.Quantum.Canon package to Microsoft.Quantum.Standard.</span></span>  <span data-ttu-id="49509-290">此套件包含大部分 Q# 程式通用的命名空間。</span><span class="sxs-lookup"><span data-stu-id="49509-290">This package contains namespaces that are common to most Q# programs.</span></span>  <span data-ttu-id="49509-291">這包括：</span><span class="sxs-lookup"><span data-stu-id="49509-291">This includes:</span></span>  
    - <span data-ttu-id="49509-292">一般作業的 Microsoft.Quantum.Canon</span><span class="sxs-lookup"><span data-stu-id="49509-292">Microsoft.Quantum.Canon for common operations</span></span>
    - <span data-ttu-id="49509-293">一般用途算術運算的 Microsoft.Quantum.Arithmetic</span><span class="sxs-lookup"><span data-stu-id="49509-293">Microsoft.Quantum.Arithmetic for general purpose arithmetic operations</span></span>
    - <span data-ttu-id="49509-294">作業用來準備量子位元狀態的 Microsoft.Quantum.Preparation</span><span class="sxs-lookup"><span data-stu-id="49509-294">Microsoft.Quantum.Preparation for operations used to prepare qubit state</span></span>
    - <span data-ttu-id="49509-295">模擬功能的 Microsoft.Quantum.Simulation</span><span class="sxs-lookup"><span data-stu-id="49509-295">Microsoft.Quantum.Simulation for simulation functionality</span></span>

<span data-ttu-id="49509-296">經過這項變更後，如果程式包含用於命名空間 Microsoft.Quatum.Canon 的單一 "open" 陳述式，且其參考的作業已移至其他三個新的命名空間，則可能會發生建置錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-296">With this change, programs that include a single "open" statement for the namespace Microsoft.Quatum.Canon may encounter build errors if the program references operations that were moved to the other three new namespaces.</span></span>  <span data-ttu-id="49509-297">為這三個新的命名空間新增額外的 open 陳述式，可直接了當地解決此問題。</span><span class="sxs-lookup"><span data-stu-id="49509-297">Adding the additional open statements for the three new namespaces is a straightforward way to resolve this issue.</span></span>  

* <span data-ttu-id="49509-298">有數個命名空間已被取代，因為其中的作業已重組至其他命名空間。</span><span class="sxs-lookup"><span data-stu-id="49509-298">Several namespaces have been deprecated as the operations within have been reorganized to other namespaces.</span></span> <span data-ttu-id="49509-299">使用這些命名空間的程式將可繼續運作，但會有編譯時間警告指出作業定義所在的命名空間。</span><span class="sxs-lookup"><span data-stu-id="49509-299">Programs that use these namespaces will continue to work, and a compile time warning will denote the namespace where the operation is defined.</span></span>  

* <span data-ttu-id="49509-300">Microsoft.Quantum.Arithmetic 命名空間已正規化為使用 <xref:microsoft.quantum.arithmetic.littleendian> 使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="49509-300">The Microsoft.Quantum.Arithmetic namespace has been normalized to use the <xref:microsoft.quantum.arithmetic.littleendian> user-defined type.</span></span> <span data-ttu-id="49509-301">需要轉換為 Little Endian 時，請使用函式 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。</span><span class="sxs-lookup"><span data-stu-id="49509-301">Use the function [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) when needed to convert to little endian.</span></span>  

* <span data-ttu-id="49509-302">有數個可呼叫項目 (函式和作業) 的名稱已變更，以符合 [Q# 樣式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="49509-302">The names of several callables (functions and operations) have been changed to conform to the [Q# Style Guide](xref:microsoft.quantum.contributing.style).</span></span>  <span data-ttu-id="49509-303">舊的可呼叫名稱已被取代。</span><span class="sxs-lookup"><span data-stu-id="49509-303">The old callable names are deprecated.</span></span>  <span data-ttu-id="49509-304">使用舊有可呼叫項目的程式將可繼續運作，但會出現編譯時間警告。</span><span class="sxs-lookup"><span data-stu-id="49509-304">Programs that use the old callables will continue to work with a compile time warning.</span></span> 

### <a name="new-samples"></a><span data-ttu-id="49509-305">新範例</span><span class="sxs-lookup"><span data-stu-id="49509-305">New Samples</span></span>

<span data-ttu-id="49509-306">我們新增了[搭配使用 Q# 與 F# 驅動程式的範例](https://github.com/Microsoft/Quantum/pull/164)。</span><span class="sxs-lookup"><span data-stu-id="49509-306">We added a [sample of using Q# with F# driver](https://github.com/Microsoft/Quantum/pull/164).</span></span>  

<span data-ttu-id="49509-307">**感謝**</span><span class="sxs-lookup"><span data-stu-id="49509-307">**Thank you!**</span></span> <span data-ttu-id="49509-308">下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。</span><span class="sxs-lookup"><span data-stu-id="49509-308">to the following contributor to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="49509-309">這些貢獻讓 Q# 程式碼的範例更加豐富：</span><span class="sxs-lookup"><span data-stu-id="49509-309">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="49509-310">Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函式合成。</span><span class="sxs-lookup"><span data-stu-id="49509-310">Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle function synthesis.</span></span> <span data-ttu-id="49509-311">[PR #135](https://github.com/Microsoft/Quantum/pull/135)。</span><span class="sxs-lookup"><span data-stu-id="49509-311">[PR #135](https://github.com/Microsoft/Quantum/pull/135).</span></span>

### <a name="migrating-existing-projects-to-061905"></a><span data-ttu-id="49509-312">將現有的專案移轉至 0.6.1905。</span><span class="sxs-lookup"><span data-stu-id="49509-312">Migrating existing projects to 0.6.1905.</span></span>

<span data-ttu-id="49509-313">若要更新 QDK，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="49509-313">See the [install guide](xref:microsoft.quantum.install) to update the QDK.</span></span>
  
<span data-ttu-id="49509-314">如果您有現有的 Q# 專案來自 0.5 版的 Quantum Development Kit，請依照下列步驟將這些專案移轉至最新版本。</span><span class="sxs-lookup"><span data-stu-id="49509-314">If you have existing Q# projects from version 0.5 of the Quantum Development Kit, the following are the steps to migrate those projects to the newest version.</span></span>

    1. <span data-ttu-id="49509-315">專案必須依序升級。</span><span class="sxs-lookup"><span data-stu-id="49509-315">Projects need to be upgraded in order.</span></span>  <span data-ttu-id="49509-316">如果您的解決方案有多個專案，請依照每個專案的參考順序加以更新。</span><span class="sxs-lookup"><span data-stu-id="49509-316">If you have a solution with multiple projects, update each project in the order they are referenced.</span></span>
    2. <span data-ttu-id="49509-317">從命令列執行 `dotnet clean`，以移除所有現有的二進位檔和中繼檔案。</span><span class="sxs-lookup"><span data-stu-id="49509-317">From a command line, Run `dotnet clean` to remove all existing binaries and intermediate files.</span></span>
    3. <span data-ttu-id="49509-318">在文字編輯器中編輯 .csproj 檔案，將所有 "Microsoft.Quantum" `PackageReference` 的版本變更為 0.6.1904 版，並將 "Microsoft.Quantum.Canon" 套件名稱變更為 "Microsoft.Quantum.Standard"，例如：</span><span class="sxs-lookup"><span data-stu-id="49509-318">In a text editor, edit the .csproj file to change the version of all the "Microsoft.Quantum" `PackageReference` to version 0.6.1904, and change the "Microsoft.Quantum.Canon" package name to "Microsoft.Quantum.Standard", for example:</span></span>

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. <span data-ttu-id="49509-319">從命令列執行下列命令：`dotnet msbuild`</span><span class="sxs-lookup"><span data-stu-id="49509-319">From the command line, run this command: `dotnet msbuild`</span></span>  
    5. <span data-ttu-id="49509-320">執行此命令後，您可能仍需手動解決因上述變更所造成的錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-320">After running this, you might still need to manually address errors due to changes listed above.</span></span>  <span data-ttu-id="49509-321">在許多情況下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 也會報告這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-321">In many cases, these errors will also be reported by IntelliSense in Visual Studio or Visual Studio Code.</span></span>
        - <span data-ttu-id="49509-322">在 Visual Studio 2019 或 Visual Studio Code 中開啟專案或其所屬解決方案的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="49509-322">Open the root folder of the project or the containing solution in Visual Studio 2019 or Visual Studio Code.</span></span>
        - <span data-ttu-id="49509-323">在編輯器中開啟 .qs 檔案後，您應該會在輸出視窗中看到 Q# 語言延伸模組的輸出。</span><span class="sxs-lookup"><span data-stu-id="49509-323">After opening a .qs file in the editor, you should see the output of the Q# language extension in the output window.</span></span>
        - <span data-ttu-id="49509-324">成功載入專案後 (會在輸出視窗中指出)，請開啟每個檔案，並手動解決其餘的所有問題。</span><span class="sxs-lookup"><span data-stu-id="49509-324">After the project has loaded successfully (indicated in the output window) open each file and manually to address all remaining issues.</span></span>

> [!NOTE]
> * <span data-ttu-id="49509-325">對於 0.6 版本，隨附於 Quantum Development Kit 的語言伺服器不支援多個工作區。</span><span class="sxs-lookup"><span data-stu-id="49509-325">For the 0.6 release, the language server included with the Quantum Development Kit does not support multiple workspaces.</span></span>
> * <span data-ttu-id="49509-326">若要在 Visual Studio Code 中使用專案，請開啟包含專案本身和所有參考專案的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="49509-326">In order to work with a project in Visual Studio Code, open the root folder containing the project itself and all referenced projects.</span></span>   
> * <span data-ttu-id="49509-327">若要在 Visual Studio 中使用解決方案，解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="49509-327">In order to work with a solution in Visual Studio, all projects contained in the solution need to be in the same folder as the solution or in one of its subfolders.</span></span>  
> * <span data-ttu-id="49509-328">在專案間移轉至 0.6 和更新版本的參考，以及使用舊版套件的專案，均**不**受支援。</span><span class="sxs-lookup"><span data-stu-id="49509-328">References between projects migrated to 0.6 and higher and projects using older package versions are **not** supported.</span></span>

## <a name="version-051904"></a><span data-ttu-id="49509-329">0\.5.1904 版</span><span class="sxs-lookup"><span data-stu-id="49509-329">Version 0.5.1904</span></span>

<span data-ttu-id="49509-330">*發行日期：2019 年 4 月 15 日*</span><span class="sxs-lookup"><span data-stu-id="49509-330">*Release date: April 15, 2019*</span></span>

<span data-ttu-id="49509-331">此版本包含 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="49509-331">This release contains bug fixes.</span></span>


## <a name="version-051903"></a><span data-ttu-id="49509-332">0\.5.1903 版</span><span class="sxs-lookup"><span data-stu-id="49509-332">Version 0.5.1903</span></span>

<span data-ttu-id="49509-333">*發行日期：2019 年 3 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="49509-333">*Release date: March 27, 2019*</span></span>

<span data-ttu-id="49509-334">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-334">This release contains the following:</span></span>

- <span data-ttu-id="49509-335">新增 Jupyter Notebook 的支援，這可提供了解 Q# 的絕佳途徑。</span><span class="sxs-lookup"><span data-stu-id="49509-335">Adds support for Jupyter Notebook, which offers a great way to learn about Q#.</span></span>  <span data-ttu-id="49509-336">請[查看新的 Jupyter Notebook 範例，並了解如何撰寫您自己的 Notebook](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="49509-336">[Check out new Jupyter Notebook samples and learn how to write your own Notebooks](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="49509-337">將整數 adder 演算法新增至 Quantum Canon 程式庫。</span><span class="sxs-lookup"><span data-stu-id="49509-337">Adds integer adder arithmetic to the Quantum Canon library.</span></span>  <span data-ttu-id="49509-338">另請參閱[說明如何使用新的整數 adder](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb) 的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="49509-338">See also a Jupyter Notebook that [describes how to use the new integer adders](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).</span></span>

- <span data-ttu-id="49509-339">社群回報的 DumpRegister 問題 ([#148](https://github.com/Microsoft/Quantum/issues/148)) 的 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="49509-339">Bug fix for DumpRegister issue reported by the community ([#148](https://github.com/Microsoft/Quantum/issues/148)).</span></span>

- <span data-ttu-id="49509-340">新增了從 [Using 陳述式](xref:microsoft.quantum.guide.qubits#allocating-qubits)傳回的功能。</span><span class="sxs-lookup"><span data-stu-id="49509-340">Added ability to return from within a [using statement](xref:microsoft.quantum.guide.qubits#allocating-qubits).</span></span>

- <span data-ttu-id="49509-341">全新設計的[使用者入門指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="49509-341">Revamped [getting started guide](xref:microsoft.quantum.install).</span></span>


## <a name="version-051902"></a><span data-ttu-id="49509-342">0\.5.1902 版</span><span class="sxs-lookup"><span data-stu-id="49509-342">Version 0.5.1902</span></span>

<span data-ttu-id="49509-343">*發行日期：2019 年 2 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="49509-343">*Release date: February 27, 2019*</span></span>

<span data-ttu-id="49509-344">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-344">This release contains the following:</span></span>

- <span data-ttu-id="49509-345">新增跨平台 Python 主機的支援。</span><span class="sxs-lookup"><span data-stu-id="49509-345">Adds support for a cross-platform Python host.</span></span>  <span data-ttu-id="49509-346">適用於 Python 的 `qsharp` 套件可讓您輕鬆地從 Python 內模擬 Q# 作業和函式。</span><span class="sxs-lookup"><span data-stu-id="49509-346">The `qsharp` package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="49509-347">深入了解 [Python 互通性](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="49509-347">Learn more about [Python interoperability](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="49509-348">Visual Studio 和 Visual Studio Code 延伸模組現已支援符號 (例如函式和作業) 的重新命名。</span><span class="sxs-lookup"><span data-stu-id="49509-348">The Visual Studio and Visual Studio Code extensions now support renaming of symbols (e.g., functions and operations).</span></span>

- <span data-ttu-id="49509-349">Visual Studio 延伸模組現已可安裝在 Visual Studio 2019 上。</span><span class="sxs-lookup"><span data-stu-id="49509-349">The Visual Studio extension can now be installed on Visual Studio 2019.</span></span>

## <a name="version-041901"></a><span data-ttu-id="49509-350">0\.4.1901 版</span><span class="sxs-lookup"><span data-stu-id="49509-350">Version 0.4.1901</span></span>

<span data-ttu-id="49509-351">*發行日期：2019 年 1 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="49509-351">*Release date: January 30, 2019*</span></span>

<span data-ttu-id="49509-352">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49509-352">This release contains the following:</span></span>

- <span data-ttu-id="49509-353">新增新的基本類型 BigInt 的支援，此類型代表任意大小帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="49509-353">adds support for a new primitive type, BigInt, which represents a signed integer of arbitrary size.</span></span>  <span data-ttu-id="49509-354">深入了解 [BigInt 類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="49509-354">Learn more about [BigInt type](xref:microsoft.quantum.guide.types).</span></span>
- <span data-ttu-id="49509-355">新增 Toffoli 模擬器，這是一種特殊用途的快速模擬器，可模擬具有大量量子位元的 X、CNOT 和多重受控 X 量子作業。</span><span class="sxs-lookup"><span data-stu-id="49509-355">adds new Toffoli simulator, a special purpose fast simulator that can simulate X, CNOT and multi-controlled X quantum operations with very large numbers of qubits.</span></span>  <span data-ttu-id="49509-356">深入了解 [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)。</span><span class="sxs-lookup"><span data-stu-id="49509-356">Learn more about [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator).</span></span>
- <span data-ttu-id="49509-357">新增簡單的資源估算器，可估算在量子電腦上執行 Q# 作業的指定執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="49509-357">adds a simple resource estimator that estimates the resources required to run a given instancee of a Q# operation on a quantum computer.</span></span>  <span data-ttu-id="49509-358">深入了解[資源估算器](xref:microsoft.quantum.machines.resources-estimator)。</span><span class="sxs-lookup"><span data-stu-id="49509-358">Learn more about the [Resource Estimator](xref:microsoft.quantum.machines.resources-estimator).</span></span>


## <a name="version-0318112802"></a><span data-ttu-id="49509-359">0\.3.1811.2802 版</span><span class="sxs-lookup"><span data-stu-id="49509-359">Version 0.3.1811.2802</span></span>

<span data-ttu-id="49509-360">*發行日期：2018 年 11 月 28 日*</span><span class="sxs-lookup"><span data-stu-id="49509-360">*Release date: November 28, 2018*</span></span>

<span data-ttu-id="49509-361">此版本已在與 `event-stream` NPM 套件相關的[延伸模組清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)期間加上旗標，並從 Marketplace 中移除，但我們的 VS Code 延伸模組並未加以使用。</span><span class="sxs-lookup"><span data-stu-id="49509-361">Even though our VS Code extension was not using it, it was flagged and removed from the marketplace during [the extensions purge](https://code.visualstudio.com/blogs/2018/11/26/event-stream) related to the `event-stream` NPM package.</span></span> <span data-ttu-id="49509-362">此版本移除了所有可能致使延伸模組觸發任何紅色旗標的執行階段相依性。</span><span class="sxs-lookup"><span data-stu-id="49509-362">This version removes all runtime dependencies that could make the extension trigger any red flags.</span></span>

<span data-ttu-id="49509-363">如果您先前已安裝此延伸模組，您必須造訪 Visual Studio Marketplace 上的 [Visual Studio Code 延伸模組的 Microsoft Quantum Development Kit](vscode:extension/quantum.quantum-devkit-vscode)，並且按 [安裝] 重新加以安裝。</span><span class="sxs-lookup"><span data-stu-id="49509-363">If you had previously installed the extension you will need to install it again by visiting the [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) extension on the Visual Studio Marketplace and press Install.</span></span> <span data-ttu-id="49509-364">很抱歉造成您的不便。</span><span class="sxs-lookup"><span data-stu-id="49509-364">We are sorry about the inconvenience.</span></span>


## <a name="version-0318111511"></a><span data-ttu-id="49509-365">0\.3.1811.1511 版</span><span class="sxs-lookup"><span data-stu-id="49509-365">Version 0.3.1811.1511</span></span>

<span data-ttu-id="49509-366">*發行日期：2018 年 11 月 20 日*</span><span class="sxs-lookup"><span data-stu-id="49509-366">*Release date: November 20, 2018*</span></span>

<span data-ttu-id="49509-367">此版本修正了導致某些使用者無法成功載入 Visual Studio 延伸模組的 Bug。</span><span class="sxs-lookup"><span data-stu-id="49509-367">This release fixes a bug that prevented some users to successfully load the Visual Studio extension.</span></span>

## <a name="version-031811203"></a><span data-ttu-id="49509-368">0\.3.1811.203 版</span><span class="sxs-lookup"><span data-stu-id="49509-368">Version 0.3.1811.203</span></span>

<span data-ttu-id="49509-369">*發行日期：2018 年 11 月 2 日*</span><span class="sxs-lookup"><span data-stu-id="49509-369">*Release date: November 2, 2018*</span></span>

<span data-ttu-id="49509-370">此版本包含一些 Bug 修正，包括：</span><span class="sxs-lookup"><span data-stu-id="49509-370">This release includes a few bug fixes, including:</span></span>

* <span data-ttu-id="49509-371">在特定情況下，叫用 `DumpMachine` 可能會變更模擬器的狀態。</span><span class="sxs-lookup"><span data-stu-id="49509-371">Invoking `DumpMachine` could change the state of the simulator under certain situations.</span></span>
* <span data-ttu-id="49509-372">移除了在使用 2.1.403 之前的 .NET Core 版本建置專案時所產生的編譯警告。</span><span class="sxs-lookup"><span data-stu-id="49509-372">Removed compilation warnings when building projects using a version of .NET Core previous to 2.1.403.</span></span>
* <span data-ttu-id="49509-373">清除了文件，特別是在 VS Code 或 Visual Studio 中暫留滑鼠時所顯示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="49509-373">Clean up of documentation, specially the tooltips shown during mouse hover in VS Code or Visual Studio.</span></span>

## <a name="version-0318102508"></a><span data-ttu-id="49509-374">0\.3.1810.2508 版</span><span class="sxs-lookup"><span data-stu-id="49509-374">Version 0.3.1810.2508</span></span>

<span data-ttu-id="49509-375">*發行日期：2018 年 10 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="49509-375">*Release date: October 29, 2018*</span></span>

<span data-ttu-id="49509-376">此版本包含新的語言功能和改良的開發人員體驗：</span><span class="sxs-lookup"><span data-stu-id="49509-376">This release includes new language features and an improved developer experience:</span></span>

* <span data-ttu-id="49509-377">此版本包含 Q# 的語言伺服器，以及 Visual Studio 和 Visual Studio Code 的用戶端整合。</span><span class="sxs-lookup"><span data-stu-id="49509-377">This release includes a language server for Q#, as well as the client integrations for Visual Studio and Visual Studio Code.</span></span> <span data-ttu-id="49509-378">這會啟用一組新的 IntelliSense 功能，以及以波狀底線的形式輸入錯誤和警告的即時反饋。</span><span class="sxs-lookup"><span data-stu-id="49509-378">This enables a new set of IntelliSense features along with live feedback on typing in form of squiggly underlinings of errors and warnings.</span></span> 
* <span data-ttu-id="49509-379">整體而言，這項更新可讓您輕鬆瀏覽至精確的診斷範圍，並且在顯示的暫留資訊中提供其他詳細資料，而大幅改善了診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="49509-379">This update greatly improves diagnostic messages in general, with easy navigation to and precise ranges for diagnostics and additional details in the displayed hover information.</span></span>
* <span data-ttu-id="49509-380">Q# 語言已經過適當擴充，而統合了開發人員執行常見作業的方式，並且對語言功能進行了新的強化，以有效表達量子運算。</span><span class="sxs-lookup"><span data-stu-id="49509-380">The Q# language has been extended in ways that unifies the ways developers can do common operations and new enhancements to the language features to powerfully express quantum computation.</span></span>  <span data-ttu-id="49509-381">此版本的 Q# 語言有若干重大變更。</span><span class="sxs-lookup"><span data-stu-id="49509-381">There are a handful of breaking changes to the Q# language with this release.</span></span>   

<span data-ttu-id="49509-382">此版本也包含新的量子化學程式庫：</span><span class="sxs-lookup"><span data-stu-id="49509-382">This release also includes a new quantum chemistry library:</span></span>

* <span data-ttu-id="49509-383">化學程式庫包含新的 Hamiltonian 模擬功能，包括：</span><span class="sxs-lookup"><span data-stu-id="49509-383">The chemistry library contains new Hamiltonian simulation features, including:</span></span>
    - <span data-ttu-id="49509-384">Trotter – 任意偶次的 Suzuki 整合器，用以改善模擬正確性。</span><span class="sxs-lookup"><span data-stu-id="49509-384">Trotter–Suzuki integrators of arbitrary even order for improved simulation accuracy.</span></span>
    - <span data-ttu-id="49509-385">採用化學專用最佳化的量子位元化模擬技術，用以降低 $T$ 閘道複雜度。</span><span class="sxs-lookup"><span data-stu-id="49509-385">Qubitization simulation technique with chemistry-specific optimizations for reducing $T$-gate complexity.</span></span>
* <span data-ttu-id="49509-386">導入了新的開放原始碼結構描述，名為 Broombridge 結構描述 (得名自被譽為 Hamiltonian 發源地的[地標](https://en.wikipedia.org/wiki/Broom_Bridge))，用以匯入分子的表示法及加以模擬。</span><span class="sxs-lookup"><span data-stu-id="49509-386">A new open source schema, called Broombridge Schema (in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) celebrated as a birthplace of Hamiltonians), is introduced for importing representations of molecules and simulating them.</span></span>
* <span data-ttu-id="49509-387">提供多個使用 Broombridge 結構描述定義的化學標記法。</span><span class="sxs-lookup"><span data-stu-id="49509-387">Multiple chemical representations defined using the Broombridge Schema are provided.</span></span>  <span data-ttu-id="49509-388">這些模型由 [NWChem](http://www.nwchem-sw.org/) (一種開放原始碼高效能運算化學工具) 所產生。</span><span class="sxs-lookup"><span data-stu-id="49509-388">These models were generated by [NWChem](http://www.nwchem-sw.org/), an open source high-performance computational chemistry tool.</span></span>
* <span data-ttu-id="49509-389">教學課程和範例會說明如何使用化學程式庫和 Broombridge 資料模型來：</span><span class="sxs-lookup"><span data-stu-id="49509-389">Tutorials and Samples describe how to use the chemistry library and the Broombridge data models to:</span></span>
    - <span data-ttu-id="49509-390">使用化學程式庫建構簡單的 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="49509-390">Construct simple Hamiltonians using the chemistry library</span></span>
    - <span data-ttu-id="49509-391">使用階段估算呈現氫化鋰的基態能量和激發態能量。</span><span class="sxs-lookup"><span data-stu-id="49509-391">Visualize ground and excited energies of Lithium Hydride using phase estimation.</span></span>
    - <span data-ttu-id="49509-392">執行量子化學模擬的資源估算。</span><span class="sxs-lookup"><span data-stu-id="49509-392">Perform resource estimates of quantum chemistry simulation.</span></span>
    - <span data-ttu-id="49509-393">對 Broombridge 結構描述所代表的分子估算能階。</span><span class="sxs-lookup"><span data-stu-id="49509-393">Estimate energy levels of molecules represented by the Broombridge schema.</span></span>
* <span data-ttu-id="49509-394">文件會說明如何使用 NWChem 產生 Q# 的量子模擬所適用的其他化學模型。</span><span class="sxs-lookup"><span data-stu-id="49509-394">Documentation describes how to use NWChem to generate additional chemical models for quantum simulation with Q#.</span></span>

<span data-ttu-id="49509-395">深入了解 [Quantum Development Kit 化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="49509-395">Learn more about the [Quantum Development Kit chemistry library](xref:microsoft.quantum.chemistry.concepts.intro).</span></span>

<span data-ttu-id="49509-396">透過新的化學程式庫，我們將程式庫劃分到新的 GitHub 存放庫 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) 中。</span><span class="sxs-lookup"><span data-stu-id="49509-396">With the new chemistry library, we are separating out the libraries into a new GitHub repo, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).</span></span>  <span data-ttu-id="49509-397">範例仍保留在存放庫 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 中。</span><span class="sxs-lookup"><span data-stu-id="49509-397">The samples remain in the repo [Microsoft/Quantum](https://github.com/Microsoft/Quantum).</span></span>  <span data-ttu-id="49509-398">歡迎大家參與對這兩個存放庫的建構！</span><span class="sxs-lookup"><span data-stu-id="49509-398">We welcome contributions to both!</span></span>

<span data-ttu-id="49509-399">此版本包含針對社群回報的問題而提供的 Bug 修正和功能：</span><span class="sxs-lookup"><span data-stu-id="49509-399">This release includes bug fixes and features for issues reported by the community:</span></span>

* <span data-ttu-id="49509-400">Intellisense 適用於 Q# 嗎？</span><span class="sxs-lookup"><span data-stu-id="49509-400">Intellisense for Q#?</span></span> <span data-ttu-id="49509-401">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。</span><span class="sxs-lookup"><span data-stu-id="49509-401">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).</span></span>
* <span data-ttu-id="49509-402">.qs 檔案 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。</span><span class="sxs-lookup"><span data-stu-id="49509-402">.qs files ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).</span></span>
* <span data-ttu-id="49509-403">改善 If 陳述式中的大括弧節略時的錯誤訊息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。</span><span class="sxs-lookup"><span data-stu-id="49509-403">Improve error message when curly braces are abbreviated in if statement ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).</span></span>
* <span data-ttu-id="49509-404">支援可變動 (重新) 繫結上的元組解構 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。</span><span class="sxs-lookup"><span data-stu-id="49509-404">Support tuple deconstruction at mutable (re-)binding ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).</span></span>
* <span data-ttu-id="49509-405">執行提供的 BitFlipCode 時發生的錯誤 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="49509-405">Error Running Provided BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>
* <span data-ttu-id="49509-406">H2SimulationGUI 有時會顯示大型尖峰 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。</span><span class="sxs-lookup"><span data-stu-id="49509-406">H2SimulationGUI displays big peaks sometimes ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="49509-407">社群貢獻</span><span class="sxs-lookup"><span data-stu-id="49509-407">Community Contributions</span></span>

<span data-ttu-id="49509-408">**感謝**</span><span class="sxs-lookup"><span data-stu-id="49509-408">**Thank you!**</span></span> <span data-ttu-id="49509-409">下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。</span><span class="sxs-lookup"><span data-stu-id="49509-409">to the following contributors to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="49509-410">這些貢獻讓 Q# 程式碼的範例更加豐富：</span><span class="sxs-lookup"><span data-stu-id="49509-410">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="49509-411">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman))：藉由建立從 QASM 到的 Q# 的轉譯程式，改善了 QASM/Q# 開發人員的體驗。</span><span class="sxs-lookup"><span data-stu-id="49509-411">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Improved the experience for QASM/Q# developers by creating a QASM to Q# translator.</span></span> <span data-ttu-id="49509-412">[PR #58](https://github.com/Microsoft/Quantum/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="49509-412">[PR #58](https://github.com/Microsoft/Quantum/pull/58).</span></span>

* <span data-ttu-id="49509-413">Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了實作 CHSH 賽局的範例；這是與非定域性相關的量子賽局。</span><span class="sxs-lookup"><span data-stu-id="49509-413">Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Contributed a sample implementing the CHSH Game, a quantum game related to non-locality.</span></span>  <span data-ttu-id="49509-414">[PR #84](https://github.com/Microsoft/Quantum/pull/84)。</span><span class="sxs-lookup"><span data-stu-id="49509-414">[PR #84](https://github.com/Microsoft/Quantum/pull/84).</span></span>

<span data-ttu-id="49509-415">同時感謝 Rohit Gupta ([@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90))、Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) 和 Lee James O'Riordan ([@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)) 為了改善我們所有人的內容，在文件、拼字和校對方面的努力付出！</span><span class="sxs-lookup"><span data-stu-id="49509-415">Thank you also to Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), and Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) for their work improving the content for all of us through documentation, spelling and typo corrections!</span></span> 

## <a name="version-021809701"></a><span data-ttu-id="49509-416">0\.2.1809.701 版</span><span class="sxs-lookup"><span data-stu-id="49509-416">Version 0.2.1809.701</span></span>

<span data-ttu-id="49509-417">*發行日期：2018 年 9 月 10 日*</span><span class="sxs-lookup"><span data-stu-id="49509-417">*Release date: September 10, 2018*</span></span>

<span data-ttu-id="49509-418">此版本包含對社群回報的問題所做的 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="49509-418">This release includes bug fixes for issues reported by the community.</span></span> <span data-ttu-id="49509-419">其中包括：</span><span class="sxs-lookup"><span data-stu-id="49509-419">Including:</span></span>

* <span data-ttu-id="49509-420">無法使用移位運算子 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。</span><span class="sxs-lookup"><span data-stu-id="49509-420">Unable to use shift operator ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).</span></span>
* <span data-ttu-id="49509-421">在列印到主控台，`QCTraceSimulator` 上的 `DumpMachine` / `DumpRegister` 會失敗 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。</span><span class="sxs-lookup"><span data-stu-id="49509-421">`DumpMachine` / `DumpRegister` fails on `QCTraceSimulator` when printing to console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).</span></span>
* <span data-ttu-id="49509-422">允許配置 0 個量子位元 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。</span><span class="sxs-lookup"><span data-stu-id="49509-422">Allow allocating 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).</span></span>
* <span data-ttu-id="49509-423">`AssertQubitState` 需要明確的 Complex() 呼叫 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。</span><span class="sxs-lookup"><span data-stu-id="49509-423">`AssertQubitState` requires explicit Complex() call ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).</span></span>
* <span data-ttu-id="49509-424">macOS 上的 `Measure` 作業一律會傳回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="49509-424">`Measure` operation always returns `One` on macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>

<span data-ttu-id="49509-425">感謝您！</span><span class="sxs-lookup"><span data-stu-id="49509-425">Thanks!</span></span> 

## <a name="version-0218063001"></a><span data-ttu-id="49509-426">0\.2.1806.3001 版</span><span class="sxs-lookup"><span data-stu-id="49509-426">Version 0.2.1806.3001</span></span>

<span data-ttu-id="49509-427">*發行日期：2018 年 6 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="49509-427">*Release date: June 30, 2018*</span></span>

<span data-ttu-id="49509-428">此版本只是 [GitHub 上回報的問題 #48](https://github.com/Microsoft/Quantum/issues/48) (如果使用者名稱包含空格，Q# 編譯即會失敗) 的快速修正。</span><span class="sxs-lookup"><span data-stu-id="49509-428">This releases is just a quick fix for [issue #48 reported on GitHub](https://github.com/Microsoft/Quantum/issues/48) (Q# compilation fails if user name contains a blank space).</span></span> <span data-ttu-id="49509-429">使用對應的新版本 (`0.2.1806.3001-preview`) 時，請遵循與 `0.2.1806.1503` 相同的更新指示。</span><span class="sxs-lookup"><span data-stu-id="49509-429">Follow same update instructions as `0.2.1806.1503` with the corresponding new version (`0.2.1806.3001-preview`).</span></span>

## <a name="version-0218061503"></a><span data-ttu-id="49509-430">0\.2.1806.1503 版</span><span class="sxs-lookup"><span data-stu-id="49509-430">Version 0.2.1806.1503</span></span>

<span data-ttu-id="49509-431">*發行日期：2018 年 6 月 22 日*</span><span class="sxs-lookup"><span data-stu-id="49509-431">*Release date: June 22, 2018*</span></span>

<span data-ttu-id="49509-432">此版本包含幾項社群貢獻，以及有所改善的偵錯體驗和增進的效能。</span><span class="sxs-lookup"><span data-stu-id="49509-432">This release includes several community contributions as well as an improved debugging experience and improved performance.</span></span>  <span data-ttu-id="49509-433">具體來說：</span><span class="sxs-lookup"><span data-stu-id="49509-433">Specifically:</span></span>

* <span data-ttu-id="49509-434">QuantumSimulator 目標電腦的小型和大型模擬的效能改進。</span><span class="sxs-lookup"><span data-stu-id="49509-434">Performance improvements on both small and large simulations for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="49509-435">改良的偵錯功能。</span><span class="sxs-lookup"><span data-stu-id="49509-435">Improved debugging functionality.</span></span>
* <span data-ttu-id="49509-436">社群在 Bug 修正、新的 Helper 函式、作業和新範例等方面的貢獻。</span><span class="sxs-lookup"><span data-stu-id="49509-436">Community contributions in bug fixes, new helper functions, operations and new samples.</span></span>

### <a name="performance-improvements"></a><span data-ttu-id="49509-437">效能改善</span><span class="sxs-lookup"><span data-stu-id="49509-437">Performance improvements</span></span>

<span data-ttu-id="49509-438">這項更新包括所有目標電腦的大量和少量量子位元模擬皆有顯著的效能改善。</span><span class="sxs-lookup"><span data-stu-id="49509-438">This update includes significant performance improvements for simulation of large and small numbers of qubits for all the target machines.</span></span>  <span data-ttu-id="49509-439">經由在 Quantum Development Kit 中作為標準範例的 H<sub>2</sub> 模擬，可發現改善的幅度顯而易見。</span><span class="sxs-lookup"><span data-stu-id="49509-439">This improvement is easily visible with the H<sub>2</sub> simulation that is a standard sample in the Quantum Development Kit.</span></span>

### <a name="improved-debugging-functionality"></a><span data-ttu-id="49509-440">改良的偵錯功能</span><span class="sxs-lookup"><span data-stu-id="49509-440">Improved debugging functionality</span></span>

<span data-ttu-id="49509-441">此更新新增了偵錯功能：</span><span class="sxs-lookup"><span data-stu-id="49509-441">This update adds new debugging functionality:</span></span>
* <span data-ttu-id="49509-442">新增了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 兩個新作業，可輸出目標量子電腦在某個時間點的波形函式相關資訊。</span><span class="sxs-lookup"><span data-stu-id="49509-442">Added two new operations,  @"microsoft.quantum.extensions.diagnostics.dumpmachine" and @"microsoft.quantum.extensions.diagnostics.dumpregister" that output wave function information about the target quantum machine at a point in time.</span></span>  
* <span data-ttu-id="49509-443">在 Visual Studio 中，對單一量子位元測量 $\ket{1}$ 的機率現在會自動顯示在 QuantumSimulator 目標電腦的偵錯視窗中。</span><span class="sxs-lookup"><span data-stu-id="49509-443">In Visual Studio, the probability of measuring a $\ket{1}$ on a single qubit is now automatically shown in the debugging window for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="49509-444">在 Visual Studio 中，變數屬性在 [自動變數] 和 [區域變數] 偵錯視窗中的顯示已有所改善。</span><span class="sxs-lookup"><span data-stu-id="49509-444">In Visual Studio, improved the display of variable properties in the **Autos** and **Locals** debug windows.</span></span> 

<span data-ttu-id="49509-445">深入了解[測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="49509-445">Learn more about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="49509-446">社群貢獻</span><span class="sxs-lookup"><span data-stu-id="49509-446">Community Contributions</span></span>

<span data-ttu-id="49509-447">Q# 編碼員社群正持續擴展中，我們十分樂見第一個由使用者參與內容建構的程式庫和範例已提交至我們的開放程式碼基底，位於 http://github.com/Microsoft/quantum 。</span><span class="sxs-lookup"><span data-stu-id="49509-447">The Q# coder community is growing and we are thrilled to see the first user contributed libraries and samples that were submitted to our open code base at http://github.com/Microsoft/quantum.</span></span>  <span data-ttu-id="49509-448">**非常感謝**</span><span class="sxs-lookup"><span data-stu-id="49509-448">**A big Thank you!**</span></span> <span data-ttu-id="49509-449">下列參與者：</span><span class="sxs-lookup"><span data-stu-id="49509-449">to the following contributors:</span></span>
* <span data-ttu-id="49509-450">Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一個範例，定義以轉換為基礎的邏輯合成方法，以建構用來實作指定排列的 Toffoli 網路。</span><span class="sxs-lookup"><span data-stu-id="49509-450">Mathias Soeken ([@msoeken](https://github.com/msoeken)):  contributed a sample defining a transformation based logic synthesis method that constructs Toffoli networks to implement a given permutation.</span></span> <span data-ttu-id="49509-451">其程式碼完全以 Q# 函式和作業撰寫。</span><span class="sxs-lookup"><span data-stu-id="49509-451">The code is written entirely in Q# functions and operations.</span></span>  <span data-ttu-id="49509-452">[PR #41](https://github.com/Microsoft/Quantum/pull/41)。</span><span class="sxs-lookup"><span data-stu-id="49509-452">[PR #41](https://github.com/Microsoft/Quantum/pull/41).</span></span>
* <span data-ttu-id="49509-453">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman))：Microsoft MVP Rolf Huisman 提供了一個範例，可從 Q# 程式碼為不具傳統控制流程的限定程式類別和限定的量子作業產生一般 QASM 程式碼。</span><span class="sxs-lookup"><span data-stu-id="49509-453">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Microsoft MVP Rolf Huisman contributed a sample that generates flat QASM code from Q# code for a restricted class of programs that do not have classical control flow and restricted quantum operations.</span></span> [<span data-ttu-id="49509-454">PR #59</span><span class="sxs-lookup"><span data-stu-id="49509-454">PR #59</span></span>](https://github.com/Microsoft/Quantum/pull/59)
* <span data-ttu-id="49509-455">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：藉由提交受控作業適用的程式庫函式，協助我們改善程式碼基底。</span><span class="sxs-lookup"><span data-stu-id="49509-455">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): helped to improve our code base by submitting a library function for controlled operations.</span></span> [<span data-ttu-id="49509-456">PR #53</span><span class="sxs-lookup"><span data-stu-id="49509-456">PR #53</span></span>](https://github.com/Microsoft/Quantum/pull/53)
* <span data-ttu-id="49509-457">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修正 @"microsoft.quantum.canon.quantumphaseestimation" 並建立了新的單元測試。</span><span class="sxs-lookup"><span data-stu-id="49509-457">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): fixed @"microsoft.quantum.canon.quantumphaseestimation" and created new unit tests.</span></span>  [<span data-ttu-id="49509-458">PR #54</span><span class="sxs-lookup"><span data-stu-id="49509-458">PR #54</span></span>](https://github.com/Microsoft/Quantum/pull/54)
* <span data-ttu-id="49509-459">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：藉由確定 QuantumSimulator 執行個體已處置，清除了遙傳範例。</span><span class="sxs-lookup"><span data-stu-id="49509-459">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): cleaned the Teleportation sample by making sure the QuantumSimulator instance is disposed.</span></span> [<span data-ttu-id="49509-460">PR #20</span><span class="sxs-lookup"><span data-stu-id="49509-460">PR #20</span></span>](https://github.com/Microsoft/Quantum/pull/20)

<span data-ttu-id="49509-461">同時也**非常感謝**</span><span class="sxs-lookup"><span data-stu-id="49509-461">Additionally, a big **Thank You!**</span></span> <span data-ttu-id="49509-462">參與商業工程服務小組的 Microsoft 軟體工程師，他們在參加黑客松期間時對我們的文件做出了重要的變更。</span><span class="sxs-lookup"><span data-stu-id="49509-462">to these Microsoft Software Engineers from the Commercial Engineering Services team contributors who made valuable changes to our documentation during their Hackathon.</span></span>  <span data-ttu-id="49509-463">他們的變更我們所有人大幅提升了定義的明確性和上線體驗：</span><span class="sxs-lookup"><span data-stu-id="49509-463">Their changes vastly improved the clarity and onboarding experience for all of us:</span></span>
* <span data-ttu-id="49509-464">Sascha Corti</span><span class="sxs-lookup"><span data-stu-id="49509-464">Sascha Corti</span></span>
* <span data-ttu-id="49509-465">Mihaela Curmei</span><span class="sxs-lookup"><span data-stu-id="49509-465">Mihaela Curmei</span></span>
* <span data-ttu-id="49509-466">John Donnelly</span><span class="sxs-lookup"><span data-stu-id="49509-466">John Donnelly</span></span>
* <span data-ttu-id="49509-467">Kirill Logachev</span><span class="sxs-lookup"><span data-stu-id="49509-467">Kirill Logachev</span></span>
* <span data-ttu-id="49509-468">Jan Pospisil</span><span class="sxs-lookup"><span data-stu-id="49509-468">Jan Pospisil</span></span>
* <span data-ttu-id="49509-469">Anita Ramanan</span><span class="sxs-lookup"><span data-stu-id="49509-469">Anita Ramanan</span></span>
* <span data-ttu-id="49509-470">Frances Tibble</span><span class="sxs-lookup"><span data-stu-id="49509-470">Frances Tibble</span></span>
* <span data-ttu-id="49509-471">Alessandro Vozza</span><span class="sxs-lookup"><span data-stu-id="49509-471">Alessandro Vozza</span></span>

### <a name="update-existing-projects"></a><span data-ttu-id="49509-472">更新現有的專案</span><span class="sxs-lookup"><span data-stu-id="49509-472">Update existing projects</span></span>

<span data-ttu-id="49509-473">此版本具完整的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="49509-473">This release is fully backwards compatible.</span></span> <span data-ttu-id="49509-474">只要將專案中的 nuget 套件更新為 `0.2.1806.1503-preview` 版，並執行**完整重建**，即可確定所有中繼檔案都會重新產生。</span><span class="sxs-lookup"><span data-stu-id="49509-474">Just update the nuget pakages in your projects to version `0.2.1806.1503-preview` and do a **full rebuild** to make sure all intermediate files are regenerated.</span></span>

<span data-ttu-id="49509-475">在 Visual Studio 中，依照關於[更新套件](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的一般指示操作。</span><span class="sxs-lookup"><span data-stu-id="49509-475">From Visual Studio, follow the normal instructions on how to [update a package](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).</span></span>

<span data-ttu-id="49509-476">若要更新命令列的專案範本，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="49509-476">To update project templates for the command line, run the following command:</span></span>
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

<span data-ttu-id="49509-477">執行此命令後，任何使用 `dotnet new <project-type> -lang Q#` 建立的新專案都會自動使用此版本的 Quantum Development Kit。</span><span class="sxs-lookup"><span data-stu-id="49509-477">After running this command, any new projects created using `dotnet new <project-type> -lang Q#` will automatically use this version of the Quantum Development Kit.</span></span>

<span data-ttu-id="49509-478">若要更新現有的專案以使用最新版本，請從各個專案的目錄中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="49509-478">To update an existing project to use the newest version, run the following command from within the directory for each project:</span></span>

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

<span data-ttu-id="49509-479">如果現有的專案也使用 XUnit 整合進行單元測試，則也可以使用類似的命令來更新該套件：</span><span class="sxs-lookup"><span data-stu-id="49509-479">If an existing project also uses XUnit integration for unit testing, then a similar command can be used to update that package as well:</span></span>
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

<span data-ttu-id="49509-480">根據您的測試專案所使用的 XUnit 版本，您可能也需要將 XUnit 更新為 2.3.1：</span><span class="sxs-lookup"><span data-stu-id="49509-480">Depending on the version of XUnit that your test project uses, you may also need to update XUnit to 2.3.1:</span></span>
```
dotnet add package xunit -v "2.3.1" 
```

<span data-ttu-id="49509-481">更新之後，請務必執行下列動作，以移除舊版所產生的所有暫存檔案：</span><span class="sxs-lookup"><span data-stu-id="49509-481">After the update, make sure you remove all temporary files generated by the previous version by doing:</span></span>
```
dotnet clean 
```

### <a name="known-issues"></a><span data-ttu-id="49509-482">已知問題</span><span class="sxs-lookup"><span data-stu-id="49509-482">Known Issues</span></span>

<span data-ttu-id="49509-483">沒有其他已知問題需要報告。</span><span class="sxs-lookup"><span data-stu-id="49509-483">No aditional known issues to report.</span></span>


## <a name="version-0218022202"></a><span data-ttu-id="49509-484">0\.2.1802.2202 版</span><span class="sxs-lookup"><span data-stu-id="49509-484">Version 0.2.1802.2202</span></span>

<span data-ttu-id="49509-485">*發行日期：2018 年 2 月 26 日*</span><span class="sxs-lookup"><span data-stu-id="49509-485">*Release date: February 26, 2018*</span></span>

<span data-ttu-id="49509-486">此版本提供在更多平台上進行開發的支援、語言互通性，和效能的強化。</span><span class="sxs-lookup"><span data-stu-id="49509-486">This release brings support for development on more platforms, language interoperability, and performance enhancements.</span></span> <span data-ttu-id="49509-487">具體來說：</span><span class="sxs-lookup"><span data-stu-id="49509-487">Specifically:</span></span>

- <span data-ttu-id="49509-488">支援以 macOS 和 Linux 為基礎的開發。</span><span class="sxs-lookup"><span data-stu-id="49509-488">Support for macOS- and Linux-based development.</span></span> 
- <span data-ttu-id="49509-489">.NET Core 相容性，包括對 Visual Studio Code 的跨平台支援。</span><span class="sxs-lookup"><span data-stu-id="49509-489">.NET Core compatibility, including support for Visual Studio Code across platforms.</span></span>
- <span data-ttu-id="49509-490">Quantum Development Kit 程式庫的完整開放原始碼授權。</span><span class="sxs-lookup"><span data-stu-id="49509-490">A full Open Source license for the Quantum Development Kit Libraries.</span></span>
- <span data-ttu-id="49509-491">針對需要 20 個或更多量子位元的專案改善了模擬器效能。</span><span class="sxs-lookup"><span data-stu-id="49509-491">Improved simulator performance on projects requiring 20 or more qubits.</span></span>
- <span data-ttu-id="49509-492">與 Python 語言的互通性 (在 Windows 上可使用預覽版本)。</span><span class="sxs-lookup"><span data-stu-id="49509-492">Interoperability with the Python language (preview release available on Windows).</span></span>

### <a name="net-editions"></a><span data-ttu-id="49509-493">.NET 版本</span><span class="sxs-lookup"><span data-stu-id="49509-493">.NET Editions</span></span>

<span data-ttu-id="49509-494">.NET 平台有兩種不同的版本可供使用：隨附於 Windows 的 .NET Framework，以及 Windows、macOS 和 Linux 上提供的開放原始碼 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="49509-494">The .NET platform is available through two different editions, the .NET Framework that is provided with Windows, and the open-source .NET Core that is available on Windows, macOS and Linux.</span></span>
<span data-ttu-id="49509-495">在此版本中，Quantum Development Kit 大部分的組件均以 .NET Standard 程式庫的形式提供，這是 Framework 和 Core 通用的一組類別。</span><span class="sxs-lookup"><span data-stu-id="49509-495">With this release, most parts of the Quantum Development Kit are provided as libraries for .NET Standard, the set of classes common to both Framework and Core.</span></span>
<span data-ttu-id="49509-496">這些程式庫因而可與最新版本的 .NET Framework 或 .NET Core 相容。</span><span class="sxs-lookup"><span data-stu-id="49509-496">These libraries are therefore compatible with recent versions of either .NET Framework or .NET Core.</span></span>

<span data-ttu-id="49509-497">因此，為了確保使用 Quantum Development Kit 撰寫的專案能有最高的可攜性，我們建議，使用 Quantum Development Kit 撰寫的程式庫專案應以 .NET Standard 為目標，而主控台應用程式則以 .NET Core 為目標。</span><span class="sxs-lookup"><span data-stu-id="49509-497">Thus, to help ensure that projects written using the Quantum Development Kit are as portable as possible, we recommend that library projects written using the Quantum Development Kit target .NET Standard, while console applications target .NET Core.</span></span>
<span data-ttu-id="49509-498">由於舊版的 Quantum Development Kit 僅支援 .NET Framework，因此您可能需要移轉現有的專案；如需如何執行此作業的詳細資訊，請參閱下文。</span><span class="sxs-lookup"><span data-stu-id="49509-498">Since previous releases of the Quantum Development Kit only supported .NET Framework, you may need to migrate your existing projects; see below for details on how to do this.</span></span>

### <a name="project-migration"></a><span data-ttu-id="49509-499">專案移轉</span><span class="sxs-lookup"><span data-stu-id="49509-499">Project Migration</span></span>

<span data-ttu-id="49509-500">使用舊版 Quantum Development Kit 建立的專案仍可運作，只要您未更新其中使用的 NuGet 套件即可。</span><span class="sxs-lookup"><span data-stu-id="49509-500">Projects created using previous versions of Quantum Development Kit will still work, as long as you don't update the NuGet packages used in them.</span></span> <span data-ttu-id="49509-501">若要將現有的程式碼移轉至新版本，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="49509-501">To migrate existing code to the new version, perform the following steps:</span></span>
1. <span data-ttu-id="49509-502">使用正確類型的 Q# 專案範本，建立新的 .NET Core 專案 (應用程式、程式庫或測試專案)。</span><span class="sxs-lookup"><span data-stu-id="49509-502">Create a new .NET Core project using the right type of Q# project template (Application, Library or Test Project).</span></span>
2. <span data-ttu-id="49509-503">將舊專案中現有的 .qs 和 .cs/.fs 檔案複製到新專案 (使用 [新增] > [現有項目])。</span><span class="sxs-lookup"><span data-stu-id="49509-503">Copy existing .qs and .cs/.fs files from the old project to the new project (using Add > Existing Item).</span></span> <span data-ttu-id="49509-504">請勿複製 AssemblyInfo.cs 檔案。</span><span class="sxs-lookup"><span data-stu-id="49509-504">Do not copy the AssemblyInfo.cs file.</span></span>
3. <span data-ttu-id="49509-505">建置並執行新的專案。</span><span class="sxs-lookup"><span data-stu-id="49509-505">Build and run the new project.</span></span>

<span data-ttu-id="49509-506">請注意，命名空間 Microsoft.Quantum.Canon 中的作業 RandomWalkPhaseEstimation 已移至 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存放庫的命名空間 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 中。</span><span class="sxs-lookup"><span data-stu-id="49509-506">Please note that the operation RandomWalkPhaseEstimation from the namespace Microsoft.Quantum.Canon was moved into the namespace Microsoft.Research.Quantum.RandomWalkPhaseEstimation in the [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) repository.</span></span>

### <a name="known-issues"></a><span data-ttu-id="49509-507">已知問題</span><span class="sxs-lookup"><span data-stu-id="49509-507">Known Issues</span></span>

- <span data-ttu-id="49509-508">在以 Q# 撰寫的測試中，`dotnet test` 的 `--filter` 選項無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="49509-508">The `--filter` option to `dotnet test` does not work correctly for tests written in Q#.</span></span>
  <span data-ttu-id="49509-509">因此，無法在 Visual Studio Code 中執行個別的單元測試；建議您在命令列上使用 `dotnet test` 重新執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="49509-509">As a result, individual unit tests cannot be run in Visual Studio Code; we recommend using `dotnet test` at the command line to re-run all tests.</span></span>

## <a name="version-0118011707"></a><span data-ttu-id="49509-510">0\.1.1801.1707 版</span><span class="sxs-lookup"><span data-stu-id="49509-510">Version 0.1.1801.1707</span></span>

<span data-ttu-id="49509-511">*發行日期：2018 年 1 月 18 日*</span><span class="sxs-lookup"><span data-stu-id="49509-511">*Release date: January 18, 2018*</span></span>

<span data-ttu-id="49509-512">此版本修正了社群回報的某些問題。</span><span class="sxs-lookup"><span data-stu-id="49509-512">This release fixes some issues reported by the community.</span></span> <span data-ttu-id="49509-513">分別是：</span><span class="sxs-lookup"><span data-stu-id="49509-513">Namely:</span></span>

- <span data-ttu-id="49509-514">模擬器現已可與早期不具 AVX 功能的 CPU 搭配運作。</span><span class="sxs-lookup"><span data-stu-id="49509-514">The simulator now works with early non-AVX-enabled CPUs.</span></span>
- <span data-ttu-id="49509-515">區域十進位設定不會導致 Q# 剖析器失敗。</span><span class="sxs-lookup"><span data-stu-id="49509-515">Regional decimal settings will not cause the Q# parser to fail.</span></span>
- <span data-ttu-id="49509-516">`SignD` 基本作業現在會傳回 `Int`，而不是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="49509-516">`SignD` primitive operation now returns `Int` rather than `Double`.</span></span>


## <a name="version-011712901"></a><span data-ttu-id="49509-517">0\.1.1712.901 版</span><span class="sxs-lookup"><span data-stu-id="49509-517">Version 0.1.1712.901</span></span>

<span data-ttu-id="49509-518">*發行日期：2017 年 12 月 11 日*</span><span class="sxs-lookup"><span data-stu-id="49509-518">*Release date: December 11, 2017*</span></span>

### <a name="known-issues"></a><span data-ttu-id="49509-519">已知問題</span><span class="sxs-lookup"><span data-stu-id="49509-519">Known Issues</span></span>

#### <a name="hardware-and-software-requirements"></a><span data-ttu-id="49509-520">硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="49509-520">Hardware and Software Requirements</span></span>

- <span data-ttu-id="49509-521">Quantum Development Kit 隨附的模擬器需要 Microsoft Windows 的 64 位元安裝才能執行。</span><span class="sxs-lookup"><span data-stu-id="49509-521">The simulator included with the Quantum Development Kit requires a 64-bit installation of Microsoft Windows to run.</span></span>
- <span data-ttu-id="49509-522">與 Quantum Development Kit 一起安裝的 Microsoft 量子模擬器會使用 Advance Vector Extensions (AVX)，且需要具有 AVX 功能的 CPU。</span><span class="sxs-lookup"><span data-stu-id="49509-522">Microsoft's quantum simulator, installed with the Quantum Development Kit, utilizes Advanced Vector Extensions (AVX), and requires an AVX-enabled CPU.</span></span> <span data-ttu-id="49509-523">2011 年第 1 季推出的 Intel 處理器 (Sandy Bridge) 或更新版本可支援 AVX。</span><span class="sxs-lookup"><span data-stu-id="49509-523">Intel processors shipped in Q1 2011 (Sandy Bridge) or later support AVX.</span></span> <span data-ttu-id="49509-524">我們正在評估對舊型 CPU 的支援，後續可能會發佈相關詳情。</span><span class="sxs-lookup"><span data-stu-id="49509-524">We are evaluating support for earlier CPUs and may announce details at a later time.</span></span>

#### <a name="project-creation"></a><span data-ttu-id="49509-525">專案建立</span><span class="sxs-lookup"><span data-stu-id="49509-525">Project Creation</span></span>

- <span data-ttu-id="49509-526">建立將使用 Q# 的解決方案 (.sln) 時，解決方案必須比其中的每個專案 (.csproj) 高一個目錄。</span><span class="sxs-lookup"><span data-stu-id="49509-526">When creating a solution (.sln) that will use Q#, the solution must be one directory higher than each project (.csproj) in the solution.</span></span> <span data-ttu-id="49509-527">在建立新的解決方案時，只要確實核取 [新增專案] 對話方塊上的 [建立解決方案的目錄] 核取方塊，即可符合此條件。</span><span class="sxs-lookup"><span data-stu-id="49509-527">When creating a new solution, this can be accomplished by making sure that the "Create directory for solution" checkbox on the "New Project" dialog box is checked.</span></span> <span data-ttu-id="49509-528">若未執行此動作，則必須手動安裝 Quantum Development Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="49509-528">If this is not done, the Quantum Development Kit NuGet packages will need to be installed manually.</span></span>

#### <a name="q"></a><span data-ttu-id="49509-529">Q#</span><span class="sxs-lookup"><span data-stu-id="49509-529">Q#</span></span>

- <span data-ttu-id="49509-530">Intellisense 不會針對 Q# 程式碼顯示適當的錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-530">Intellisense does not display proper errors for Q# code.</span></span> <span data-ttu-id="49509-531">請確實在 Visual Studio 錯誤清單中顯示建置錯誤，以查看正確的 Q# 錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-531">Make sure that you are displaying Build errors in the Visual Studio Error List to see correct Q# errors.</span></span> <span data-ttu-id="49509-532">另請注意，必須在您完成建置後，才會顯示 Q# 錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-532">Also note that Q# errors will not show up until after you've done a build.</span></span>
- <span data-ttu-id="49509-533">在部分應用程式中使用可變動陣列可能會導致非預期的行為。</span><span class="sxs-lookup"><span data-stu-id="49509-533">Using a mutable array in a partial application may lead to unexpected behavior.</span></span>
- <span data-ttu-id="49509-534">將不可變陣列繫結至可變動陣列 (讓 a = b，其中 b 是可變動陣列)，可能會導致非預期的行為。</span><span class="sxs-lookup"><span data-stu-id="49509-534">Binding an immutable array to a mutable array (let a = b, where b is a mutable array) may lead to unexpected behavior.</span></span>
- <span data-ttu-id="49509-535">分析、程式碼涵蓋範圍和其他 VS 外掛程式不一定會正確計算 Q# 的行數和區塊數。</span><span class="sxs-lookup"><span data-stu-id="49509-535">Profiling, code coverage and other VS plugins may not always count Q# lines and blocks accurately.</span></span>
- <span data-ttu-id="49509-536">Q# 編譯器不會驗證差補字串。</span><span class="sxs-lookup"><span data-stu-id="49509-536">The Q# compiler does not validate interpolated strings.</span></span> <span data-ttu-id="49509-537">您可以藉由在 Q# 差補字串中拚寫錯誤的變數名稱或使用運算式，來建立 C# 編譯錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-537">It is possible to create C# compilation errors by misspelling variable names or using expressions in Q# interpolated strings.</span></span>

#### <a name="simulation"></a><span data-ttu-id="49509-538">模擬</span><span class="sxs-lookup"><span data-stu-id="49509-538">Simulation</span></span>

- <span data-ttu-id="49509-539">量子模擬器會使用 OpenMP 來平行處理所需的線性代數。</span><span class="sxs-lookup"><span data-stu-id="49509-539">The Quantum Simulator uses OpenMP to parallelize the linear algebra required.</span></span> <span data-ttu-id="49509-540">根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位元的程式常會執行緩慢，因為所需的協調會阻礙實際的工作。</span><span class="sxs-lookup"><span data-stu-id="49509-540">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="49509-541">將環境變數 OMP_NUM_THREADS 設定為較小的數值，即可修正此問題。</span><span class="sxs-lookup"><span data-stu-id="49509-541">This can be fixed by setting the environment variable OMP_NUM_THREADS to a small number.</span></span> <span data-ttu-id="49509-542">一個非常粗略的經驗法則是，1 個執行緒最多可用於 4 個量子位元，而其後的每個量子位元則應使用一個額外的執行緒，但這主要取決於您的演算法。</span><span class="sxs-lookup"><span data-stu-id="49509-542">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

#### <a name="debugging"></a><span data-ttu-id="49509-543">偵錯</span><span class="sxs-lookup"><span data-stu-id="49509-543">Debugging</span></span>

- <span data-ttu-id="49509-544">F11 (逐步執行) 在 Q# 程式碼中無法運作。</span><span class="sxs-lookup"><span data-stu-id="49509-544">F11 (step in) doesn't work in Q# code.</span></span>
- <span data-ttu-id="49509-545">在中斷點或單一步驟暫停時，Q# 程式碼中醒目提示的程式碼有時並不正確。</span><span class="sxs-lookup"><span data-stu-id="49509-545">Code highlighting in Q# code at a breakpoint or single-step pause is sometimes inaccurate.</span></span> <span data-ttu-id="49509-546">醒目提示的程式碼行是正確的，但有時候，醒目提示的開頭和結尾會位於行中不正確的資料行上。</span><span class="sxs-lookup"><span data-stu-id="49509-546">The correct line will be highlighted, but sometimes the highlight will start and end at incorrect columns on the line.</span></span>

#### <a name="testing"></a><span data-ttu-id="49509-547">測試</span><span class="sxs-lookup"><span data-stu-id="49509-547">Testing</span></span>

- <span data-ttu-id="49509-548">測試必須在 64 位元模式中執行。</span><span class="sxs-lookup"><span data-stu-id="49509-548">Tests must be executed in 64-bit mode.</span></span> <span data-ttu-id="49509-549">如果您的測試失敗並出現 BadImageFormatException，請移至 [測試] 功能表，然後選取 [測試設定] > [預設處理器架構] > [X64]。</span><span class="sxs-lookup"><span data-stu-id="49509-549">If your tests are failing with a BadImageFormatException, go to the Test menu and select Test Settings > Default Processor Architecture > X64.</span></span>
- <span data-ttu-id="49509-550">有些測試的執行會非常耗時 (最多可能需要 5 分鐘，視您的電腦而定)。</span><span class="sxs-lookup"><span data-stu-id="49509-550">Some tests take a long time (possibly as much as 5 minutes depending on your computer) to run.</span></span> <span data-ttu-id="49509-551">這是正常的，因為有些測試會使用超過 20 個量子位元；我們最大的測試目前以 23 個量子位元執行。</span><span class="sxs-lookup"><span data-stu-id="49509-551">This is normal, as some use over twenty qubits; our largest test currently runs on 23 qubits.</span></span>

#### <a name="samples"></a><span data-ttu-id="49509-552">範例</span><span class="sxs-lookup"><span data-stu-id="49509-552">Samples</span></span>

- <span data-ttu-id="49509-553">在某些電腦上，某些小型樣本可能會執行緩慢，除非環境變數 OMP_NUM_THREADS 設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="49509-553">On some machines, some small samples may run slowly unless the environment variable OMP_NUM_THREADS is set to "1".</span></span> <span data-ttu-id="49509-554">另請參閱「模擬」下的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="49509-554">See also the release note under "Simulation".</span></span>

#### <a name="libraries"></a><span data-ttu-id="49509-555">程式庫</span><span class="sxs-lookup"><span data-stu-id="49509-555">Libraries</span></span>

- <span data-ttu-id="49509-556">既有的隱含假設是，傳至作業中不同引數的量子位元是相異的。</span><span class="sxs-lookup"><span data-stu-id="49509-556">There is an implicit assumption that the qubits passed to an operation in different arguments are all distinct.</span></span> <span data-ttu-id="49509-557">例如，所有的程式庫作業 (以及所有模擬器) 都會假設傳至受控 NOT 的兩個量子位元是不同的。</span><span class="sxs-lookup"><span data-stu-id="49509-557">For instance, all of the library operations (and all of the simulators) assume that the two qubits passed to a controlled NOT are different qubits.</span></span> <span data-ttu-id="49509-558">若違反此假設，可能會導致無法預期的錯誤。</span><span class="sxs-lookup"><span data-stu-id="49509-558">Violating this assumption may lead to unpredictable unexpected.</span></span> <span data-ttu-id="49509-559">您可以使用量子電腦追蹤模擬器來測試這種情況。</span><span class="sxs-lookup"><span data-stu-id="49509-559">It is possible to test for this using the quantum computer tracer simulator.</span></span>
- <span data-ttu-id="49509-560">Microsoft.Quantum.Bind 函式不一定在各種情況下都會如預期運作。</span><span class="sxs-lookup"><span data-stu-id="49509-560">The Microsoft.Quantum.Bind function may not act as expected in all cases.</span></span>
- <span data-ttu-id="49509-561">在 Microsoft.Quantum.Extensions.Math 命名空間中，SignD 函式會傳回雙精度浮點數 (而非整數)，但基礎 System.Math.Sign 函式則一律會傳回整數。</span><span class="sxs-lookup"><span data-stu-id="49509-561">In the Microsoft.Quantum.Extensions.Math namespace, the SignD function returns a Double rather than an Int, although the underlying System.Math.Sign function always returns an integer.</span></span> <span data-ttu-id="49509-562">您可以將結果與 1.0、-1.0 和 0.0 進行比較，因為這些雙精度浮點數具有相同的二進位表示法。</span><span class="sxs-lookup"><span data-stu-id="49509-562">It is safe to compare the result against 1.0, -1.0, and 0.0, since these doubles all have exact binary representations.</span></span>
