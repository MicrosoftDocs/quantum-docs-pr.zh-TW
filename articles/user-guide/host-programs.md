---
title: '執行 Q # 程式的方式'
description: '概述執行 Q # 程式的不同方式。 從命令列、Q # Jupyter 筆記本和傳統主機程式（Python 或 .NET 語言）。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887657"
---
# <a name="ways-to-run-a-q-program"></a>執行 Q # 程式的方式

其中一個配量開發工具組的最大優點是跨平臺和開發環境的彈性。
不過，這也表示新的 Q # 使用者可能會發現，在[安裝指南](xref:microsoft.quantum.install)中找到的許多選項會讓他們感到困惑或不知所措。
在此頁面上，我們將說明當問 # 程式執行時，會發生什麼事，並比較使用者可以執行這項作業的不同方式。

主要的差別在於可以執行 Q #：
- 作為獨立應用程式，其中 Q # 是唯一牽涉到的語言，而程式則是直接叫用。 有兩種方法實際上屬於此類別：
  - 命令列介面
  - Q# Jupyter Notebook
- 使用以 Python 或 .NET 語言（例如 c # 或 F #）撰寫的其他*主機程式*，接著會叫用程式，並可進一步處理傳回的結果。

為了充分瞭解這些程式及其差異，我們考慮了一個簡單的 Q # 程式，並比較它可以執行的方式。

## <a name="basic-q-program"></a>基本 Q # 程式

基本的量副程式可能包含在重迭狀態為 $ \ket $ 和 $ \ket $ 的等中準備 qubit {0} {1} 、測量它，然後傳回結果，而這兩個狀態的其中一種會以相等的機率隨機進行。
事實上，此程式是「[量子亂數產生器](xref:microsoft.quantum.quickstarts.qrng)」快速入門的核心。

在 Q # 中，這會由下列程式碼執行：

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

