---
title: 測試和偵錯
description: 瞭解如何使用單元測試、事實和判斷提示，以及傾印函式來測試和偵測量副程式。
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: 374ac42255ab6b2c5eff8ab7879b3a5103181f7f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430912"
---
# <a name="testing-and-debugging"></a>測試和偵錯

就像傳統程式設計一樣，要能夠檢查配量程式是否符合預期，以及能夠診斷出不正確的量副程式，是很重要的。
在本節中，我們將討論 Q # 提供的工具，以測試和偵測量副程式。

## <a name="unit-tests"></a>單元測試

測試傳統程式的一個常見方法是撰寫稱為「*單元測試*」的小型程式，以在程式庫中執行程式碼，並將其輸出與某些預期的輸出做比較。
例如，我們可能會想要確保傳回 `Square(2)` `4` ，因為我們知道 $ 2 ^ 2 = $4 的*先驗*。

問 # 支援針對量副程式建立單元測試，並可在[xUnit](https://xunit.github.io/)單元測試架構中做為測試執行。

### <a name="creating-a-test-project"></a>建立測試專案

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

開啟 Visual Studio 2019。 移至 `File` 功能表，然後選取 [] `New`  >  `Project...` 。
在右上角搜尋 `Q#` ，然後選取 `Q# Test Project` 範本。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

從您最愛的命令列中，執行下列命令：
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

您的新專案將會有一個檔案 `Tests.qs` ，可提供一個方便的位置來定義新的 Q # 單元測試。
一開始此檔案包含一個範例單元測試， `AllocateQubit` 它會檢查新配置的 qubit 是否處於 $ \ket {0} $ 狀態，並列印一則訊息：

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

：新增：接受類型的引數並傳回的任何 Q # 作業或函式，都 `Unit` `Unit` 可以透過屬性標示為單元測試 `@Test("...")` 。 上述屬性的引數 `"QuantumSimulator"` 會指定要在其上執行測試的目標。 單一測試可以在多個目標上執行。 例如，新增上述的屬性 `@Test("ResourcesEstimator")` `AllocateQubit` 。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
儲存檔案並執行所有測試。 現在應該有兩個單元測試，一個在 QuantumSimulator 上執行 AllocateQubit，另一個在 ResourceEstimator 中執行。 

Q # 編譯器會將內建目標 "QuantumSimulator"、"ToffoliSimulator" 和 "ResourcesEstimator" 辨識為適用于單元測試的有效執行目標。 也可以指定任何完整名稱，以定義自訂的執行目標。 

### <a name="running-q-unit-tests"></a>執行 Q # 單元測試

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

針對每個解決方案的一次設定，移至 `Test` 功能表並選取 `Test Settings`  >  `Default Processor Architecture`  >  `X64` 。

> [!TIP]
> Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項（）檔案中 `.suo` 。
> 如果您刪除此檔案，就必須 `X64` 再次選取作為您的處理器架構。

建立專案，移至 `Test` 功能表並選取 `Windows`  >  `Test Explorer` 。 `AllocateQubit`會顯示在群組中的測試清單中 `Not Run Tests` 。 選取 `Run All` 或執行此個別測試，它應該會通過！

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

若要執行測試，請流覽至專案資料夾（包含的資料夾 `Tests.csproj` ），然後執行命令：

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

單元測試可以根據其名稱和/或執行目標來進行篩選：

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

內建函式的 <xref:microsoft.quantum.intrinsic.message> 類型為 `(String -> Unit)` ，可讓您建立診斷訊息。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在測試瀏覽器中執行測試並按一下測試之後，會出現一個面板，其中包含測試執行的相關資訊：通過/失敗狀態、經過時間和「輸出」連結。 如果您按一下 [輸出] 連結，測試輸出將會在新視窗中開啟。

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

每項測試的通過/失敗狀態會由列印到主控台 `dotnet test` 。
對於失敗的測試，輸出也會列印到主控台，以協助診斷失敗。

