---
title: 'IQ # 魔術命令'
author: rmshaffer
uid: microsoft.quantum.iqsharp.magic-ref.index
ms.author: rmshaffer
ms.date: 08/25/2020
ms.topic: article
ms.openlocfilehash: d6bf8407e40be092689b38cf90514c88f798cc2f
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "88862955"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="93ad6-102">IQ # 魔術命令</span><span class="sxs-lookup"><span data-stu-id="93ad6-102">IQ# Magic Commands</span></span>
| <span data-ttu-id="93ad6-103">魔術命令</span><span class="sxs-lookup"><span data-stu-id="93ad6-103">Magic Command</span></span> | <span data-ttu-id="93ad6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="93ad6-104">Summary</span></span> |
|---------------|---------|
| [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect) | <span data-ttu-id="93ad6-105">連線到 Azure Quantum 工作區，或顯示目前的連線狀態。</span><span class="sxs-lookup"><span data-stu-id="93ad6-105">Connects to an Azure Quantum workspace or displays current connection status.</span></span> |
| [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute) | <span data-ttu-id="93ad6-106">在 Azure Quantum 工作區中執行作業。</span><span class="sxs-lookup"><span data-stu-id="93ad6-106">Executes a job in an Azure Quantum workspace.</span></span> |
| [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs) | <span data-ttu-id="93ad6-107">在目前的 Azure Quantum 工作區中顯示作業清單。</span><span class="sxs-lookup"><span data-stu-id="93ad6-107">Displays a list of jobs in the current Azure Quantum workspace.</span></span> |
| [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output) | <span data-ttu-id="93ad6-108">在目前的 Azure Quantum 工作區中顯示作業的結果。</span><span class="sxs-lookup"><span data-stu-id="93ad6-108">Displays results for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status) | <span data-ttu-id="93ad6-109">在目前的 Azure Quantum 工作區中顯示作業的狀態。</span><span class="sxs-lookup"><span data-stu-id="93ad6-109">Displays status for a job in the current Azure Quantum workspace.</span></span> |
| [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit) | <span data-ttu-id="93ad6-110">將作業提交至 Azure Quantum 工作區。</span><span class="sxs-lookup"><span data-stu-id="93ad6-110">Submits a job to an Azure Quantum workspace.</span></span> |
| [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target) | <span data-ttu-id="93ad6-111">在 Azure Quantum 工作區中設定或顯示 Q# 作業提交的作用中執行目標。</span><span class="sxs-lookup"><span data-stu-id="93ad6-111">Sets or displays the active execution target for Q# job submission in an Azure Quantum workspace.</span></span> |
| [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata) | <span data-ttu-id="93ad6-112">檢查單一 kata 測試的參考實作。</span><span class="sxs-lookup"><span data-stu-id="93ad6-112">Checks the reference implementation for a single kata's test.</span></span> |
| [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge) | <span data-ttu-id="93ad6-113">從指定的 .yaml 檔案載入並傳回 Broombridge 的電子結構問題表示法。</span><span class="sxs-lookup"><span data-stu-id="93ad6-113">Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span> |
| [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode) | <span data-ttu-id="93ad6-114">將 fermion Hamiltonian 編碼成 Q # 可使用的格式。</span><span class="sxs-lookup"><span data-stu-id="93ad6-114">Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span> |
| [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms) | <span data-ttu-id="93ad6-115">將字詞新增至 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="93ad6-115">Adds terms to a fermion Hamiltonian.</span></span> |
| [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load) | <span data-ttu-id="93ad6-116">載入電子結構問題的 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="93ad6-116">Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="93ad6-117">問題是從檔案載入，或做為引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="93ad6-117">The problem is loaded from a file or passed as an argument.</span></span> |
| [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load) | <span data-ttu-id="93ad6-118">載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="93ad6-118">Loads Broombridge electronic structure problem and returns selected input state.</span></span> |
| [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config) | <span data-ttu-id="93ad6-119">允許設定或查詢設定選項。</span><span class="sxs-lookup"><span data-stu-id="93ad6-119">Allows setting or querying configuration options.</span></span> |
| [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate) | <span data-ttu-id="93ad6-120">在 ResourcesEstimator 目標電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="93ad6-120">Runs a given function or operation on the ResourcesEstimator target machine.</span></span> |
| [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata) | <span data-ttu-id="93ad6-121">執行單一測試。</span><span class="sxs-lookup"><span data-stu-id="93ad6-121">Executes a single test.</span></span> |
| [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic) | <span data-ttu-id="93ad6-122">傳回所有目前可用的魔術命令清單。</span><span class="sxs-lookup"><span data-stu-id="93ad6-122">Returns a list of all currently available magic commands.</span></span> |
| [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen) | <span data-ttu-id="93ad6-123">列出目前開啟的命名空間及其別名。</span><span class="sxs-lookup"><span data-stu-id="93ad6-123">Lists currently opened namespaces and their aliases.</span></span> |
| [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package) | <span data-ttu-id="93ad6-124">提供載入 NuGet 套件的功能。</span><span class="sxs-lookup"><span data-stu-id="93ad6-124">Provides the ability to load a NuGet package.</span></span> |
| [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance) | <span data-ttu-id="93ad6-125">報告此核心的目前效能計量。</span><span class="sxs-lookup"><span data-stu-id="93ad6-125">Reports current performance metrics for this kernel.</span></span> |
| [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project) | <span data-ttu-id="93ad6-126">提供可檢視或新增 Q # 專案參考的功能。</span><span class="sxs-lookup"><span data-stu-id="93ad6-126">Provides the ability to view or add Q# project references.</span></span> |
| [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate) | <span data-ttu-id="93ad6-127">在 QuantumSimulator 目標電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="93ad6-127">Runs a given function or operation on the QuantumSimulator target machine.</span></span> |
| [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) | <span data-ttu-id="93ad6-128">在 ToffoliSimulator 目標電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="93ad6-128">Runs a given function or operation on the ToffoliSimulator target machine.</span></span> |
| [`%trace`](xref:microsoft.quantum.iqsharp.magic-ref.trace) | <span data-ttu-id="93ad6-129">視覺化指定作業的執行路徑。</span><span class="sxs-lookup"><span data-stu-id="93ad6-129">Visualizes the execution path of the given operation.</span></span> |
| [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who) | <span data-ttu-id="93ad6-130">列出目前工作階段中可使用的 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="93ad6-130">Lists the Q# operations available in the current session.</span></span> |
| [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace) | <span data-ttu-id="93ad6-131">提供與目前工作區相關的動作。</span><span class="sxs-lookup"><span data-stu-id="93ad6-131">Provides actions related to the current workspace.</span></span> |
