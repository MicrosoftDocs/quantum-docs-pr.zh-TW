---
title: 測試並除錯 Q# 程式
description: 瞭解如何使用單元測試、事實和斷言以及轉儲函數來測試和調試量子程式。
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030577"
---
# <a name="testing-and-debugging"></a>測試和偵錯

與經典程式設計一樣,必須能夠檢查量子程式是否按預期操作,並能夠診斷不正確的量子程式。
在本節中,我們將介紹 Q# 提供的用於測試和調試量子程式的工具。

## <a name="unit-tests"></a>單元測試

測試經典程式的一種常見方法是編寫稱為*單元測試*的小程式,這些程式在庫中運行代碼,並將其輸出與一些預期輸出進行比較。
例如,我們可能希望確保`Square(2)``4`返回 ,因為我們知道*先驗*的 $2 我們要 2 我們要 2 = 4$。

Q# 支援為量子程式創建單元測試,可在[xUnit](https://xunit.github.io/)單元測試框架中作為測試執行。

### <a name="creating-a-test-project"></a>建立測試項目

#### <a name="visual-studio-2019"></a>[視覺工作室 2019](#tab/tabid-vs2019)

開啟 Visual Studio 2019。 跳到選單並`File``New` > `Project...`選擇 。
在右上角,搜索`Q#`,然後`Q# Test Project`選擇 範本。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

從您最喜愛的命令列中,執行以下指令:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

您的新專案將有一個檔`Tests.qs`,這為定義新的 Q# 單元測試提供了一個方便的位置。
最初,此檔包含一個範例單元`AllocateQubit`測試,該測試檢查新分配的 qubit{0}是否處於 $ket $ 狀態並列印訊息:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: 任何採用`Unit`類型`Unit`和返回 參數的 Q# 操作`@Test("...")`或函數都可以通過 屬性標記為單元測試。 `"QuantumSimulator"`上面該屬性的參數指定執行測試的目標。 可以在多個目標上執行單個測試。 例如,在上`@Test("ResourcesEstimator")``AllocateQubit`添加一個屬性。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
保存檔並執行所有測試。 現在應該有兩個單元測試,一個在昆騰模擬器上執行分配Qubit,另一個在資源估計器中執行。 

Q# 編譯器將內置目標"量子模擬器"、"Toffoli模擬器"和"資源估計器"識別為單元測試的有效執行目標。 還可以指定任何完全限定的名稱來定義自定義執行目標。 

### <a name="running-q-unit-tests"></a>執行 Q# 單元測試

#### <a name="visual-studio-2019"></a>[視覺工作室 2019](#tab/tabid-vs2019)

作為一次性`Test`每個解決方案設定,轉到選單並`Test Settings` > `Default Processor Architecture` > `X64`選擇 。

> [!TIP]
> Visual Studio 的預設處理器架構結構設定存儲在每個解決方案的`.suo`解決方案選項 ( ) 檔案中。
> 如果刪除此檔,則需要再次選擇`X64`作為處理器體系結構。

產生`Test`項目,轉到選單並選擇`Windows` > `Test Explorer`。 `AllocateQubit`將顯示在`Not Run Tests`組中的測試清單中。 選擇`Run All`或運行此單個測試,並且它應該通過!

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

要執行測試,請瀏覽到項目資料夾(包含`Tests.csproj`的資料夾),並執行以下指令:

```bash
$ dotnet restore
$ dotnet test
```

您應該會看到類似以下的輸出：

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

儲存測試可以根據其名稱和/或執行目標進行篩選:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

內部函數<xref:microsoft.quantum.intrinsic.message>具有`(String -> Unit)`類型 ,並能夠創建診斷消息。

#### <a name="visual-studio-2019"></a>[視覺工作室 2019](#tab/tabid-vs2019)

在測試資源管理器中執行測試並按一下測試後,將顯示一個面板,其中將顯示有關測試執行的資訊:通過/失敗狀態、已用時間和"輸出"連結。 如果按下「輸出」連結,測試輸出將在新視窗中打開。

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

每個測試的通過/失敗狀態由`dotnet test`列印到主控台。
對於失敗的測試,輸出也會列印到主控台,以幫助診斷故障。