***

## <a name="facts-and-assertions"></a>事實和判斷提示

因為 Q # 中的函式沒有任何_邏輯_副作用，所以執行其輸出類型為空元組之函式的任何_其他類型_， `()` 永遠不會從 Q # 程式中觀察到。
也就是說，目的電腦可以選擇不執行任何會傳回的函式， `()` 並保證此省略不會修改任何下列 Q 號碼程式碼的行為。
這會讓函式傳回（也就 `()` `Unit` 是）一個有用的工具，將判斷提示和偵錯工具內嵌到 Q # 程式中。 

讓我們來看一個簡單的範例：

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

在這裡，關鍵字 `fail` 指出計算不應繼續，並在執行 Q # 程式的目的電腦中引發例外狀況。
根據定義，無法從 Q # 中觀察到這種失敗，因為在到達語句之後，不會再執行任何其他的 Q # 程式碼 `fail` 。
因此，如果我們繼續呼叫 `PositivityFact` ，我們可以確保其輸入是正數。

請注意，我們可以 `PositivityFact` 使用 [`Fact`](xref:microsoft.quantum.diagnostics.fact) 命名空間中的函式，來執行與相同的行為 <xref:microsoft.quantum.diagnostics> ：

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

另一方面，*判斷*提示的使用方式類似于事實，但可能相依于目的電腦的狀態。 同樣地，它們會定義為作業，而事實會定義為函數（如上所示）。
若要瞭解差異，請考慮下列在判斷提示內的事實用法：

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

在這裡，我們會使用作業 <xref:microsoft.quantum.environment.getqubitsavailabletouse> 來傳回可供使用的 qubits 數目。
這顯然取決於程式及其執行環境的全域狀態，因此的定義 `AssertQubitsAreAvailable` 也必須是一項作業。
不過，我們可以使用該全域狀態來產生簡單的 `Bool` 值做為函數的輸入 `Fact` 。

根據這些想法，[序言](xref:microsoft.quantum.libraries.standard.prelude)提供兩個特別有用的判斷提示， <xref:microsoft.quantum.intrinsic.assert> 並將 <xref:microsoft.quantum.intrinsic.assertprob> 模型化為作業 `()` 。 這些判斷提示各自採用 Pauli 運算子來描述特定測量量、要執行測量的量子暫存器，以及假設結果。
在模擬使用的目的機器上，我們不會受限於「[無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)，而且可以執行這類測量，而不會干擾傳遞至這類判斷提示的暫存器。
模擬器可以接著類似于上述的函式 `PositivityFact` ，如果不會觀察到假設結果，則中止計算：

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

在實體量子硬體上，如果沒有複製定理可防止檢查配量狀態，和作業只會傳回，而 `Assert` `AssertProb` 不會 `()` 有其他效果。

命名空間提供多個系列函式，可 <xref:microsoft.quantum.diagnostics> `Assert` 讓我們檢查更先進的條件。 

## <a name="dump-functions"></a>傾印函式

為協助針對量副程式進行疑難排解， <xref:microsoft.quantum.diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister> 。 產生的每個輸出都取決於目的電腦。

### <a name="dumpmachine"></a>DumpMachine

