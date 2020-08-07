---
title: 量子資源估計工具-量子開發工具組
description: 深入瞭解 Microsoft QDK resources 估計工具，其會估計在量子電腦上執行特定作業實例所需的資源 Q# 。
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868180"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a> (QDK) 資源估計工具的量子開發工具組

顧名思義，類別會估計在 `ResourcesEstimator` 量子電腦上執行特定作業實例所需的資源 Q# 。 它會執行量子作業，而不實際模擬量子電腦的狀態，來完成這項操作;基於這個理由，它會針對 Q# 使用數千個 qubits 的作業估計資源，前提是程式碼的傳統部分會在合理的時間內執行。

[資源] 估計工具建置於 [配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器] 之上，以提供一組更豐富的計量和工具來協助調試 Q# 程式。

## <a name="invoking-and-running-the-resources-estimator"></a>叫用和執行資源估計工具

您可以使用 [資源] 估計工具來執行任何作業 Q# 。 如需其他詳細資訊，請參閱[執行 Q# 程式的方式](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-resources-estimator-from-c"></a>叫用從 C 估計工具的資源# 

就像其他目標機器一樣，您必須先建立 `ResourceEstimator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。

請注意，不同於 `QuantumSimulator` 類別，`ResourceEstimator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

如範例所示，會 `ResourcesEstimator` 提供 `ToTSV()` 方法，它會產生具有 tab 分隔值的資料表， (TSV) 。 您可以將資料表儲存至檔案，或將它顯示到主控台進行分析。 以下是前述程式的範例輸出：

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> `ResourcesEstimator`實例不會在每次執行時重設其計算。 如果您使用相同的實例來執行另一個作業，它會匯總新的結果與現有的結果。 如果您需要重設執行之間的計算，請在每次執行時建立新的實例。

### <a name="invoking-the-resources-estimator-from-python"></a>叫用從 Python 估計工具的資源

使用來自 Python 程式庫的[estimate_resources ( # B1](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法和匯入的作業 Q# ：

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>從命令列叫用資源估計工具

Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s**快捷方式) 參數來指定 `ResourcesEstimator` 目的電腦。 下列命令會使用 [資源] 估計工具來執行程式： 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>叫用從 Juptyer 筆記本估計工具的資源

使用 I Q# 魔術命令[% 估價](xref:microsoft.quantum.iqsharp.magic-ref.simulate)來執行作業 Q# 。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>以程式設計方式抓取估計的資料

除了 TSV 資料表以外，您還可以透過資源估計工具的屬性，以程式設計方式抓取執行期間預估的資源 `Data` 。 `Data`屬性會提供 `System.DataTable` 具有兩個數據行的實例： `Metric` 和，並以 `Sum` 度量的名稱編制索引。

下列程式碼示範如何抓取和列印工作所 `QubitClifford` 使用的、 `T` 和作業總數 `CNOT` Q# ：

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>回報的計量

[資源] 估計工具會追蹤下列計量：

|計量|描述|
|----|----|
|__CNOT__    |作業的執行計數 `CNOT` (也稱為受控制的 Pauli X 作業) 。|
|__QubitClifford__ |任何單一 qubit Clifford 和 Pauli 作業的執行計數。|
|__Measure (量值)__     |任何測量的執行計數。  |
|__R__    |任何單一 qubit 旋轉、排除 `T` 、Clifford 和 Pauli 作業的執行計數。  |
|__T__    |`T`作業和其 conjugates 的執行計數，包括 `T` 作業、T_x = .h 和 T_y = Hy Hy。  |
|__Depth__|作業所執行的配量線路深度下限 Q# 。 根據預設，深度度量只會計算網 `T` 關。 如需詳細資訊，請參閱[Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。   |
|__寬度__    |執行作業期間配置的最大 qubits 數目下限 Q# 。 不可能同時達到__深度__和__寬度__的下限。  |
|__BorrowedWidth__    |在作業內借用的 qubits 數目上限 Q# 。  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供測量結果的機率

您可以 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 從 <xref:microsoft.quantum.diagnostics> 命名空間使用，以提供有關測量作業預期機率的資訊。 如需詳細資訊，請參閱[量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器

## <a name="see-also"></a>另請參閱

- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子 Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator) 