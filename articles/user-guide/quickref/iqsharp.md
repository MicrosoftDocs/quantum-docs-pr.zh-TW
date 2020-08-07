---
title: 我的 Q# 神奇命令
description: Q#Jupyter 筆記本的我魔術命令快速參考 Q# 頁面
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb7b5543ef9222e6bab2b1cbbc7e3ebb54863438
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867976"
---
# <a name="ino-locq-magic-commands"></a><span data-ttu-id="78e73-103">我的 Q# 神奇命令</span><span class="sxs-lookup"><span data-stu-id="78e73-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="78e73-104">一般</span><span class="sxs-lookup"><span data-stu-id="78e73-104">General</span></span>

- <span data-ttu-id="78e73-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config)：允許設定或查詢設定選項。</span><span class="sxs-lookup"><span data-stu-id="78e73-105">[`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Allows setting or querying configuration options.</span></span>
- <span data-ttu-id="78e73-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate)：在 ResourcesEstimator 目的電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="78e73-106">[`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Runs a given function or operation on the ResourcesEstimator target machine.</span></span>
- <span data-ttu-id="78e73-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic)：傳回所有目前可用的魔術命令清單。</span><span class="sxs-lookup"><span data-stu-id="78e73-107">[`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="78e73-108">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package)：提供載入 NuGet 封裝的功能。</span><span class="sxs-lookup"><span data-stu-id="78e73-108">[`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Provides the ability to load a NuGet package.</span></span>
- <span data-ttu-id="78e73-109">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance)：報告此核心的目前效能計量。</span><span class="sxs-lookup"><span data-stu-id="78e73-109">[`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="78e73-110">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate)：在 QuantumSimulator 目的電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="78e73-110">[`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="78e73-111">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli)：在 ToffoliSimulator 目的電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="78e73-111">[`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Runs a given function or operation on the ToffoliSimulator target machine.</span></span>
- <span data-ttu-id="78e73-112">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who)：列出 Q# 目前會話中可用的作業。</span><span class="sxs-lookup"><span data-stu-id="78e73-112">[`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lists the Q# operations available in the current session.</span></span>
- <span data-ttu-id="78e73-113">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace)：提供與目前工作區相關的動作。</span><span class="sxs-lookup"><span data-stu-id="78e73-113">[`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Provides actions related to the current workspace.</span></span>

### <a name="azure-quantum-integration"></a><span data-ttu-id="78e73-114">Azure 量子整合</span><span class="sxs-lookup"><span data-stu-id="78e73-114">Azure Quantum integration</span></span>

- <span data-ttu-id="78e73-115">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect)：連接到 Azure 配量工作區，或顯示目前的線上狀態。</span><span class="sxs-lookup"><span data-stu-id="78e73-115">[`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Connects to an Azure Quantum workspace or displays current connection status.</span></span>
- <span data-ttu-id="78e73-116">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute)：在 Azure 量子工作區中執行作業。</span><span class="sxs-lookup"><span data-stu-id="78e73-116">[`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Executes a job in an Azure Quantum workspace.</span></span>
- <span data-ttu-id="78e73-117">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs)：顯示目前 Azure 量子工作區中的作業清單。</span><span class="sxs-lookup"><span data-stu-id="78e73-117">[`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Displays a list of jobs in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="78e73-118">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output)：在目前的 Azure 量子工作區中顯示作業的結果。</span><span class="sxs-lookup"><span data-stu-id="78e73-118">[`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Displays results for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="78e73-119">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status)：顯示目前 Azure 配量工作區中作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="78e73-119">[`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Displays status for a job in the current Azure Quantum workspace.</span></span>
- <span data-ttu-id="78e73-120">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit)：將作業提交至 Azure 量子工作區。</span><span class="sxs-lookup"><span data-stu-id="78e73-120">[`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submits a job to an Azure Quantum workspace.</span></span>
- <span data-ttu-id="78e73-121">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target)：設定或顯示 Q# 在 Azure 量子工作區中提交作業的作用中執行目標。</span><span class="sxs-lookup"><span data-stu-id="78e73-121">[`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span>

### <a name="chemistry-from-microsoftquantumchemistry-package"></a><span data-ttu-id="78e73-122">來自 Microsoft. 量子化學套件的化學 () </span><span class="sxs-lookup"><span data-stu-id="78e73-122">Chemistry (from Microsoft.Quantum.Chemistry package)</span></span>

- <span data-ttu-id="78e73-123">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge)：從指定的 yaml 檔案載入並傳回 Broombridge 的電子結構問題標記法。</span><span class="sxs-lookup"><span data-stu-id="78e73-123">[`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="78e73-124">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode)：將 fermion Hamiltonian 編碼為可使用的格式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="78e73-124">[`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="78e73-125">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms)：將詞彙新增至 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="78e73-125">[`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="78e73-126">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load)：載入電子結構問題的 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="78e73-126">[`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="78e73-127">問題是從檔案載入，或做為引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="78e73-127">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="78e73-128">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load)：載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="78e73-128">[`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="katas-from-microsoftquantumkatas-package"></a><span data-ttu-id="78e73-129">Katas 套件中的 Katas () </span><span class="sxs-lookup"><span data-stu-id="78e73-129">Katas (from Microsoft.Quantum.Katas package)</span></span>

- <span data-ttu-id="78e73-130">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata)：執行單一測試，並報告測試是否成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="78e73-130">[`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="78e73-131">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata)：檢查單一 kata 之測試的參考執行。</span><span class="sxs-lookup"><span data-stu-id="78e73-131">[`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="78e73-132">具體來說，它會將單一工作的參考實替換成儲存格，並報告測試是否成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="78e73-132">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
