---
title: 範例 NWChem 量副程式
description: 使用 NWChem 的輸入組，逐步解說取得量子化學模擬的閘道計數範例。
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 986ff2c2ff144c57bd01ddeea0467d0168fd9334
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835752"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="b71d1-103">端對端使用 NWChem</span><span class="sxs-lookup"><span data-stu-id="b71d1-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="b71d1-104">在本文中，您將逐步解說如何從 [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) 輸入組開始取得量子化學模擬的閘道計數範例。</span><span class="sxs-lookup"><span data-stu-id="b71d1-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="b71d1-105">繼續進行此範例之前，請確定您已安裝 Docker， [並遵循安裝和驗證指南](xref:microsoft.quantum.chemistry.concepts.installation)。</span><span class="sxs-lookup"><span data-stu-id="b71d1-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="b71d1-106">其他資訊：</span><span class="sxs-lookup"><span data-stu-id="b71d1-106">For more information:</span></span>
- [<span data-ttu-id="b71d1-107">NWChem 輸入投影片的結構</span><span class="sxs-lookup"><span data-stu-id="b71d1-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="b71d1-108">用於量子開發工具組的輸入組指令</span><span class="sxs-lookup"><span data-stu-id="b71d1-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [<span data-ttu-id="b71d1-109">安裝化學程式庫和相依性</span><span class="sxs-lookup"><span data-stu-id="b71d1-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="b71d1-110">資源計數</span><span class="sxs-lookup"><span data-stu-id="b71d1-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="b71d1-111">此範例需要 Windows PowerShell Core 才能執行。</span><span class="sxs-lookup"><span data-stu-id="b71d1-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="b71d1-112">下載適用于 Windows、macOS 或 Linux 的 PowerShell Core https://github.com/PowerShell/PowerShell 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="b71d1-113">匯入必要的 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="b71d1-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="b71d1-114">如果您尚未這麼做，請複製 [Microsoft/量子存放庫](https://github.com/Microsoft/Quantum)，其中包含使用量子開發工具組的範例和公用程式：</span><span class="sxs-lookup"><span data-stu-id="b71d1-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="b71d1-115">複製之後 `Microsoft/Quantum` ，請在 `cd` 資料夾中執行，並匯 `utilities/` 入 PowerShell 模組以使用 Docker 和 NWChem：</span><span class="sxs-lookup"><span data-stu-id="b71d1-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="b71d1-116">根據預設，Windows 會防止執行任何腳本或模組做為安全性措施。</span><span class="sxs-lookup"><span data-stu-id="b71d1-116">By default, Windows prevents the running of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="b71d1-117">若要允許 `Invoke-NWChem.psm1` 在 Windows 上執行的模組，您可能需要變更原則。</span><span class="sxs-lookup"><span data-stu-id="b71d1-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the policy.</span></span>
> <span data-ttu-id="b71d1-118">若要這樣做，請執行 `Set-ExecutionPolicy` 下列命令：</span><span class="sxs-lookup"><span data-stu-id="b71d1-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="b71d1-119">當您結束 PowerShell 時，原則將會還原。</span><span class="sxs-lookup"><span data-stu-id="b71d1-119">The policy will revert when you exit PowerShell.</span></span>
> <span data-ttu-id="b71d1-120">如果您想要儲存原則，請針對下列各項使用不同的值 `-Scope` ：</span><span class="sxs-lookup"><span data-stu-id="b71d1-120">If you would like to save the policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="b71d1-121">您現在應該可以 `Convert-NWChemToBroombridge` 使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b71d1-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="b71d1-122">接下來，我們將匯入 `Get-GateCount` **GetGateCount** 範例所提供的命令。</span><span class="sxs-lookup"><span data-stu-id="b71d1-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="b71d1-123">如需完整的詳細資訊，請參閱 [範例所提供的指示](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount)。</span><span class="sxs-lookup"><span data-stu-id="b71d1-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="b71d1-124">接下來，執行下列程式， `<runtime>` 使用、或來取代， `win10-x64` `osx-x64` `linux-x64` 視您的作業系統而定：</span><span class="sxs-lookup"><span data-stu-id="b71d1-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="b71d1-125">您現在應該可以 `Get-GateCount` 使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="b71d1-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="b71d1-126">輸入投影片</span><span class="sxs-lookup"><span data-stu-id="b71d1-126">Input Decks</span></span> ##

<span data-ttu-id="b71d1-127">NWChem 套件會採用稱為 _輸入_ 投影片的文字檔，以指定要解決的量子化學問題，以及其他參數，例如記憶體配置設定。</span><span class="sxs-lookup"><span data-stu-id="b71d1-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="b71d1-128">在此範例中，我們將使用 NWChem 隨附的其中一個預先製作的輸入投影片。</span><span class="sxs-lookup"><span data-stu-id="b71d1-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="b71d1-129">首先，複製 [nwchemgit/nwchem 存放庫](https://github.com/nwchemgit/nwchem)：</span><span class="sxs-lookup"><span data-stu-id="b71d1-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="b71d1-130">由於這是非常大的存放庫，因此我們可以使用引數來進行淺層複製，以節省一些頻寬和磁碟空間 `--depth 1` 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="b71d1-131">不過，這是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="b71d1-131">This is optional, however.</span></span>
> <span data-ttu-id="b71d1-132">如果沒有，複製作業將會正常運作 `--depth 1` 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="b71d1-133">此存放 `nwchemgit/nwchem` 庫隨附各種可用於量子開發工具組的輸入投影片，列在[ `QA/chem_library_tests` 資料夾](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests)底下。</span><span class="sxs-lookup"><span data-stu-id="b71d1-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span></span>
<span data-ttu-id="b71d1-134">在此範例中，我們將使用 `H4` 輸入組：</span><span class="sxs-lookup"><span data-stu-id="b71d1-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="b71d1-135">有問題的分子是由 4 hydrogen 原子組成的系統，這些原子會根據一個角度來排列，如投影片名稱所示的參數 `alpha` `h4_sto6g_alpha.nw` 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="b71d1-136">H4 是自1970年起計算化學的已知 [分子基準](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="b71d1-137">此參數表示投影片 `sto6g` 會根據 Slater 類型的 orbital 來執行標記法，具體而言，就是與具有6個高斯基礎函式的 [停止-nG 基礎](https://en.wikipedia.org/wiki/STO-nG_basis_sets) 函數相關的標記法。</span><span class="sxs-lookup"><span data-stu-id="b71d1-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="b71d1-138">這份輸入組還包含了數個 NWChem Tensor 縮減 Engine 的指示 (的 TCE) ，引導 NWChem 產生與量子開發工具組交互操作所需的資訊：</span><span class="sxs-lookup"><span data-stu-id="b71d1-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="b71d1-139">從 NWChem 產生和取用 Broombridge 輸出</span><span class="sxs-lookup"><span data-stu-id="b71d1-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="b71d1-140">您現在已具備產生和取用 Broombridge 檔所需的一切。</span><span class="sxs-lookup"><span data-stu-id="b71d1-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="b71d1-141">若要執行 NWChem 並為輸入組產生 Broombridge 檔 `h4_sto6g_0.000.nw` ，請執行 `Convert-NWChemToBroombridge` ：</span><span class="sxs-lookup"><span data-stu-id="b71d1-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="b71d1-142">當您第一次執行此命令時，Docker 會 `nwchemorg/nwchem-qc` 為您下載映射。</span><span class="sxs-lookup"><span data-stu-id="b71d1-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="b71d1-143">這可能需要一些時間，視您的連線速度而定，可能會讓您有機會取得咖啡的咖啡。</span><span class="sxs-lookup"><span data-stu-id="b71d1-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="b71d1-144">這會產生名為的 Broombridge 檔 `h4_sto6g_0.000.yaml` ，您可以搭配 `Get-GateCount` 使用：</span><span class="sxs-lookup"><span data-stu-id="b71d1-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="b71d1-145">您現在應該會看到主控台輸出，其中包含各種量子模擬方法的資源估計，例如 T 計數、旋轉計數、CNOT 計數等：</span><span class="sxs-lookup"><span data-stu-id="b71d1-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="b71d1-146">這裡有許多要做的事：</span><span class="sxs-lookup"><span data-stu-id="b71d1-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="b71d1-147">試用不同的預先定義輸入投影片，例如，藉由改變 `alpha` 中的 `h4_sto6g_alpha.nw` 參數，</span><span class="sxs-lookup"><span data-stu-id="b71d1-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="b71d1-148">嘗試直接編輯 NWChem 投影片來修改投影片，例如，探索 `STO-nG` 各種選項的模型，</span><span class="sxs-lookup"><span data-stu-id="b71d1-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="b71d1-149">嘗試其他可用的預先定義 NWChem 輸入投影片 `nwchem/qa/chem_library_tests`</span><span class="sxs-lookup"><span data-stu-id="b71d1-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="b71d1-150">試用一套預先定義的 Broombridge YAML 基準測試（從 NWChem 產生），並可在 [Microsoft/量子存放庫](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)中取得。</span><span class="sxs-lookup"><span data-stu-id="b71d1-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="b71d1-151">這些基準測試包括：</span><span class="sxs-lookup"><span data-stu-id="b71d1-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="b71d1-152">small 分子，例如分子 hydrogen (H2) 、Beryllium () 、鋰氫化 (LiH) 、</span><span class="sxs-lookup"><span data-stu-id="b71d1-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="b71d1-153">較大的分子，例如臭氧 (O3) 、Beta carotene、cytosine 等等。</span><span class="sxs-lookup"><span data-stu-id="b71d1-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="b71d1-154">試用以圖形化前端 [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem) 號，以提供 Microsoft 量子開發工具組的介面。</span><span class="sxs-lookup"><span data-stu-id="b71d1-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="b71d1-155">從 EMSL 箭號產生 Broombridge 輸出</span><span class="sxs-lookup"><span data-stu-id="b71d1-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="b71d1-156">若要開始使用 web 前端 EMSL 箭號，請 [在這裡](https://arrows.emsl.pnnl.gov/api/qsharp_chem)流覽瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="b71d1-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="b71d1-157">在網頁瀏覽器中執行 EMSL 箭號需要啟用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b71d1-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="b71d1-158">請參閱下列 [指示](https://www.enable-javascript.com/) ，以瞭解如何在瀏覽器中啟用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b71d1-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="b71d1-159">首先，在 [查詢] 方塊中輸入分子，顯示 ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="b71d1-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="b71d1-160">您可以依口語名稱輸入許多分子，例如 "caffeine" 而非 "1，3，7-Trimethylxanthine"。</span><span class="sxs-lookup"><span data-stu-id="b71d1-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="b71d1-161">接著，按一下顯示的按鈕 ``theory{qsharp_chem}`` 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="b71d1-162">這將會進一步填入查詢方塊，其中包含指示執行以 Broombridge YAML 格式匯出輸出的指示。</span><span class="sxs-lookup"><span data-stu-id="b71d1-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="b71d1-163">現在，clock 開啟 ``Run Arrows`` 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="b71d1-164">視輸入的大小而定，這可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="b71d1-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="b71d1-165">或者，如果先前已計算過特定模型，則可以非常快速地完成，因為它只會計算資料庫中的查閱量。</span><span class="sxs-lookup"><span data-stu-id="b71d1-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="b71d1-166">無論是哪一種情況，您都會進入新的頁面，其中包含針對您的輸入所指定的 NWChem 所執行之特定的眾多資訊。</span><span class="sxs-lookup"><span data-stu-id="b71d1-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="b71d1-167">您可以從開頭為下列標頭的區段下載並儲存 Broombridge YAML 檔案：</span><span class="sxs-lookup"><span data-stu-id="b71d1-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="b71d1-168">按一下 [開啟] ``download`` ，以唯一的檔案名儲存本機複本，例如 ``qsharp_chem48443.yaml`` (每個執行) 的特定名稱將會不同。</span><span class="sxs-lookup"><span data-stu-id="b71d1-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="b71d1-169">然後，您可以進一步處理上述的檔案，例如，搭配</span><span class="sxs-lookup"><span data-stu-id="b71d1-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="b71d1-170">取得資源計數。</span><span class="sxs-lookup"><span data-stu-id="b71d1-170">to get resource counts.</span></span> 

<span data-ttu-id="b71d1-171">您可以從 EMSL 箭號起始頁的索引標籤中，享受可以存取的3D 分子 builder ``Arrows Entry - 3D Builder`` 。</span><span class="sxs-lookup"><span data-stu-id="b71d1-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="b71d1-172">按一下所顯示分子的 [JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 圖片可讓您進行編輯。</span><span class="sxs-lookup"><span data-stu-id="b71d1-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="b71d1-173">您可以四處移動原子、將原子分開，使其分子間的距離變更、新增/移除原子等。針對上述每個選項，在 [查詢] 方塊中加入之後 ``theory{qsharp_chem}`` ，您就可以產生 BROOMBRIDGE YAML 架構的實例，並使用量子化學程式庫進一步探索它。</span><span class="sxs-lookup"><span data-stu-id="b71d1-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
