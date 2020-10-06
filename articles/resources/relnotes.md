---
title: Quantum 開發套件版本資訊
description: 深入了解 Microsoft Quantum Development Kit 預覽版的最新更新。
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 27038a86dc4854c397458d95529aca463d493fd6
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771324"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a><span data-ttu-id="b5f7c-103">Microsoft Quantum Development Kit 版本資訊</span><span class="sxs-lookup"><span data-stu-id="b5f7c-103">Microsoft Quantum Development Kit Release Notes</span></span>

<span data-ttu-id="b5f7c-104">本文包含各個 Quantum Development Kit 版本的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-104">This article contains information on each Quantum Development Kit release.</span></span>

<span data-ttu-id="b5f7c-105">如需安裝指示，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-105">For installation instructions, please refer to the [install guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b5f7c-106">如需更新指示，請參閱[更新指南](xref:microsoft.quantum.update)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-106">For update instructions, please refer to the [update guide](xref:microsoft.quantum.update).</span></span>

## <a name="version-01220100504"></a><span data-ttu-id="b5f7c-107">版本0.12.20100504</span><span class="sxs-lookup"><span data-stu-id="b5f7c-107">Version 0.12.20100504</span></span>

<span data-ttu-id="b5f7c-108">*發行日期：2020年10月5日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-108">*Release date: October 5th, 2020*</span></span>

<span data-ttu-id="b5f7c-109">此版本修正了影響筆記本載入的錯誤 Q# (請參閱 [iqsharp # 331](https://github.com/microsoft/iqsharp/pull/331)) 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-109">This release fixes a bug affecting load of Q# notebooks (see [iqsharp#331](https://github.com/microsoft/iqsharp/pull/331)).</span></span>

## <a name="version-01220092803"></a><span data-ttu-id="b5f7c-110">版本0.12.20092803</span><span class="sxs-lookup"><span data-stu-id="b5f7c-110">Version 0.12.20092803</span></span>

<span data-ttu-id="b5f7c-111">*發行日期：2020年9月29日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-111">*Release date: September 29th, 2020*</span></span>