***

## <a name="facts-and-assertions"></a>事實與斷言

由於 Q# 中的函數沒有_邏輯_副作用,因此從 Q# 程式中永遠無法觀察到執行輸出`()`類型為空元組 的函數的任何其他_效果_。
也就是說,目標計算機可以選擇不執行返回的任何函數`()`,保證此遺漏不會修改以下任何 Q# 代碼的行為。
這使得函數返回`()`(`Unit`即 ) 成為將斷言和調試邏輯嵌入到 Q# 程式中的有用工具。 

讓我們考慮一個簡單的範例:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

此處,關鍵字`fail`指示計算不應繼續,從而在運行 Q# 程式的目標電腦中引發異常。
根據定義,無法從 Q# 內部觀察到此類故障,因為在到達語句後不會運行`fail`進一步的 Q# 代碼。
因此,如果我們通過調用`PositivityFact`,我們可以放心,它的意見是積極的。

請注意,我們可以實現與`PositivityFact`[`Fact`](xref:microsoft.quantum.diagnostics.fact)<xref:microsoft.quantum.diagnostics>使用 命名空間中的函數相同的行為:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

另一方面,*斷言*與事實類似,但可能取決於目標計算機的狀態。 相應地,它們定義為操作,而事實定義為函數(如上所述)。
要理解區別,請考慮以下在斷言中使用事實:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

在這裡,我們使用 該<xref:microsoft.quantum.environment.getqubitsavailabletouse>操作返回可供使用的量子位數。
由於這顯然取決於程式的全域狀態及其執行環境,因此我們的定義`AssertQubitsAreAvailable`也必須是操作。
但是,我們可以使用該全域狀態生成一個簡單的`Bool`值作為函數的`Fact`輸入。

