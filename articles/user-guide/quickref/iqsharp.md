---
title: 'IQ # 魔術命令'
description: '使用 Q # Jupyter 筆記本的 IQ # 魔術命令快速參考頁面'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431014"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="3c69b-103">IQ # 魔術命令</span><span class="sxs-lookup"><span data-stu-id="3c69b-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="3c69b-104">一般</span><span class="sxs-lookup"><span data-stu-id="3c69b-104">General</span></span>

- <span data-ttu-id="3c69b-105">`%config`：設定或取得設定喜好設定。</span><span class="sxs-lookup"><span data-stu-id="3c69b-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="3c69b-106">`%estimate`：在 QuantumSimulator 目的電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="3c69b-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="3c69b-107">`%lsmagic`：傳回所有目前可用的魔術命令清單。</span><span class="sxs-lookup"><span data-stu-id="3c69b-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="3c69b-108">`%package`：提供載入 Nuget 封裝的功能。</span><span class="sxs-lookup"><span data-stu-id="3c69b-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="3c69b-109">`%performance`：報告此核心的目前效能計量。</span><span class="sxs-lookup"><span data-stu-id="3c69b-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="3c69b-110">`%simulate`：在 QuantumSimulator 目的電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="3c69b-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="3c69b-111">`%toffoli`：在 ToffoliSimulator 模擬器目的電腦上執行指定的函式或作業。</span><span class="sxs-lookup"><span data-stu-id="3c69b-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="3c69b-112">`%who`：提供與目前工作區相關的動作。</span><span class="sxs-lookup"><span data-stu-id="3c69b-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="3c69b-113">`%workspace`：傳回目前會話中定義的所有作業和函式清單，不論是以互動方式或從目前工作區載入。</span><span class="sxs-lookup"><span data-stu-id="3c69b-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="3c69b-114">化學</span><span class="sxs-lookup"><span data-stu-id="3c69b-114">Chemistry</span></span>

- <span data-ttu-id="3c69b-115">`%chemistry.broombridge`：從指定的 yaml 檔案載入並傳回 Broombridge 的電子結構問題標記法。</span><span class="sxs-lookup"><span data-stu-id="3c69b-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="3c69b-116">`%chemistry.encode`：將 fermion Hamiltonian 編碼成 Q # 可使用的格式。</span><span class="sxs-lookup"><span data-stu-id="3c69b-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="3c69b-117">`%chemistry.fh.add_terms`：將詞彙新增至 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="3c69b-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="3c69b-118">`%chemistry.fh.load`：載入電子結構問題的 fermion Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="3c69b-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="3c69b-119">問題是從檔案載入，或做為引數傳遞。</span><span class="sxs-lookup"><span data-stu-id="3c69b-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="3c69b-120">`%chemistry.inputstate.load`：載入 Broombridge 電子結構問題，並傳回選取的輸入狀態。</span><span class="sxs-lookup"><span data-stu-id="3c69b-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="3c69b-121">Katas 套件中的</span><span class="sxs-lookup"><span data-stu-id="3c69b-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="3c69b-122">`%kata`：執行單一測試，並報告測試是否成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="3c69b-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="3c69b-123">`%check_kata`：檢查單一 kata 之測試的參考執行。</span><span class="sxs-lookup"><span data-stu-id="3c69b-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="3c69b-124">具體來說，它會將單一工作的參考實替換成儲存格，並報告測試是否成功傳遞。</span><span class="sxs-lookup"><span data-stu-id="3c69b-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
