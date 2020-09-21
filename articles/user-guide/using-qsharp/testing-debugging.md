---
title: 測試和偵錯
description: 瞭解如何使用單元測試、事實和判斷提示，以及傾印函式來測試和偵測量副程式。
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f2181d388a59c1c6c5a0f13c9aa49d5fa1e51ae
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833178"
---
# <a name="testing-and-debugging"></a>測試和偵錯

就像傳統程式設計一樣，必須能夠檢查量副程式是否正常運作，並且能夠診斷不正確的行為。
在本節中，我們將討論 Q# 針對量副程式進行測試和偵測所提供的工具。

## <a name="unit-tests"></a>單元測試

測試傳統程式的其中一個常見方法是撰寫稱為 *單元測試*的小程式，以在程式庫中執行程式碼，並將其輸出與某些預期輸出進行比較。
例如，您可以確定 `Square(2)` `4` 因為您知道 $ 2 ^ 2 = $4 的 *先驗* ，所以會傳回。

Q# 支援建立量副程式的單元測試，並可在 [xUnit](https://xunit.github.io/) 單元測試架構中以測試的形式執行。

### <a name="creating-a-test-project"></a>建立測試專案

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

開啟 Visual Studio 2019。 移**至 [檔案**] 功能表，然後選取 [**新增 > 專案**...]。在右上角，搜尋 `Q#` 並選取 [ ** Q# 測試專案**] 範本。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

從您最愛的命令列執行下列命令：
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

您的新專案有一個單一檔案 `Tests.qs` ，它提供了一個方便的位置來定義新的 Q# 單元測試。
一開始，這個檔案包含一個範例單元測試， `AllocateQubit` 它會檢查新配置的量子位是否處於 $ \ket {0} $ 狀態並列印訊息：

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

任何 Q# 採用型別和傳回之引數的作業或函數，都 `Unit` `Unit` 可以透過屬性標示為單元測試 `@Test("...")` 。 在上述範例中，該屬性的引數會 `"QuantumSimulator"` 指定測試執行的目標。 單一測試可以在多個目標上執行。 例如，在之前加入屬性 `@Test("ResourcesEstimator")` `AllocateQubit` 。 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
儲存檔案並執行所有測試。 現在應該會有兩個單元測試，一個在 `AllocateQubit` 上執行 `QuantumSimulator` ，另一個在上執行 `ResourcesEstimator` 。 

編譯器會將 Q# 內建目標 `"QuantumSimulator"` 、 `"ToffoliSimulator"` 和 `"ResourcesEstimator"` 視為單元測試的有效執行目標。 您也可以指定任何完整名稱來定義自訂的執行目標。 

### <a name="running-no-locq-unit-tests"></a>執行 Q# 單元測試

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在每個解決方案的一次性設定中，移至 [ **測試** ] 功能表，然後選取 [ **測試設定] > 預設的處理器架構 > X64**]。

> [!TIP]
> Visual Studio 的預設處理器架構設定會儲存在每個解決方案的解決方案選項 () 檔案中 `.suo` 。
> 如果您刪除此檔案，則需要再次選取 **X64** 作為處理器架構。

建立專案，開啟 [ **測試** ] 功能表，然後選取 [ **Windows > 測試瀏覽器**]。 **AllocateQubit** 會顯示在 [ **未執行的測試** ] 群組中的測試清單中。 選取 [ **全部執行** ] 或 [執行這個個別測試]。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

若要執行測試，請流覽至專案資料夾 (包含) 的資料夾 `Tests.csproj` ，然後執行命令：

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

您可以根據其名稱或執行目標來篩選單元測試：

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

內建函數 <xref:microsoft.quantum.intrinsic.message> 具有類型 `(String -> Unit)` ，可讓您建立診斷訊息。

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

在測試瀏覽器中執行測試並按一下測試之後，面板會顯示測試回合的相關資訊：通過/失敗狀態、經過時間，以及輸出的連結。 按一下 [ **輸出** ]，以在新視窗中開啟測試輸出。

