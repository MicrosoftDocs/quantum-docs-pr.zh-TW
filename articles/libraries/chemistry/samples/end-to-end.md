---
title: 以 NWChem 進行端對端 |Microsoft Docs
description: NWChem 檔的端對端檔
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185812"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="8d182-103">使用 NWChem 端對端</span><span class="sxs-lookup"><span data-stu-id="8d182-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="8d182-104">在此頁面中，我們將逐步解說如何取得量子化學模擬的閘道計數，從[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)的輸入牌組開始。</span><span class="sxs-lookup"><span data-stu-id="8d182-104">In this page, we will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="8d182-105">繼續進行此範例之前，請確定您已安裝 Docker，請遵循[安裝和驗證指南](xref:microsoft.quantum.chemistry.concepts.installation)。</span><span class="sxs-lookup"><span data-stu-id="8d182-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="8d182-106">詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="8d182-106">For more information:</span></span>
- [<span data-ttu-id="8d182-107">NWChem 輸入卡座的結構</span><span class="sxs-lookup"><span data-stu-id="8d182-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="8d182-108">用於配量開發工具組的輸入組命令</span><span class="sxs-lookup"><span data-stu-id="8d182-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="8d182-109">安裝化學程式庫和相依性</span><span class="sxs-lookup"><span data-stu-id="8d182-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="8d182-110">資源計數</span><span class="sxs-lookup"><span data-stu-id="8d182-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="8d182-111">此範例需要執行 Windows PowerShell Core。</span><span class="sxs-lookup"><span data-stu-id="8d182-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="8d182-112">在 https://github.com/PowerShell/PowerShell 下載適用于 Windows、macOS 或 Linux 的 PowerShell Core。</span><span class="sxs-lookup"><span data-stu-id="8d182-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="8d182-113">匯入必要的 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="8d182-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="8d182-114">如果您尚未這麼做，請複製[Microsoft/量子存放庫](https://github.com/Microsoft/Quantum)，其中包含使用配量開發工具組的範例和公用程式：</span><span class="sxs-lookup"><span data-stu-id="8d182-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="8d182-115">複製 `Microsoft/Quantum`之後，請在 `utilities/` 資料夾中執行 `cd`，並匯入 PowerShell 模組以使用 Docker 和 NWChem：</span><span class="sxs-lookup"><span data-stu-id="8d182-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="8d182-116">根據預設，Windows 會防止執行任何腳本或模組做為安全性措施。</span><span class="sxs-lookup"><span data-stu-id="8d182-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="8d182-117">若要允許 `Invoke-NWChem.psm1` 的模組在 Windows 上執行，您可能需要變更執行原則。</span><span class="sxs-lookup"><span data-stu-id="8d182-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="8d182-118">若要這麼做，請執行 `Set-ExecutionPolicy` 命令：</span><span class="sxs-lookup"><span data-stu-id="8d182-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="8d182-119">然後，當您結束 PowerShell 時，就會還原執行原則。</span><span class="sxs-lookup"><span data-stu-id="8d182-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="8d182-120">如果您想要儲存執行原則，請針對 `-Scope`使用不同的值：</span><span class="sxs-lookup"><span data-stu-id="8d182-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="8d182-121">您現在應該可以使用 [`Convert-NWChemToBroombridge`] 命令：</span><span class="sxs-lookup"><span data-stu-id="8d182-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="8d182-122">接下來，我們將匯入**GetGateCount**範例所提供的 `Get-GateCount` 命令。</span><span class="sxs-lookup"><span data-stu-id="8d182-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="8d182-123">如需完整詳細資料，請參閱[範例提供的指示](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount)。</span><span class="sxs-lookup"><span data-stu-id="8d182-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span></span>
<span data-ttu-id="8d182-124">接下來，根據您的作業系統，執行下列程式，將 `<runtime>` 取代為 `win10-x64`、`osx-x64`或 `linux-x64`：</span><span class="sxs-lookup"><span data-stu-id="8d182-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="8d182-125">您現在應該可以使用 [`Get-GateCount`] 命令：</span><span class="sxs-lookup"><span data-stu-id="8d182-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="8d182-126">輸入牌</span><span class="sxs-lookup"><span data-stu-id="8d182-126">Input Decks</span></span> ##

<span data-ttu-id="8d182-127">NWChem 套件會採用一個稱為_輸入組_的文字檔，它會指定要解決的量子化學問題，以及其他參數，例如記憶體配置設定。</span><span class="sxs-lookup"><span data-stu-id="8d182-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="8d182-128">在此範例中，我們將使用 NWChem 隨附的其中一個預先製作的輸入組。</span><span class="sxs-lookup"><span data-stu-id="8d182-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="8d182-129">首先，複製[nwchemgit/nwchem 存放庫](https://github.com/nwchemgit/nwchem)：</span><span class="sxs-lookup"><span data-stu-id="8d182-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="8d182-130">因為這是非常大型的存放庫，所以我們可以使用 `--depth 1` 引數來執行淺層複製，以節省一些頻寬和磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="8d182-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="8d182-131">不過，這是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="8d182-131">This is optional, however.</span></span>
> <span data-ttu-id="8d182-132">在沒有 `--depth 1`的情況下，複製作業就沒問題。</span><span class="sxs-lookup"><span data-stu-id="8d182-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="8d182-133">`nwchemgit/nwchem` 存放庫隨附各種不同的輸入表，適用于 [ [`QA/chem_library_tests`] 資料夾](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)底下所列的 [配量開發工具組]。</span><span class="sxs-lookup"><span data-stu-id="8d182-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="8d182-134">在此範例中，我們將使用 `H4` 的輸入組：</span><span class="sxs-lookup"><span data-stu-id="8d182-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="8d182-135">有問題的分子是4個 hydrogen 原子的系統，其排列在根據某個角度而定的特定幾何中，參數 `alpha` 如投影片的名稱 `h4_sto6g_alpha.nw` 所示。</span><span class="sxs-lookup"><span data-stu-id="8d182-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="8d182-136">H4 是自1970年起，適用于計算化學的已知[分子基準測試](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511)。</span><span class="sxs-lookup"><span data-stu-id="8d182-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="8d182-137">參數 `sto6g` 表示該牌堆會根據 Slater 類型的 orbital 來實作為代表，具體來說，就是與具有6個高斯基礎函式的[停止 nG 設定](https://en.wikipedia.org/wiki/STO-nG_basis_sets)相關的標記法。</span><span class="sxs-lookup"><span data-stu-id="8d182-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="8d182-138">此輸入組還包含數個 NWChem 張量縮減 Engine （TCE）指示，引導 NWChem 產生與量子開發工具組互通所需的資訊：</span><span class="sxs-lookup"><span data-stu-id="8d182-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="8d182-139">產生和使用 NWChem 的 Broombridge 輸出</span><span class="sxs-lookup"><span data-stu-id="8d182-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="8d182-140">我們現在有了產生和使用 Broombridge 檔所需的所有專案。</span><span class="sxs-lookup"><span data-stu-id="8d182-140">We now have everything we need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="8d182-141">若要執行 NWChem，並為 `h4_sto6g_0.000.nw` 輸入組產生 Broombridge 檔，請執行 `Convert-NWChemToBroombridge`：</span><span class="sxs-lookup"><span data-stu-id="8d182-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="8d182-142">當您第一次執行此命令時，Docker 會為您下載 `nwchemorg/nwchem-qc` 映射。</span><span class="sxs-lookup"><span data-stu-id="8d182-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="8d182-143">這可能需要一些時間，視您的連線速度而定，可能會提供一杯咖啡的機會。</span><span class="sxs-lookup"><span data-stu-id="8d182-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="8d182-144">這會產生稱為 `h4_sto6g_0.000.yaml` 的 Broombridge 檔，可與 `Get-GateCount`搭配使用：</span><span class="sxs-lookup"><span data-stu-id="8d182-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that we can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="8d182-145">您現在應該會看到包含資源估計的主控台輸出，例如 T 計數、旋轉計數、CNOT-CONTAINS 計數等等，適用于各種不同的量子模擬方法：</span><span class="sxs-lookup"><span data-stu-id="8d182-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

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

<span data-ttu-id="8d182-146">這裡有許多要做的事：</span><span class="sxs-lookup"><span data-stu-id="8d182-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="8d182-147">請嘗試不同的預先定義的輸入組，例如，藉由在 `h4_sto6g_alpha.nw`中改變參數 `alpha`，</span><span class="sxs-lookup"><span data-stu-id="8d182-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="8d182-148">請嘗試直接編輯 NWChem 投影片來修改投影片，例如，探索適用于多種選擇的 `STO-nG` 模型，</span><span class="sxs-lookup"><span data-stu-id="8d182-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="8d182-149">嘗試其他在 `nwchem/qa/chem_library_tests`提供的預先定義 NWChem 輸入組。</span><span class="sxs-lookup"><span data-stu-id="8d182-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="8d182-150">試用從 NWChem 產生的一組預先定義的 Broombridge YAML 基準測試，並以[Microsoft/量子存放庫](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="8d182-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="8d182-151">這些基準測試包括：</span><span class="sxs-lookup"><span data-stu-id="8d182-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="8d182-152">小型分子驅使分子，例如分子 hydrogen （H2）、Beryllium （是）、鋰鎳氫（LiH）、</span><span class="sxs-lookup"><span data-stu-id="8d182-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="8d182-153">較大的分子驅使分子，例如 ozone （O3）、搶鮮版（Beta） carotene、cytosine 等等。</span><span class="sxs-lookup"><span data-stu-id="8d182-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="8d182-154">試試看具有 Microsoft Quantum Development Kit 介面的圖形化前端[EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號。</span><span class="sxs-lookup"><span data-stu-id="8d182-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="8d182-155">從 EMSL 箭號產生 Broombridge 輸出</span><span class="sxs-lookup"><span data-stu-id="8d182-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="8d182-156">若要開始使用以 web 為基礎的前端 EMSL 箭號，請在[這裡](https://arrows.emsl.pnnl.gov/api/qsharp_chem)流覽瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="8d182-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="8d182-157">在網頁瀏覽器中執行 EMSL 箭號需要啟用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="8d182-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="8d182-158">請參閱這些[指示](https://www.enable-javascript.com/)，以瞭解如何在您的瀏覽器中啟用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="8d182-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="8d182-159">首先，在 [查詢] 方塊中輸入分子，其中會顯示 ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="8d182-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="8d182-160">您可以依其口語上名稱輸入許多分子驅使分子，例如 "caffeine"，而不是 "1，3，7-Trimethylxanthine"。</span><span class="sxs-lookup"><span data-stu-id="8d182-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="8d182-161">接下來，按一下顯示 [``theory{qsharp_chem}``] 的按鈕。</span><span class="sxs-lookup"><span data-stu-id="8d182-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="8d182-162">這將會進一步在查詢方塊中填入指示，此指令會告知執行以 Broombridge YAML 格式匯出輸出。</span><span class="sxs-lookup"><span data-stu-id="8d182-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="8d182-163">現在，``Run Arrows``上的時鐘。</span><span class="sxs-lookup"><span data-stu-id="8d182-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="8d182-164">視輸入的大小而定，這可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="8d182-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="8d182-165">或者，如果已在之前計算過特定的模型，則可以非常快速地完成作業，因為它只會為資料庫中的查閱量。</span><span class="sxs-lookup"><span data-stu-id="8d182-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="8d182-166">不論是哪一種情況，您都會進入新的頁面，其中包含針對輸入所指定之 NWChem 的特定執行相關資訊眾多。</span><span class="sxs-lookup"><span data-stu-id="8d182-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="8d182-167">您可以從開頭為下列標頭的區段下載並儲存 Broombridge YAML 檔案：</span><span class="sxs-lookup"><span data-stu-id="8d182-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
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

<span data-ttu-id="8d182-168">按一下 [``download``]，這會以唯一的檔案名（例如 ``qsharp_chem48443.yaml``）儲存本機複本（每次執行時都有不同的名稱）。</span><span class="sxs-lookup"><span data-stu-id="8d182-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="8d182-169">然後，您可以使用上述程式進一步處理此檔案，例如</span><span class="sxs-lookup"><span data-stu-id="8d182-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="8d182-170">取得資源計數。</span><span class="sxs-lookup"><span data-stu-id="8d182-170">to get resource counts.</span></span> 

<span data-ttu-id="8d182-171">您可能會喜歡可從 [EMSL 箭號] 起始頁的 [``Arrows Entry - 3D Builder``] 索引標籤存取的3D 分子 builder。</span><span class="sxs-lookup"><span data-stu-id="8d182-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="8d182-172">按一下所顯示分子的[JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 圖片，即可讓您進行編輯。</span><span class="sxs-lookup"><span data-stu-id="8d182-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="8d182-173">您可以四處移動原子、將原子拖曳到彼此的分子距離變更、新增/移除原子等等。針對上述每個選項，一旦您在 [查詢] 方塊中加入 ``theory{qsharp_chem}`` 之後，就可以產生 Broombridge YAML 架構的實例，並使用 [量子化學程式庫] 進一步探索它。</span><span class="sxs-lookup"><span data-stu-id="8d182-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
