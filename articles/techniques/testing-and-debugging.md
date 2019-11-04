---
title: 'Q # 技術-測試和調試 |Microsoft Docs'
description: 'Q # 技術-測試和調試'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183483"
---
# <a name="testing-and-debugging"></a>測試和調試

就像傳統程式設計一樣，要能夠檢查配量程式是否符合預期，以及能夠診斷出不正確的量副程式，是很重要的。
在本節中，我們將討論 Q # 提供的工具，以測試和偵測量副程式。

## <a name="unit-tests"></a>單元測試

測試傳統程式的一個常見方法是撰寫稱為「*單元測試*」的小型程式，以在程式庫中執行程式碼，並將其輸出與某些預期的輸出做比較。
例如，我們可能會想要確保 `Square(2)` 會傳回 `4`，因為我們知道 $ 2 ^ 2 = $4*的先驗*。

問 # 支援針對量副程式建立單元測試，並可在[xUnit](https://xunit.github.io/)單元測試架構中做為測試執行。

### <a name="creating-a-test-project"></a>建立測試專案

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

開啟 Visual Studio 2019。 移至 [`File`] 功能表，然後選取 [`New` > `Project...`]。
在 [專案範本瀏覽器] 的 [`Installed` > `Visual C#`] 底下，選取 [`Q# Test Project`] 範本。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

從您最愛的命令列中，執行下列命令：
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

不論是哪一種情況，您的新專案都會開啟兩個檔案。
第一個檔案（`Tests.qs`）提供一個方便的位置來定義新的 Q # 單元測試。
這個檔案一開始會包含一個範例單元測試 `AllocateQubitTest`，它會檢查新配置的 qubit 是否處於 $ \ket{0}$ 狀態，並會列印一則訊息：

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

與 `(Unit -> Unit)` 相容 `(Unit => Unit)` 或函式的任何 Q # 作業，都可以當做單元測試來執行。 

第二個檔案（`TestSuiteRunner.cs` 包含探索並執行 Q # 單元測試的方法）。 這是 `TestTarget` 批註 `OperationDriver` 屬性的方法。
`OperationDriver` 屬性是 Xunit 延伸模組程式庫 Xunit 的一部分。
單元測試架構會針對其探索到的每個 Q # 單元測試，呼叫 `TestTarget` 方法。
架構會透過 `op` 引數，將單元測試描述傳遞給方法。 下列程式程式碼：
```csharp
op.TestOperationRunner(sim);
```
在 `QuantumSimulator`上執行單元測試。

根據預設，單元測試探索機制會尋找符合下列屬性的所有 Q # 函數或相容類型的作業：
* 位於與 `OperationDriver` 屬性標注之方法相同的元件中。
* 位於與 `OperationDriver` 屬性標注之方法相同的命名空間中。
* 名稱結尾為 `Test`。

您可以使用 `OperationDriver` 屬性的選擇性參數來設定元件、命名空間和單元測試函式和作業的尾碼：
* `AssemblyName` 參數會設定要在其中搜尋測試的元件名稱。
* `TestNamespace` 參數會設定要在其中搜尋測試的命名空間名稱。
* `Suffix` 設定視為單元測試之作業或函數名稱的尾碼。

此外，`TestCasePrefix` 選擇性參數可讓您設定測試案例名稱的前置詞。 作業名稱前面的前置詞會出現在測試案例清單中。 例如，`TestCasePrefix = "QSim:"` 會導致 `AllocateQubitTest` 在找到的測試清單中顯示為 `QSim:AllocateQubitTest`。 這可能有助於表示用來執行測試的模擬器。

### <a name="running-q-unit-tests"></a>執行 Q # 單元測試

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

如果是一次的每一解決方案設定，請移至 `Test` 功能表，然後選取 `Test Settings` > `Default Processor Architecture` > `X64`。

> [!TIP]
> Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項（`.suo`）檔案中。
> 如果您刪除此檔案，則需要選取 [`X64`] 做為您的處理器架構。

建立專案，移至 [`Test`] 功能表，然後選取 [`Windows` > `Test Explorer`]。 `AllocateQubitTest` 會顯示在 `Not Run Tests` 群組中的測試清單中。 選取 `Run All` 或執行此個別測試，它應該會通過！

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

