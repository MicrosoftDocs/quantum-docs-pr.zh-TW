---
title: 範例 NWChem 量副程式
description: 使用 NWChem 的輸入組，逐步解說取得量子化學模擬的閘道計數範例。
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: e0ec7dcbdccbab5c81177a4223c71fd3f2ce57d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847769"
---
# <a name="end-to-end-with-nwchem"></a>端對端使用 NWChem #

在本文中，您將逐步解說如何從 [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) 輸入組開始取得量子化學模擬的閘道計數範例。
繼續進行此範例之前，請確定您已安裝 Docker， [並遵循安裝和驗證指南](xref:microsoft.quantum.chemistry.concepts.installation)。

其他資訊：
- [NWChem 輸入投影片的結構](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [用於量子開發工具組的輸入組指令](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [安裝化學程式庫和相依性](xref:microsoft.quantum.chemistry.concepts.installation)
- [資源計數](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> 此範例需要 Windows PowerShell Core 才能執行。
> 下載適用于 Windows、macOS 或 Linux 的 PowerShell Core https://github.com/PowerShell/PowerShell 。

## <a name="importing-required-powershell-modules"></a>匯入必要的 PowerShell 模組 ##

如果您尚未這麼做，請複製 [Microsoft/量子存放庫](https://github.com/Microsoft/Quantum)，其中包含使用量子開發工具組的範例和公用程式：

```powershell
git clone https://github.com/Microsoft/Quantum
```

複製之後 `Microsoft/Quantum` ，請在 `cd` 資料夾中執行，並匯 `utilities/` 入 PowerShell 模組以使用 Docker 和 NWChem：

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> 根據預設，Windows 會防止執行任何腳本或模組做為安全性措施。
> 若要允許 `Invoke-NWChem.psm1` 在 Windows 上執行的模組，您可能需要變更原則。
> 若要這樣做，請執行 `Set-ExecutionPolicy` 下列命令：
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> 當您結束 PowerShell 時，原則將會還原。
> 如果您想要儲存原則，請針對下列各項使用不同的值 `-Scope` ：
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

您現在應該可以 `Convert-NWChemToBroombridge` 使用下列命令：

```powershell
Get-Command -Module InvokeNWChem
```

接下來，我們將匯入 `Get-GateCount` **GetGateCount** 範例所提供的命令。
如需完整的詳細資訊，請參閱 [範例所提供的指示](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount)。
接下來，執行下列程式， `<runtime>` 使用、或來取代， `win10-x64` `osx-x64` `linux-x64` 視您的作業系統而定：

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

您現在應該可以 `Get-GateCount` 使用下列命令：

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>輸入投影片 ##

NWChem 套件會採用稱為 _輸入_ 投影片的文字檔，以指定要解決的量子化學問題，以及其他參數，例如記憶體配置設定。
在此範例中，我們將使用 NWChem 隨附的其中一個預先製作的輸入投影片。
首先，複製 [nwchemgit/nwchem 存放庫](https://github.com/nwchemgit/nwchem)：

> [!NOTE]
> 由於這是非常大的存放庫，因此我們可以使用引數來進行淺層複製，以節省一些頻寬和磁碟空間 `--depth 1` 。
> 不過，這是選擇性的。
> 如果沒有，複製作業將會正常運作 `--depth 1` 。

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

此存放 `nwchemgit/nwchem` 庫隨附各種可用於量子開發工具組的輸入投影片，列在[ `QA/chem_library_tests` 資料夾](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests)底下。
在此範例中，我們將使用 `H4` 輸入組：

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

有問題的分子是由 4 hydrogen 原子組成的系統，這些原子會根據一個角度來排列，如投影片名稱所示的參數 `alpha` `h4_sto6g_alpha.nw` 。 H4 是自1970年起計算化學的已知 [分子基準](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) 。 此參數表示投影片 `sto6g` 會根據 Slater 類型的 orbital 來執行標記法，具體而言，就是與具有6個高斯基礎函式的 [停止-nG 基礎](https://en.wikipedia.org/wiki/STO-nG_basis_sets) 函數相關的標記法。 這份輸入組還包含了數個 NWChem Tensor 縮減 Engine 的指示 (的 TCE) ，引導 NWChem 產生與量子開發工具組交互操作所需的資訊：

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>從 NWChem 產生和取用 Broombridge 輸出 ##

您現在已具備產生和取用 Broombridge 檔所需的一切。
若要執行 NWChem 並為輸入組產生 Broombridge 檔 `h4_sto6g_0.000.nw` ，請執行 `Convert-NWChemToBroombridge` ：

> [!NOTE]
> 當您第一次執行此命令時，Docker 會 `nwchemorg/nwchem-qc` 為您下載映射。
> 這可能需要一些時間，視您的連線速度而定，可能會讓您有機會取得咖啡的咖啡。

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

這會產生名為的 Broombridge 檔 `h4_sto6g_0.000.yaml` ，您可以搭配 `Get-GateCount` 使用：

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

您現在應該會看到主控台輸出，其中包含各種量子模擬方法的資源估計，例如 T 計數、旋轉計數、CNOT 計數等：

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
- 試用不同的預先定義輸入投影片，例如，藉由改變 `alpha` 中的 `h4_sto6g_alpha.nw` 參數， 
- 嘗試直接編輯 NWChem 投影片來修改投影片，例如，探索 `STO-nG` 各種選項的模型， 
- 嘗試其他可用的預先定義 NWChem 輸入投影片 `nwchem/qa/chem_library_tests`
- 試用一套預先定義的 Broombridge YAML 基準測試（從 NWChem 產生），並可在 [Microsoft/量子存放庫](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)中取得。 這些基準測試包括： 
    - small 分子，例如分子 hydrogen (H2) 、Beryllium () 、鋰氫化 (LiH) 、
    - 較大的分子，例如臭氧 (O3) 、Beta carotene、cytosine 等等。 
- 試用以圖形化前端 [EMSL 箭](https://arrows.emsl.pnnl.gov/api/qsharp_chem) 號，以提供 Microsoft 量子開發工具組的介面。 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>從 EMSL 箭號產生 Broombridge 輸出 ##

若要開始使用 web 前端 EMSL 箭號，請 [在這裡](https://arrows.emsl.pnnl.gov/api/qsharp_chem)流覽瀏覽器。 

> [!NOTE]
> 在網頁瀏覽器中執行 EMSL 箭號需要啟用 JavaScript。 請參閱下列 [指示](https://www.enable-javascript.com/) ，以瞭解如何在瀏覽器中啟用 JavaScript。 

首先，在 [查詢] 方塊中輸入分子，顯示 ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

您可以依口語名稱輸入許多分子，例如 "caffeine" 而非 "1，3，7-Trimethylxanthine"。 

接著，按一下顯示的按鈕 ``theory{qsharp_chem}`` 。 這將會進一步填入查詢方塊，其中包含指示執行以 Broombridge YAML 格式匯出輸出的指示。 

現在，clock 開啟 ``Run Arrows`` 。 視輸入的大小而定，這可能需要一些時間。 或者，如果先前已計算過特定模型，則可以非常快速地完成，因為它只會計算資料庫中的查閱量。 無論是哪一種情況，您都會進入新的頁面，其中包含針對您的輸入所指定的 NWChem 所執行之特定的眾多資訊。 

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

按一下 [開啟] ``download`` ，以唯一的檔案名儲存本機複本，例如 ``qsharp_chem48443.yaml`` (每個執行) 的特定名稱將會不同。 然後，您可以進一步處理上述的檔案，例如，搭配 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
取得資源計數。 

您可以從 EMSL 箭號起始頁的索引標籤中，享受可以存取的3D 分子 builder ``Arrows Entry - 3D Builder`` 。 按一下所顯示分子的 [JSMol](http://wiki.jmol.org/index.php/JSmol) 3d 圖片可讓您進行編輯。 您可以四處移動原子、將原子分開，使其分子間的距離變更、新增/移除原子等。針對上述每個選項，在 [查詢] 方塊中加入之後 ``theory{qsharp_chem}`` ，您就可以產生 BROOMBRIDGE YAML 架構的實例，並使用量子化學程式庫進一步探索它。 