![測試輸出](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

每項測試的通過/失敗狀態都會列印到主控台 `dotnet test` 。
針對失敗的測試，輸出也會列印到主控台，以協助診斷失敗。

***

## <a name="facts-and-assertions"></a>事實和判斷提示

因為中的函式沒有 Q# _邏輯_ 副作用，所以您永遠不會在程式中觀察到 Q# 任何其他類型的效果，從執行其輸出類型為空元組的函式 `()` 。
也就是說，目的電腦可以選擇不執行任何會傳回的函式，以 `()` 保證此省略不會修改任何下列程式碼的行為 Q# 。
此行為可讓函式傳回 `()` (，例如 `Unit`) 將判斷提示和偵測邏輯內嵌到程式中的有用工具 Q# 。 

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

在這裡，關鍵字 `fail` 表示計算不應繼續，並且會在執行程式的目的電腦上引發例外狀況 Q# 。
根據定義，無法從內觀察到這類失敗 Q# ，因為目的電腦在到達語句之後就不再執行程式 Q# 代碼 `fail` 。
因此，如果我們繼續進行呼叫 `PositivityFact` ，我們可以確保其輸入是正面的。

請注意，我們可以 `PositivityFact` 使用 [`Fact`](xref:microsoft.quantum.diagnostics.fact) 命名空間中的函式來執行相同的行為 <xref:microsoft.quantum.diagnostics> ：

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

另一方面，*判斷*提示的使用方式類似于事實，但可能取決於目的電腦的狀態。 同樣地，它們會定義為作業，而事實會定義為函式 (如先前範例) 。
若要瞭解差異，請考慮在判斷提示中使用下列事實：

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

在這裡，我們會使用作業 <xref:microsoft.quantum.environment.getqubitsavailabletouse> 來傳回可使用的量子位數目。
由於這取決於程式的全域狀態及其執行環境，我們的定義 `AssertQubitsAreAvailable` 也必須是一項作業。
不過，我們可以使用該全域狀態來產生簡單的 `Bool` 值做為函數的輸入 `Fact` 。

[序言](xref:microsoft.quantum.libraries.standard.prelude)是以這些概念為基礎，提供兩個特別有用的判斷提示， <xref:microsoft.quantum.diagnostics.assertmeasurement> 並將 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 模型化為作業 `()` 。 這些判斷提示各採用 Pauli 運算子，以描述感興趣的特定量值、執行測量的量子暫存器，以及假設結果。
由模擬運作的目的電腦不會受到 [無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)的系結，而且可以執行這類度量，而不會干擾傳遞至這類判斷提示的暫存器。
然後，模擬器可以像之前的函式一樣 `PositivityFact` ，在實務中未觀察到假設結果時停止計算：

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

在不復制定理可防止檢查量子狀態的實體量子硬體上， `AssertMeasurement` 和作業只會傳回而 `AssertMeasurementProbability` 不會 `()` 有其他效果。

<xref:microsoft.quantum.diagnostics>命名空間會提供更多的系列函式 `Assert` ，讓您可以檢查更多的 advanced 條件。 

## <a name="dump-functions"></a>傾印函式

為協助針對量副程式進行疑難排解， <xref:microsoft.quantum.diagnostics> 命名空間提供兩個函式，可將目的電腦的目前狀態傾印到檔案中： <xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister> 。 產生的輸出取決於目的電腦。

### <a name="dumpmachine"></a>DumpMachine

以量子開發工具組的一部分散發的全狀態量子模擬器，會寫入整個量子系統的 [wave](https://en.wikipedia.org/wiki/Wave_function) 函式檔案，做為一維的複數陣列，其中每個元素都代表測量計算基礎狀態 $ \ket{n} $ 之機率的波幅，其中 $ \ket{n} = \ket{b_ {n-1} .。。b_1b_0} $ 代表位 $ \{ b_i \} $。 例如，在只有兩個量子位的電腦上配置且在量子狀態 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } \ket 中 {2} {10} ，\end{align} $ $ 呼叫會 <xref:microsoft.quantum.diagnostics.dumpmachine> 產生下列輸出：

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

第一個資料列會以其重大順序提供批註，內含對應量子位的識別碼。
其餘的資料列描述測量以笛卡兒和極座標形式測量基礎狀態向量 $ \ket{n} $ 的機率幅度。 第一列的詳細資料：

* **`∣0❭:`** 此資料列對應于 `0` 計算基礎狀態
* **`0.707107 +  0.000000 i`**：笛卡兒格式的機率幅度。
* **` == `**： `equal` 符號會分隔兩個對等的表示。
* **`**********  `**：量值的圖形表示，的數目 `*` 會與測量這個狀態向量的機率成正比。
* **`[ 0.500000 ]`**：量值的數值
* **`    ---`**：振幅階段的圖形表示 (查看下列輸出) 。
* **`[ 0.0000 rad ]`**：階段的數值 (弧度) 。

大小和階段都會以圖形表示顯示。 大小表示是很簡單的：它會顯示一個橫條，也就是 `*` 更大的機率。 在階段中，我們會根據範圍顯示下列符號來代表角度：

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

下列範例顯示 `DumpMachine` 一些常見狀態：

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
  > 量子位的識別碼會在執行時間指派，且不一定會與量子位的配置順序或其在量子位暫存器中的位置對齊。


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > 您可以在程式碼中放入中斷點，並檢查量子位變數的值，以在 Visual Studio 中找出量子位識別碼，例如：
  > 
  > ![在 Visual Studio 中顯示量子位識別碼](~/media/qubit_id.png)
  >
  > 索引為 on 的 `0` 量子位 `register2` 具有 id = `3` ，量子位的索引 `1` 識別碼為 `2` 。

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > 您可以使用函式來尋找量子位識別碼 <xref:microsoft.quantum.intrinsic.message> ，並在訊息中傳遞量子位變數，例如：
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > 這可能會產生下列輸出：
  >```
  > 0=q:3; 1=q:2
  >```
  > 這表示具有 index 的量子位 `0` `register2` 具有 id =，而 `3` 索引的量子位具有 `1` id = `2` 。


***

因為 <xref:microsoft.quantum.diagnostics.dumpmachine> 是  <xref:microsoft.quantum.diagnostics> 命名空間的一部分，所以您必須加入 `open` 語句來存取它：

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

<xref:microsoft.quantum.diagnostics.dumpregister> 的運作方式 <xref:microsoft.quantum.diagnostics.dumpmachine> ，不同之處在于它也會採用量子位的陣列，將資訊數量限制為只有與相對應的量子位相關的資訊。

同樣地 <xref:microsoft.quantum.diagnostics.dumpmachine> ，所產生的資訊 <xref:microsoft.quantum.diagnostics.dumpregister> 取決於目的電腦。 針對完整狀態量子模擬器，它會寫入至檔案，而 wave 函式是由所提供量子位所產生的量子子系統全域階段所產生，其格式與相同 <xref:microsoft.quantum.diagnostics.dumpmachine> 。  例如，再一次重新執行一部只配置了兩個量子位的電腦，並在量子州 $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{ (1 + i) } {2} \ket {10} =-e ^ {-i \ pi/4} ( ( \frac {1} {\sqrt {2} } \ket {0} -\frac{ (1 + i) } {2} \ket {1} ) \otimes {2} } \frac{- {0} (\end{align} $ $ 呼叫 <xref:microsoft.quantum.diagnostics.dumpregister> 以 `qubit[0]` 產生下列輸出：

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

而且，呼叫 <xref:microsoft.quantum.diagnostics.dumpregister> 以 `qubit[1]` 產生下列輸出：

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

一般情況下，使用另一個暫存器纏結的暫存器狀態是混合的狀態，而不是單純的狀態。 在此情況下，會 <xref:microsoft.quantum.diagnostics.dumpregister> 輸出下列訊息：

```
Qubits provided (0;) are entangled with some other qubit.
```

下列範例會示範如何 <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> 在程式碼中使用和 Q# ：

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

在和函 `Assert` 式 `Dump` 和作業之上， Q# 支援標準 Visual Studio 偵錯工具功能的子集： [設定行中斷點](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)、 [使用 F10 逐步執行程式碼](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)，以及在模擬器上執行您的程式碼時，可以 [檢查傳統變數的值](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) 。

在 Visual Studio Code 中的偵錯工具會利用 c # 針對 OmniSharp 所支援的 Visual Studio Code 擴充功能所提供的偵錯工具，且需要安裝 [最新版本](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)。 