若要執行測試，請流覽至專案資料夾（包含 `Tests.csproj`的資料夾），然後執行命令：

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

***

## <a name="logging-and-assertions"></a>記錄和判斷提示

問 # 中的函式沒有副作用的其中一個重要結果，就是執行某個函式的輸出類型為空元組 `()` 的任何效果，都不能從 Q # 程式中觀察到。
也就是說，目的電腦可以選擇不執行任何會傳回 `()` 的函式，保證此省略不會修改任何下列 Q 號碼程式碼的行為。
這會讓函式傳回 `()` 有用的工具，將判斷提示和偵錯工具內嵌到 Q # 程式中。 

### <a name="logging"></a>記錄

內建函式 <xref:microsoft.quantum.intrinsic.message> 具有類型 `(String -> Unit)`，並可讓您建立診斷訊息。

`QuantumSimulator` 的 `onLog` 動作可以用來定義當問 # 程式碼呼叫 `Message`時所執行的動作。 根據預設，記錄的訊息會列印到標準輸出。

定義單元測試套件時，已記錄的訊息可以導向至測試輸出。 從 Q # 測試專案範本建立專案時，會針對套件預先設定此重新導向，並根據預設建立此重新導向，如下所示：

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在測試瀏覽器中執行測試並按一下測試之後，會出現一個面板，其中包含測試執行的相關資訊：通過/失敗狀態、經過時間和「輸出」連結。 如果您按一下 [輸出] 連結，測試輸出將會在新視窗中開啟。

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

`dotnet test`，會將每個測試的通過/失敗狀態列印到主控台。
針對失敗的測試，記錄為上述 `output.WriteLine(msg)` 呼叫結果的輸出也會列印到主控台，以協助診斷失敗。

***

### <a name="assertions"></a>聲明

相同的邏輯也可以套用到執行判斷提示。 讓我們來看一個簡單的範例：

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

在這裡，關鍵字 `fail` 表示計算不應繼續，而是在執行 Q # 程式的目的電腦中引發例外狀況。
根據定義，無法從 Q # 中觀察到這種錯誤，因為在到達 `fail` 語句之後，不會再執行 Q # 程式碼。
因此，如果我們繼續呼叫 `AssertPositive`，我們可以確保其輸入是正數。

根據這些想法，[序言](xref:microsoft.quantum.libraries.standard.prelude)提供兩個特別有用的判斷提示，<xref:microsoft.quantum.intrinsic.assert>，並 <xref:microsoft.quantum.intrinsic.assertprob> 模型化 as 作業放入 `()`。 這些判斷提示各自採用 Pauli 運算子來描述特定測量量、要執行測量的量子暫存器，以及假設結果。
在模擬使用的目的機器上，我們不會受限於「[無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)，而且可以執行這類測量，而不會干擾傳遞至這類判斷提示的暫存器。
模擬器之後就可以類似于上述的 `AssertPositive` 函式，如果在實際情況下不會觀察到假設的結果，就會中止計算：

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

在實體量子硬體上，如果沒有複製定理可防止檢查配量狀態，`Assert` 和 `AssertProb` 作業只會傳回 `()`，而不會有任何其他效果。

<xref:microsoft.quantum.diagnostics> 命名空間提供 `Assert` 系列的多項功能，可讓我們檢查更先進的條件。 

## <a name="dump-functions"></a>傾印函式

為了協助針對量副程式進行疑難排解，<xref:microsoft.quantum.diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister>。 產生的每個輸出都取決於目的電腦。

### <a name="dumpmachine"></a>DumpMachine

