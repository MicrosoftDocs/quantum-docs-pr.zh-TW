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
# <a name="chemistry-library-installation-and-validation"></a>化學程式庫安裝和驗證

配量開發工具組透過 NuGet 套件提供對量子化學應用程式的支援 [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) 。
與其他 NuGet 套件一樣，將化學程式庫新增至您的專案是非常簡單的。

**Visual Studio 2019：** 如果您使用 Visual Studio 2019，您可以使用 NuGet 套件管理員來新增量子化學套件。
若要開啟 [封裝管理員]，請以滑鼠右鍵按一下您想要新增化學程式庫的專案，然後選取 [管理 NuGet 套件 ...]，如下列螢幕擷取畫面所示。

![使用 Visual Studio 2019 中的 NuGet 套件管理員](~/media/vs2017-nuget-manage-packages.png)

從 [流覽] 索引標籤中，搜尋封裝名稱 "Microsoft. 量子。

> [!NOTE]
> 請務必勾選 [包含發行前版本]。

![[包含發行前版本] 核取方塊](~/media/vs2017-nuget-package-search.png)

這會列出可供下載的套件。
按一下左側窗格中的 [...]，在右側窗格中選取最新的發行前版本，然後按一下 [安裝]：

![安裝最新的 Microsoft 量子封裝](~/media/vs2017-nuget-select-chem.png)

