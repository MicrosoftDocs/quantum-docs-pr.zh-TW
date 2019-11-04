---
title: 量子模擬器和主應用程式 | Microsoft Docs
description: 說明如何使用傳統運算的 .NET 語言 (通常是 C# 或 Q#) 來驅動量子模擬器。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442221"
---
# <a name="quantum-simulators-and-host-applications"></a>量子模擬器和主應用程式

## <a name="what-youll-learn"></a>您會學習到的知識

> [!div class="checklist"]
> * 執行量子演算法的方法
> * 此版本包含哪些量子模擬器
> * 如何為量子演算法編寫 C# 驅動程式

## <a name="the-quantum-development-kit-execution-model"></a>Quantum Development Kit 執行模型

在[編寫量子程式](xref:microsoft.quantum.write-program)中，我們藉由將 `QuantumSimulator` 物件傳遞給演算法類別的 `Run` 方法，執行了我們的量子演算法。
`QuantumSimulator` 類別會藉由完全模擬量子態向量來執行量子演算法，這種做法非常適合用來執行和測試 `Teleport`。
如需量子態向量的詳細資訊，請參閱[概念指南](xref:microsoft.quantum.concepts.intro)。

其他目標機器也可用來執行量子演算法。
該機器會負責為演算法提供量子基元實作。
這包括基元操作，例如 H、CNOT 和 Measure，以及量子位元管理和追蹤。
不同類別的量子機器代表相同量子演算法的不同執行模型。

每種量子機器都可以針對這些基元提供不同的實作。
例如，Development Kit 中包含的量子電腦追蹤模擬器就完全不會進行任何模擬。
相反地，該模擬器會追蹤該演算法的量子閘、量子位元和其他資源使用狀況。

### <a name="quantum-machines"></a>量子機器

在未來，我們將定義其他量子機器類別，以支援其他類型的模擬，以及支援拓撲量子電腦上的執行作業。
讓演算法可以在改變基礎機器實作的情況下保持不變，您就可以輕鬆地在模擬中測試演算法並進行偵錯，然後再於真正的硬體上執行，因為您知道演算法並未改變。

### <a name="whats-included-in-this-release"></a>此版本包含的類別

這一版的 Quantum Developer Kit 包含數個量子機器類別。
這些類別全都定義在 `Microsoft.Quantum.Simulation.Simulators` 命名空間中。

* [完整狀態向量模擬器](xref:microsoft.quantum.machines.full-state-simulator)，`QuantumSimulator` 類別。
* [簡單的資源估算器](xref:microsoft.quantum.machines.resources-estimator)，`ResourcesEstimator` 類別，其可讓您對執行量子演算法所需的資源進行最上層的分析。
* [追蹤型資源估算器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)，`QCTraceSimulator` 類別，其可讓您針對演算法整個呼叫圖的資源耗用情形進行進階分析。
* [Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)，`ToffoliSimulator` 類別。

## <a name="writing-a-host-application"></a>撰寫主應用程式

在[撰寫量子程式](xref:microsoft.quantum.write-program)中，我們針對遙傳演算法編寫了簡單的 C# 驅動程式。 C# 驅動程式有 4 個主要目的：

* 建構目標機器
* 計算量子演算法所需的任何引數
* 使用模擬器執行量子演算法
* 處理操作結果

在這裡，我們會更詳細地討論每個步驟。

### <a name="constructing-the-target-machine"></a>建構目標機器

量子機器是一般 .NET 類別的執行個體，因此可藉由叫用其建構函式來加以建立，就和任何 .NET 類別一樣。
某些模擬器 (包括 `QuantumSimulator`) 會實作 .NET <xref:System.IDisposable?displayProperty=nameWithType> 介面，因此應該包裝到 C# `using` 陳述式中。

### <a name="computing-arguments-for-the-algorithm"></a>計算演算法的引數

在 `Teleport` 範例中，我們計算了一些相當不自然的引數，來傳遞至我們的量子演算法。
不過，更常見的情況是，量子演算法需要大量資料，而從傳統驅動程式提供這些資料會最為簡單。

例如，在進行化學模擬時，量子演算法需要分子軌道相互作用積分法所形成的大型資料表。
一般而言，這些積分法會從執行演算法時所提供的檔案中讀取而來。
由於 Q# 沒有存取檔案系統的機制，因此這類資料最好由傳統驅動程式收集，再傳遞給量子演算法的 `Run` 方法。

傳統驅動程式會扮演重要角色的另一種情況是在變分方法中。
這個演算法類別會根據一些傳統參數來準備量子態，並用該量子態來計算一些感興趣的值。
這些參數會根據某種類型的爬山演算法或機器學習演算法進行調整，然後再重新執行量子演算法。
對於這類演算法，爬山演算法本身最好實作為純粹的傳統函式以供傳統驅動程式呼叫；然後，再將爬山演算法的結果傳遞給量子演算法的下一次執行。

### <a name="running-the-quantum-algorithm"></a>執行量子演算法

這個部分通常非常簡單。
每個 Q# 操作都會編譯成可提供靜態 `Run` 方法的類別。
這個方法的引數是由操作本身的簡維引數元組所提供，再加上另外要在執行模擬器時搭配使用的第一個引數。 對於預期具名元組的類型為 `(a: String, (b: Double, c: Double))` 的操作，其簡維對應項的類型為 `(String a, Double b, Double c)`。


在將引數傳遞給 `Run` 方法時，會有一些微妙差異：

* 陣列必須包裝在 `Microsoft.Quantum.Simulation.Core.QArray<T>` 物件中。
    `QArray` 類別所具有的建構函式可接受適當物件的任何已排序集合 (`IEnumerable<T>`)。
* Q# 中的空白元組 `()` 在 C# 中會以 `QVoid.Instance` 表示。
* 非空白元組則會表示為 .NET `ValueTuple` 執行個體。
* Q# 的使用者定義型別會以其基底類型的形式來傳遞。
* 若要將操作或函式傳遞給 `Run` 方法，您必須使用模擬器的 `Get<>` 方法，取得操作或函式類別的執行個體。

### <a name="processing-the-results"></a>處理結果

量子演算法的結果會從 `Run` 方法傳回。
`Run` 方法會以非同步方式執行，因此會傳回 <xref:System.Threading.Tasks.Task`1> 的執行個體。
有多種方式可取得實際操作的結果。 最簡單的方式是使用 `Task` 的 [`Result` 屬性](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result)：

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
但使用其他技術 (如使用 [`Wait` 方法](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) 或 C# [`await` 關鍵字](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)) 也行。

如同引數，Q# 元組會表示為 `ValueTuple` 執行個體，而 Q# 陣列則會表示為 `QArray` 執行個體。
使用者定義型別會以其基底類型的形式來傳回。
空白元組 `()` 會以 `QVoid` 類別的執行個體形式來傳回。

許多量子演算法都需要大量後期處理才能衍生出有用的答案。
例如，Shor 演算法的量子部分只是計算的開端，目的是要尋找某個數字的因數。

大部分情況下，在傳統驅動程式中執行這類後期處理最為簡單容易。
只有傳統驅動程式可以向使用者報告結果，或將結果寫入到磁碟。
傳統驅動程式將可存取分析程式庫，以及未在 Q# 中公開的其他數學函式。


## <a name="failures"></a>失敗

在執行操作期間到達 Q# `fail` 陳述式時，系統會擲回 `ExecutionFailException`。

由於在 `Run` 方法中使用 `System.Task`，因此在到達 `fail` 陳述式時所擲回的例外狀況將會包裝到 `System.AggregateException` 中。
若要找出失敗的實際原因，您必須反覆執行到 `AggregateException` 
`InnerExceptions`，例如：

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>其他傳統語言

雖然我們提供的範例採用的是 C#、F# 和 Python，但 Quantum Development Kit 也支援使用其他語言來編寫傳統的主機程式。
例如，如果您想要採用 Visual Basic 來編寫主機程式，[應該也不會有問題](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net)。
