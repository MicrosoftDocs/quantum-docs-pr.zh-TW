---
title: 執行程式的方式 Q#
description: 概述執行程式的不同方式 Q# 。 從命令列、 Q# Jupyter 筆記本和傳統主機程式（以 Python 或 .net 語言）。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e3fa83700417a4ffaf9e3be91796c9e9513b253
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869727"
---
# <a name="ways-to-run-a-no-locq-program"></a>執行程式的方式 Q#

其中一個配量開發工具組的最大優點是跨平臺和開發環境的彈性。
不過，這也表示新的 Q# 使用者可能會因為[安裝指南](xref:microsoft.quantum.install)中的許多選項而感到困惑或不知所措。
在此頁面上，我們會說明執行程式時所發生 Q# 的狀況，並比較使用者可以執行的不同方式。

主要的差別在於 Q# 可以執行：
- 作為獨立應用程式，其中 Q# 是所牽涉到的唯一語言，而程式則是直接叫用。 有兩種方法實際上屬於此類別：
  - 命令列介面
  - Q#Jupyter 筆記本
- 使用以 Python 或 .NET 語言撰寫的其他*主機程式* (例如 c # 或 F # ) ，接著會叫用程式，並可進一步處理傳回的結果。

為了充分瞭解這些程式及其差異，我們考慮了一個簡單的 Q# 程式，並比較它可以執行的方式。

## <a name="basic-no-locq-program"></a>基本 Q# 程式

基本的量副程式可能包含在重迭狀態為 $ \ket $ 和 $ \ket $ 的等中準備 qubit {0} {1} 、測量它，然後傳回結果，而這兩個狀態的其中一種會以相等的機率隨機進行。
事實上，此程式是「[量子亂數產生器](xref:microsoft.quantum.quickstarts.qrng)」快速入門的核心。

在中 Q# ，這會由下列程式碼執行：

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

不過，此程式碼單獨無法由執行 Q# 。
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

雖然此頁面上的範例只包含 Q# *作業*，但我們所討論的所有概念也等同于函式 Q# * *，因此我們將它們統稱為*callables*。 其差異會在[ Q# 基本概念：作業](xref:microsoft.quantum.guide.basics#q-operations-and-functions)和函式中討論，而有關定義它們的詳細資訊可在[作業和](xref:microsoft.quantum.guide.operationsfunctions)函式中找到。

### <a name="callable-defined-in-a-no-locq-file"></a>檔案中 Q# 定義的可呼叫

可呼叫的就是所呼叫和所執行的 Q# 。
不過，它還需要一些額外的新增專案，才能組成完整的檔案 `*.qs` Q# 。

所有 Q# 類型和 callables (您所定義的，以及語言) 內建的，都是在*命名空間*中定義，這會提供可供參考的每一個完整名稱。

例如， [`H`](xref:microsoft.quantum.intrinsic.h) 和 [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) 作業可在 [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) 和命名空間中找到 [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) (部分的標準連結[ Q# 庫](xref:microsoft.quantum.qsharplibintro)) 。
因此，一律可以透過其*完整*名稱來呼叫它們， `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` 但一律這麼做會導致非常雜亂的程式碼。

相反地， `open` 語句可讓您以更精確的縮寫來參考 callables，如同我們在上述作業主體中所做的一樣。
因此，包含作業的完整檔案 Q# 包括定義我們自己的命名空間、開啟作業所使用之 callables 的命名空間，然後進行作業：

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

現在，程式的一般執行模式 Q# 會變得很清楚。

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

首先，要執行的特定可呼叫具有相同命名空間中定義的任何其他 callables 和類型的存取權。
它也會從任何程式庫存取這些連結[ Q# 庫](xref:microsoft.quantum.libraries)，但必須透過其完整名稱或使用上述語句來參考它們 `open` 。

可呼叫的本身會在*[目的電腦](xref:microsoft.quantum.machines)* 上執行。
這類目的機器可以是實際的量子硬體，或 QDK 中提供的多個模擬器。
就我們的目的而言，最有用的目的機器是一種[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器的實例， `QuantumSimulator` 它會計算程式的行為，就像是在免雜訊的量子電腦上執行一樣。

到目前為止，我們已說明在執行特定的可呼叫時，會發生什麼事 Q# 。
不論 Q# 是用於獨立應用程式還是主機程式中，這個一般程式都是更多或更少的---因此 QDK 的彈性。
另一種呼叫量子開發工具組的方法，因此會在叫用呼叫的*方式*中顯示其本身 Q# ，並以何種方式傳回任何結果。
更具體的說，差異在於 
1. 指出要執行哪些可呼叫 Q# ，
2. 如何提供可能的可呼叫引數，
3. 指定要在其上執行的目的電腦，以及
4. 傳回任何結果的方式。

首先，我們會討論如何 Q# 從命令列使用獨立應用程式來完成此作業，然後繼續使用 Python 和 c # 主機程式。
我們會保留 Jupyter 筆記本的獨立應用程式 Q# ，因為與前三項不同的是，它的主要功能並不是以本機檔案為中心 Q# 。

> [!NOTE]
> 雖然我們不會在這些範例中說明它，但執行方法之間的一個共同點是，從程式內部列印的任何訊息，都是透過 Q# 或的方式 ([`Message`](xref:microsoft.quantum.intrinsic.message) ，例如 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine)) 通常會列印到個別的主控台。

## <a name="no-locq-from-the-command-line"></a>Q#從命令列
開始撰寫程式最簡單的方法之一， Q# 就是避免擔心個別檔案和第二種語言。
搭配 QDK 擴充功能使用 Visual Studio Code 或 Visual Studio，可讓我們從單一檔案執行 callables 的順暢工作流程 Q# Q# 。

為此，我們最終會藉由輸入來叫用程式的執行
```dotnetcli
dotnet run
```
在命令列中。
最簡單的工作流程是當終端機的目錄位置與檔案相同時 Q# ，您可以 Q# 使用 VS Code 中的整合式終端機，輕鬆地在檔案編輯的同時進行處理，例如。
不過，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)會接受許多選項，而且只要提供檔案的位置，程式也可以從不同的位置執行 `--project <PATH>` Q# 。


### <a name="add-entry-point-to-no-locq-file"></a>將進入點新增 Q# 至檔案

大部分的檔案 Q# 會包含一個以上的可呼叫，因此，我們需要讓編譯器知道當我們提供命令時要執行*的可*呼叫 `dotnet run` 。
這是使用檔案本身的簡單變更來完成 Q# ： 
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

如果我們將 `@EntryPoint()` 屬性移至這個新作業的前面 (注意，檔案) 中只能有一條這一行，而嘗試執行它只會 `dotnet run` 產生錯誤訊息，指出需要哪些額外的命令列選項，以及如何表達它們。

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
> 在中定義的引數名稱， `camelCase` 會由編譯器稍微改變，以接受作為 Q# 輸入。 例如，如果不是 `n` ，我們使用上述的名稱 `numQubits` ，則會在命令列中透過 `--num-qubits 4` （而不是）來提供此輸入 `-n 4` 。

錯誤訊息也會提供可使用的其他選項，包括如何變更目的電腦。

### <a name="different-target-machines"></a>不同的目的電腦

由於我們的作業輸出在實際的 qubits 上是預期的動作結果，因此從命令列的預設目的電腦就是全狀態 quauntum 模擬器 `QuantumSimulator` 。
不過，我們可以指示 callables 在特定目的電腦上執行，並使用 `--simulator` (或速記 `-s`) 選項。

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

### <a name="non-no-locq-dotnet-run-options"></a>非 Q# `dotnet run` 選項

如同我們在上面提到的 `--project` 選項，此[ `dotnet run` 命令](https://docs.microsoft.com/dotnet/core/tools/dotnet-run)也會接受與可呼叫引數無關的選項 Q# 。
如果同時提供兩種選項， `dotnet` 必須先提供特定的選項，後面接著分隔符號 `--` ，然後是 Q# 特定的選項。
例如，針對上述作業，指定路徑和數位 qubits 會透過執行 `dotnet run --project <PATH> -- -n <n>` 。

## <a name="no-locq-with-host-programs"></a>Q#使用主機程式

使用我們的檔案 Q# 時，直接從命令列呼叫作業或函式的替代方法，是使用其他傳統語言的*主機程式*。 具體而言，這可以透過 Python 或 .NET 語言（例如 c # 或 F # (）來完成，因此我們只會在此詳述 c #) 。
若要啟用互通性，需要進行一些設定，但這些詳細資料可在[安裝指南](xref:microsoft.quantum.install)中找到。

簡言之，這種情況現在包含主機程式檔案 (例如 `*.py` `*.cs` ，或) 在與檔案相同的位置 Q# 。
它現在是已執行的*主機*程式，在執行過程中，它可以從檔案呼叫特定的 Q# 作業和函數 Q# 。
互通性的核心是以編譯器為基礎， Q# 讓主機程式可以存取檔案的內容， Q# 以便呼叫這些檔案。

使用主機程式的其中一個主要優點是，程式所傳回的傳統資料 Q# 可以在主機語言中進一步處理。
這可能是由一些先進的資料處理所組成 (例如，無法在) 內部執行的專案 Q# ，然後 Q# 根據這些結果呼叫進一步的動作，或做為繪製結果的簡單 Q# 方式。

一般的配置如下所示，我們將在下面討論 Python 和 c # 的特定執行。 您可以在[.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)（英文）中找到使用 F # 主機程式的範例。

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()` Q# 命令列應用程式所使用的屬性不能與主機程式一起使用。
> 如果主機所呼叫的檔案中有錯誤，則會引發錯誤 Q# 。 

若要使用不同的主機程式，檔案不需要進行任何變更 `*.qs` Q# 。
下列主機程式執行全都使用相同的檔案 Q# ：

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
1. 匯入 `qsharp` 模組，其會註冊模組載入器以進行 Q# 互通性。 
    這可讓 Q# 命名空間顯示為 Python 模組，我們可以從這裡「匯入」 Q# callables。
    請注意，技術上並不是匯 Q# 入的 callables 本身，而是允許呼叫它們的 Python 存根。
    然後這些類別的行為就像是 Python 類別的物件，我們會使用方法來指定要將作業傳送至執行的目的電腦。

2. 匯入這些 Q# callables，我們將在此案例中直接叫用--- `MeasureSuperposition` 和 `MeasureSuperpositionArray` 。
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    匯 `qsharp` 入模組之後，您也可以直接從連結 Q# 庫命名空間匯入 callables。

3. 在任何其他 Python 程式碼中，您現在可以在特定目的電腦上呼叫這些 callables，並將它們的傳回指派給變數， (如果傳回值) 以供進一步使用。

#### <a name="specifying-target-machines"></a>指定目的電腦
呼叫要在特定目的電腦上執行的作業，是透過匯入物件上不同的 Python 方法來完成。
例如， `.simulate(<args>)` `QuantumSimulator` 會使用來執行作業，而 `.estimate_resources(<args>)` 則是在上執行 `ResourcesEstimator` 。

#### <a name="passing-inputs-to-q"></a>將輸入傳遞至 Q\#
可呼叫的引數 Q# 應該以關鍵字引數的形式提供，其中關鍵字是可呼叫定義中的引數名稱 Q# 。
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

Q#編譯器的運作方式是從檔案中的命名空間產生名為 c # 的命名空間 Q# Q# 。
它會針對其中所定義的每個 callables 或類型，進一步產生名為的 c # 類別 Q# 。

首先，我們會將主機程式中使用的任何類別提供 `using` 給語句使用，其大致類似于為檔案 `open` 中的語句 Q# ：

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

接下來，我們會宣告 c # 命名空間、一些其他部分和片段 (在) 之下看到完整的程式碼區塊，然後使用任何傳統程式設計 (（例如計算 callables) 的引數） Q# 。
在我們的案例中，這不是必要的，但在[.net 互通性範例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)中可以找到這種用法的範例。

#### <a name="target-machines"></a>目標電腦

回到 Q# ，我們必須建立要在其中執行作業的目的電腦的實例。

```csharp
            using var sim = new QuantumSimulator();
```

使用其他目的機器就像具現化不同的電腦一樣簡單，不過執行此作業和處理傳回的方式可能稍有不同。
為求簡潔，我們現在會將設為 [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ，並包含 [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [下列](#including-the-resources-estimator)。

從作業產生的每個 c # 類別 Q# 都有 `Run` 方法，其第一個引數必須是目的機器實例。
因此，若要 `MeasureSuperposition` 在上執行 `QuantumSimulator` ，我們使用 `MeasureSuperposition.Run(sim)` 。
然後，可以將傳回的結果指派給 c # 中的變數：

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`方法會以非同步方式執行，因為這會是實際量子硬體的情況，因此 `await` 關鍵字會封鎖進一步執行，直到工作完成為止。

如果可呼叫的沒有任何傳回 (也就是 Q#) 的傳回型別 `Unit` ，則執行仍然可以相同的方式進行，而不需要將它指派給變數。
在此情況下，整個程式程式碼只會包含 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>引數

可呼叫的任何引數 Q# 只會當做 afer 目的電腦的其他引數傳遞。
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
> 由於編譯器與命名空間的互通性，我們也可以 Q# 在沒有語句的情況下提供 callables `using NamespaceName;` ，並只比對 c # 命名空間的標題。
> 也就是將取代 `namespace host` 為 `namespace NamespaceName` 。

#### <a name="including-the-resources-estimator"></a>包含資源估計工具

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)需要稍微不同的實作為捕獲輸出。

首先，改為使用語句來將它們具現化為變數 `using` (如同我們處理 `QuantumSimulator`) ，我們會透過將類別的物件更直接具現化

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

請注意，而不是多個作業所使用的單一目標模擬器 Q# ，我們已為每個作業具現化一個。 這是因為物件本身會在做為目的機器時修改，而且之後可以使用類別方法來抓取其結果 `.ToTSV()` 。

若要在資源估算器上執行作業，我們使用

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
然後以 tab 鍵分隔值的形式提取結果， (TSV) 搭配 `estimatorSingleQ.ToTSV()` 和 `estimatorMultiQ.ToTSV()` 。

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

## <a name="no-locq-jupyter-notebooks"></a>Q#Jupyter 筆記本
Q#Jupyter 筆記本利用 I Q# 核心，可讓您在單一筆記本中定義、編譯和執行 Q# callables，---全部都隨附指示、附注和其他內容。
這表示雖然可以匯入和使用檔案的內容 `*.qs` Q# ，但它們在執行模型中並不是必要的。

在這裡，我們將詳細說明如何執行 Q# 上述定義的作業，但在 Q# [簡介 Q# 和 Jupyter 筆記本](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)中，會提供使用 Jupyter 筆記本的更廣泛簡介。

### <a name="defining-operations"></a>定義作業

在 Q# Jupyter Notebook 中，您會輸入程式碼，就像我們在檔案的 Q# 命名空間內所做的一樣 Q# 。

因此，我們可以使用適用于其個別命名空間的語句，從[ Q# 標準程式庫](xref:microsoft.quantum.qsharplibintro)啟用 callables 的存取權 `open` 。
使用這類語句執行資料格時，這些命名空間的定義可在整個工作區中使用。

> [!NOTE]
> Callables 會[Microsoft.Quantum.Intrinsic](xref:microsoft.quantum.intrinsic) [Microsoft.Quantum.Canon](xref:microsoft.quantum.canon) [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) 自動提供給 Q# Jupyter 筆記本中的資料格內所定義的作業，而 Canon (例如和) 。
> 不過，從外部來源檔案引入的程式碼不是如此， Q# ([簡介 Q# 和 Jupyter 筆記本](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)) 所顯示的進程。 
> 

同樣地，定義作業只需要撰寫程式 Q# 代碼並執行儲存格。

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

然後，輸出會列出這些作業，然後再從未來的資料格進行呼叫。

### <a name="target-machines"></a>目標電腦

在特定目的電腦上執行作業的功能是透過[我的 Q# 魔術命令](xref:microsoft.quantum.guide.quickref.iqsharp)來提供。
例如， `%simulate` 會使用 `QuantumSimulator` ，並 `%estimate` 使用 `ResourcesEstimator` ：

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>將輸入傳遞至函數和作業

執行魔術命令目前只能搭配不接受引數的作業使用。 因此，若要執行，我們必須定義「包裝函式」作業， `MeasureSuperpositionArray` 然後使用引數呼叫作業：

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

這項作業當然可以與 `%estimate` 和其他執行命令類似使用。