不過，此程式碼單獨無法由 Q # 執行。
為此，它需要組成作業的[主體，然後](xref:microsoft.quantum.guide.basics#q-operations-and-functions)在呼叫---直接或另一個作業時執行。 因此，您可以撰寫下列格式的作業：
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
您已定義 `MeasureSuperposition` 不接受任何輸入的作業，而且會傳回[結果](xref:microsoft.quantum.guide.types)類型的值。

雖然此頁面上的範例僅包含 Q #*作業*，但我們所討論的所有概念也等同于 q # 函*式，因此*我們將它們統稱為*callables*。 其差異會在[問答 # 基本概念：作業](xref:microsoft.quantum.guide.basics#q-operations-and-functions)和函式中討論，而有關定義它們的詳細資訊可在[作業和功能](xref:microsoft.quantum.guide.operationsfunctions)中找到。

### <a name="callable-defined-in-a-q-file"></a>在 Q # 檔案中定義的可呼叫

可呼叫的就是由 Q # 所呼叫和執行的確切方法。
不過，它還需要一些額外的新增專案，才能組成完整的 `*.qs` Q # 檔案。

所有的 Q # 類型和 callables （您所定義的和語言內建的）都是在*命名空間*中定義，這會提供可供參考的每一個完整名稱。

例如， [`H`](xref:microsoft.quantum.intrinsic.h) 和 [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 作業可在 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) 和命名空間中找到 [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) （ [Q # 標準程式庫](xref:microsoft.quantum.qsharplibintro)的一部分）。
因此，一律可以透過其*完整*名稱來呼叫它們， `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 但一律這麼做會導致非常雜亂的程式碼。

相反地， `open` 語句可讓您以更精確的縮寫來參考 callables，如同我們在上述作業主體中所做的一樣。
因此，包含我們的作業的完整 Q # 檔案是由定義我們自己的命名空間、開啟作業所使用之 callables 的命名空間，然後進行作業：

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> 命名空間也可以在開啟時進行*別名*，這有助於在兩個命名空間中的可呼叫/型別名稱衝突時很有説明。
> 例如，我們可以改為使用 `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` 上述，然後透過呼叫 `H` `NamespaceWithH.H(<qubit>)` 。

> [!NOTE]
> 其中一個例外狀況是 [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) 命名空間，它一律會自動開啟。
> 因此，您 [`Length`](xref:microsoft.quantum.core.length) 一律可以直接使用 callables like。

### <a name="execution-on-target-machines"></a>在目的電腦上執行

現在，Q # 程式的一般執行模式會變得很清楚。

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

首先，要執行的特定可呼叫具有相同命名空間中定義的任何其他 callables 和類型的存取權。
它也會從任何[Q # 程式庫](xref:microsoft.quantum.libraries)存取這些內容，但必須透過其完整名稱或使用上述語句來加以參考 `open` 。

可呼叫的本身會在*[目的電腦](xref:microsoft.quantum.machines)* 上執行。
這類目的機器可以是實際的量子硬體，或 QDK 中提供的多個模擬器。
就我們的目的而言，最有用的目的機器是一種[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器的實例， `QuantumSimulator` 它會計算程式的行為，就像是在免雜訊的量子電腦上執行一樣。

到目前為止，我們已說明執行特定的 Q # 可呼叫時，會發生什麼事。
無論是在獨立應用程式或主機程式中使用 Q #，這個一般程式都是更多或更少的---因此 QDK 的彈性。
呼叫量子開發工具組的不同方法之間的差異，因此會顯示*如何*呼叫 Q # 可呼叫的方式，以及傳回任何結果的方式。
更具體的說，差異在於 
1. 指出要執行哪一個 Q # 可呼叫，
2. 如何提供可能的可呼叫引數，
3. 指定要在其上執行的目的電腦，以及
4. 傳回任何結果的方式。

首先，我們會討論如何從命令列使用 Q # 獨立應用程式來完成此作業，然後繼續使用 Python 和 c # 主機程式。
最後，我們會保留 Q # Jupyter 筆記本的獨立應用程式，因為與前三項不同的是，它的主要功能並不是在本機的 Q # 檔案中間。

> [!NOTE]
> 雖然我們不會在這些範例中說明，但執行方法之間的一個共同點是，從 Q # 程式中列印的任何訊息（ [`Message`](xref:microsoft.quantum.intrinsic.message) 例如或 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ），通常都會列印到個別的主控台。

## <a name="q-from-the-command-line"></a>命令列中的 Q #
開始撰寫 Q # 程式最簡單的方法之一，就是避免擔心個別檔案和第二種語言。
使用 Visual Studio Code 或 Visual Studio 搭配 QDK 擴充功能，可讓我們從單一的 Q # 檔案執行 Q # callables，以提供順暢的工作流程。

為此，我們最終會藉由輸入來叫用程式的執行
```dotnetcli
dotnet run
```
在命令列中。
最簡單的工作流程是當終端機的目錄位置與 Q # 檔案相同時，您可以在 VS Code 中使用整合式終端機，輕鬆地與 Q # 檔案編輯一起處理，例如。
不過，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)會接受許多選項，而且程式也可以從不同的位置執行，方法是直接提供 `--project <PATH>` Q # 檔案的位置。


### <a name="add-entry-point-to-q-file"></a>將進入點新增至 Q # 檔案

大部分的 Q # 檔案會包含一個以上的可呼叫，因此，我們需要讓編譯器知道當我們提供命令時要執行*的可*呼叫 `dotnet run` 。
這是使用 Q # 檔案本身的簡單變更來完成： 
    - 加入具有 `@EntryPoint()` 直接在可呼叫前面的一行。

因此，上述的檔案會變成
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

現在， `dotnet run` 從命令列呼叫 `MeasureSuperposition` 會導致執行，然後傳回的值會直接列印到終端機。
因此，您會看到 `One` 或 `Zero` 列印。 

請注意，如果您在下方定義了更多 callables，則只 `MeasureSuperposition` 會執行。
此外，如果您的可呼叫在宣告之前包含[檔批註](xref:microsoft.quantum.guide.filestructure#documentation-comments)，就不會有任何問題， `@EntryPoint()` 屬性可以直接放在它們的上方。

### <a name="callable-arguments"></a>可呼叫的引數

到目前為止，我們只考慮不接受輸入的作業。
假設我們想要執行類似的作業，但在多個 qubits 上---提供作為引數的數目。
這類作業可以撰寫成
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
其中，傳回的值是測量結果的陣列。
請注意， [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 和 [`ForEach`](xref:microsoft.quantum.arrays.foreach) 都在 [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) 和 [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 命名空間中， `open` 每個都需要額外的語句。

如果我們將 `@EntryPoint()` 屬性移至這個新作業的前面（請注意，檔案中只能有一個這一行），嘗試執行它只會 `dotnet run` 產生一則錯誤訊息，指出需要哪些其他命令列選項，以及如何表達它們。

命令列的一般格式實際上是 `dotnet run [options]` ，而且會在該處提供可呼叫的引數。
在此情況下， `n` 會遺漏引數，並顯示我們需要提供選項 `-n <n>` 。 若要 `MeasureSuperpositionArray` 執行 `n=4` qubits，我們因此使用

```dotnetcli
dotnet run -n 4
```

產生類似于的輸出

```output
[Zero,One,One,One]
```

這當然會延伸到多個引數。

> [!NOTE]
> 在中定義的引數名稱 `camelCase` 會由編譯器稍微改變，以接受為 Q # 輸入。 例如，如果不是 `n` ，我們使用上述的名稱 `numQubits` ，則會在命令列中透過 `--num-qubits 4` （而不是）來提供此輸入 `-n 4` 。

錯誤訊息也會提供可使用的其他選項，包括如何變更目的電腦。

### <a name="different-target-machines"></a>不同的目的電腦

由於我們的作業輸出在實際的 qubits 上是預期的動作結果，因此從命令列的預設目的電腦就是全狀態 quauntum 模擬器 `QuantumSimulator` 。
不過，我們可以使用選項 `--simulator` （或速記）指示在特定目的電腦上執行 callables `-s` 。

例如，我們可以在上執行它 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) ：

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

列印的輸出就是

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

如需這些計量指示的詳細資訊，請參閱[Resource 估計工具：回報的計量](xref:microsoft.quantum.machines.resources-estimator#metrics-reported)。

### <a name="command-line-execution-summary"></a>命令列執行摘要
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>非 Q # `dotnet run` 選項

如同我們在上面提到的 `--project` 選項，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)也會接受與 Q # 可呼叫引數無關的選項。
如果同時提供兩種選項， `dotnet` 必須先提供特定的選項，後面接著分隔符號 `--` ，然後是 Q # 特有的選項。
例如，針對上述作業，指定路徑和數位 qubits 會透過執行 `dotnet run --project <PATH> -- -n <n>` 。

## <a name="q-with-host-programs"></a>Q # 與主機程式

在我們的問 # 檔案中，直接從命令列呼叫作業或函式的替代方法，是使用其他傳統語言的*主機程式*。 具體而言，這可以透過 Python 或 .NET 語言（例如 c # 或 F #）來完成（為了簡潔起見，我們只會在此詳述 c #）。
若要啟用互通性，需要進行一些設定，但這些詳細資料可在[安裝指南](xref:microsoft.quantum.install)中找到。

簡單地說，這種情況現在會 `*.py` `*.cs` 在與 Q # 檔案相同的位置中包含主機程式檔案（例如或）。
它現在是已執行的*主機*程式，在執行過程中，它可以從 q # 檔案呼叫特定的 q # 作業和函數。
互通性的核心是以 Q # 編譯器為基礎，讓 Q # 檔案的內容可供主機程式存取，以供呼叫。

使用主機程式的其中一個主要優點是，可以在主機語言中進一步處理 Q # 程式所傳回的傳統資料。
這可能是由一些先進的資料處理（例如，無法在 Q # 內部執行的專案）所組成，然後根據這些結果呼叫進一步的 Q # 動作，或像繪製 Q # 結果一樣簡單。

一般的配置如下所示，我們將在下面討論 Python 和 c # 的特定執行。 您可以在[.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)（英文）中找到使用 F # 主機程式的範例。

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> 用於 `@EntryPoint()` Q # 命令列應用程式的屬性不能與主機程式一起使用。
> 如果主控制項所呼叫的 Q # 檔案中有錯誤，則會引發錯誤。 

若要使用不同的主機程式，Q # 檔案不需要進行任何變更 `*.qs` 。
下列主機程式執行全都使用相同的 Q # 檔案：

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

選取與您感歡迎的主機語言相對應的索引標籤。

### <a name="python"></a>[Python](#tab/tabid-python)
Python 主機程式的結構如下所示：
1. 匯入 `qsharp` 模組，其會註冊 Q # 互通性的模組載入器。 
    這可讓 Q # 命名空間顯示為 Python 模組，我們可以從這裡「匯入」 Q # callables。
    請注意，技術上並不是已匯入的 Q # callables 本身，而是允許呼叫它們的 Python 存根。
    然後這些類別的行為就像是 Python 類別的物件，我們會使用方法來指定要將作業傳送至執行的目的電腦。

2. 匯入這些問 # callables，我們將在此案例中直接叫用--- `MeasureSuperposition` 和 `MeasureSuperpositionArray` 。
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    匯 `qsharp` 入模組之後，您也可以直接從 Q # 程式庫命名空間匯入 callables。

3. 在任何其他 Python 程式碼中，您現在可以在特定目的電腦上呼叫這些 callables，並將其傳回指派給變數（如果傳回值）以供進一步使用。

#### <a name="specifying-target-machines"></a>指定目的電腦
呼叫要在特定目的電腦上執行的作業，是透過匯入物件上不同的 Python 方法來完成。
例如， `.simulate(<args>)` `QuantumSimulator` 會使用來執行作業，而 `.estimate_resources(<args>)` 則是在上執行 `ResourcesEstimator` 。

#### <a name="passing-inputs-to-q"></a>將輸入傳遞至 Q\#
您應該以關鍵字引數的形式提供 Q # 可呼叫的引數，其中關鍵字是 Q # 可呼叫定義中的引數名稱。
也就是 `MeasureSuperpositionArray.simulate(n=4)` 有效，而則 `MeasureSuperpositionArray.simulate(4)` 會擲回錯誤。

因此，Python 主機程式 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

會產生如下所示的輸出：

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

C # 主機程式有多個元件，而且非常接近 QDK 的某些元件，例如模擬器，其本身是以 c # 為基礎。

問 # 編譯器的運作方式是從我們的 Q # 檔案中的 Q # 命名空間產生名為的 c # 命名空間。
它會針對每個 Q # callables 或其中所定義的類型，進一步產生名為的 c # 類別。

首先，我們會將主機程式中使用的任何類別提供 `using` 給語句使用，其大致類似于于 `open` Q # 檔案中的語句：

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

接下來，我們會宣告 c # 命名空間、一些其他部分（請參閱下方的完整程式碼區塊），然後再宣告任何傳統程式設計（例如，針對 Q # callables 計算引數）。
在我們的案例中，這不是必要的，但在[.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)中可以找到這種用法的範例。

#### <a name="target-machines"></a>目標電腦

回到問 #，我們必須建立要在其中執行作業之目的電腦的實例。

```csharp
            using var sim = new QuantumSimulator();
```

使用其他目的機器就像具現化不同的電腦一樣簡單，不過執行此作業和處理傳回的方式可能稍有不同。
為求簡潔，我們現在會將設為 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ，並包含 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [下列](#including-the-resources-estimator)。

從 Q # 作業產生的每個 c # 類別都有 `Run` 方法，其第一個引數必須是目的機器實例。
因此，若要 `MeasureSuperposition` 在上執行 `QuantumSimulator` ，我們使用 `MeasureSuperposition.Run(sim)` 。
然後，可以將傳回的結果指派給 c # 中的變數：

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`方法會以非同步方式執行，因為這會是實際量子硬體的情況，因此 `await` 關鍵字會封鎖進一步執行，直到工作完成為止。

如果問 # 可呼叫不具有任何傳回（也就是有傳回型別 `Unit` ），則執行時仍可以相同的方式進行，而不需要將它指派給變數。
在此情況下，整個程式程式碼只會包含 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>引數

只要以其他引數的形式傳遞 Q # 可呼叫的任何引數，就會 afer 目的電腦。
因此，qubits 上的結果會透過來 `MeasureSuperpositionArray` `n=4` 提取 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

因此，完整的 c # 主機程式可能如下所示

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

在 c # 檔案的位置，您可以在命令列中輸入來執行主機程式。
```dotnetcli
dotnet run
```
在此情況下，您會看到寫入主控台的輸出，如下所示 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> 由於編譯器與命名空間的互通性，因此我們可以在沒有語句的情況下，讓我們的 Q # callables 可供使用 `using NamespaceName;` ，並只比對 c # 命名空間的標題。
> 也就是將取代 `namespace host` 為 `namespace NamespaceName` 。

#### <a name="including-the-resources-estimator"></a>包含資源估計工具

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)需要稍微不同的實作為捕獲輸出。

首先，改為使用語句將它們當做變數來 `using` 具現化（如同我們所做的 `QuantumSimulator` ），我們會透過將類別的物件直接具現化

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

請注意，而不是多個 Q # 作業所使用的單一目標模擬器，而是每個都具現化一個。 這是因為物件本身會在做為目的機器時修改，而且之後可以使用類別方法來抓取其結果 `.ToTSV()` 。

若要在資源估算器上執行作業，我們使用

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
然後使用和，將結果當做定位字元分隔值（TSV）來提取 `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` 。

因此，完整的 c # 主機程式使用 `QuantumSimulator` 和都 `ResourcesEstimator` 可以採用下列格式：

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


這會產生類似的輸出

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a>Q# Jupyter Notebook
問 # Jupyter 筆記本使用 IQ # kernel，這可讓您在單一筆記本中定義、編譯和執行 Q # callables，---全部連同指示、附注和其他內容一起進行。
這表示雖然可以匯入和使用 Q # 檔案的內容 `*.qs` ，但它們在執行模型中並不是必要的。

在這裡，我們將詳細說明如何執行上面定義的 Q # 作業，但在[問答 # 和 Jupyter 筆記本簡介](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中，會提供使用 q # Jupyter 筆記本的更廣泛簡介。

### <a name="defining-operations"></a>定義作業

在 Q # Jupyter Notebook 中，您可以輸入 Q # 程式碼，就像我們在 Q # 檔案的命名空間內所做的一樣。

因此，我們可以使用適用于其個別命名空間的語句，從[Q # 標準程式庫](xref:microsoft.quantum.qsharplibintro)啟用 callables 的存取權 `open` 。
使用這類語句執行資料格時，這些命名空間的定義可在整個工作區中使用。

> [!NOTE]
> [Canon](xref:microsoft.quantum.canon) （例如和）[的 Callables](xref:microsoft.quantum.intrinsic)會 [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 自動提供給 Q # Jupyter 筆記本中的資料格內所定義的作業。
> 不過，從外部 Q # 來源檔案引入的程式碼並不適用（在[q # 和 Jupyter 筆記本簡介](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中所顯示的進程）。 
> 

同樣地，定義作業只需要撰寫 Q # 程式碼並執行儲存格。

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

然後，輸出會列出這些作業，然後再從未來的資料格進行呼叫。

### <a name="target-machines"></a>目標電腦

在特定目的電腦上執行作業的功能是透過[IQ # 魔術命令](xref:microsoft.quantum.guide.quickref.iqsharp)來提供。
例如， `%simulate` 會使用 `QuantumSimulator` ，並 `%estimate` 使用 `ResourcesEstimator` ：

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>將輸入傳遞至函數和作業

執行魔術命令目前只能搭配不接受引數的作業使用。 因此，若要執行，我們必須定義「包裝函式」作業， `MeasureSuperpositionArray` 然後使用引數呼叫作業：

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

這項作業當然可以與 `%estimate` 和其他執行命令類似使用。