在這些想法的基礎上[,前奏](xref:microsoft.quantum.libraries.standard.prelude)提供了兩個特別有用的斷<xref:microsoft.quantum.intrinsic.assert>言<xref:microsoft.quantum.intrinsic.assertprob>, 兩`()`者都模仿到 上的操作。 這些斷言每個都採用一個 Pauli 運算符來描述特定的興趣測量、要對其進行測量的量子寄存器以及假設結果。
在通過類比工作的目標機器上,我們不受[無克隆定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的約束,可以執行這種測量,而不會干擾傳遞給此類斷言的寄存器。
然後,如果在實踐中無法觀察到假設結果`PositivityFact`,模擬器可以中止計算,類似於上面的函數:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

在物理量子硬體上,無克隆定理阻止量子狀態的檢查,`Assert``AssertProb`和 操作`()`只是返回 ,沒有其他效果。

命名<xref:microsoft.quantum.diagnostics>空間`Assert`提供了多個系列的函數,使我們能夠檢查更高級的條件。 

## <a name="dump-functions"></a>傾印函數

為了協助對量子程式進行故障排除,<xref:microsoft.quantum.diagnostics>命名空間提供了兩個函數,可以轉儲到檔案中的目標電腦的當前狀態<xref:microsoft.quantum.diagnostics.dumpmachine>:<xref:microsoft.quantum.diagnostics.dumpregister>和 。 每個機器的生成輸出取決於目標計算機。

### <a name="dumpmachine"></a>DumpMachine

作為量子開發工具組的一部分分佈的全態量子模擬器將整個量子系統的[波函數](https://en.wikipedia.org/wiki/Wave_function)寫入檔,作為一維的複數陣列,其中每個元素表示測量計算基礎狀態 $_ket_n$的概率的振幅,其中 $ket\n} = \ket\n= [ket\b_{n]...b_1b_0_$為位\{$b_i\}$。 例如,在只分配兩個量子位且處於量子狀態的計算機上,$$_開始\對齊_ket_psi}{1}= _frac{2}[sqrt]{00} \ket - [frac](1 ={2} i)]\ket,[end]###$${10}調用<xref:microsoft.quantum.diagnostics.dumpmachine>將生成此輸出:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一行按重要順序提供具有相應量子位的的的註釋。
其餘行描述以笛卡爾和極性格式測量基礎狀態向量 $_ket_n_$ 的概率振幅。 詳細介紹第一行:

* **`∣0❭:`** 此行對應於`0`計算基礎狀態
* **`0.707107 +  0.000000 i`**:以笛卡爾格式表示的概率振幅。
* **` == `**:符號`equal`分離兩個等效表示形式。
* **`**********  `**: 震級的圖形表示,`*`數量 與測量此狀態向量的概率成正比。
* **`[ 0.500000 ]`**:震級的數值
* **`    ---`**: 振幅相的圖形表示(見下文)。
* **`[ 0.0000 rad ]`**:相位的數值(以弧度表示)。

大小和相位都顯示圖形表示。 幅度表示是直截了當的:它顯示一個柱線`*`,柱值的概率越大。 對於相位,我們顯示以下符號以表示基於範圍的角度:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

以下範例顯示了`DumpMachine`某些常見狀態:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > qubit 的 ID 在執行時分配,它不一定與分配 qubit 的順序或其在 qubit 寄存器中的位置保持一致。


#### <a name="visual-studio-2019"></a>[視覺工作室 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 您可以透過在代碼中放置中斷點並檢查 qubit 變數的值來在 Visual Studio 中找出 qubit ID,例如:
  > 
  > ![在視覺工作室中顯示 qubit ID](~/media/qubit_id.png)
  >
  > `0`索引上的`register2`qubit 的代碼`3`= , 索`1`引`2`的 qubit 具有 id= 。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 您可以透過<xref:microsoft.quantum.intrinsic.message>使用函數並傳遞訊息中的 qubit 變數來找出 qubit ID,例如:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 可以產生此輸出:
  >```
  > 0=q:3; 1=q:2
  >```
  > 這`0``register2`表示 索引上的 qubit`3`具有 id_,`1`索引`2`的 qubit 具有 id= 。


***

<xref:microsoft.quantum.diagnostics.dumpmachine>是命名空間的<xref:microsoft.quantum.diagnostics>一部分,因此為了使用它,您必須添加一個`open`語句:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister>工作方式<xref:microsoft.quantum.diagnostics.dumpmachine>如下,只不過還需要一個量子位數組來將資訊量限制為僅與相應量子位相關的資訊量。

與<xref:microsoft.quantum.diagnostics.dumpmachine>,<xref:microsoft.quantum.diagnostics.dumpregister>生成 的資訊取決於目標計算機。 對於全態量子模擬器,它將波函數寫入到量子子系統的全域階段<xref:microsoft.quantum.diagnostics.dumpmachine>,該子系統由提供的量子位以與的格式相同。  例如, 再次拍攝一台只分配兩個量子位且處於量子狀態的機器 $$開始 \ket_psi} ={1}_frac _sqrt{2}{00} = ket - [frac[1{2} = i]\ket{0} {2} {1} {2}{0}<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[0]`{10} = - e_-i_pi/4{1}* ({2}[frac ]sqrt = \ket - [frac](1 = i)] \ket) \fc_-(1 = i)][sqrt] \ket),[ 結束]\align= $$$$$s 調用 生成 此輸出:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

並呼叫<xref:microsoft.quantum.diagnostics.dumpregister>`qubit[1]`產生此輸出:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

通常,與另一個寄存器糾纏的寄存器狀態是混合狀態,而不是純狀態。 在這種情況下,<xref:microsoft.quantum.diagnostics.dumpregister>輸出以下訊息:

```
Qubits provided (0;) are entangled with some other qubit.
```

下面的範例展示如何在 Q# 代碼<xref:microsoft.quantum.diagnostics.dumpregister>中<xref:microsoft.quantum.diagnostics.dumpmachine>使用兩 者:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>偵錯

除了函數與`Assert``Dump`操作,Q# 還支援標準 Visual Studio 除錯功能的子集:在模擬器上的程式碼執行期間,可以使用 F10[設定線斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints),[單步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)以及[檢查經典變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)。

從 Visual Studio 程式碼中的除錯利用由 OmniSharp 提供支援的 Visual Studio 程式碼延伸 C# 提供的除錯功能,並且需要安裝[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)。 