如需詳細資訊，請參閱[套件管理員 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。

或者，您可以使用 [套件管理員主控台]，透過命令列介面，將量子化學程式庫新增至您的專案。

![從命令列使用套件管理員主控台](~/media/vs2017-nuget-console-menu.png)

從 [套件管理員主控台] 執行下列步驟：

```
Install-Package Microsoft.Quantum.Chemistry
```

如需詳細資訊，請參閱[套件管理員主控台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。

**命令列或 Visual Studio Code：** 單獨使用命令列或從 Visual Studio Code 中，您可以使用 `dotnet` 命令，將 NuGet 套件參考新增至您的專案：

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>正在驗證您的安裝 

就像其他的「量子開發工具組」，「量子化學程式庫」隨附一些完整記載的範例，可協助您快速啟動並執行。
若要使用這些範例來測試您的安裝，請複製[主要的範例存放庫](https://github.com/Microsoft/Quantum)，然後執行其中一個範例。  例如，若要執行 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) 範例：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

若要在複製存放庫之後，使用 Microsoft Visual Studio 驗證量子化學程式庫的安裝：
    1. 在 [化學] 資料夾中開啟 [ChemistrySamples] 方案。  
    2. 選取 [樣本/1]。 簡單的分子驅使分子/MolecularHydrogen 做為啟始專案。
    3. 按 F5 執行分子 Hydrogen 量子階段估計示範。

如需估計能源等級值的詳細資訊，請參閱[取得能源等級估計](xref:microsoft.quantum.chemistry.examples.energyestimate)。   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>搭配 NWChem 使用量子開發工具組 ##

MolecularHydrogen 範例會使用手動設定的分子輸入資料。  雖然這適用于小型範例，但大規模的配量化學需要 Hamiltonians 數百萬或數十億個詞彙。 可調整的計算化學套件所產生的這類 Hamiltonians 太大，無法以手動方式匯入。 

適用于量子開發工具組的量子化學程式庫是設計來與計算化學套件搭配運作，最值得注意的是在太平洋西北部國家實驗室的環境分子科學實驗室（EMSL）所開發的[**NWChem**](http://www.nwchem-sw.org/)計算化學平臺。
特別是， `Microsoft.Quantum.Chemistry` 封裝會提供工具來載入[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中所代表之量子化學模擬問題的實例，而這也支援由最新版本的 NWChem 匯出。

若要使用 NWChem 搭配配量開發工具組來啟動並執行，建議您採用下列其中一種方法：
- 開始使用[IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)中的範例所提供的現有 Broombridge 檔案。
- 使用 [ [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號產生器] 做為要 NWChem 之 web 型前端的 Microsoft Quantum Development Kit，以產生新的 Broombridge 格式化分子輸入檔。  
- 使用 PNNL 提供的[Docker 映射](https://hub.docker.com/r/nwchemorg/nwchem-qc/)來執行 NWChem，或
- 針對您的平臺[編譯 NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) 。

請參閱[NWChem 的端對端](xref:microsoft.quantum.chemistry.examples.endtoend)，以取得有關如何使用 NWChem 到化學模型來分析量子開發套件化學程式庫的詳細資訊。

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>開始使用範例所提供的 Broombridge 檔案

[量子開發工具組範例] 存放庫中的[IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)資料夾包含 Broombridge 格式化的分子資料檔案。  

如需簡單範例，請使用化學程式庫範例[GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) ，從 Broombridge 檔案的其中一個載入 Hamiltonian，並執行量子模擬 algorigthms 的閘道估計：

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

如需如何輸入 Broombridge 架構所代表之分子驅使分子的詳細資訊，請參閱[從檔案載入 Hamiltonian](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 。  

如需資源估計的詳細資訊，請參閱[取得資源計數](xref:microsoft.quantum.chemistry.examples.resourcecounts)。  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>開始使用 EMSL 箭號 Builder

EMSL 箭號是使用 NWChem 和化學計算資料庫來產生分子資料的工具。  [Microsoft Quantum Development Kit 的 EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號產生器可讓您使用多個分子模型產生器來輸入您的模型，並產生要供量子開發工具組使用的 Broombridge 資料檔案。  

在 [EMSL] 頁面上，按一下 [' 指令 '] 索引標籤，並遵循 [' Simple 範例 '] 指示來產生 Broombridge 檔案。  然後嘗試執行 [' GetGateCount '] 來查看這些分子驅使分子的量子資源估計值。

### <a name="installing-nwchem-from-source"></a>從來源安裝 NWChem

[PNNL 會提供](http://www.nwchem-sw.org/index.php/Compiling_NWChem)如何從來源安裝 NWChem 的完整指示。

> [!TIP]
> 如果您想要使用 Windows 10 的 NWChem，適用于 Linux 的 Windows 子系統是很好的選擇。
> 安裝[適用于 Windows 的 Ubuntu 18.04 LTS](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)之後，請 `ubuntu18.04` 從您最愛的終端機執行，並遵循上面的指示，從來源安裝 NWChem。

從來源編譯 NWChem 之後，您可以執行 `yaml_driver` NWChem 所提供的腳本，以從 NWChem 的輸入投影片快速產生 Broombridge 實例：

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

此命令會 `input.yaml` 在您目前的目錄內，以 Broombridge 格式建立新檔案。

### <a name="using-nwchem-with-docker"></a>使用 NWChem 搭配 Docker

使用 NWChem 的預先建立映射可透過[Docker Hub](https://hub.docker.com)跨平臺提供。
若要開始使用，請遵循適用于您平臺的 Docker 安裝指示：

- [安裝適用于 Ubuntu 的 Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [安裝適用于 macOS 的 Docker](https://docs.docker.com/docker-for-mac/install/)
- [安裝適用於 Windows 的 Docker 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> 如果您使用適用於 Windows 的 Docker，就必須使用 Docker daemon 來共用包含臨時目錄的磁片磁碟機（通常是 `C:\` 磁片磁碟機）。 如需詳細資訊，請參閱[Docker 檔](https://docs.docker.com/docker-for-windows/#shared-drives)。

安裝 Docker 之後，您可以使用配量開發工具組範例所提供的 PowerShell 模組來執行映射，或者您可以手動執行映射。
我們會在這裡詳細說明如何使用 PowerShell;如果您想要手動使用 Docker 映射，請參閱[映射提供的檔](https://hub.docker.com/r/nwchemorg/nwchem-qc/)。

#### <a name="running-nwchem-through-powershell-core"></a>透過 PowerShell Core 執行 NWChem

若要搭配使用 NWChem Docker 映射與配量開發工具組，我們提供一個小型的 PowerShell 模組來處理將檔案移入和移出 NWChem 的功能。
如果您尚未安裝 PowerShell Core，您可以從[GitHub 上的 powershell 存放庫](https://github.com/PowerShell/PowerShell#get-powershell)下載跨平臺。

> [!NOTE]
> PowerShell Core 也用於一些範例，以示範與資料科學和商務分析工作流程的互通性。

安裝 PowerShell Core 之後，匯入 `InvokeNWChem.psm1` 以在目前的會話中提供 NWChem 命令：

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

這會讓 `Convert-NWChemToBroombridge` 命令可在您目前的 PowerShell 會話中使用。
若要從 Docker 下載任何所需的映射，並使用它們來執行 NWChem 輸入組並將輸出捕獲到 Broombridge，請執行下列程式：

```powershell
Convert-NWChemToBroombridge ./input.nw
```

這會藉由在上執行 NWChem 來建立 Broombridge 檔案 `input.nw` 。
根據預設，Broombridge 輸出將會具有與輸入組相同的名稱和路徑，並將 `.nw` 副檔名取代成 `.yaml` 。
您可以使用參數將此覆寫 `-DestinationPath` 為 `Convert-NWChemToBroombridge` 。
您可以使用 PowerShell 的內建說明功能來取得詳細資訊：

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