散發為量子開發工具組一部分的全狀態配量模擬器會以一維複數陣列的形式，將整個量子系統的[wave 函數](https://en.wikipedia.org/wiki/Wave_function)寫入檔案中，其中每個專案都代表測量計算基礎狀態 $ \ket{n} $ 的機率幅度，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $ b_i $ b_1b_0} \{ $ \} 。 例如，在只配置兩個 qubits 且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{（1 + i）} \ket 的電腦上 {2} ， {10} \end{align} $ $ 呼叫會 <xref:microsoft.quantum.diagnostics.dumpmachine> 產生下列輸出：

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。
其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{n} $ 的機率幅度。 第一列的詳細資料：

* **`∣0❭:`** 此資料列對應于 `0` 計算基礎狀態
* **`0.707107 +  0.000000 i`**：笛卡爾格式的機率幅度。
* **` == `**： `equal` 正負號 seperates 兩個對等的標記法。
* **`**********  `**：大小的圖形表示，的數目與 `*` 測量此狀態向量的機率成正比。
* **`[ 0.500000 ]`**：量值的數值
* **`    ---`**：振幅階段的圖形標記法（請參閱下文）。
* **`[ 0.0000 rad ]`**：階段的數值（以弧度為單位）。

大小和階段都會以圖形標記法顯示。 量值的表示方式很簡單：它會顯示的長條，長條的機率愈大 `*` 。 在階段中，我們會根據範圍顯示下列符號來表示角度：

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

下列範例會顯示 `DumpMachine` 一些常見的狀態：

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
  > Qubit 的識別碼會在執行時間指派，而且不一定會與 qubit 的配置順序或其在 qubit 暫存器內的位置對齊。


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 您可以在程式碼中放入中斷點，並檢查 qubit 變數的值，藉以找出 Visual Studio 中的 qubit 識別碼，例如：
  > 
  > ![在 Visual Studio 中顯示 qubit 識別碼](~/media/qubit_id.png)
  >
  > 索引 on 的 qubit `0` `register2` 具有識別碼 = `3` ，索引的 qubit 具有 `1` 識別碼 = `2` 。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 您可以使用函式 <xref:microsoft.quantum.intrinsic.message> 並傳遞訊息中的 qubit 變數，來找出 qubit 識別碼，例如：
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 這可能會產生此輸出：
  >```
  > 0=q:3; 1=q:2
  >```
  > 這表示索引 on 的 qubit `0` `register2` 具有識別碼 = `3` ，索引的 qubit 具有 `1` 識別碼 = `2` 。


***

<xref:microsoft.quantum.diagnostics.dumpmachine>是 <xref:microsoft.quantum.diagnostics> 命名空間的一部分，因此若要使用它，您必須加入 `open` 語句：

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

<xref:microsoft.quantum.diagnostics.dumpregister>的運作方式類似 <xref:microsoft.quantum.diagnostics.dumpmachine> ，但它也會採用 qubits 陣列，將資訊數量限制為僅與對應的 qubits 相關。

如同 <xref:microsoft.quantum.diagnostics.dumpmachine> ，所產生的資訊 <xref:microsoft.quantum.diagnostics.dumpregister> 取決於目的電腦。 對於全狀態的配量模擬器，它會將 wave 函式寫入檔案中，並以與相同格式，由提供的 qubits 所產生之量子子系統的全域階段 <xref:microsoft.quantum.diagnostics.dumpmachine> 。  例如，再次使用已配置兩個 qubits 的機器，並在量子 state $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{（1 + i）} {2} \ket {10} =-e ^ {-i \ pi/4} （（\frac {1} {\sqrt {2} } \ket {0} -\frac{（1 + i）} \ket） {2} {1} \otimes \frac{-（1 + i）} {\sqrt {2} } \ket {0} ）、\end{align} $ $ 對的呼叫會產生下列 <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` 輸出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

<xref:microsoft.quantum.diagnostics.dumpregister>對的呼叫會 `qubit[1]` 產生下列輸出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

一般來說，與另一個暫存器光子的暫存器的狀態是混合狀態，而不是純狀態。 在此情況下，會 <xref:microsoft.quantum.diagnostics.dumpregister> 輸出下列訊息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下列範例會示範如何 <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> 在您的 Q # 程式碼中使用和：

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

在和函 `Assert` 式 `Dump` 和作業的頂端，Q # 支援標準 Visual Studio 偵錯工具的子集：[設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)及[檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)，都可以在模擬器的程式碼執行期間進行。

在 Visual Studio Code 中的偵錯工具會利用 c # 提供的偵錯工具功能，以供 OmniSharp 所支援的 Visual Studio Code 延伸模組，而且需要安裝[最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。 
