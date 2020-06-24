---
title: 'Microsoft Q # 化學程式庫安裝和驗證'
description: 瞭解如何安裝 Microsoft 量子化學程式庫，並將它與 NWChem 計算化學平臺搭配使用。
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274696"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="e3ce1-103">化學程式庫安裝和驗證</span><span class="sxs-lookup"><span data-stu-id="e3ce1-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="e3ce1-104">配量開發工具組透過 NuGet 套件提供對量子化學應用程式的支援 [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) 。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="e3ce1-105">與其他 NuGet 套件一樣，將化學程式庫新增至您的專案是非常簡單的。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="e3ce1-106">**Visual Studio 2019：** 如果您使用 Visual Studio 2019，您可以使用 NuGet 套件管理員來新增量子化學套件。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="e3ce1-107">若要開啟 [封裝管理員]，請以滑鼠右鍵按一下您想要新增化學程式庫的專案，然後選取 [管理 NuGet 套件 ...]，如下列螢幕擷取畫面所示。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![使用 Visual Studio 2019 中的 NuGet 套件管理員](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="e3ce1-109">從 [流覽] 索引標籤中，搜尋封裝名稱 "Microsoft. 量子。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-109">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="e3ce1-110">請務必勾選 [包含發行前版本]。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-110">Make sure to tick "Include prerelease."</span></span>

![[包含發行前版本] 核取方塊](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="e3ce1-112">這會列出可供下載的套件。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-112">This will list the packages available for download.</span></span>
<span data-ttu-id="e3ce1-113">按一下左側窗格中的 [...]，在右側窗格中選取最新的發行前版本，然後按一下 [安裝]：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-113">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![安裝最新的 Microsoft 量子封裝](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="e3ce1-115">如需詳細資訊，請參閱[套件管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-115">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="e3ce1-116">或者，您可以使用 [套件管理員主控台]，透過命令列介面，將量子化學程式庫新增至您的專案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-116">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![從命令列使用套件管理員主控台](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="e3ce1-118">從 [套件管理員主控台] 執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-118">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="e3ce1-119">如需詳細資訊，請參閱[套件管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-119">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="e3ce1-120">**命令列或 Visual Studio Code：** 單獨使用命令列或從 Visual Studio Code 中，您可以使用 `dotnet` 命令，將 NuGet 套件參考新增至您的專案：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-120">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="e3ce1-121">正在驗證您的安裝</span><span class="sxs-lookup"><span data-stu-id="e3ce1-121">Verifying Your Installation</span></span> 

<span data-ttu-id="e3ce1-122">就像其他的「量子開發工具組」，「量子化學程式庫」隨附一些完整記載的範例，可協助您快速啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-122">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="e3ce1-123">若要使用這些範例來測試您的安裝，請複製[主要的範例存放庫](https://github.com/Microsoft/Quantum)，然後執行其中一個範例。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-123">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="e3ce1-124">例如，若要執行 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) 範例：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-124">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="e3ce1-125">若要在複製存放庫之後，使用 Microsoft Visual Studio 驗證量子化學程式庫的安裝：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-125">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="e3ce1-126">在 [化學] 資料夾中開啟 [ChemistrySamples] 方案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-126">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="e3ce1-127">選取 [樣本/1]。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-127">Select Samples/1.</span></span> <span data-ttu-id="e3ce1-128">簡單的分子驅使分子/MolecularHydrogen 做為啟始專案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-128">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="e3ce1-129">按 F5 執行分子 Hydrogen 量子階段估計示範。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-129">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="e3ce1-130">如需估計能源等級值的詳細資訊，請參閱[取得能源等級估計](xref:microsoft.quantum.chemistry.examples.energyestimate)。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-130">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="e3ce1-131">搭配 NWChem 使用量子開發工具組</span><span class="sxs-lookup"><span data-stu-id="e3ce1-131">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="e3ce1-132">MolecularHydrogen 範例會使用手動設定的分子輸入資料。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-132">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="e3ce1-133">雖然這適用于小型範例，但大規模的配量化學需要 Hamiltonians 數百萬或數十億個詞彙。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-133">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="e3ce1-134">可調整的計算化學套件所產生的這類 Hamiltonians 太大，無法以手動方式匯入。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-134">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="e3ce1-135">適用于量子開發工具組的量子化學程式庫是設計來與計算化學套件搭配運作，最值得注意的是在太平洋西北部國家實驗室的環境分子科學實驗室（EMSL）所開發的[**NWChem**](http://www.nwchem-sw.org/)計算化學平臺。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-135">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="e3ce1-136">特別是， `Microsoft.Quantum.Chemistry` 封裝會提供工具來載入[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中所代表之量子化學模擬問題的實例，而這也支援由最新版本的 NWChem 匯出。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-136">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="e3ce1-137">若要使用 NWChem 搭配配量開發工具組來啟動並執行，建議您採用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-137">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="e3ce1-138">開始使用[IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)中的範例所提供的現有 Broombridge 檔案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-138">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="e3ce1-139">使用 [ [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號產生器] 做為要 NWChem 之 web 型前端的 Microsoft Quantum Development Kit，以產生新的 Broombridge 格式化分子輸入檔。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-139">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="e3ce1-140">使用 PNNL 提供的[Docker 映射](https://hub.docker.com/r/nwchemorg/nwchem-qc/)來執行 NWChem，或</span><span class="sxs-lookup"><span data-stu-id="e3ce1-140">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="e3ce1-141">針對您的平臺[編譯 NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) 。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-141">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="e3ce1-142">請參閱[NWChem 的端對端](xref:microsoft.quantum.chemistry.examples.endtoend)，以取得有關如何使用 NWChem 到化學模型來分析量子開發套件化學程式庫的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-142">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="e3ce1-143">開始使用範例所提供的 Broombridge 檔案</span><span class="sxs-lookup"><span data-stu-id="e3ce1-143">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="e3ce1-144">[量子開發工具組範例] 存放庫中的[IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)資料夾包含 Broombridge 格式化的分子資料檔案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-144">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="e3ce1-145">如需簡單範例，請使用化學程式庫範例[GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) ，從 Broombridge 檔案的其中一個載入 Hamiltonian，並執行量子模擬 algorigthms 的閘道估計：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-145">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="e3ce1-146">如需如何輸入 Broombridge 架構所代表之分子驅使分子的詳細資訊，請參閱[從檔案載入 Hamiltonian](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-146">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="e3ce1-147">如需資源估計的詳細資訊，請參閱[取得資源計數](xref:microsoft.quantum.chemistry.examples.resourcecounts)。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-147">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="e3ce1-148">開始使用 EMSL 箭號 Builder</span><span class="sxs-lookup"><span data-stu-id="e3ce1-148">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="e3ce1-149">EMSL 箭號是使用 NWChem 和化學計算資料庫來產生分子資料的工具。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-149">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="e3ce1-150">[Microsoft Quantum Development Kit 的 EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號產生器可讓您使用多個分子模型產生器來輸入您的模型，並產生要供量子開發工具組使用的 Broombridge 資料檔案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-150">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="e3ce1-151">在 [EMSL] 頁面上，按一下 [' 指令 '] 索引標籤，並遵循 [' Simple 範例 '] 指示來產生 Broombridge 檔案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-151">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="e3ce1-152">然後嘗試執行 [' GetGateCount '] 來查看這些分子驅使分子的量子資源估計值。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-152">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="e3ce1-153">從來源安裝 NWChem</span><span class="sxs-lookup"><span data-stu-id="e3ce1-153">Installing NWChem from Source</span></span>

<span data-ttu-id="e3ce1-154">[PNNL 會提供](http://www.nwchem-sw.org/index.php/Compiling_NWChem)如何從來源安裝 NWChem 的完整指示。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-154">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="e3ce1-155">如果您想要使用 Windows 10 的 NWChem，適用于 Linux 的 Windows 子系統是很好的選擇。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-155">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="e3ce1-156">安裝[適用于 Windows 的 Ubuntu 18.04 LTS](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)之後，請 `ubuntu18.04` 從您最愛的終端機執行，並遵循上面的指示，從來源安裝 NWChem。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-156">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="e3ce1-157">從來源編譯 NWChem 之後，您可以執行 `yaml_driver` NWChem 所提供的腳本，以從 NWChem 的輸入投影片快速產生 Broombridge 實例：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-157">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="e3ce1-158">此命令會 `input.yaml` 在您目前的目錄內，以 Broombridge 格式建立新檔案。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-158">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="e3ce1-159">使用 NWChem 搭配 Docker</span><span class="sxs-lookup"><span data-stu-id="e3ce1-159">Using NWChem with Docker</span></span>

<span data-ttu-id="e3ce1-160">使用 NWChem 的預先建立映射可透過[Docker Hub](https://hub.docker.com)跨平臺提供。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-160">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="e3ce1-161">若要開始使用，請遵循適用于您平臺的 Docker 安裝指示：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-161">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="e3ce1-162">安裝適用于 Ubuntu 的 Docker</span><span class="sxs-lookup"><span data-stu-id="e3ce1-162">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="e3ce1-163">安裝適用于 macOS 的 Docker</span><span class="sxs-lookup"><span data-stu-id="e3ce1-163">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="e3ce1-164">安裝適用於 Windows 的 Docker 10</span><span class="sxs-lookup"><span data-stu-id="e3ce1-164">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="e3ce1-165">如果您使用適用於 Windows 的 Docker，就必須使用 Docker daemon 來共用包含臨時目錄的磁片磁碟機（通常是 `C:\` 磁片磁碟機）。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-165">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="e3ce1-166">如需詳細資訊，請參閱[Docker 檔](https://docs.docker.com/docker-for-windows/#shared-drives)。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-166">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="e3ce1-167">安裝 Docker 之後，您可以使用配量開發工具組範例所提供的 PowerShell 模組來執行映射，或者您可以手動執行映射。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-167">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="e3ce1-168">我們會在這裡詳細說明如何使用 PowerShell;如果您想要手動使用 Docker 映射，請參閱[映射提供的檔](https://hub.docker.com/r/nwchemorg/nwchem-qc/)。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-168">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="e3ce1-169">透過 PowerShell Core 執行 NWChem</span><span class="sxs-lookup"><span data-stu-id="e3ce1-169">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="e3ce1-170">若要搭配使用 NWChem Docker 映射與配量開發工具組，我們提供一個小型的 PowerShell 模組來處理將檔案移入和移出 NWChem 的功能。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-170">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="e3ce1-171">如果您尚未安裝 PowerShell Core，您可以從[GitHub 上的 powershell 存放庫](https://github.com/PowerShell/PowerShell#get-powershell)下載跨平臺。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-171">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="e3ce1-172">PowerShell Core 也用於一些範例，以示範與資料科學和商務分析工作流程的互通性。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-172">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="e3ce1-173">安裝 PowerShell Core 之後，匯入 `InvokeNWChem.psm1` 以在目前的會話中提供 NWChem 命令：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-173">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="e3ce1-174">這會讓 `Convert-NWChemToBroombridge` 命令可在您目前的 PowerShell 會話中使用。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-174">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="e3ce1-175">若要從 Docker 下載任何所需的映射，並使用它們來執行 NWChem 輸入組並將輸出捕獲到 Broombridge，請執行下列程式：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-175">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="e3ce1-176">這會藉由在上執行 NWChem 來建立 Broombridge 檔案 `input.nw` 。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-176">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="e3ce1-177">根據預設，Broombridge 輸出將會具有與輸入組相同的名稱和路徑，並將 `.nw` 副檔名取代成 `.yaml` 。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-177">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="e3ce1-178">您可以使用參數將此覆寫 `-DestinationPath` 為 `Convert-NWChemToBroombridge` 。</span><span class="sxs-lookup"><span data-stu-id="e3ce1-178">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="e3ce1-179">您可以使用 PowerShell 的內建說明功能來取得詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="e3ce1-179">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
