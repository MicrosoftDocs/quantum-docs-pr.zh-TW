---
title: 我的 Q# 神奇命令
description: Q#使用 Jupyter 筆記本的 I 魔術命令快速參考頁面 Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863688"
---
# <a name="ino-locq-magic-commands"></a><span data-ttu-id="7b19b-103">我的 Q# 神奇命令</span><span class="sxs-lookup"><span data-stu-id="7b19b-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="7b19b-104">一般</span><span class="sxs-lookup"><span data-stu-id="7b19b-104">General</span></span>

- <span data-ttu-id="7b19b-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允許設定或查詢設定選項。</span><span class="sxs-lookup"><span data-stu-id="7b19b-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Allows setting or querying configuration options.</span></span>
- <span data-ttu-id="7b19b-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目的電腦上執行指定的函數或作業。</span><span class="sxs-lookup"><span data-stu-id="7b19b-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Runs a given function or operation on the ResourcesEstimator target machine.</span></span>
- <span data-ttu-id="7b19b-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：傳回所有目前可用魔術命令的清單。</span><span class="sxs-lookup"><span data-stu-id="7b19b-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="7b19b-108">[`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen)：列出目前開啟的命名空間及其別名。</span><span class="sxs-lookup"><span data-stu-id="7b19b-108">[`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Lists currently opened namespaces and their aliases.</span></span>
- <span data-ttu-id="7b19b-109">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供載入 NuGet 套件的功能。</span><span class="sxs-lookup"><span data-stu-id="7b19b-109">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Provides the ability to load a NuGet package.</span></span>
- <span data-ttu-id="7b19b-110">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：報告此核心目前的效能計量。</span><span class="sxs-lookup"><span data-stu-id="7b19b-110">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="7b19b-111">[`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project)：提供可查看或加入 Q# 專案參考的功能。</span><span class="sxs-lookup"><span data-stu-id="7b19b-111">[`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Provides the ability to view or add Q# project references.</span></span> 
- <span data-ttu-id="7b19b-112">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目的電腦上執行指定的函數或作業。</span><span class="sxs-lookup"><span data-stu-id="7b19b-112">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="7b19b-113">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目的電腦上執行指定的函數或作業。</span><span class="sxs-lookup"><span data-stu-id="7b19b-113">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Runs a given function or operation on the ToffoliSimulator target machine.</span></span>
- <span data-ttu-id="7b19b-114">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出 Q# 目前會話中的可用作業。</span><span class="sxs-lookup"><span data-stu-id="7b19b-114">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lists the Q# operations available in the current session.</span></span>
- <span data-ttu-id="7b19b-115">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供與目前工作區相關的動作。</span><span class="sxs-lookup"><span data-stu-id="7b19b-115">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Provides actions related to the current workspace.</span></span>

### <a name="azure-quantum-integration"></a><span data-ttu-id="7b19b-116">Azure Quantum 整合</span><span class="sxs-lookup"><span data-stu-id="7b19b-116">Azure Quantum integration</span></span>

- <span data-ttu-id="7b19b-117">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：連接到 Azure Quantum 工作區，或顯示目前的連接狀態。</span><span class="sxs-lookup"><span data-stu-id="7b19b-117">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Connects to an Azure Quantum workspace or displays current connection status.</span></span>
- <span data-ttu-id="7b19b-118">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：在 Azure Quantum 工作區中執行工作。</span><span class="sxs-lookup"><span data-stu-id="7b19b-118">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Executes a job in an Azure Quantum workspace.</span></span>
- <span data-ttu-id="7b19b-119">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：顯示目前 Azure Quantum 工作區中的作業清單。</span><span class="sxs-lookup"><span data-stu-id="7b19b-119">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Displays a list of jobs in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="7b19b-120">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：顯示目前 Azure Quantum 工作區中工作的結果。</span><span class="sxs-lookup"><span data-stu-id="7b19b-120">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Displays results for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="7b19b-121">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：顯示目前 Azure Quantum 工作區中工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="7b19b-121">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Displays status for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="7b19b-122">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：將作業提交至 Azure Quantum 工作區。</span><span class="sxs-lookup"><span data-stu-id="7b19b-122">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submits a job to an Azure Quantum workspace.</span></span>
- <span data-ttu-id="7b19b-123">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)：設定或顯示 Q# Azure Quantum 工作區中的作業提交使用中的執行目標。</span><span class="sxs-lookup"><span data-stu-id="7b19b-123">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span>

### <a name="chemistry-from-microsoftquantumchemistry-package"></a><span data-ttu-id="7b19b-124">來自 Microsoft 量子化學套件的化學 () </span><span class="sxs-lookup"><span data-stu-id="7b19b-124">Chemistry (from Microsoft.Quantum.Chemistry package)</span></span>

- <span data-ttu-id="7b19b-125">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：從指定的 yaml 檔案載入並傳回 Broombridge 的電子結構問題表示。</span><span class="sxs-lookup"><span data-stu-id="7b19b-125">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="7b19b-126">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：將 fermion Hamiltonian 編碼為可使用的格式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="7b19b-126">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="7b19b-127">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：將詞彙新增至 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="7b19b-127">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="7b19b-128">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：針對電子結構問題載入 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="7b19b-128">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="7b19b-129">問題是從檔案載入，或做為引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="7b19b-129">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="7b19b-130">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="7b19b-130">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="katas-from-microsoftquantumkatas-package"></a><span data-ttu-id="7b19b-131">Katas (Katas 套件) </span><span class="sxs-lookup"><span data-stu-id="7b19b-131">Katas (from Microsoft.Quantum.Katas package)</span></span>

- <span data-ttu-id="7b19b-132">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：執行單一測試，並報告測試是否成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="7b19b-132">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="7b19b-133">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：檢查單一 kata 測試的參考執行。</span><span class="sxs-lookup"><span data-stu-id="7b19b-133">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="7b19b-134">具體而言，它會將單一工作的參考實作為儲存格，並報告測試是否成功通過。</span><span class="sxs-lookup"><span data-stu-id="7b19b-134">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
