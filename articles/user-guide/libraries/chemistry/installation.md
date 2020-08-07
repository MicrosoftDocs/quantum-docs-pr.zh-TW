---
title: Microsoft Q# 化學程式庫安裝
description: 瞭解如何安裝 Microsoft 量子化學程式庫，並將它與 NWChem 計算化學平臺搭配使用。
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5fe973d24ceffd413cdbd3c543013dcc7ee379c0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869336"
---
# <a name="chemistry-library-installation"></a>化學程式庫安裝

[ **MolecularHydrogen**範例](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen)會使用手動設定的分子輸入資料。
雖然這適用于小型範例，但大規模的量子化學需要 Hamiltonians 數百萬或數十億個詞彙。
可調整的計算化學套件所產生的這類 Hamiltonians 太大，無法以手動方式匯入。

適用于配量開發工具組的量子化學程式庫是設計來與計算化學封裝搭配使用，最值得注意的是環境分子科學實驗室所開發的[**NWChem**](http://www.nwchem-sw.org/)計算化學平臺 (EMSL) 在太平洋西北部國家實驗室。
特別是， [ **Microsoft 量子**套件](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)提供的工具可用來載入[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中所呈現之量子化學模擬問題的實例，也支援由最新版本的 NWChem 匯出。

量子開發工具組化學程式庫也提供命令列工具，可在 `qdk-chem` 舊版格式和[Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)之間進行轉換。

本節將詳細說明如何使用 NWChem 和 Broombridge 的量子開發工具組，或舊版格式和 `qdk-chem` 。

## <a name="using-the-quantum-development-kit-with-nwchem"></a>搭配 NWChem 使用量子開發工具組

若要使用 NWChem 搭配量子開發工具組來啟動並執行，請使用下列其中一種方法：

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
> 如果您使用適用於 Windows 的 Docker，就必須共用包含臨時目錄的磁片磁碟機 (這通常是 `C:\` Docker daemon 所) 的磁片磁碟機。 如需詳細資訊，請參閱[Docker 檔](https://docs.docker.com/docker-for-windows/#shared-drives)。

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

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>搭配使用量子開發工具組`qdk-chem`

若要安裝 `qdk-chem` ，您可以在命令列使用 .NET Core SDK：

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

安裝之後 `qdk-chem` ，您可以使用 `--help` 選項來取得工具所提供功能的更多詳細資料 `qdk-chem` 。

若要在 Broombridge 之間進行轉換，您可以使用 `qdk-chem convert` 命令：

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

此 `qdk-chem convert` 命令也可以接受其來自標準輸入的資料，並可寫入標準輸出; 這在腳本中特別有用，並與匯出為舊版格式的工具整合。
例如，在 Bash 中：

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
