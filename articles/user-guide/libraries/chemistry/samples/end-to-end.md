---
title: 範例 NWChem 量副程式
description: 使用 NWChem 的輸入組，逐步解說取得量子化學模擬的閘道計數範例。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 7605676e05ee352e47791657eeaafceef5dbb493
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274346"
---
# <a name="end-to-end-with-nwchem"></a>端對端使用 NWChem #

在本文中，您將逐步解說從[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)的輸入牌中取得量子化學模擬的閘道計數的範例。
繼續進行此範例之前，請確定您已安裝 Docker，請遵循[安裝和驗證指南](xref:microsoft.quantum.chemistry.concepts.installation)。

其他資訊：
- [NWChem 輸入卡座的結構](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [用於配量開發工具組的輸入組命令](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [安裝化學程式庫和相依性](xref:microsoft.quantum.chemistry.concepts.installation)
- [資源計數](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> 此範例需要執行 Windows PowerShell Core。
> 在下載適用于 Windows、macOS 或 Linux 的 PowerShell Core https://github.com/PowerShell/PowerShell 。

## <a name="importing-required-powershell-modules"></a>匯入必要的 PowerShell 模組 ##

如果您尚未這麼做，請複製[Microsoft/量子存放庫](https://github.com/Microsoft/Quantum)，其中包含使用配量開發工具組的範例和公用程式：

```powershell
git clone https://github.com/Microsoft/Quantum
```

複製之後 `Microsoft/Quantum` ，請執行 `cd` `utilities/` 資料夾並匯入 PowerShell 模組，以使用 Docker 和 NWChem：

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> 根據預設，Windows 會防止執行任何腳本或模組做為安全性措施。
> 若要允許之類的模組 `Invoke-NWChem.psm1` 在 Windows 上執行，您可能需要變更執行原則。
> 若要這麼做，請執行 `Set-ExecutionPolicy` 命令：
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> 然後，當您結束 PowerShell 時，就會還原執行原則。
> 如果您想要儲存執行原則，請針對下列各項使用不同的值 `-Scope` ：
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

您現在應該有 `Convert-NWChemToBroombridge` 可用的命令：

```powershell
Get-Command -Module InvokeNWChem
```

接下來，我們將匯入 `Get-GateCount` **GetGateCount**範例所提供的命令。
如需完整詳細資料，請參閱[範例提供的指示](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount)。
接下來，請執行下列 `<runtime>` 程式，並以 `win10-x64` 、或取代， `osx-x64` `linux-x64` 視您的作業系統而定：

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

您現在應該有 `Get-GateCount` 可用的命令：

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>輸入牌 ##

NWChem 套件會採用一個稱為_輸入組_的文字檔，它會指定要解決的量子化學問題，以及其他參數，例如記憶體配置設定。
在此範例中，我們將使用 NWChem 隨附的其中一個預先製作的輸入組。
首先，複製[nwchemgit/nwchem 存放庫](https://github.com/nwchemgit/nwchem)：

> [!NOTE]
> 因為這是非常大型的存放庫，所以我們可以執行淺層複製，以使用引數來儲存一些頻寬和磁碟空間 `--depth 1` 。
> 不過，這是選擇性的。
> 在沒有的情況下，複製作業就沒問題 `--depth 1` 。

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

存放 `nwchemgit/nwchem` 庫隨附各種不同的輸入表，適用于在[ `QA/chem_library_tests` 資料夾](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)底下列出的量子開發工具組。
在此範例中，我們將使用 `H4` 輸入組：

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

有問題的分子是4個 hydrogen 原子的系統，其相片順序是根據某個角度的特定幾何， `alpha` 如組名中所指出的參數 `h4_sto6g_alpha.nw` 。 H4 是自1970年起，適用于計算化學的已知[分子基準測試](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511)。 參數表示 `sto6g` 該牌堆會根據 Slater 類型的 orbital 來實作為標記法，具體來說，就是與具有6個高斯基礎函式的[停止 nG 設定](https://en.wikipedia.org/wiki/STO-nG_basis_sets)相關的標記法。 此輸入組還包含數個 NWChem 張量縮減 Engine （TCE）指示，引導 NWChem 產生與量子開發工具組互通所需的資訊：

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>產生和使用 NWChem 的 Broombridge 輸出 ##

您現在已具備產生和使用 Broombridge 檔所需的所有專案。
若要執行 NWChem 並為輸入組產生 Broombridge 檔 `h4_sto6g_0.000.nw` ，請執行 `Convert-NWChemToBroombridge` ：

> [!NOTE]
> 當您第一次執行此命令時，Docker 會 `nwchemorg/nwchem-qc` 為您下載映射。
> 這可能需要一些時間，視您的連線速度而定，可能會提供一杯咖啡的機會。

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

這會產生名為的 Broombridge 檔 `h4_sto6g_0.000.yaml` ，您可以搭配 `Get-GateCount` 使用：

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

您現在應該會看到包含資源估計的主控台輸出，例如 T 計數、旋轉計數、CNOT-CONTAINS 計數等等，適用于各種不同的量子模擬方法：

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

這裡有許多要做的事： 
- 請嘗試不同的預先定義輸入組，例如，藉由 `alpha` 在中改變參數 `h4_sto6g_alpha.nw` ， 
- 嘗試直接編輯 NWChem 投影片來修改投影片，例如，探索 `STO-nG` 各種 n 選項的模型， 
- 嘗試其他預先定義的 NWChem 輸入卡座，其位於 `nwchem/qa/chem_library_tests` 、
- 試用從 NWChem 產生的一組預先定義的 Broombridge YAML 基準測試，並以[Microsoft/量子存放庫](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)的一部分提供。 這些基準測試包括： 
    - 小型分子驅使分子，例如分子 hydrogen （H2）、Beryllium （是）、鋰鎳氫（LiH）、
    - 較大的分子驅使分子，例如 ozone （O3）、搶鮮版（Beta） carotene、cytosine 等等。 
- 試試看具有 Microsoft Quantum Development Kit 介面的圖形化前端[EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem)號。 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>從 EMSL 箭號產生 Broombridge 輸出 ##

若要開始使用以 web 為基礎的前端 EMSL 箭號，請在[這裡](https://arrows.emsl.pnnl.gov/api/qsharp_chem)流覽瀏覽器。 

> [!NOTE]
> 在網頁瀏覽器中執行 EMSL 箭號需要啟用 JavaScript。 請參閱這些[指示](https://www.enable-javascript.com/)，以瞭解如何在您的瀏覽器中啟用 JavaScript。 

首先，在 [查詢] 方塊中輸入分子，其中會顯示``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

您可以依其口語上名稱輸入許多分子驅使分子，例如 "caffeine"，而不是 "1，3，7-Trimethylxanthine"。 

接下來，按一下顯示的按鈕 ``theory{qsharp_chem}`` 。 這將會進一步在查詢方塊中填入指示，此指令會告知執行以 Broombridge YAML 格式匯出輸出。 

現在，時鐘開啟 ``Run Arrows`` 。 視輸入的大小而定，這可能需要一些時間。 或者，如果已在之前計算過特定的模型，則可以非常快速地完成作業，因為它只會為資料庫中的查閱量。 不論是哪一種情況，您都會進入新的頁面，其中包含針對輸入所指定之 NWChem 的特定執行相關資訊眾多。 

您可以從開頭為下列標頭的區段下載並儲存 Broombridge YAML 檔案： 
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

按一下 [開啟] ``download`` ，以使用唯一的檔案名（例如）來儲存本機複本 ``qsharp_chem48443.yaml`` （每次執行時，特定名稱會不同）。 然後，您可以使用上述程式進一步處理此檔案，例如 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
取得資源計數。 

您可能會喜歡可從 ``Arrows Entry - 3D Builder`` [EMSL 箭號] 起始頁的索引標籤存取的3d 分子 builder。 按一下所顯示分子的[JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 圖片，即可讓您進行編輯。 您可以四處移動原子、將原子拖曳到彼此的分子距離變更、新增/移除原子等等。針對上述每個選項，一旦您 ``theory{qsharp_chem}`` 在 [查詢] 方塊中新增，您就可以產生 BROOMBRIDGE YAML 架構的實例，並使用 [量子化學程式庫] 進一步探索它。 