散發為量子開發工具組一部分的全狀態配量模擬器會以一維複數陣列的形式，將整個量子系統的[wave](https://en.wikipedia.org/wiki/Wave_function)函式寫入檔案中，其中每個元素都代表的振幅測量計算基礎狀態 $ \ket{n} $ 的機率，其中 $ \ket{n} = \ket{b_ {n-1} .。。bits $\{的 b_1b_0} $ b_i\}$。 例如，在只配置兩個 qubits 且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10}中的電腦上，\end{align} $ $ 呼叫 <xref:microsoft.quantum.diagnostics.dumpmachine> 會產生此輸出:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。
其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{n} $ 的機率幅度。 第一列的詳細資料：

* **`∣0❭:`** 此資料列對應至 `0` 計算基礎狀態
* **`0.707107 +  0.000000 i`** ：以笛卡兒格式的機率幅度。
* **` == `** ： `equal` sign seperates 兩個對等的標記法。
* **`**********  `** ：大小的圖形表示，`*` 的數目與測量此狀態向量的機率成正比。
* **`[ 0.500000 ]`** ：量值的數值
* **`    ---`** ：波幅階段的圖形標記法（請參閱下文）。
* **`[ 0.0000 rad ]`** ：階段的數值（以弧度為單位）。

大小和階段都會以圖形標記法顯示。 量值的表示方式很簡單：它會顯示 `*`的長條，長條的機率愈大。 在階段中，我們會根據範圍顯示下列符號來表示角度：

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

下列範例顯示一些常見狀態的 `DumpMachine`：

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


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 您可以在程式碼中放入中斷點，並檢查 qubit 變數的值，藉以找出 Visual Studio 中的 qubit 識別碼，例如：
  > 
  > ![在 Visual Studio 中顯示 qubit 識別碼](~/media/qubit_id.png)
  >
  > `register2` 索引 `0` 的 qubit 具有識別碼 =`3`，索引 `1` 的 qubit 具有識別碼 =`2`。

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 您可以使用 <xref:microsoft.quantum.intrinsic.message> 函式並傳遞訊息中的 qubit 變數，來找出 qubit 識別碼，例如：
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 這可能會產生此輸出：
  >```
  > 0=q:3; 1=q:2
  >```
  > 這表示 `register2` 索引 `0` 的 qubit 具有識別碼 =`3`，索引 `1` 的 qubit 具有識別碼 =`2`。


***

<xref:microsoft.quantum.diagnostics.dumpmachine> 是 <xref:microsoft.quantum.diagnostics> 命名空間的一部分，因此若要使用它，您必須加入 `open` 語句：

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

<xref:microsoft.quantum.diagnostics.dumpregister> 的運作方式類似 <xref:microsoft.quantum.diagnostics.dumpmachine>，不同之處在于它也會採用 qubits 陣列，將資訊數量限制為僅與對應的 qubits 相關。

如同 <xref:microsoft.quantum.diagnostics.dumpmachine>，<xref:microsoft.quantum.diagnostics.dumpregister> 產生的資訊取決於目的電腦。 對於全狀態的配量模擬器，它會將 wave 函式寫入檔案中，並以 <xref:microsoft.quantum.diagnostics.dumpmachine>的相同格式，由提供的 qubits 所產生的量子子系統的全域階段來運作。  例如，請再次將只有兩個 qubits 配置的機器，並在量子 state $ $ \begin{align} \ket{\psi} = \frac{1}{\sqrt{2}} \ket{00}-\frac{（1 + i）}{2} \ket{10} =-e ^ {-i \ pi/4} （（\frac{1}{\sqrt{2}} \ket{0}-\frac{（1 + i）}{2} \ket{1}） \otimes \frac{-（1 + i）} {\sqrt{2}} \ket{0}），\end{align} $ $ 呼叫 <xref:microsoft.quantum.diagnostics.dumpregister> 以進行 `qubit[0]` 會產生此輸出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

而呼叫 `qubit[1]` 的 <xref:microsoft.quantum.diagnostics.dumpregister> 會產生下列輸出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

一般來說，與另一個暫存器光子的暫存器的狀態是混合狀態，而不是純狀態。 在此情況下，<xref:microsoft.quantum.diagnostics.dumpregister> 會輸出下列訊息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下列範例會示範如何在您的 Q # 程式碼中使用 <xref:microsoft.quantum.diagnostics.dumpregister> 和 <xref:microsoft.quantum.diagnostics.dumpmachine>：

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

在 `Assert` 和 `Dump` 函式和作業之上，Q # 支援標準 Visual Studio 偵錯工具的子集：[設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、[使用 F10 逐步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)及[檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)在模擬器上執行程式碼期間都可以。

尚不支援在 Visual Studio Code 中進行調試。

