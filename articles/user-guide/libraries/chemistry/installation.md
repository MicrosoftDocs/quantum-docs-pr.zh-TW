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
ms.openlocfilehash: f1a7d1d041dab73980d8debc179d6c79acac6d33
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759794"
---
# <a name="chemistry-library-installation"></a>化學程式庫安裝

[ **MolecularHydrogen**範例](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen)會使用手動設定的分子輸入資料。
雖然這適用于小型範例，但大規模的量子化學需要 Hamiltonian 上百萬或數十億個詞彙。
可調整的計算化學套件所產生的這類 Hamiltonian 太大，無法以手動方式匯入。

量子開發工具組的量子化學程式庫是設計來與運算化學套件搭配使用，最值得注意的是， [**NWChem**](http://www.nwchem-sw.org/) 的計算化學平臺是由環境分子科學實驗室所開發 (EMSL 在太平洋西北部國內實驗室的) 。
尤其是，在[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中， [ **Microsoft 量子化學**套件](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)提供載入量子化學模擬問題實例的工具，也支援最新的 NWChem 版本進行匯出。

量子開發工具組化學程式庫也提供命令列工具，可 `qdk-chem` 用於在舊版格式和 [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)之間進行轉換。

本節將詳細說明如何使用 NWChem 和 Broombridge 的量子開發工具組，或舊版格式和 `qdk-chem` 。

## <a name="using-the-quantum-development-kit-with-nwchem"></a>使用量子開發工具組搭配 NWChem

若要使用 NWChem 搭配量子開發工具組來啟動並執行，請使用下列其中一種方法：

- 在 [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)上使用範例中提供的現有 Broombridge 檔案開始使用。
- 使用 [Microsoft 量子開發工具組的 EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem) 號產生器（這是以 web 為基礎的前端來 NWChem），以產生新的 Broombridge 格式化分子輸入檔。  
- 使用 KRISHNAMOORTHY 提供的 [Docker 映射](https://hub.docker.com/r/nwchemorg/nwchem-qc/) 來執行 NWChem，或
- 為您的平臺[編譯 NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) 。

如需有關如何使用 NWChem 與化學模型來分析量子 Developmen 套件化學程式庫的詳細資訊，請參閱 [使用 NWChem 的端對端](xref:microsoft.quantum.chemistry.examples.endtoend) 。

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>開始使用範例中提供的 Broombridge 檔案

量子開發工具組範例存放庫中的 [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML) 資料夾包含 Broombridge 格式化的分子資料檔案。  

簡單的範例，請使用化學程式庫範例 [GetGateCount](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/GetGateCount) ，從 Broombridge 檔的其中一個載入 Hamiltonian，並執行量子模擬 algorigthms 的閘道估計：

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

如需如何輸入 Broombridge 架構所代表之分子的詳細資訊，請參閱 [從檔案載入 Hamiltonian](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) 。  

如需資源估計的詳細資訊，請參閱 [取得資源計數](xref:microsoft.quantum.chemistry.examples.resourcecounts) 。  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>開始使用 EMSL 箭號 Builder

EMSL 箭號是使用 NWChem 和化學計算資料庫來產生分子資料的工具。  [適用于 Microsoft 量子開發工具組的 EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem) 號產生器可讓您使用多個分子模型產生器來輸入您的模型，並產生量子開發工具組所要使用的 Broombridge 資料檔案。  

在 [EMSL] 頁面上，按一下 [' 指令 '] 索引標籤，然後依照 [' Simple 範例 '] 指示來產生 Broombridge 檔案。  然後嘗試執行 [' GetGateCount ']，以查看這些分子的量子資源預估值。

### <a name="installing-nwchem-from-source"></a>從來源安裝 NWChem

[由 krishnamoorthy 提供](http://www.nwchem-sw.org/index.php/Compiling_NWChem)有關如何從來源安裝 NWChem 的完整指示。

> [!TIP]
> 如果您想要從 Windows 10 使用 NWChem，則 Windows 子系統 Linux 版是絕佳的選項。
> 安裝 [適用于 Windows 的 Ubuntu 18.04 LTS](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)之後，請 `ubuntu18.04` 從您最愛的終端機執行，並遵循上面的指示，從來源安裝 NWChem。

從來源編譯 NWChem 之後，您可以執行 `yaml_driver` NWChem 隨附的腳本，從 NWChem 輸入投影片快速產生 Broombridge 實例：

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

此命令會 `input.yaml` 在您目前的目錄中建立 Broombridge 格式的新檔案。

### <a name="using-nwchem-with-docker"></a>搭配使用 NWChem 與 Docker

使用 NWChem 的預先建立映射可透過 [Docker Hub](https://hub.docker.com)跨平臺使用。
若要開始使用，請遵循適用于您平臺的 Docker 安裝指示：

- [安裝適用于 Ubuntu 的 Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [安裝適用于 macOS 的 Docker](https://docs.docker.com/docker-for-mac/install/)
- [安裝適用於 Windows 的 Docker 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> 如果您使用適用於 Windows 的 Docker，就必須共用包含臨時目錄的磁片磁碟機 (這通常是 `C:\` 使用 Docker daemon) 的磁片磁碟機。 如需詳細資訊，請參閱 [Docker 檔](https://docs.docker.com/docker-for-windows/#shared-drives) 。

安裝 Docker 之後，您可以使用隨附于量子開發工具組範例的 PowerShell 模組來執行映射，也可以手動執行映射。
我們將在此詳細說明如何使用 PowerShell;如果您想要手動使用 Docker 映射，請參閱 [映射所提供的檔](https://hub.docker.com/r/nwchemorg/nwchem-qc/)。

#### <a name="running-nwchem-through-powershell-core"></a>正在執行 NWChem 至 PowerShell Core

為了搭配使用 NWChem Docker 映射與量子開發工具組，我們提供了一個小型的 PowerShell 模組，可處理移入和移出 NWChem 的檔案。
如果您還沒有安裝 PowerShell Core，可以從 [GitHub 上的 PowerShell 存放庫](https://github.com/PowerShell/PowerShell#get-powershell)下載跨平臺。

> [!NOTE]
> PowerShell Core 也會用於一些範例，以示範與資料科學和商務分析工作流程之間的互通性。

安裝 PowerShell Core 之後，請匯入 `InvokeNWChem.psm1` 以使 NWChem 命令可在目前的會話中使用：

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

這會讓 `Convert-NWChemToBroombridge` 命令可在您目前的 PowerShell 會話中使用。
若要從 Docker 下載任何所需的映射，並使用它們來執行 NWChem 輸入投影片並將輸出捕獲到 Broombridge，請執行下列動作：

```powershell
Convert-NWChemToBroombridge ./input.nw
```

這會藉由在上執行 NWChem 來建立 Broombridge 檔 `input.nw` 。
根據預設，Broombridge 輸出的名稱和路徑會與輸入組的名稱和路徑相同，並以 `.nw` 取代的副檔名取代 `.yaml` 。
這可以透過使用 `-DestinationPath` 參數來覆寫 `Convert-NWChemToBroombridge` 。
您可以使用 PowerShell 的內建說明功能來取得詳細資訊：

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>使用量子開發工具組搭配 `qdk-chem`

若要安裝 `qdk-chem` ，您可以在命令列使用 .NET Core SDK：

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

安裝之後 `qdk-chem` ，您可以使用 `--help` 選項來取得工具所提供功能的更多詳細資料 `qdk-chem` 。

若要在 Broombridge 之間轉換，您可以使用 `qdk-chem convert` 下列命令：

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

此 `qdk-chem convert` 命令也可以接受來自標準輸入的資料，並且可以寫入標準輸出; 這在腳本中特別有用，而且可與匯出為舊版格式的工具整合。
例如，在 Bash 中：

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