<span data-ttu-id="b5f7c-112">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-112">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-113">[量子中繼標記法](https://github.com/microsoft/qsharp-language/tree/main/Specifications/QIR#quantum-intermediate-representation-qir)的公告和草稿規格 (QIR) 預定作為跨不同前端和後端的通用格式。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-113">Announcement and draft specification of [Quantum Intermediate Representation (QIR)](https://github.com/microsoft/qsharp-language/tree/main/Specifications/QIR#quantum-intermediate-representation-qir) intended as a common format across different front- and back-ends.</span></span> <span data-ttu-id="b5f7c-114">另請參閱我們在 QIR 上的 [blog 文章](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir) 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-114">See also our [blog post](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir) on QIR.</span></span>
- <span data-ttu-id="b5f7c-115">推出新的[ Q# 語言](https://github.com/microsoft/qsharp-language)存放庫，其中也包含完整的[ Q# 檔](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-115">Launch of our new [Q# language repo](https://github.com/microsoft/qsharp-language) containing also the full [Q# documentation](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language).</span></span>
- <span data-ttu-id="b5f7c-116">針對涉及大量量子位之程式的 QuantumSimulator 效能改進：更好的應用程式閘道融合決策;改進 Linux 系統上的平行處理;新增閘道執行的智慧型排程;bug 修正。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-116">Performance improvements for QuantumSimulator for programs involving a large number of qubits: better application of gate fusion decisions; improved parallelization on Linux system; added intelligent scheduling of gate execution; bug fixes.</span></span>
- <span data-ttu-id="b5f7c-117">Visual Studio 中的檔案現在支援 IntelliSense 功能 Q# ，而且即使沒有專案檔也 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-117">IntelliSense features are now supported for Q# files in Visual Studio and Visual Studio Code even without a project file.</span></span>
- <span data-ttu-id="b5f7c-118">各種 Q# /Python 互通性的增強功能和 bug 修正，包括更好的 NumPy 資料類型支援。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-118">Various Q#/Python interoperability improvements and bug fixes, including better support for NumPy data types.</span></span>
- <span data-ttu-id="b5f7c-119">Microsoft. array 命名空間的增強功能 (請參閱 [microsoft/QuantumLibraries # 313](https://github.com/microsoft/QuantumLibraries/issues/313)) 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-119">Improvements to the Microsoft.Quantum.Arrays namespace (see [microsoft/QuantumLibraries#313](https://github.com/microsoft/QuantumLibraries/issues/313)).</span></span>
- <span data-ttu-id="b5f7c-120">加入新的 [重複使用-Success 範例](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/repeat-until-success) ，此範例只會使用兩個量子位。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-120">Added a new [Repeat-Until-Success sample](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/repeat-until-success) that uses only two qubits.</span></span>

<span data-ttu-id="b5f7c-121">自上次發行之後，我們的每個開放原始碼存放庫中的預設分支已重新命名為 `main` 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-121">Since the last release, the default branch in each of our open source repositories has been renamed to `main`.</span></span>

<span data-ttu-id="b5f7c-122">請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)的封閉式 pr 完整清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-122">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24).</span></span>

## <a name="version-01220082513"></a><span data-ttu-id="b5f7c-123">版本0.12.20082513</span><span class="sxs-lookup"><span data-stu-id="b5f7c-123">Version 0.12.20082513</span></span>

<span data-ttu-id="b5f7c-124">*發行日期：2020年8月25日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-124">*Release date: August 25th, 2020*</span></span>

<span data-ttu-id="b5f7c-125">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-125">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-126">新的 [Microsoft 量子命名空間](xref:microsoft.quantum.random)，提供更方便的方式，從程式內取樣隨機值 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-126">New [Microsoft.Quantum.Random namespace](xref:microsoft.quantum.random), providing a more convenient way to sample random values from within Q# programs.</span></span> <span data-ttu-id="b5f7c-127"> ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311)， [qsharp-runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328)) </span><span class="sxs-lookup"><span data-stu-id="b5f7c-127">([QuantumLibraries#311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-runtime#328](https://github.com/microsoft/qsharp-runtime/pull/328))</span></span>
- <span data-ttu-id="b5f7c-128">改進了[具有新作業的 `DumpOperation` ](xref:microsoft.quantum.diagnostics.dumpoperation) [Microsoft 量子. 診斷命名空間](xref:microsoft.quantum.diagnostics)，以及限制量子位配置和 oracle 呼叫的新作業。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-128">Improved [Microsoft.Quantum.Diagnostics namespace](xref:microsoft.quantum.diagnostics) with new [`DumpOperation` operation](xref:microsoft.quantum.diagnostics.dumpoperation), and new operations for restricting qubit allocation and oracle calls.</span></span> <span data-ttu-id="b5f7c-129"> ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302)) </span><span class="sxs-lookup"><span data-stu-id="b5f7c-129">([QuantumLibraries#302](https://github.com/microsoft/QuantumLibraries/pull/302))</span></span>
- <span data-ttu-id="b5f7c-130">Python 中的新[ `%project` 魔術命令](xref:microsoft.quantum.iqsharp.magic-ref.project) Q# 和 Python 中的[ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) ，可支援對 Q# 目前工作區資料夾以外專案的參考。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-130">New [`%project` magic command](xref:microsoft.quantum.iqsharp.magic-ref.project) in IQ# and [`qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) in Python to support references to Q# projects outside the current workspace folder.</span></span> <span data-ttu-id="b5f7c-131">如需這項功能目前的限制，請參閱 [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-131">See [iqsharp#277](https://github.com/microsoft/iqsharp/issues/277) for the current limitations of this feature.</span></span> 
- <span data-ttu-id="b5f7c-132">支援自動載入 `.csproj` /Python 主機的檔案 Q# ，可讓您在初始化時載入外部專案或封裝參考。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-132">Support for automatically loading `.csproj` files for IQ#/Python hosts, which allows external project or package references to be loaded at initialization time.</span></span> <span data-ttu-id="b5f7c-133">如需詳細資訊，請參閱使用[ Q# Python 和 Jupyter 筆記本](xref:microsoft.quantum.guide.host-programs)的指南。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-133">See the guide for using [Q# with Python and Jupyter Notebooks](xref:microsoft.quantum.guide.host-programs) for more details.</span></span>
- <span data-ttu-id="b5f7c-134">新增了 ErrorCorrection 的症狀範例。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-134">Added ErrorCorrection.Syndrome sample.</span></span>
- <span data-ttu-id="b5f7c-135">已將可調式的結合新增至 SimpleIsing。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-135">Added tunable coupling to SimpleIsing.</span></span>
- <span data-ttu-id="b5f7c-136">已更新 HiddenShift 範例。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-136">Updated HiddenShift sample.</span></span>
- <span data-ttu-id="b5f7c-137">已新增使用格羅弗的演算法來解決 Sudoku 的範例 (外部投稿) </span><span class="sxs-lookup"><span data-stu-id="b5f7c-137">Added sample for solving Sudoku with Grover's algorithm (external contribution)</span></span>
- <span data-ttu-id="b5f7c-138">一般錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-138">General bug fixes.</span></span>

<span data-ttu-id="b5f7c-139">請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-139">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01220072031"></a><span data-ttu-id="b5f7c-140">版本0.12.20072031</span><span class="sxs-lookup"><span data-stu-id="b5f7c-140">Version 0.12.20072031</span></span>

<span data-ttu-id="b5f7c-141">*發行日期：2020年7月21日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-141">*Release date: July 21st, 2020*</span></span>

<span data-ttu-id="b5f7c-142">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-142">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-143">您現在可以在執行所有未來的資料格時，在筆記本中開啟的命名空間 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-143">Opened namespaces in Q# notebooks are now available when running all future cells.</span></span> <span data-ttu-id="b5f7c-144">例如，您可以在筆記本頂端的資料格中開啟一次命名空間，而不需要在每個程式碼資料格中開啟相關的命名空間。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-144">This allows, for example, namespaces to be opened once in a cell at the top of the notebook, rather than needing to open relevant namespaces in each code cell.</span></span> <span data-ttu-id="b5f7c-145">新的 `%lsopen` 魔術命令會顯示目前開啟的命名空間清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-145">A new `%lsopen` magic command displays the list of currently-opened namespaces.</span></span>

<span data-ttu-id="b5f7c-146">請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-146">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01220070124"></a><span data-ttu-id="b5f7c-147">版本0.12.20070124</span><span class="sxs-lookup"><span data-stu-id="b5f7c-147">Version 0.12.20070124</span></span>

<span data-ttu-id="b5f7c-148">*發行日期：2020年7月2日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-148">*Release date: July 2nd, 2020*</span></span>

<span data-ttu-id="b5f7c-149">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-149">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-150">`qdk-chem`用於轉換舊版電子結構問題序列化格式的新工具 (例如： FCIDUMP) 至[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-150">New `qdk-chem` tool for converting legacy electronic structure problem serialization formats (e.g.: FCIDUMP) to [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)</span></span>
- <span data-ttu-id="b5f7c-151">命名空間中的新函 [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) 式和作業時使用轉換和分解型合成演算法來套用傳統 oracle。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-151">New functions and operations in the [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) namespace for coherently applying classical oracles using transformation- and decomposition-based synthesis algorithms.</span></span>
- <span data-ttu-id="b5f7c-152">我 Q# 現在允許 `%simulate` 、 `%estimate` 和其他魔術命令的引數。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-152">IQ# now allows arguments to the `%simulate`, `%estimate`, and other magic commands.</span></span> <span data-ttu-id="b5f7c-153">如需詳細資訊，請參閱[ `%simulate` 魔術命令參考](xref:microsoft.quantum.iqsharp.magic-ref.simulate)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-153">See the [`%simulate` magic command reference](xref:microsoft.quantum.iqsharp.magic-ref.simulate) for more details.</span></span>
- <span data-ttu-id="b5f7c-154">I 中的新階段顯示選項 Q# 。如需詳細資訊，請參閱[ `%config` 魔術命令參考](xref:microsoft.quantum.iqsharp.magic-ref.config)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-154">New phase display options in IQ#. See the [`%config` magic command reference](xref:microsoft.quantum.iqsharp.magic-ref.config) for more details.</span></span>
- <span data-ttu-id="b5f7c-155">我 Q# 和 `qsharp` python 套件現在透過 conda 套件提供 ([qsharp](https://anaconda.org/quantum-engineering/qsharp) 和 [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) ，以簡化 Q# conda 環境中 Jupyter 和 Python 功能的本機安裝。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-155">IQ# and the `qsharp` Python package are now provided via conda packages ([qsharp](https://anaconda.org/quantum-engineering/qsharp) and [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) to simplify local installation of Q# Jupyter and Python functionality to a conda environment.</span></span> <span data-ttu-id="b5f7c-156">如需詳細資訊，請參閱[ Q# Jupyter 筆記本](xref:microsoft.quantum.install.jupyter)和[ Q# Python](xref:microsoft.quantum.install.python)安裝指南。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-156">See the [Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) and [Q# with Python](xref:microsoft.quantum.install.python) installation guides for more details.</span></span>
- <span data-ttu-id="b5f7c-157">使用模擬器時，量子位在發行時不再需要處於 | 0 ⟩狀態，但如果在釋放前立即測量，則可以自動重設。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-157">When using the simulator, qubits no longer need to be in the |0⟩ state upon release, but can be automatically reset if they were measured immediately before releasing.</span></span>
- <span data-ttu-id="b5f7c-158">更新可讓使用者更輕鬆地取用 Q# 具有不同 QDK 版本的程式庫套件，但只需要符合主要 & 次要版本號碼，而不是完全相同的版本</span><span class="sxs-lookup"><span data-stu-id="b5f7c-158">Updates to make it easier for IQ# users to consume library packages with different QDK versions, requiring only major & minor version numbers match rather than the exact same version</span></span>
- <span data-ttu-id="b5f7c-159">已移除被取代的 `Microsoft.Quantum.Primitive.*` 命名空間</span><span class="sxs-lookup"><span data-stu-id="b5f7c-159">Removed deprecated `Microsoft.Quantum.Primitive.*` namespace</span></span>
- <span data-ttu-id="b5f7c-160">移動的作業：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-160">Moved operations:</span></span>
  - <span data-ttu-id="b5f7c-161">`Microsoft.Quantum.Intrinsic.Assert` 現在為 `Microsoft.Quantum.Diagnostics.AssertMeasurement`</span><span class="sxs-lookup"><span data-stu-id="b5f7c-161">`Microsoft.Quantum.Intrinsic.Assert` is now `Microsoft.Quantum.Diagnostics.AssertMeasurement`</span></span>
  - <span data-ttu-id="b5f7c-162">`Microsoft.Quantum.Intrinsic.AssertProb` 現在為 `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`</span><span class="sxs-lookup"><span data-stu-id="b5f7c-162">`Microsoft.Quantum.Intrinsic.AssertProb` is now `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`</span></span>
- <span data-ttu-id="b5f7c-163">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="b5f7c-163">Bug fixes</span></span> 

<span data-ttu-id="b5f7c-164">請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-164">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0112006403"></a><span data-ttu-id="b5f7c-165">版本 0.11.2006.403</span><span class="sxs-lookup"><span data-stu-id="b5f7c-165">Version 0.11.2006.403</span></span>

<span data-ttu-id="b5f7c-166">*發行日期：2020 年 6 月 4 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-166">*Release date: June 4th, 2020*</span></span>

<span data-ttu-id="b5f7c-167">此版本修正了影響專案編譯的 bug Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-167">This release fixes a bug affecting compilation of Q# projects.</span></span>

## <a name="version-0112006207"></a><span data-ttu-id="b5f7c-168">版本 0.11.2006.207</span><span class="sxs-lookup"><span data-stu-id="b5f7c-168">Version 0.11.2006.207</span></span>

<span data-ttu-id="b5f7c-169">*發行日期：2020 年 6 月 3 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-169">*Release date: June 3rd, 2020*</span></span>

<span data-ttu-id="b5f7c-170">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-170">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-171">Q#當進入點出現時，筆記本和 Python 主機程式將不再失敗 Q#</span><span class="sxs-lookup"><span data-stu-id="b5f7c-171">Q# notebooks and Python host programs will no longer fail when a Q# entry point is present</span></span>
- <span data-ttu-id="b5f7c-172">更新[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)以使用存取修飾詞</span><span class="sxs-lookup"><span data-stu-id="b5f7c-172">Updates to [Standard library](xref:microsoft.quantum.libraries.standard.intro) to use access modifiers</span></span>
- <span data-ttu-id="b5f7c-173">編譯器現在允許在內建重寫步驟之間進行重寫步驟的外掛程式</span><span class="sxs-lookup"><span data-stu-id="b5f7c-173">Compiler now allows plug-in of rewrite steps between built-in rewrite steps</span></span>
- <span data-ttu-id="b5f7c-174">已遵循我們的 [API 原則](xref:microsoft.quantum.contributing.api-design)中所述的排程，移除數個已遭取代的函式和作業。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-174">Several deprecated functions and operations have been removed following the schedule described in our [API principles](xref:microsoft.quantum.contributing.api-design).</span></span> <span data-ttu-id="b5f7c-175">Q# 在版本0.11.2004.2825 中建立沒有警告的程式和程式庫將繼續以未修改的方式運作。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-175">Q# programs and libraries that build without warnings in version 0.11.2004.2825 will continue to work unmodified.</span></span>

<span data-ttu-id="b5f7c-176">請參閱連結[庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[運行](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)時間、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)、 [I Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed)和[Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)的封閉式 pr 完整清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-176">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [IQ#](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

> [!NOTE]
> <span data-ttu-id="b5f7c-177">此版本包含影響專案編譯的錯誤（bug） Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-177">This version contains a bug affecting compilation of Q# projects.</span></span> <span data-ttu-id="b5f7c-178">我們建議您升級至較新的版本。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-178">We recommend upgrading to a newer release.</span></span>

## <a name="version-01120042825"></a><span data-ttu-id="b5f7c-179">0\.11.2004.2825 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-179">Version 0.11.2004.2825</span></span>

<span data-ttu-id="b5f7c-180">*發行日期：2020 年 4 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-180">*Release date: April 30th, 2020*</span></span>

<span data-ttu-id="b5f7c-181">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-181">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-182">新的 Q# 應用程式支援，不再需要 c # 或 Python 主機檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-182">New support for Q# applications, which no longer require a C# or Python host file.</span></span> <span data-ttu-id="b5f7c-183">如需開始使用應用程式的詳細資訊 Q# ，請參閱 [這裡](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-183">For more information on getting started with Q# applications, see [here](xref:microsoft.quantum.install.standalone).</span></span>
- <span data-ttu-id="b5f7c-184">已更新的量子隨機數字產生器快速入門，不再需要 C# 或 Python 主機檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-184">Updated quantum random number generator quickstart to no longer require a C# or Python host file.</span></span> <span data-ttu-id="b5f7c-185">請參閱更新的[快速入門](xref:microsoft.quantum.quickstarts.qrng)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-185">See the updated  [Quickstart](xref:microsoft.quantum.quickstarts.qrng)</span></span>
- <span data-ttu-id="b5f7c-186">Docker 映射的效能改進 Q#</span><span class="sxs-lookup"><span data-stu-id="b5f7c-186">Performance improvements to IQ# Docker images</span></span>

> [!NOTE]
> <span data-ttu-id="b5f7c-187">Q#[`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint)目前無法從 Python 或 .net 主機程式呼叫使用新屬性的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-187">Q# applications using the new [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) attribute currently cannot be called from Python or .NET host programs.</span></span>
> <span data-ttu-id="b5f7c-188">如需詳細資訊，請參閱 [Python](xref:microsoft.quantum.install.python) 和 [.NET 互通性](xref:microsoft.quantum.install.cs) 指南。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-188">See the [Python](xref:microsoft.quantum.install.python) and [.NET interoperability](xref:microsoft.quantum.install.cs) guides for more information.</span></span>

## <a name="version-01120033107"></a><span data-ttu-id="b5f7c-189">0\.11.2003.3107 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-189">Version 0.11.2003.3107</span></span>

<span data-ttu-id="b5f7c-190">*發行日期：2020 年 3 月 31 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-190">*Release date: March 31, 2020*</span></span>

<span data-ttu-id="b5f7c-191">此版本包含版本 0.11.2003.2506 的次要錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-191">This release contains minor bugfixes for version 0.11.2003.2506.</span></span>

## <a name="version-01120032506"></a><span data-ttu-id="b5f7c-192">0\.11.2003.2506 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-192">Version 0.11.2003.2506</span></span>

<span data-ttu-id="b5f7c-193">*發行日期：2020 年 3 月 26 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-193">*Release date: March 26th, 2020*</span></span>

<span data-ttu-id="b5f7c-194">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-194">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-195">的新支援存取修飾詞 Q# ，如需詳細資訊，請參閱檔案 [結構](xref:microsoft.quantum.guide.filestructure)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-195">New support for access modifiers in Q#, for more information see [File Structures](xref:microsoft.quantum.guide.filestructure)</span></span>
- <span data-ttu-id="b5f7c-196">已更新為 .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="b5f7c-196">Updated to .NET Core SDK 3.1</span></span>

<span data-ttu-id="b5f7c-197">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-197">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020022610"></a><span data-ttu-id="b5f7c-198">0\.10.2002.2610 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-198">Version 0.10.2002.2610</span></span>

<span data-ttu-id="b5f7c-199">*發行日期：2020 年 2 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-199">*Release date: February 27th, 2020*</span></span>

<span data-ttu-id="b5f7c-200">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-200">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-201">新的量子機器學習程式庫。如需詳細資訊，請移至我們的 [QML 文件頁面](xref:microsoft.quantum.machine-learning.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-201">New Quantum Machine Learning library, for more information go to our [QML docs page](xref:microsoft.quantum.machine-learning.concepts.intro)</span></span>
- <span data-ttu-id="b5f7c-202">我的 Q# bug 修正，在載入 NuGet 套件時，最多可提升 10 20 倍的效能</span><span class="sxs-lookup"><span data-stu-id="b5f7c-202">IQ# bug fixes, resulting in up to a 10-20x performance increase when loading NuGet packages</span></span>

<span data-ttu-id="b5f7c-203">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-203">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01020012831"></a><span data-ttu-id="b5f7c-204">0\.10.2001.2831 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-204">Version 0.10.2001.2831</span></span>

<span data-ttu-id="b5f7c-205">*發行日期：2020 年 1 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-205">*Release date: January 29th, 2020*</span></span>

<span data-ttu-id="b5f7c-206">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-206">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-207">新的 Microsoft.Quantum.SDK NuGet 套件，將在建立新專案時取代 Microsoft.Quantum.Development.Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-207">New Microsoft.Quantum.SDK NuGet package which will replace Microsoft.Quantum.Development.Kit NuGet package when creating new projects.</span></span> <span data-ttu-id="b5f7c-208">現有專案將會繼續支援 Microsoft.Quantum.Development.Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-208">Microsoft.Quantum.Development.Kit NuGet package will continue to be supported for existing projects.</span></span> 
- <span data-ttu-id="b5f7c-209">支援 Q# 編譯器擴充功能（由新的套件 NuGet 提供）。如需詳細資訊，請參閱[Github 上的檔](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler)、[編譯器延伸模組範例](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions)和[ Q# 開發人員 Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-209">Support for Q# compiler extensions, enabled by the new Microsoft.Quantum.SDK NuGet packge, for more information see the [documentation on Github](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler), the [compiler extensions sample](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions) and the [Q# Dev Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)</span></span>
- <span data-ttu-id="b5f7c-210">新增 .NET Core 3.1 支援，強烈建議您安裝 3.1.100 版，因為使用舊版 .NET Core SDK 版本可能會造成問題</span><span class="sxs-lookup"><span data-stu-id="b5f7c-210">Added support for .NET Core 3.1, it is highly recommended to have version 3.1.100 installed since building with older .NET Core SDK versions may cause issues</span></span>
- <span data-ttu-id="b5f7c-211">在 Microsoft.Quantum.QsCompiler.Experimental 下提供新的編譯器轉換</span><span class="sxs-lookup"><span data-stu-id="b5f7c-211">New compiler transformations available under Microsoft.Quantum.QsCompiler.Experimental</span></span>
- <span data-ttu-id="b5f7c-212">以 HTML 格式公開輸出狀態向量的新功能Q#</span><span class="sxs-lookup"><span data-stu-id="b5f7c-212">New functionality to expose output state vectors as HTML in IQ#</span></span>
- <span data-ttu-id="b5f7c-213">已將 EstimateFrequencyA 支援新增至適用於 Hadamard 和 SWAP 測試的 Microsoft.Quantum.Characterization</span><span class="sxs-lookup"><span data-stu-id="b5f7c-213">Added support for EstimateFrequencyA to Microsoft.Quantum.Characterization for Hadamard and SWAP tests</span></span>
- <span data-ttu-id="b5f7c-214">AmplitudeAmplification 命名空間現在使用 Q# 樣式指南</span><span class="sxs-lookup"><span data-stu-id="b5f7c-214">AmplitudeAmplification namespace now uses Q# style guide</span></span>

<span data-ttu-id="b5f7c-215">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-215">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019120501"></a><span data-ttu-id="b5f7c-216">版本 0.10.1912.0501</span><span class="sxs-lookup"><span data-stu-id="b5f7c-216">Version 0.10.1912.0501</span></span>

<span data-ttu-id="b5f7c-217">*發行日期：2019 年 12 月 5 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-217">*Release date: December 5th, 2019*</span></span>

<span data-ttu-id="b5f7c-218">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-218">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-219">單元測試的新測試屬性 Q# ，請參閱[此處的](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test)更新 API 檔和更新的測試[here](xref:microsoft.quantum.guide.testingdebugging) & 偵錯工具指南</span><span class="sxs-lookup"><span data-stu-id="b5f7c-219">New Test attribute for Q# unit testing, see updated API documentation [here](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) and updated testing & debugging guide [here](xref:microsoft.quantum.guide.testingdebugging)</span></span>
- <span data-ttu-id="b5f7c-220">在程式執行錯誤的情況下新增堆疊追蹤 Q#</span><span class="sxs-lookup"><span data-stu-id="b5f7c-220">Added stack trace in the case of a Q# program run error</span></span>
- <span data-ttu-id="b5f7c-221">由於 [OmniSharp C# Visual Studio Code 延伸模組](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)更新，支援在 Visual Studio Code 中的中斷點</span><span class="sxs-lookup"><span data-stu-id="b5f7c-221">Support for breakpoints in Visual Studio Code due to an update in the [OmniSharp C# Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span></span>

<span data-ttu-id="b5f7c-222">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-222">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-01019111607"></a><span data-ttu-id="b5f7c-223">版本 0.10.1911.1607</span><span class="sxs-lookup"><span data-stu-id="b5f7c-223">Version 0.10.1911.1607</span></span>

<span data-ttu-id="b5f7c-224">*發行日期：2019 年 11 月 17 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-224">*Release date: November 17th, 2019*</span></span>

<span data-ttu-id="b5f7c-225">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-225">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-226">[Quantum Katas](https://github.com/Microsoft/QuantumKatas) 和 Jupyter 筆記本的效能修正</span><span class="sxs-lookup"><span data-stu-id="b5f7c-226">Performance fix for [Quantum Katas](https://github.com/Microsoft/QuantumKatas) and Jupyter notebooks</span></span>

<span data-ttu-id="b5f7c-227">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-227">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  


## <a name="version-0101911307"></a><span data-ttu-id="b5f7c-228">版本 0.10.1911.307</span><span class="sxs-lookup"><span data-stu-id="b5f7c-228">Version 0.10.1911.307</span></span>

<span data-ttu-id="b5f7c-229">*發行日期：2019 年 11 月 1 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-229">*Release date: November 1st, 2019*</span></span>

<span data-ttu-id="b5f7c-230">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-230">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-231">Visual Studio Code & Visual Studio 擴充功能的更新，可將語言伺服器部署為獨立的可執行檔，以消除 .NET Core SDK 版本相依性</span><span class="sxs-lookup"><span data-stu-id="b5f7c-231">Updates to Visual Studio Code & Visual Studio extensions to deploy language server as a self-contained executable file, eliminating the .NET Core SDK version dependency</span></span>  
- <span data-ttu-id="b5f7c-232">移轉到 .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b5f7c-232">Migration to .NET Core 3.0</span></span>
- <span data-ttu-id="b5f7c-233">重大更新 - Microsoft.Quantum.Simulation.Core.IOperationFactory 引進新的 `Fail` 方法</span><span class="sxs-lookup"><span data-stu-id="b5f7c-233">Breaking change to Microsoft.Quantum.Simulation.Core.IOperationFactory with introduction of new `Fail` method.</span></span> <span data-ttu-id="b5f7c-234">此方法只會影響未擴充 SimulatorBase 的自訂模擬器。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-234">It affects only custom simulators that do not extend SimulatorBase.</span></span> <span data-ttu-id="b5f7c-235">如需詳細資料，請[檢閱 GitHub 中的提取要求](https://github.com/microsoft/qsharp-runtime/pull/59)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-235">For more details, [view the pull request on GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).</span></span>
- <span data-ttu-id="b5f7c-236">受取代屬性的新增支援</span><span class="sxs-lookup"><span data-stu-id="b5f7c-236">New support for Deprecated attributes</span></span>

<span data-ttu-id="b5f7c-237">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-237">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-0919093002"></a><span data-ttu-id="b5f7c-238">0\.9.1909.3002 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-238">Version 0.9.1909.3002</span></span>

<span data-ttu-id="b5f7c-239">*發行日期：2019 年 9 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-239">*Release date: September 30th, 2019*</span></span>

<span data-ttu-id="b5f7c-240">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-240">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-241">Q#Visual Studio 2019 (16.3 版中的程式碼自動完成的新支援 &) & Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b5f7c-241">New support for Q# code completion in Visual Studio 2019 (versions 16.3 & later) & Visual Studio Code</span></span>
- <span data-ttu-id="b5f7c-242">量子 adder 的新 [Quantum Kata](https://github.com/Microsoft/QuantumKatas)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-242">New [Quantum Kata](https://github.com/Microsoft/QuantumKatas) for quantum adders</span></span>

<span data-ttu-id="b5f7c-243">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-243">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-09-packagereference-0919082902"></a><span data-ttu-id="b5f7c-244">0\.9 版 (*PackageReference 0.9.1908.2902*)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-244">Version 0.9 (*PackageReference 0.9.1908.2902*)</span></span>

<span data-ttu-id="b5f7c-245">*發行日期：2019 年 8 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-245">*Release date: August 29th, 2019*</span></span>

<span data-ttu-id="b5f7c-246">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-246">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-247">中 [結合語句](xref:microsoft.quantum.guide.operationsfunctions#conjugations) 的新支援 Q#</span><span class="sxs-lookup"><span data-stu-id="b5f7c-247">New support for [conjugation statements](xref:microsoft.quantum.guide.operationsfunctions#conjugations) in Q#</span></span>
- <span data-ttu-id="b5f7c-248">編譯器中的新程式碼動作 (例如：「取代為」、「新增文件」)，以及簡單的陣列項目更新</span><span class="sxs-lookup"><span data-stu-id="b5f7c-248">New code actions in the compiler, such as: "replace with", "add documentation", and simple array item update</span></span>
- <span data-ttu-id="b5f7c-249">在 Visual Studio Code 延伸模組中新增了安裝範本和新的專案命令</span><span class="sxs-lookup"><span data-stu-id="b5f7c-249">Added install template and new project commands to Visual Studio Code extension</span></span>
- <span data-ttu-id="b5f7c-250">新增了 ApplyIf 結合器的新變體，例如 [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-250">Added new variants of ApplyIf combinator such as [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)</span></span>
- <span data-ttu-id="b5f7c-251">有額外的 [Quantum Katas](https://github.com/Microsoft/QuantumKatas) 可轉換為 Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="b5f7c-251">Additional [Quantum Katas](https://github.com/Microsoft/QuantumKatas) converted to Jupyter Notebooks</span></span>
- <span data-ttu-id="b5f7c-252">Visual Studio 延伸模組現在需要 Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b5f7c-252">Visual Studio Extension now requires Visual Studio 2019</span></span>

<span data-ttu-id="b5f7c-253">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)、[編譯器](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed)、[執行階段](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed)、[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)和 [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed) 完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-253">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) and [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="b5f7c-254">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-254">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="b5f7c-255">深入瞭解[ Q# 開發人員 blog](https://devblogs.microsoft.com/qsharp)上的這些變更。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-255">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

## <a name="version-08-packagereference-0819071701"></a><span data-ttu-id="b5f7c-256">0\.8 版 (*PackageReference 0.8.1907.1701*)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-256">Version 0.8 (*PackageReference 0.8.1907.1701*)</span></span>

<span data-ttu-id="b5f7c-257">*發行日期：2019 年 7 月 12 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-257">*Release date: July 12, 2019*</span></span>

<span data-ttu-id="b5f7c-258">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-258">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-259">切割陣列的新索引位置；請[參閱語言參考](xref:microsoft.quantum.guide.expressions#array-slices)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-259">New indexing locations for slicing arrays, [see the language reference](xref:microsoft.quantum.guide.expressions#array-slices) for more information.</span></span>
- <span data-ttu-id="b5f7c-260">已新增 [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry)上裝載的 Dockerfile，如需詳細資訊，請參閱 [I 存放 Q# 庫。](https://github.com/microsoft/iqsharp/blob/main/README.md)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-260">Added Dockerfile hosted on the [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry), see the [IQ# repository for more information](https://github.com/microsoft/iqsharp/blob/main/README.md)</span></span>
- <span data-ttu-id="b5f7c-261">[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的重大變更、組態設定的更新、名稱變更；請參閱 [.NET API 瀏覽器以了解更新的名稱](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-261">Breaking change for [the trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), update to configuration settings, name changes; see the [.NET API Browser for the updated names](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).</span></span>

<span data-ttu-id="b5f7c-262">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-262">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

## <a name="version-07-packagereference-0719053109"></a><span data-ttu-id="b5f7c-263">0\.7 版 (*PackageReference 0.7.1905.3109*)</span><span class="sxs-lookup"><span data-stu-id="b5f7c-263">Version 0.7 (*PackageReference 0.7.1905.3109*)</span></span>

<span data-ttu-id="b5f7c-264">*發行日期：2019 年 5 月 31 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-264">*Release date: May 31, 2019*</span></span>

<span data-ttu-id="b5f7c-265">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-265">This release contains the following:</span></span>
- <span data-ttu-id="b5f7c-266">語言的新增專案 Q#</span><span class="sxs-lookup"><span data-stu-id="b5f7c-266">additions to the Q# language,</span></span> 
- <span data-ttu-id="b5f7c-267">化學程式庫的更新，</span><span class="sxs-lookup"><span data-stu-id="b5f7c-267">updates to the chemistry library,</span></span> 
- <span data-ttu-id="b5f7c-268">新的數值程式庫。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-268">a new numerics library.</span></span>

<span data-ttu-id="b5f7c-269">請參閱[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)完整的已關閉 PR 清單。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-269">See the full list of closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="b5f7c-270">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-270">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="b5f7c-271">深入瞭解[ Q# 開發人員 blog](https://devblogs.microsoft.com/qsharp)上的這些變更。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-271">Read more about these changes on the [Q# dev blog](https://devblogs.microsoft.com/qsharp).</span></span>

### <a name="no-locq-language-syntax"></a><span data-ttu-id="b5f7c-272">Q# 語言語法</span><span class="sxs-lookup"><span data-stu-id="b5f7c-272">Q# language syntax</span></span>
<span data-ttu-id="b5f7c-273">此版本新增了 Q# 語言語法：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-273">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="b5f7c-274">新增[使用者自訂類型](xref:microsoft.quantum.guide.types#user-defined-types)的具名項目。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-274">Add named items for [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types).</span></span>  
* <span data-ttu-id="b5f7c-275">使用者定義類型建構函式現在可以當作函式使用。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-275">User-defined type constructors can now be used as functions.</span></span>
* <span data-ttu-id="b5f7c-276">在使用者定義類型中新增 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 和 [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) 的支援。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-276">Add support for [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) and [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) in user-defined types.</span></span>
* <span data-ttu-id="b5f7c-277">[重複直到成功](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)迴圈的修復區塊現在是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-277">Fixup-block for [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) loops is now optional.</span></span>
* <span data-ttu-id="b5f7c-278">我們現在支援函式中 (而非作業中) 的 While 迴圈。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-278">We now support while loops in functions (not in operations).</span></span>

### <a name="library"></a><span data-ttu-id="b5f7c-279">程式庫</span><span class="sxs-lookup"><span data-stu-id="b5f7c-279">Library</span></span> 

<span data-ttu-id="b5f7c-280">此版本新增了數值程式庫：請深入了解如何[使用新的數值程式庫](xref:microsoft.quantum.numerics.usage)，並試用[新範例](https://github.com/microsoft/quantum/tree/main/Numerics)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-280">This release adds a numerics library: Learn more about how to [use the new numerics library](xref:microsoft.quantum.numerics.usage) and try out the [new samples](https://github.com/microsoft/quantum/tree/main/Numerics).</span></span>  <span data-ttu-id="b5f7c-281">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-281">[PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).</span></span>  

<span data-ttu-id="b5f7c-282">此版本重組、擴充並更新了化學程式庫：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-282">This release reorganizes extends and updates the chemistry library:</span></span>
* <span data-ttu-id="b5f7c-283">改善元件的模組化、擴充性、一般程式碼清除功能。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-283">Improves modularity of components, extensibility, general code cleanup.</span></span>  <span data-ttu-id="b5f7c-284">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-284">[PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).</span></span>
* <span data-ttu-id="b5f7c-285">新增[多重參考波函數](xref:microsoft.quantum.chemistry.concepts.multireference)的支援，包括疏鬆多重參考波函數和單一結合叢集。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-285">Add support for [multi-reference wavefunctions](xref:microsoft.quantum.chemistry.concepts.multireference), both sparse multi-reference wavefunctions and unitary coupled cluster.</span></span>  <span data-ttu-id="b5f7c-286">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-286">[PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>
* <span data-ttu-id="b5f7c-287">(謝謝！)[1QBit](https://1qbit.com) 參與者 ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit))：使用變分 ansatz 的能量評估。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-287">(Thank you!) [1QBit](https://1qbit.com) contributor ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energy evaluation using variational ansatz.</span></span> <span data-ttu-id="b5f7c-288">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-288">[PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).</span></span>
* <span data-ttu-id="b5f7c-289">將 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 結構描述更新為新的 [0.2 版](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)，並新增單一結合叢集規格。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-289">Updating [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema to new [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), adding unitary coupled cluster specification.</span></span> <span data-ttu-id="b5f7c-290">[問題 #65](https://github.com/microsoft/QuantumLibraries/issues/65)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-290">[Issue #65](https://github.com/microsoft/QuantumLibraries/issues/65).</span></span>
* <span data-ttu-id="b5f7c-291">將 Python 互通性新增至化學程式庫函式。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-291">Adding Python interoperability to chemistry library functions.</span></span> <span data-ttu-id="b5f7c-292">試著使用此[範例](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-292">Try out this [sample](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration).</span></span> <span data-ttu-id="b5f7c-293">[問題 #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-293">[Issue #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).</span></span>

## <a name="version-061905"></a><span data-ttu-id="b5f7c-294">0\.6.1905 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-294">Version 0.6.1905</span></span>

<span data-ttu-id="b5f7c-295">*發行日期：2019 年 5 月 3 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-295">*Release date: May 3, 2019*</span></span>

<span data-ttu-id="b5f7c-296">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-296">This release contains the following:</span></span>
- <span data-ttu-id="b5f7c-297">對語言進行變更 Q# ，</span><span class="sxs-lookup"><span data-stu-id="b5f7c-297">makes changes to the Q# language,</span></span> 
- <span data-ttu-id="b5f7c-298">重新建構 Quantum Development Kit 程式庫，</span><span class="sxs-lookup"><span data-stu-id="b5f7c-298">restructures the Quantum Development Kit libraries,</span></span> 
- <span data-ttu-id="b5f7c-299">新增範例，以及</span><span class="sxs-lookup"><span data-stu-id="b5f7c-299">adds new samples, and</span></span> 
- <span data-ttu-id="b5f7c-300">修正 Bug。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-300">fixes bugs.</span></span>  <span data-ttu-id="b5f7c-301">[程式庫](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed)和[範例](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed)的數個已關閉的 PR。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-301">Several closed PRs for [libraries](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) and [samples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).</span></span>  

<span data-ttu-id="b5f7c-302">此處會摘要說明這些變更，以及升級現有程式的指示。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-302">The changes are summarized here as well as instructions for upgrading your existing programs.</span></span>  <span data-ttu-id="b5f7c-303">您可以在 devblogs.microsoft.com/qsharp 上深入了解這些變更。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-303">You can read more about these changes on devblogs.microsoft.com/qsharp.</span></span>

### <a name="no-locq-language-syntax"></a><span data-ttu-id="b5f7c-304">Q# 語言語法</span><span class="sxs-lookup"><span data-stu-id="b5f7c-304">Q# language syntax</span></span>
<span data-ttu-id="b5f7c-305">此版本新增了 Q# 語言語法：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-305">This release adds new Q# language syntax:</span></span>
* <span data-ttu-id="b5f7c-306">使用 `+` 運算子新增[用來表示量子作業特製化 (控制和伴隨) 的快速方法](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-306">Add a [shorthand way to express specializations of quantum operations](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (control and adjoints) with `+` operators.</span></span>  <span data-ttu-id="b5f7c-307">舊語法已被取代。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-307">The old syntax is deprecated.</span></span>  <span data-ttu-id="b5f7c-308">使用舊語法的程式 (例如 `: adjoint`) 將可繼續運作，但會產生編譯時間警告。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-308">Programs that use the old syntax (e.g., `: adjoint`) will continue to work, but a compile time warning will be generated.</span></span>  
* <span data-ttu-id="b5f7c-309">新增 [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 的運算子 `w/`，可用來將陣列的建立表示為現有陣列的修改。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-309">Add a new operator for [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions), `w/`, can be used to express array creation as a modification of an existing array.</span></span>
* <span data-ttu-id="b5f7c-310">新增一般 [apply-and-update 陳述式](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols)，例如 `+=`、`w/=`。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-310">Add the common [apply-and-update statement](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), e.g., `+=`, `w/=`.</span></span>
* <span data-ttu-id="b5f7c-311">新增為[開放式指示詞](xref:microsoft.quantum.guide.filestructure#open-directives)中的命名空間指定簡短名稱的方法。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-311">Add a way to specify a short name for namespaces in [open directives](xref:microsoft.quantum.guide.filestructure#open-directives).</span></span>

<span data-ttu-id="b5f7c-312">在此版本中，我們不再允許在 set 陳述式的左側指定陣列元素。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-312">With this release, we no longer allow an array element to be specified on the left side of a set statement.</span></span>  <span data-ttu-id="b5f7c-313">這是因為該語法意味著陣列是可變動的，然而事實上，作業的結果一律是經由修改建立新陣列。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-313">This is because that syntax implies that arrays are mutable when in fact, the result of the operation has always been the creation of a new array with the modification.</span></span>  <span data-ttu-id="b5f7c-314">系統將會產生編譯器錯誤，並建議使用新的 copy-and-update 運算子 `w/` 達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-314">Instead, a compiler error will be generated with a suggestion to use the new copy-and-update operator, `w/`, to accomplish the same result.</span></span>  

### <a name="library-restructuring"></a><span data-ttu-id="b5f7c-315">程式庫重建</span><span class="sxs-lookup"><span data-stu-id="b5f7c-315">Library restructuring</span></span>
<span data-ttu-id="b5f7c-316">此版本重組了程式庫，使其能以一致的方式擴展：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-316">This release reorganizes the libraries to enable their growth in a consistent way:</span></span>
* <span data-ttu-id="b5f7c-317">將 Microsoft.Quantum.Primitive 命名空間重新命名為 Microsoft.Quantum.Intrinsic。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-317">Renames the Microsoft.Quantum.Primitive namespace  to Microsoft.Quantum.Intrinsic.</span></span>  <span data-ttu-id="b5f7c-318">這些作業會由目標電腦實作。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-318">These operations are implemented by the target machine.</span></span>  <span data-ttu-id="b5f7c-319">Microsoft.Quantum.Primitive 命名空間已被取代。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-319">The Microsoft.Quantum.Primitive namespace is deprecated.</span></span>  <span data-ttu-id="b5f7c-320">當程式使用已被取代的名稱呼叫作業和函式時，會有執行階段警告提出建議。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-320">A runtime warning will advise when programs call operations and functions using deprecated names.</span></span>

* <span data-ttu-id="b5f7c-321">將 Microsoft.Quantum.Canon 套件重新命名為 Microsoft.Quantum.Standard。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-321">Renames the Microsoft.Quantum.Canon package to Microsoft.Quantum.Standard.</span></span>  <span data-ttu-id="b5f7c-322">此套件包含大部分程式通用的命名空間 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-322">This package contains namespaces that are common to most Q# programs.</span></span>  <span data-ttu-id="b5f7c-323">這包括：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-323">This includes:</span></span>  
    - <span data-ttu-id="b5f7c-324">一般作業的 Microsoft.Quantum.Canon</span><span class="sxs-lookup"><span data-stu-id="b5f7c-324">Microsoft.Quantum.Canon for common operations</span></span>
    - <span data-ttu-id="b5f7c-325">一般用途算術運算的 Microsoft.Quantum.Arithmetic</span><span class="sxs-lookup"><span data-stu-id="b5f7c-325">Microsoft.Quantum.Arithmetic for general purpose arithmetic operations</span></span>
    - <span data-ttu-id="b5f7c-326">作業用來準備量子位元狀態的 Microsoft.Quantum.Preparation</span><span class="sxs-lookup"><span data-stu-id="b5f7c-326">Microsoft.Quantum.Preparation for operations used to prepare qubit state</span></span>
    - <span data-ttu-id="b5f7c-327">模擬功能的 Microsoft.Quantum.Simulation</span><span class="sxs-lookup"><span data-stu-id="b5f7c-327">Microsoft.Quantum.Simulation for simulation functionality</span></span>

<span data-ttu-id="b5f7c-328">經過這項變更後，如果程式包含用於命名空間 Microsoft.Quatum.Canon 的單一 "open" 陳述式，且其參考的作業已移至其他三個新的命名空間，則可能會發生建置錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-328">With this change, programs that include a single "open" statement for the namespace Microsoft.Quatum.Canon may encounter build errors if the program references operations that were moved to the other three new namespaces.</span></span>  <span data-ttu-id="b5f7c-329">為這三個新的命名空間新增額外的 open 陳述式，可直接了當地解決此問題。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-329">Adding the additional open statements for the three new namespaces is a straightforward way to resolve this issue.</span></span>  

* <span data-ttu-id="b5f7c-330">有數個命名空間已被取代，因為其中的作業已重組至其他命名空間。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-330">Several namespaces have been deprecated as the operations within have been reorganized to other namespaces.</span></span> <span data-ttu-id="b5f7c-331">使用這些命名空間的程式將可繼續運作，但會有編譯時間警告指出作業定義所在的命名空間。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-331">Programs that use these namespaces will continue to work, and a compile time warning will denote the namespace where the operation is defined.</span></span>  

* <span data-ttu-id="b5f7c-332">Microsoft.Quantum.Arithmetic 命名空間已正規化為使用 <xref:microsoft.quantum.arithmetic.littleendian> 使用者定義類型。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-332">The Microsoft.Quantum.Arithmetic namespace has been normalized to use the <xref:microsoft.quantum.arithmetic.littleendian> user-defined type.</span></span> <span data-ttu-id="b5f7c-333">需要轉換為 Little Endian 時，請使用函式 [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-333">Use the function [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) when needed to convert to little endian.</span></span>  

* <span data-ttu-id="b5f7c-334">數個 callables (函式和作業) 的名稱已變更為符合[ Q# 樣式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-334">The names of several callables (functions and operations) have been changed to conform to the [Q# Style Guide](xref:microsoft.quantum.contributing.style).</span></span>  <span data-ttu-id="b5f7c-335">舊的可呼叫名稱已被取代。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-335">The old callable names are deprecated.</span></span>  <span data-ttu-id="b5f7c-336">使用舊有可呼叫項目的程式將可繼續運作，但會出現編譯時間警告。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-336">Programs that use the old callables will continue to work with a compile time warning.</span></span> 

### <a name="new-samples"></a><span data-ttu-id="b5f7c-337">新範例</span><span class="sxs-lookup"><span data-stu-id="b5f7c-337">New Samples</span></span>

<span data-ttu-id="b5f7c-338">我們新增了搭配 [ Q# F # 驅動程式使用的範例](https://github.com/Microsoft/Quantum/pull/164)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-338">We added a [sample of using Q# with F# driver](https://github.com/Microsoft/Quantum/pull/164).</span></span>  

<span data-ttu-id="b5f7c-339">**感謝**</span><span class="sxs-lookup"><span data-stu-id="b5f7c-339">**Thank you!**</span></span> <span data-ttu-id="b5f7c-340">下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-340">to the following contributor to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="b5f7c-341">這些貢獻會大幅增加至豐富的程式 Q# 代碼範例：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-341">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="b5f7c-342">Mathias Soeken ([@msoeken](https://github.com/msoeken))：Oracle 函式合成。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-342">Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle function synthesis.</span></span> <span data-ttu-id="b5f7c-343">[PR #135](https://github.com/Microsoft/Quantum/pull/135)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-343">[PR #135](https://github.com/Microsoft/Quantum/pull/135).</span></span>

### <a name="migrating-existing-projects-to-061905"></a><span data-ttu-id="b5f7c-344">將現有的專案移轉至 0.6.1905。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-344">Migrating existing projects to 0.6.1905.</span></span>

<span data-ttu-id="b5f7c-345">若要更新 QDK，請參閱[安裝指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-345">See the [install guide](xref:microsoft.quantum.install) to update the QDK.</span></span>
  
<span data-ttu-id="b5f7c-346">如果您有 Q# 來自量子開發工具組0.5 版的現有專案，以下是將這些專案遷移至最新版本的步驟。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-346">If you have existing Q# projects from version 0.5 of the Quantum Development Kit, the following are the steps to migrate those projects to the newest version.</span></span>

1. <span data-ttu-id="b5f7c-347">專案必須依序升級。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-347">Projects need to be upgraded in order.</span></span>  <span data-ttu-id="b5f7c-348">如果您的解決方案有多個專案，請依照每個專案的參考順序加以更新。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-348">If you have a solution with multiple projects, update each project in the order they are referenced.</span></span>
2. <span data-ttu-id="b5f7c-349">從命令提示字元執行， `dotnet clean` 以移除所有現有的二進位檔和中繼檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-349">From a command prompt, Run `dotnet clean` to remove all existing binaries and intermediate files.</span></span>
3. <span data-ttu-id="b5f7c-350">在文字編輯器中編輯 .csproj 檔案，將所有 "Microsoft.Quantum" `PackageReference` 的版本變更為 0.6.1904 版，並將 "Microsoft.Quantum.Canon" 套件名稱變更為 "Microsoft.Quantum.Standard"，例如：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-350">In a text editor, edit the .csproj file to change the version of all the "Microsoft.Quantum" `PackageReference` to version 0.6.1904, and change the "Microsoft.Quantum.Canon" package name to "Microsoft.Quantum.Standard", for example:</span></span>

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. <span data-ttu-id="b5f7c-351">從命令提示字元中，執行此命令： `dotnet msbuild`</span><span class="sxs-lookup"><span data-stu-id="b5f7c-351">From the command prompt, run this command: `dotnet msbuild`</span></span>  
5. <span data-ttu-id="b5f7c-352">執行此命令後，您可能仍需手動解決因上述變更所造成的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-352">After running this, you might still need to manually address errors due to changes listed above.</span></span>  <span data-ttu-id="b5f7c-353">在許多情況下，Visual Studio 或 Visual Studio Code 中的 IntelliSense 也會報告這些錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-353">In many cases, these errors will also be reported by IntelliSense in Visual Studio or Visual Studio Code.</span></span>
    - <span data-ttu-id="b5f7c-354">在 Visual Studio 2019 或 Visual Studio Code 中開啟專案或其所屬解決方案的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-354">Open the root folder of the project or the containing solution in Visual Studio 2019 or Visual Studio Code.</span></span>
    - <span data-ttu-id="b5f7c-355">在編輯器中開啟 qs 檔案之後，您應該會 Q# 在 [輸出] 視窗中看到語言延伸模組的輸出。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-355">After opening a .qs file in the editor, you should see the output of the Q# language extension in the output window.</span></span>
    - <span data-ttu-id="b5f7c-356">成功載入專案後 (會在輸出視窗中指出)，請開啟每個檔案，並手動解決其餘的所有問題。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-356">After the project has loaded successfully (indicated in the output window) open each file and manually to address all remaining issues.</span></span>

> [!NOTE]
> * <span data-ttu-id="b5f7c-357">對於 0.6 版本，隨附於 Quantum Development Kit 的語言伺服器不支援多個工作區。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-357">For the 0.6 release, the language server included with the Quantum Development Kit does not support multiple workspaces.</span></span>
> * <span data-ttu-id="b5f7c-358">若要在 Visual Studio Code 中使用專案，請開啟包含專案本身和所有參考專案的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-358">In order to work with a project in Visual Studio Code, open the root folder containing the project itself and all referenced projects.</span></span>   
> * <span data-ttu-id="b5f7c-359">若要在 Visual Studio 中使用解決方案，解決方案中包含的所有專案必須位於與解決方案相同的資料夾中，或解決方案的其中一個子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-359">In order to work with a solution in Visual Studio, all projects contained in the solution need to be in the same folder as the solution or in one of its subfolders.</span></span>  
> * <span data-ttu-id="b5f7c-360">在專案間移轉至 0.6 和更新版本的參考，以及使用舊版套件的專案，均**不**受支援。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-360">References between projects migrated to 0.6 and higher and projects using older package versions are **not** supported.</span></span>

## <a name="version-051904"></a><span data-ttu-id="b5f7c-361">0\.5.1904 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-361">Version 0.5.1904</span></span>

<span data-ttu-id="b5f7c-362">*發行日期：2019 年 4 月 15 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-362">*Release date: April 15, 2019*</span></span>

<span data-ttu-id="b5f7c-363">此版本包含 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-363">This release contains bug fixes.</span></span>


## <a name="version-051903"></a><span data-ttu-id="b5f7c-364">0\.5.1903 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-364">Version 0.5.1903</span></span>

<span data-ttu-id="b5f7c-365">*發行日期：2019 年 3 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-365">*Release date: March 27, 2019*</span></span>

<span data-ttu-id="b5f7c-366">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-366">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-367">新增 Jupyter Notebook 的支援，提供絕佳的學習方式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-367">Adds support for Jupyter Notebook, which offers a great way to learn about Q#.</span></span>  <span data-ttu-id="b5f7c-368">請[查看新的 Jupyter Notebook 範例，並了解如何撰寫您自己的 Notebook](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-368">[Check out new Jupyter Notebook samples and learn how to write your own Notebooks](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="b5f7c-369">將整數 adder 演算法新增至 Quantum Canon 程式庫。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-369">Adds integer adder arithmetic to the Quantum Canon library.</span></span>  <span data-ttu-id="b5f7c-370">另請參閱[說明如何使用新的整數 adder](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb) 的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-370">See also a Jupyter Notebook that [describes how to use the new integer adders](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb).</span></span>

- <span data-ttu-id="b5f7c-371">社群回報的 DumpRegister 問題 ([#148](https://github.com/Microsoft/Quantum/issues/148)) 的 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-371">Bug fix for DumpRegister issue reported by the community ([#148](https://github.com/Microsoft/Quantum/issues/148)).</span></span>

- <span data-ttu-id="b5f7c-372">新增了從 [Using 陳述式](xref:microsoft.quantum.guide.qubits#allocating-qubits)傳回的功能。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-372">Added ability to return from within a [using statement](xref:microsoft.quantum.guide.qubits#allocating-qubits).</span></span>

- <span data-ttu-id="b5f7c-373">全新設計的[使用者入門指南](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-373">Revamped [getting started guide](xref:microsoft.quantum.install).</span></span>


## <a name="version-051902"></a><span data-ttu-id="b5f7c-374">0\.5.1902 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-374">Version 0.5.1902</span></span>

<span data-ttu-id="b5f7c-375">*發行日期：2019 年 2 月 27 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-375">*Release date: February 27, 2019*</span></span>

<span data-ttu-id="b5f7c-376">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-376">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-377">新增跨平台 Python 主機的支援。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-377">Adds support for a cross-platform Python host.</span></span>  <span data-ttu-id="b5f7c-378">`qsharp`適用于 python 的套件可讓您輕鬆地 Q# 從 Python 內模擬作業和函式。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-378">The `qsharp` package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="b5f7c-379">深入了解 [Python 互通性](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-379">Learn more about [Python interoperability](xref:microsoft.quantum.install).</span></span> 

- <span data-ttu-id="b5f7c-380">Visual Studio 和 Visual Studio Code 延伸模組現已支援符號 (例如函式和作業) 的重新命名。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-380">The Visual Studio and Visual Studio Code extensions now support renaming of symbols (e.g., functions and operations).</span></span>

- <span data-ttu-id="b5f7c-381">Visual Studio 延伸模組現已可安裝在 Visual Studio 2019 上。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-381">The Visual Studio extension can now be installed on Visual Studio 2019.</span></span>

## <a name="version-041901"></a><span data-ttu-id="b5f7c-382">0\.4.1901 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-382">Version 0.4.1901</span></span>

<span data-ttu-id="b5f7c-383">*發行日期：2019 年 1 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-383">*Release date: January 30, 2019*</span></span>

<span data-ttu-id="b5f7c-384">此版本包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-384">This release contains the following:</span></span>

- <span data-ttu-id="b5f7c-385">新增新的基本類型 BigInt 的支援，此類型代表任意大小帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-385">adds support for a new primitive type, BigInt, which represents a signed integer of arbitrary size.</span></span>  <span data-ttu-id="b5f7c-386">深入了解 [BigInt 類型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-386">Learn more about [BigInt type](xref:microsoft.quantum.guide.types).</span></span>
- <span data-ttu-id="b5f7c-387">新增 Toffoli 模擬器，這是一種特殊用途的快速模擬器，可模擬具有大量量子位元的 X、CNOT 和多重受控 X 量子作業。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-387">adds new Toffoli simulator, a special purpose fast simulator that can simulate X, CNOT and multi-controlled X quantum operations with very large numbers of qubits.</span></span>  <span data-ttu-id="b5f7c-388">深入了解 [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-388">Learn more about [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator).</span></span>
- <span data-ttu-id="b5f7c-389">新增簡單的資源估算器，以估計在量子電腦上執行特定實例作業所需的資源 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-389">adds a simple resource estimator that estimates the resources required to run a given instancee of a Q# operation on a quantum computer.</span></span>  <span data-ttu-id="b5f7c-390">深入了解[資源估算器](xref:microsoft.quantum.machines.resources-estimator)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-390">Learn more about the [Resource Estimator](xref:microsoft.quantum.machines.resources-estimator).</span></span>


## <a name="version-0318112802"></a><span data-ttu-id="b5f7c-391">0\.3.1811.2802 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-391">Version 0.3.1811.2802</span></span>

<span data-ttu-id="b5f7c-392">*發行日期：2018 年 11 月 28 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-392">*Release date: November 28, 2018*</span></span>

<span data-ttu-id="b5f7c-393">此版本已在與 `event-stream` NPM 套件相關的[延伸模組清除](https://code.visualstudio.com/blogs/2018/11/26/event-stream)期間加上旗標，並從 Marketplace 中移除，但我們的 VS Code 延伸模組並未加以使用。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-393">Even though our VS Code extension was not using it, it was flagged and removed from the marketplace during [the extensions purge](https://code.visualstudio.com/blogs/2018/11/26/event-stream) related to the `event-stream` NPM package.</span></span> <span data-ttu-id="b5f7c-394">此版本移除了所有可能致使延伸模組觸發任何紅色旗標的執行階段相依性。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-394">This version removes all runtime dependencies that could make the extension trigger any red flags.</span></span>

<span data-ttu-id="b5f7c-395">如果您先前已安裝此延伸模組，您必須造訪 Visual Studio Marketplace 上的 [Visual Studio Code 延伸模組的 Microsoft Quantum Development Kit](vscode:extension/quantum.quantum-devkit-vscode)，並且按 [安裝] 重新加以安裝。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-395">If you had previously installed the extension you will need to install it again by visiting the [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) extension on the Visual Studio Marketplace and press Install.</span></span> <span data-ttu-id="b5f7c-396">很抱歉造成您的不便。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-396">We are sorry about the inconvenience.</span></span>


## <a name="version-0318111511"></a><span data-ttu-id="b5f7c-397">0\.3.1811.1511 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-397">Version 0.3.1811.1511</span></span>

<span data-ttu-id="b5f7c-398">*發行日期：2018 年 11 月 20 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-398">*Release date: November 20, 2018*</span></span>

<span data-ttu-id="b5f7c-399">此版本修正了導致某些使用者無法成功載入 Visual Studio 延伸模組的 Bug。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-399">This release fixes a bug that prevented some users to successfully load the Visual Studio extension.</span></span>

## <a name="version-031811203"></a><span data-ttu-id="b5f7c-400">0\.3.1811.203 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-400">Version 0.3.1811.203</span></span>

<span data-ttu-id="b5f7c-401">*發行日期：2018 年 11 月 2 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-401">*Release date: November 2, 2018*</span></span>

<span data-ttu-id="b5f7c-402">此版本包含一些 Bug 修正，包括：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-402">This release includes a few bug fixes, including:</span></span>

* <span data-ttu-id="b5f7c-403">在特定情況下，叫用 `DumpMachine` 可能會變更模擬器的狀態。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-403">Invoking `DumpMachine` could change the state of the simulator under certain situations.</span></span>
* <span data-ttu-id="b5f7c-404">移除了在使用 2.1.403 之前的 .NET Core 版本建置專案時所產生的編譯警告。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-404">Removed compilation warnings when building projects using a version of .NET Core previous to 2.1.403.</span></span>
* <span data-ttu-id="b5f7c-405">清除了文件，特別是在 VS Code 或 Visual Studio 中暫留滑鼠時所顯示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-405">Clean up of documentation, specially the tooltips shown during mouse hover in VS Code or Visual Studio.</span></span>

## <a name="version-0318102508"></a><span data-ttu-id="b5f7c-406">0\.3.1810.2508 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-406">Version 0.3.1810.2508</span></span>

<span data-ttu-id="b5f7c-407">*發行日期：2018 年 10 月 29 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-407">*Release date: October 29, 2018*</span></span>

<span data-ttu-id="b5f7c-408">此版本包含新的語言功能和改良的開發人員體驗：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-408">This release includes new language features and an improved developer experience:</span></span>

* <span data-ttu-id="b5f7c-409">此版本包含的語言伺服器 Q# ，以及 Visual Studio 和 Visual Studio Code 的用戶端整合。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-409">This release includes a language server for Q#, as well as the client integrations for Visual Studio and Visual Studio Code.</span></span> <span data-ttu-id="b5f7c-410">這會啟用一組新的 IntelliSense 功能，以及以波狀底線的形式輸入錯誤和警告的即時反饋。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-410">This enables a new set of IntelliSense features along with live feedback on typing in form of squiggly underlinings of errors and warnings.</span></span> 
* <span data-ttu-id="b5f7c-411">整體而言，這項更新可讓您輕鬆瀏覽至精確的診斷範圍，並且在顯示的暫留資訊中提供其他詳細資料，而大幅改善了診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-411">This update greatly improves diagnostic messages in general, with easy navigation to and precise ranges for diagnostics and additional details in the displayed hover information.</span></span>
* <span data-ttu-id="b5f7c-412">Q#這種語言的延伸方法，是讓開發人員可以進行一般作業的方式，以及語言功能的新增強功能，來強大且快速的量子計算。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-412">The Q# language has been extended in ways that unifies the ways developers can do common operations and new enhancements to the language features to powerfully express quantum computation.</span></span>  <span data-ttu-id="b5f7c-413">這一版的語言有一些重大變更 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-413">There are a handful of breaking changes to the Q# language with this release.</span></span>   

<span data-ttu-id="b5f7c-414">此版本也包含新的量子化學程式庫：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-414">This release also includes a new quantum chemistry library:</span></span>

* <span data-ttu-id="b5f7c-415">化學程式庫包含新的 Hamiltonian 模擬功能，包括：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-415">The chemistry library contains new Hamiltonian simulation features, including:</span></span>
    - <span data-ttu-id="b5f7c-416">Trotter – 任意偶次的 Suzuki 整合器，用以改善模擬正確性。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-416">Trotter–Suzuki integrators of arbitrary even order for improved simulation accuracy.</span></span>
    - <span data-ttu-id="b5f7c-417">採用化學專用最佳化的量子位元化模擬技術，用以降低 $T$ 閘道複雜度。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-417">Qubitization simulation technique with chemistry-specific optimizations for reducing $T$-gate complexity.</span></span>
* <span data-ttu-id="b5f7c-418">導入了新的開放原始碼結構描述，名為 Broombridge 結構描述 (得名自被譽為 Hamiltonian 發源地的[地標](https://en.wikipedia.org/wiki/Broom_Bridge))，用以匯入分子的表示法及加以模擬。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-418">A new open source schema, called Broombridge Schema (in reference to a [landmark](https://en.wikipedia.org/wiki/Broom_Bridge) celebrated as a birthplace of Hamiltonians), is introduced for importing representations of molecules and simulating them.</span></span>
* <span data-ttu-id="b5f7c-419">提供多個使用 Broombridge 結構描述定義的化學標記法。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-419">Multiple chemical representations defined using the Broombridge Schema are provided.</span></span>  <span data-ttu-id="b5f7c-420">這些模型由 [NWChem](http://www.nwchem-sw.org/) (一種開放原始碼高效能運算化學工具) 所產生。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-420">These models were generated by [NWChem](http://www.nwchem-sw.org/), an open source high-performance computational chemistry tool.</span></span>
* <span data-ttu-id="b5f7c-421">教學課程和範例會說明如何使用化學程式庫和 Broombridge 資料模型來：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-421">Tutorials and Samples describe how to use the chemistry library and the Broombridge data models to:</span></span>
    - <span data-ttu-id="b5f7c-422">使用化學程式庫建構簡單的 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="b5f7c-422">Construct simple Hamiltonians using the chemistry library</span></span>
    - <span data-ttu-id="b5f7c-423">使用階段估算呈現氫化鋰的基態能量和激發態能量。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-423">Visualize ground and excited energies of Lithium Hydride using phase estimation.</span></span>
    - <span data-ttu-id="b5f7c-424">執行量子化學模擬的資源估算。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-424">Perform resource estimates of quantum chemistry simulation.</span></span>
    - <span data-ttu-id="b5f7c-425">對 Broombridge 結構描述所代表的分子估算能階。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-425">Estimate energy levels of molecules represented by the Broombridge schema.</span></span>
* <span data-ttu-id="b5f7c-426">檔說明如何使用 NWChem 來產生其他化學模型，以使用進行量子模擬 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-426">Documentation describes how to use NWChem to generate additional chemical models for quantum simulation with Q#.</span></span>

<span data-ttu-id="b5f7c-427">深入了解 [Quantum Development Kit 化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-427">Learn more about the [Quantum Development Kit chemistry library](xref:microsoft.quantum.chemistry.concepts.intro).</span></span>

<span data-ttu-id="b5f7c-428">透過新的化學程式庫，我們將程式庫劃分到新的 GitHub 存放庫 [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) 中。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-428">With the new chemistry library, we are separating out the libraries into a new GitHub repo, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).</span></span>  <span data-ttu-id="b5f7c-429">範例仍保留在存放庫 [Microsoft/Quantum](https://github.com/Microsoft/Quantum) 中。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-429">The samples remain in the repo [Microsoft/Quantum](https://github.com/Microsoft/Quantum).</span></span>  <span data-ttu-id="b5f7c-430">歡迎大家參與對這兩個存放庫的建構！</span><span class="sxs-lookup"><span data-stu-id="b5f7c-430">We welcome contributions to both!</span></span>

<span data-ttu-id="b5f7c-431">此版本包含針對社群回報的問題而提供的 Bug 修正和功能：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-431">This release includes bug fixes and features for issues reported by the community:</span></span>

* <span data-ttu-id="b5f7c-432">Intellisense 適用于 Q# ？</span><span class="sxs-lookup"><span data-stu-id="b5f7c-432">Intellisense for Q#?</span></span> <span data-ttu-id="b5f7c-433">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-433">([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).</span></span>
* <span data-ttu-id="b5f7c-434">.qs 檔案 ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-434">.qs files ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).</span></span>
* <span data-ttu-id="b5f7c-435">改善 If 陳述式中的大括弧節略時的錯誤訊息 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-435">Improve error message when curly braces are abbreviated in if statement ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).</span></span>
* <span data-ttu-id="b5f7c-436">支援可變動 (重新) 繫結上的元組解構 ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-436">Support tuple deconstruction at mutable (re-)binding ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).</span></span>
* <span data-ttu-id="b5f7c-437">執行提供的 BitFlipCode 時發生的錯誤 ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-437">Error Running Provided BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>
* <span data-ttu-id="b5f7c-438">H2SimulationGUI 有時會顯示大型尖峰 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-438">H2SimulationGUI displays big peaks sometimes ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="b5f7c-439">社群貢獻</span><span class="sxs-lookup"><span data-stu-id="b5f7c-439">Community Contributions</span></span>

<span data-ttu-id="b5f7c-440">**感謝**</span><span class="sxs-lookup"><span data-stu-id="b5f7c-440">**Thank you!**</span></span> <span data-ttu-id="b5f7c-441">下列參與者在 http://github.com/Microsoft/Quantum 對我們的開放程式碼基底所做的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-441">to the following contributors to our open code base at http://github.com/Microsoft/Quantum.</span></span> <span data-ttu-id="b5f7c-442">這些貢獻會大幅增加至豐富的程式 Q# 代碼範例：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-442">These contributions add significantly to the rich samples of Q# code:</span></span>

* <span data-ttu-id="b5f7c-443">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)) ：藉 Q# 由建立 QASM 至翻譯工具來改善 QASM/開發人員的體驗 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-443">Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Improved the experience for QASM/Q# developers by creating a QASM to Q# translator.</span></span> <span data-ttu-id="b5f7c-444">[PR #58](https://github.com/Microsoft/Quantum/pull/58)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-444">[PR #58](https://github.com/Microsoft/Quantum/pull/58).</span></span>

* <span data-ttu-id="b5f7c-445">Andrew Helwer ([@ahelwer](https://github.com/ahelwer))：提供了實作 CHSH 賽局的範例；這是與非定域性相關的量子賽局。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-445">Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Contributed a sample implementing the CHSH Game, a quantum game related to non-locality.</span></span>  <span data-ttu-id="b5f7c-446">[PR #84](https://github.com/Microsoft/Quantum/pull/84)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-446">[PR #84](https://github.com/Microsoft/Quantum/pull/84).</span></span>

<span data-ttu-id="b5f7c-447">同時感謝 Rohit Gupta ([@guptarohit](https://github.com/guptarohit)，[PR #90](https://github.com/Microsoft/quantum/pull/90))、Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi)，[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) 和 Lee James O'Riordan ([@mlxd](https://github.com/mlxd)，[PR #96](https://github.com/Microsoft/Quantum/pull/96)) 為了改善我們所有人的內容，在文件、拼字和校對方面的努力付出！</span><span class="sxs-lookup"><span data-stu-id="b5f7c-447">Thank you also to Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), and Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) for their work improving the content for all of us through documentation, spelling and typo corrections!</span></span> 

## <a name="version-021809701"></a><span data-ttu-id="b5f7c-448">0\.2.1809.701 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-448">Version 0.2.1809.701</span></span>

<span data-ttu-id="b5f7c-449">*發行日期：2018 年 9 月 10 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-449">*Release date: September 10, 2018*</span></span>

<span data-ttu-id="b5f7c-450">此版本包含對社群回報的問題所做的 Bug 修正。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-450">This release includes bug fixes for issues reported by the community.</span></span> <span data-ttu-id="b5f7c-451">其中包括：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-451">Including:</span></span>

* <span data-ttu-id="b5f7c-452">無法使用移位運算子 ([GitHub](https://github.com/Microsoft/Quantum/issues/75))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-452">Unable to use shift operator ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).</span></span>
* <span data-ttu-id="b5f7c-453">在列印到主控台，`QCTraceSimulator` 上的 `DumpMachine` / `DumpRegister` 會失敗 ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-453">`DumpMachine` / `DumpRegister` fails on `QCTraceSimulator` when printing to console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).</span></span>
* <span data-ttu-id="b5f7c-454">允許配置 0 個量子位元 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-454">Allow allocating 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).</span></span>
* <span data-ttu-id="b5f7c-455">`AssertQubitState` 需要明確的 Complex() 呼叫 ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-455">`AssertQubitState` requires explicit Complex() call ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).</span></span>
* <span data-ttu-id="b5f7c-456">macOS 上的 `Measure` 作業一律會傳回 `One` ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546))。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-456">`Measure` operation always returns `One` on macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).</span></span>

<span data-ttu-id="b5f7c-457">感謝您！</span><span class="sxs-lookup"><span data-stu-id="b5f7c-457">Thanks!</span></span> 

## <a name="version-0218063001"></a><span data-ttu-id="b5f7c-458">0\.2.1806.3001 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-458">Version 0.2.1806.3001</span></span>

<span data-ttu-id="b5f7c-459">*發行日期：2018 年 6 月 30 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-459">*Release date: June 30, 2018*</span></span>

<span data-ttu-id="b5f7c-460">此版本只是 [在 GitHub 上回報的問題 #48](https://github.com/Microsoft/Quantum/issues/48) 的快速修正（ Q# 如果使用者名稱包含空白空間) ，就 (編譯失敗）。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-460">This releases is just a quick fix for [issue #48 reported on GitHub](https://github.com/Microsoft/Quantum/issues/48) (Q# compilation fails if user name contains a blank space).</span></span> <span data-ttu-id="b5f7c-461">使用對應的新版本 (`0.2.1806.3001-preview`) 時，請遵循與 `0.2.1806.1503` 相同的更新指示。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-461">Follow same update instructions as `0.2.1806.1503` with the corresponding new version (`0.2.1806.3001-preview`).</span></span>

## <a name="version-0218061503"></a><span data-ttu-id="b5f7c-462">0\.2.1806.1503 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-462">Version 0.2.1806.1503</span></span>

<span data-ttu-id="b5f7c-463">*發行日期：2018 年 6 月 22 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-463">*Release date: June 22, 2018*</span></span>

<span data-ttu-id="b5f7c-464">此版本包含幾項社群貢獻，以及有所改善的偵錯體驗和增進的效能。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-464">This release includes several community contributions as well as an improved debugging experience and improved performance.</span></span>  <span data-ttu-id="b5f7c-465">具體來說：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-465">Specifically:</span></span>

* <span data-ttu-id="b5f7c-466">QuantumSimulator 目標電腦的小型和大型模擬的效能改進。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-466">Performance improvements on both small and large simulations for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="b5f7c-467">改良的偵錯功能。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-467">Improved debugging functionality.</span></span>
* <span data-ttu-id="b5f7c-468">社群在 Bug 修正、新的 Helper 函式、作業和新範例等方面的貢獻。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-468">Community contributions in bug fixes, new helper functions, operations and new samples.</span></span>

### <a name="performance-improvements"></a><span data-ttu-id="b5f7c-469">效能改善</span><span class="sxs-lookup"><span data-stu-id="b5f7c-469">Performance improvements</span></span>

<span data-ttu-id="b5f7c-470">這項更新包括所有目標電腦的大量和少量量子位元模擬皆有顯著的效能改善。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-470">This update includes significant performance improvements for simulation of large and small numbers of qubits for all the target machines.</span></span>  <span data-ttu-id="b5f7c-471">經由在 Quantum Development Kit 中作為標準範例的 H<sub>2</sub> 模擬，可發現改善的幅度顯而易見。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-471">This improvement is easily visible with the H<sub>2</sub> simulation that is a standard sample in the Quantum Development Kit.</span></span>

### <a name="improved-debugging-functionality"></a><span data-ttu-id="b5f7c-472">改良的偵錯功能</span><span class="sxs-lookup"><span data-stu-id="b5f7c-472">Improved debugging functionality</span></span>

<span data-ttu-id="b5f7c-473">此更新新增了偵錯功能：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-473">This update adds new debugging functionality:</span></span>
* <span data-ttu-id="b5f7c-474">新增了 @"microsoft.quantum.extensions.diagnostics.dumpmachine" 和 @"microsoft.quantum.extensions.diagnostics.dumpregister" 兩個新作業，可輸出目標量子電腦在某個時間點的波形函式相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-474">Added two new operations,  @"microsoft.quantum.extensions.diagnostics.dumpmachine" and @"microsoft.quantum.extensions.diagnostics.dumpregister" that output wave function information about the target quantum machine at a point in time.</span></span>  
* <span data-ttu-id="b5f7c-475">在 Visual Studio 中，對單一量子位元測量 $\ket{1}$ 的機率現在會自動顯示在 QuantumSimulator 目標電腦的偵錯視窗中。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-475">In Visual Studio, the probability of measuring a $\ket{1}$ on a single qubit is now automatically shown in the debugging window for the QuantumSimulator target machine.</span></span>
* <span data-ttu-id="b5f7c-476">在 Visual Studio 中，變數屬性在 [自動變數] 和 [區域變數] 偵錯視窗中的顯示已有所改善。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-476">In Visual Studio, improved the display of variable properties in the **Autos** and **Locals** debug windows.</span></span> 

<span data-ttu-id="b5f7c-477">深入了解[測試和偵錯](xref:microsoft.quantum.guide.testingdebugging)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-477">Learn more about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

### <a name="community-contributions"></a><span data-ttu-id="b5f7c-478">社群貢獻</span><span class="sxs-lookup"><span data-stu-id="b5f7c-478">Community Contributions</span></span>

<span data-ttu-id="b5f7c-479">Q#編碼員社區正在成長，我們會很高興以查看第一個使用者參與的程式庫，以及提交給開放程式碼基底的範例 http://github.com/Microsoft/quantum 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-479">The Q# coder community is growing and we are thrilled to see the first user contributed libraries and samples that were submitted to our open code base at http://github.com/Microsoft/quantum.</span></span>  <span data-ttu-id="b5f7c-480">**非常感謝**</span><span class="sxs-lookup"><span data-stu-id="b5f7c-480">**A big Thank you!**</span></span> <span data-ttu-id="b5f7c-481">下列參與者：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-481">to the following contributors:</span></span>
* <span data-ttu-id="b5f7c-482">Mathias Soeken ([@msoeken](https://github.com/msoeken))：提供了一個範例，定義以轉換為基礎的邏輯合成方法，以建構用來實作指定排列的 Toffoli 網路。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-482">Mathias Soeken ([@msoeken](https://github.com/msoeken)):  contributed a sample defining a transformation based logic synthesis method that constructs Toffoli networks to implement a given permutation.</span></span> <span data-ttu-id="b5f7c-483">程式碼完全以函式 Q# 和作業撰寫。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-483">The code is written entirely in Q# functions and operations.</span></span>  <span data-ttu-id="b5f7c-484">[PR #41](https://github.com/Microsoft/Quantum/pull/41)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-484">[PR #41](https://github.com/Microsoft/Quantum/pull/41).</span></span>
* <span data-ttu-id="b5f7c-485">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)) ： Microsoft MVP Rolf Huisman 所提供的範例會從程式碼產生一般 QASM 程式碼，該 Q# 程式碼適用于沒有傳統控制流程和受限式量子作業的有限類別程式碼。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-485">RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): Microsoft MVP Rolf Huisman contributed a sample that generates flat QASM code from Q# code for a restricted class of programs that do not have classical control flow and restricted quantum operations.</span></span> [<span data-ttu-id="b5f7c-486">PR #59</span><span class="sxs-lookup"><span data-stu-id="b5f7c-486">PR #59</span></span>](https://github.com/Microsoft/Quantum/pull/59)
* <span data-ttu-id="b5f7c-487">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314))：藉由提交受控作業適用的程式庫函式，協助我們改善程式碼基底。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-487">Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): helped to improve our code base by submitting a library function for controlled operations.</span></span> [<span data-ttu-id="b5f7c-488">PR #53</span><span class="sxs-lookup"><span data-stu-id="b5f7c-488">PR #53</span></span>](https://github.com/Microsoft/Quantum/pull/53)
* <span data-ttu-id="b5f7c-489">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111))：修正 @"microsoft.quantum.canon.quantumphaseestimation" 並建立了新的單元測試。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-489">Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): fixed @"microsoft.quantum.canon.quantumphaseestimation" and created new unit tests.</span></span>  [<span data-ttu-id="b5f7c-490">PR #54</span><span class="sxs-lookup"><span data-stu-id="b5f7c-490">PR #54</span></span>](https://github.com/Microsoft/Quantum/pull/54)
* <span data-ttu-id="b5f7c-491">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit))：藉由確定 QuantumSimulator 執行個體已處置，清除了遙傳範例。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-491">Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): cleaned the Teleportation sample by making sure the QuantumSimulator instance is disposed.</span></span> [<span data-ttu-id="b5f7c-492">PR #20</span><span class="sxs-lookup"><span data-stu-id="b5f7c-492">PR #20</span></span>](https://github.com/Microsoft/Quantum/pull/20)

<span data-ttu-id="b5f7c-493">同時也**非常感謝**</span><span class="sxs-lookup"><span data-stu-id="b5f7c-493">Additionally, a big **Thank You!**</span></span> <span data-ttu-id="b5f7c-494">參與商業工程服務小組的 Microsoft 軟體工程師，他們在參加黑客松期間時對我們的文件做出了重要的變更。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-494">to these Microsoft Software Engineers from the Commercial Engineering Services team contributors who made valuable changes to our documentation during their Hackathon.</span></span>  <span data-ttu-id="b5f7c-495">他們的變更我們所有人大幅提升了定義的明確性和上線體驗：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-495">Their changes vastly improved the clarity and onboarding experience for all of us:</span></span>
* <span data-ttu-id="b5f7c-496">Sascha Corti</span><span class="sxs-lookup"><span data-stu-id="b5f7c-496">Sascha Corti</span></span>
* <span data-ttu-id="b5f7c-497">Mihaela Curmei</span><span class="sxs-lookup"><span data-stu-id="b5f7c-497">Mihaela Curmei</span></span>
* <span data-ttu-id="b5f7c-498">John Donnelly</span><span class="sxs-lookup"><span data-stu-id="b5f7c-498">John Donnelly</span></span>
* <span data-ttu-id="b5f7c-499">Kirill Logachev</span><span class="sxs-lookup"><span data-stu-id="b5f7c-499">Kirill Logachev</span></span>
* <span data-ttu-id="b5f7c-500">Jan Pospisil</span><span class="sxs-lookup"><span data-stu-id="b5f7c-500">Jan Pospisil</span></span>
* <span data-ttu-id="b5f7c-501">Anita Ramanan</span><span class="sxs-lookup"><span data-stu-id="b5f7c-501">Anita Ramanan</span></span>
* <span data-ttu-id="b5f7c-502">Frances Tibble</span><span class="sxs-lookup"><span data-stu-id="b5f7c-502">Frances Tibble</span></span>
* <span data-ttu-id="b5f7c-503">Alessandro Vozza</span><span class="sxs-lookup"><span data-stu-id="b5f7c-503">Alessandro Vozza</span></span>

### <a name="update-existing-projects"></a><span data-ttu-id="b5f7c-504">更新現有的專案</span><span class="sxs-lookup"><span data-stu-id="b5f7c-504">Update existing projects</span></span>

<span data-ttu-id="b5f7c-505">此版本具完整的回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-505">This release is fully backwards compatible.</span></span> <span data-ttu-id="b5f7c-506">只要將專案中的 nuget 套件更新為 `0.2.1806.1503-preview` 版，並執行**完整重建**，即可確定所有中繼檔案都會重新產生。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-506">Just update the nuget pakages in your projects to version `0.2.1806.1503-preview` and do a **full rebuild** to make sure all intermediate files are regenerated.</span></span>

<span data-ttu-id="b5f7c-507">在 Visual Studio 中，依照關於[更新套件](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package)的一般指示操作。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-507">From Visual Studio, follow the normal instructions on how to [update a package](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).</span></span>

<span data-ttu-id="b5f7c-508">若要更新命令列的專案範本，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-508">To update project templates for the command line, run the following command:</span></span>
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

<span data-ttu-id="b5f7c-509">執行此命令後，任何使用 `dotnet new <project-type> -lang Q#` 建立的新專案都會自動使用此版本的 Quantum Development Kit。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-509">After running this command, any new projects created using `dotnet new <project-type> -lang Q#` will automatically use this version of the Quantum Development Kit.</span></span>

<span data-ttu-id="b5f7c-510">若要更新現有的專案以使用最新版本，請從各個專案的目錄中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-510">To update an existing project to use the newest version, run the following command from within the directory for each project:</span></span>

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

<span data-ttu-id="b5f7c-511">如果現有的專案也使用 XUnit 整合進行單元測試，則也可以使用類似的命令來更新該套件：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-511">If an existing project also uses XUnit integration for unit testing, then a similar command can be used to update that package as well:</span></span>
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

<span data-ttu-id="b5f7c-512">根據您的測試專案所使用的 XUnit 版本，您可能也需要將 XUnit 更新為 2.3.1：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-512">Depending on the version of XUnit that your test project uses, you may also need to update XUnit to 2.3.1:</span></span>
```
dotnet add package xunit -v "2.3.1" 
```

<span data-ttu-id="b5f7c-513">更新之後，請務必執行下列動作，以移除舊版所產生的所有暫存檔案：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-513">After the update, make sure you remove all temporary files generated by the previous version by doing:</span></span>
```
dotnet clean 
```

### <a name="known-issues"></a><span data-ttu-id="b5f7c-514">已知問題</span><span class="sxs-lookup"><span data-stu-id="b5f7c-514">Known Issues</span></span>

<span data-ttu-id="b5f7c-515">沒有其他已知問題需要報告。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-515">No aditional known issues to report.</span></span>


## <a name="version-0218022202"></a><span data-ttu-id="b5f7c-516">0\.2.1802.2202 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-516">Version 0.2.1802.2202</span></span>

<span data-ttu-id="b5f7c-517">*發行日期：2018 年 2 月 26 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-517">*Release date: February 26, 2018*</span></span>

<span data-ttu-id="b5f7c-518">此版本提供在更多平台上進行開發的支援、語言互通性，和效能的強化。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-518">This release brings support for development on more platforms, language interoperability, and performance enhancements.</span></span> <span data-ttu-id="b5f7c-519">具體來說：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-519">Specifically:</span></span>

- <span data-ttu-id="b5f7c-520">支援以 macOS 和 Linux 為基礎的開發。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-520">Support for macOS- and Linux-based development.</span></span> 
- <span data-ttu-id="b5f7c-521">.NET Core 相容性，包括對 Visual Studio Code 的跨平台支援。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-521">.NET Core compatibility, including support for Visual Studio Code across platforms.</span></span>
- <span data-ttu-id="b5f7c-522">Quantum Development Kit 程式庫的完整開放原始碼授權。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-522">A full Open Source license for the Quantum Development Kit Libraries.</span></span>
- <span data-ttu-id="b5f7c-523">針對需要 20 個或更多量子位元的專案改善了模擬器效能。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-523">Improved simulator performance on projects requiring 20 or more qubits.</span></span>
- <span data-ttu-id="b5f7c-524">與 Python 語言的互通性 (在 Windows 上可使用預覽版本)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-524">Interoperability with the Python language (preview release available on Windows).</span></span>

### <a name="net-editions"></a><span data-ttu-id="b5f7c-525">.NET 版本</span><span class="sxs-lookup"><span data-stu-id="b5f7c-525">.NET Editions</span></span>

<span data-ttu-id="b5f7c-526">.NET 平台有兩種不同的版本可供使用：隨附於 Windows 的 .NET Framework，以及 Windows、macOS 和 Linux 上提供的開放原始碼 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-526">The .NET platform is available through two different editions, the .NET Framework that is provided with Windows, and the open-source .NET Core that is available on Windows, macOS and Linux.</span></span>
<span data-ttu-id="b5f7c-527">在此版本中，Quantum Development Kit 大部分的組件均以 .NET Standard 程式庫的形式提供，這是 Framework 和 Core 通用的一組類別。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-527">With this release, most parts of the Quantum Development Kit are provided as libraries for .NET Standard, the set of classes common to both Framework and Core.</span></span>
<span data-ttu-id="b5f7c-528">這些程式庫因而可與最新版本的 .NET Framework 或 .NET Core 相容。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-528">These libraries are therefore compatible with recent versions of either .NET Framework or .NET Core.</span></span>

<span data-ttu-id="b5f7c-529">因此，為了確保使用 Quantum Development Kit 撰寫的專案能有最高的可攜性，我們建議，使用 Quantum Development Kit 撰寫的程式庫專案應以 .NET Standard 為目標，而主控台應用程式則以 .NET Core 為目標。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-529">Thus, to help ensure that projects written using the Quantum Development Kit are as portable as possible, we recommend that library projects written using the Quantum Development Kit target .NET Standard, while console applications target .NET Core.</span></span>
<span data-ttu-id="b5f7c-530">由於舊版的 Quantum Development Kit 僅支援 .NET Framework，因此您可能需要移轉現有的專案；如需如何執行此作業的詳細資訊，請參閱下文。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-530">Since previous releases of the Quantum Development Kit only supported .NET Framework, you may need to migrate your existing projects; see below for details on how to do this.</span></span>

### <a name="project-migration"></a><span data-ttu-id="b5f7c-531">專案移轉</span><span class="sxs-lookup"><span data-stu-id="b5f7c-531">Project Migration</span></span>

<span data-ttu-id="b5f7c-532">使用舊版 Quantum Development Kit 建立的專案仍可運作，只要您未更新其中使用的 NuGet 套件即可。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-532">Projects created using previous versions of Quantum Development Kit will still work, as long as you don't update the NuGet packages used in them.</span></span> <span data-ttu-id="b5f7c-533">若要將現有的程式碼移轉至新版本，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-533">To migrate existing code to the new version, perform the following steps:</span></span>
1. <span data-ttu-id="b5f7c-534">使用正確類型的專案範本來建立新的 .NET Core 專案 Q# (應用程式、程式庫或測試專案) 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-534">Create a new .NET Core project using the right type of Q# project template (Application, Library or Test Project).</span></span>
2. <span data-ttu-id="b5f7c-535">將舊專案中現有的 .qs 和 .cs/.fs 檔案複製到新專案 (使用 [新增] > [現有項目])。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-535">Copy existing .qs and .cs/.fs files from the old project to the new project (using Add > Existing Item).</span></span> <span data-ttu-id="b5f7c-536">請勿複製 AssemblyInfo.cs 檔案。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-536">Do not copy the AssemblyInfo.cs file.</span></span>
3. <span data-ttu-id="b5f7c-537">建置並執行新的專案。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-537">Build and run the new project.</span></span>

<span data-ttu-id="b5f7c-538">請注意，命名空間 Microsoft.Quantum.Canon 中的作業 RandomWalkPhaseEstimation 已移至 [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) 存放庫的命名空間 Microsoft.Research.Quantum.RandomWalkPhaseEstimation 中。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-538">Please note that the operation RandomWalkPhaseEstimation from the namespace Microsoft.Quantum.Canon was moved into the namespace Microsoft.Research.Quantum.RandomWalkPhaseEstimation in the [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) repository.</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5f7c-539">已知問題</span><span class="sxs-lookup"><span data-stu-id="b5f7c-539">Known Issues</span></span>

- <span data-ttu-id="b5f7c-540">的 `--filter` 選項 `dotnet test` 無法針對以撰寫的測試正確運作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-540">The `--filter` option to `dotnet test` does not work correctly for tests written in Q#.</span></span>
  <span data-ttu-id="b5f7c-541">因此，無法在 Visual Studio Code 中執行個別單元測試;建議您 `dotnet test` 在命令提示字元中使用，以重新執行所有測試。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-541">As a result, individual unit tests cannot be run in Visual Studio Code; we recommend using `dotnet test` at the command prompt to re-run all tests.</span></span>

## <a name="version-0118011707"></a><span data-ttu-id="b5f7c-542">0\.1.1801.1707 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-542">Version 0.1.1801.1707</span></span>

<span data-ttu-id="b5f7c-543">*發行日期：2018 年 1 月 18 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-543">*Release date: January 18, 2018*</span></span>

<span data-ttu-id="b5f7c-544">此版本修正了社群回報的某些問題。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-544">This release fixes some issues reported by the community.</span></span> <span data-ttu-id="b5f7c-545">分別是：</span><span class="sxs-lookup"><span data-stu-id="b5f7c-545">Namely:</span></span>

- <span data-ttu-id="b5f7c-546">模擬器現已可與早期不具 AVX 功能的 CPU 搭配運作。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-546">The simulator now works with early non-AVX-enabled CPUs.</span></span>
- <span data-ttu-id="b5f7c-547">區域小數設定不會導致剖析器 Q# 失敗。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-547">Regional decimal settings will not cause the Q# parser to fail.</span></span>
- <span data-ttu-id="b5f7c-548">`SignD` 基本作業現在會傳回 `Int`，而不是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-548">`SignD` primitive operation now returns `Int` rather than `Double`.</span></span>


## <a name="version-011712901"></a><span data-ttu-id="b5f7c-549">0\.1.1712.901 版</span><span class="sxs-lookup"><span data-stu-id="b5f7c-549">Version 0.1.1712.901</span></span>

<span data-ttu-id="b5f7c-550">*發行日期：2017 年 12 月 11 日*</span><span class="sxs-lookup"><span data-stu-id="b5f7c-550">*Release date: December 11, 2017*</span></span>

### <a name="known-issues"></a><span data-ttu-id="b5f7c-551">已知問題</span><span class="sxs-lookup"><span data-stu-id="b5f7c-551">Known Issues</span></span>

#### <a name="hardware-and-software-requirements"></a><span data-ttu-id="b5f7c-552">硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="b5f7c-552">Hardware and Software Requirements</span></span>

- <span data-ttu-id="b5f7c-553">Quantum Development Kit 隨附的模擬器需要 Microsoft Windows 的 64 位元安裝才能執行。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-553">The simulator included with the Quantum Development Kit requires a 64-bit installation of Microsoft Windows to run.</span></span>
- <span data-ttu-id="b5f7c-554">與 Quantum Development Kit 一起安裝的 Microsoft 量子模擬器會使用 Advance Vector Extensions (AVX)，且需要具有 AVX 功能的 CPU。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-554">Microsoft's quantum simulator, installed with the Quantum Development Kit, utilizes Advanced Vector Extensions (AVX), and requires an AVX-enabled CPU.</span></span> <span data-ttu-id="b5f7c-555">2011 年第 1 季推出的 Intel 處理器 (Sandy Bridge) 或更新版本可支援 AVX。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-555">Intel processors shipped in Q1 2011 (Sandy Bridge) or later support AVX.</span></span> <span data-ttu-id="b5f7c-556">我們正在評估對舊型 CPU 的支援，後續可能會發佈相關詳情。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-556">We are evaluating support for earlier CPUs and may announce details at a later time.</span></span>

#### <a name="project-creation"></a><span data-ttu-id="b5f7c-557">專案建立</span><span class="sxs-lookup"><span data-stu-id="b5f7c-557">Project Creation</span></span>

- <span data-ttu-id="b5f7c-558">當您建立將使用的方案 ( .sln) 時 Q# ，方案必須高於方案中的每個專案 ( .csproj) 的一個目錄。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-558">When creating a solution (.sln) that will use Q#, the solution must be one directory higher than each project (.csproj) in the solution.</span></span> <span data-ttu-id="b5f7c-559">在建立新的解決方案時，只要確實核取 [新增專案] 對話方塊上的 [建立解決方案的目錄] 核取方塊，即可符合此條件。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-559">When creating a new solution, this can be accomplished by making sure that the "Create directory for solution" checkbox on the "New Project" dialog box is checked.</span></span> <span data-ttu-id="b5f7c-560">若未執行此動作，則必須手動安裝 Quantum Development Kit NuGet 套件。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-560">If this is not done, the Quantum Development Kit NuGet packages will need to be installed manually.</span></span>

#### Q#

- <span data-ttu-id="b5f7c-561">Intellisense 不會顯示適當的程式 Q# 代碼錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-561">Intellisense does not display proper errors for Q# code.</span></span> <span data-ttu-id="b5f7c-562">請確定您在 Visual Studio 錯誤清單中顯示組建錯誤，以查看正確的 Q# 錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-562">Make sure that you are displaying Build errors in the Visual Studio Error List to see correct Q# errors.</span></span> <span data-ttu-id="b5f7c-563">另請注意，在 Q# 您完成組建之前，不會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-563">Also note that Q# errors will not show up until after you've done a build.</span></span>
- <span data-ttu-id="b5f7c-564">在部分應用程式中使用可變動陣列可能會導致非預期的行為。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-564">Using a mutable array in a partial application may lead to unexpected behavior.</span></span>
- <span data-ttu-id="b5f7c-565">將不可變陣列繫結至可變動陣列 (讓 a = b，其中 b 是可變動陣列)，可能會導致非預期的行為。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-565">Binding an immutable array to a mutable array (let a = b, where b is a mutable array) may lead to unexpected behavior.</span></span>
- <span data-ttu-id="b5f7c-566">程式碼剖析、程式碼涵蓋範圍和其他 VS 外掛程式不一定會 Q# 正確地計算行數和區塊數。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-566">Profiling, code coverage and other VS plugins may not always count Q# lines and blocks accurately.</span></span>
- <span data-ttu-id="b5f7c-567">Q#編譯器不會驗證內插字串。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-567">The Q# compiler does not validate interpolated strings.</span></span> <span data-ttu-id="b5f7c-568">您可以藉由拼錯變數名稱或在內插字串中使用運算式，來建立 c # 編譯錯誤 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-568">It is possible to create C# compilation errors by misspelling variable names or using expressions in Q# interpolated strings.</span></span>

#### <a name="simulation"></a><span data-ttu-id="b5f7c-569">模擬</span><span class="sxs-lookup"><span data-stu-id="b5f7c-569">Simulation</span></span>

- <span data-ttu-id="b5f7c-570">量子模擬器會使用 OpenMP 來平行處理所需的線性代數。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-570">The Quantum Simulator uses OpenMP to parallelize the linear algebra required.</span></span> <span data-ttu-id="b5f7c-571">根據預設，OpenMP 會使用所有可用的硬體執行緒，這表示具有少量量子位元的程式常會執行緩慢，因為所需的協調會阻礙實際的工作。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-571">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="b5f7c-572">將環境變數 OMP_NUM_THREADS 設定為較小的數值，即可修正此問題。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-572">This can be fixed by setting the environment variable OMP_NUM_THREADS to a small number.</span></span> <span data-ttu-id="b5f7c-573">一個非常粗略的經驗法則是，1 個執行緒最多可用於 4 個量子位元，而其後的每個量子位元則應使用一個額外的執行緒，但這主要取決於您的演算法。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-573">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

#### <a name="debugging"></a><span data-ttu-id="b5f7c-574">偵錯</span><span class="sxs-lookup"><span data-stu-id="b5f7c-574">Debugging</span></span>

- <span data-ttu-id="b5f7c-575">) 中的 F11 (步驟無法在程式碼中運作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-575">F11 (step in) doesn't work in Q# code.</span></span>
- <span data-ttu-id="b5f7c-576">在 Q# 程式碼中以中斷點或單一步驟暫停的程式碼反白顯示，有時會是不正確的。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-576">Code highlighting in Q# code at a breakpoint or single-step pause is sometimes inaccurate.</span></span> <span data-ttu-id="b5f7c-577">醒目提示的程式碼行是正確的，但有時候，醒目提示的開頭和結尾會位於行中不正確的資料行上。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-577">The correct line will be highlighted, but sometimes the highlight will start and end at incorrect columns on the line.</span></span>

#### <a name="testing"></a><span data-ttu-id="b5f7c-578">測試</span><span class="sxs-lookup"><span data-stu-id="b5f7c-578">Testing</span></span>

- <span data-ttu-id="b5f7c-579">測試必須在64位模式下執行。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-579">Tests must be run in 64-bit mode.</span></span> <span data-ttu-id="b5f7c-580">如果您的測試失敗並出現 BadImageFormatException，請移至 [測試] 功能表，然後選取 [測試設定] > [預設處理器架構] > [X64]。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-580">If your tests are failing with a BadImageFormatException, go to the Test menu and select Test Settings > Default Processor Architecture > X64.</span></span>
- <span data-ttu-id="b5f7c-581">有些測試的執行會非常耗時 (最多可能需要 5 分鐘，視您的電腦而定)。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-581">Some tests take a long time (possibly as much as 5 minutes depending on your computer) to run.</span></span> <span data-ttu-id="b5f7c-582">這是正常的，因為有些測試會使用超過 20 個量子位元；我們最大的測試目前以 23 個量子位元執行。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-582">This is normal, as some use over twenty qubits; our largest test currently runs on 23 qubits.</span></span>

#### <a name="samples"></a><span data-ttu-id="b5f7c-583">範例</span><span class="sxs-lookup"><span data-stu-id="b5f7c-583">Samples</span></span>

- <span data-ttu-id="b5f7c-584">在某些電腦上，某些小型樣本可能會執行緩慢，除非環境變數 OMP_NUM_THREADS 設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-584">On some machines, some small samples may run slowly unless the environment variable OMP_NUM_THREADS is set to "1".</span></span> <span data-ttu-id="b5f7c-585">另請參閱「模擬」下的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-585">See also the release note under "Simulation".</span></span>

#### <a name="libraries"></a><span data-ttu-id="b5f7c-586">程式庫</span><span class="sxs-lookup"><span data-stu-id="b5f7c-586">Libraries</span></span>

- <span data-ttu-id="b5f7c-587">既有的隱含假設是，傳至作業中不同引數的量子位元是相異的。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-587">There is an implicit assumption that the qubits passed to an operation in different arguments are all distinct.</span></span> <span data-ttu-id="b5f7c-588">例如，所有的程式庫作業 (以及所有模擬器) 都會假設傳至受控 NOT 的兩個量子位元是不同的。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-588">For instance, all of the library operations (and all of the simulators) assume that the two qubits passed to a controlled NOT are different qubits.</span></span> <span data-ttu-id="b5f7c-589">若違反此假設，可能會導致無法預期的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-589">Violating this assumption may lead to unpredictable unexpected.</span></span> <span data-ttu-id="b5f7c-590">您可以使用量子電腦追蹤模擬器來測試這種情況。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-590">It is possible to test for this using the quantum computer tracer simulator.</span></span>
- <span data-ttu-id="b5f7c-591">Microsoft.Quantum.Bind 函式不一定在各種情況下都會如預期運作。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-591">The Microsoft.Quantum.Bind function may not act as expected in all cases.</span></span>
- <span data-ttu-id="b5f7c-592">在 Microsoft.Quantum.Extensions.Math 命名空間中，SignD 函式會傳回雙精度浮點數 (而非整數)，但基礎 System.Math.Sign 函式則一律會傳回整數。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-592">In the Microsoft.Quantum.Extensions.Math namespace, the SignD function returns a Double rather than an Int, although the underlying System.Math.Sign function always returns an integer.</span></span> <span data-ttu-id="b5f7c-593">您可以將結果與 1.0、-1.0 和 0.0 進行比較，因為這些雙精度浮點數具有相同的二進位表示法。</span><span class="sxs-lookup"><span data-stu-id="b5f7c-593">It is safe to compare the result against 1.0, -1.0, and 0.0, since these doubles all have exact binary representations.</span></span>
