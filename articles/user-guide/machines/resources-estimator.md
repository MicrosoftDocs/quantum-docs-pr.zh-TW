---
title: 量子資源估計工具-量子開發工具組
description: '深入瞭解 Microsoft QDK resources 估計工具，其會估計在量子電腦上執行 Q # 作業的指定實例所需的資源。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870529"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>量子開發工具組（QDK）資源估計工具

顧名思義，類別會估計在 `ResourcesEstimator` 量子電腦上執行 Q # 作業的指定實例所需的資源。 它會執行量子作業，而不實際模擬量子電腦的狀態，來完成這項操作;基於這個理由，如果程式碼的傳統部分在合理的時間內執行，它會估計使用數千個 qubits 的 Q # 作業資源。

[資源] 估計工具建置於 [配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器] 之上，可提供一組更豐富的計量和工具，協助您進行程式設計。

## <a name="invoking-and-running-the-resources-estimator"></a>叫用和執行資源估計工具

您可以使用 [資源] 估計工具來執行任何 Q # 作業。 如需其他詳細資訊，請參閱[執行 Q # 程式的方式](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-resources-estimator-from-c"></a>叫用從 C 估計工具的資源# 

如同其他目的電腦，您必須先建立類別的實例 `ResourceEstimator` ，然後將它當做作業之方法的第一個參數來傳遞 `Run` 。

請注意，與類別不同的是， `QuantumSimulator` `ResourceEstimator` 類別不會執行 <xref:System.IDisposable> 介面，因此您不需要將它放在 `using` 語句內。

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

如範例所示，會 `ResourcesEstimator` 提供 `ToTSV()` 方法，它會產生包含定位字元分隔值（TSV）的資料表。 您可以將資料表儲存至檔案，或將它顯示到主控台進行分析。 以下是前述程式的範例輸出：

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

使用來自 Python 程式庫的[estimate_resources （）](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法，以及匯入的 Q # 操作：

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>從命令列叫用資源估計工具

從命令列執行 Q # 程式時，請使用 **--** 模擬器（或 **-s**快捷方式）參數來指定 `ResourcesEstimator` 目的電腦。 下列命令會使用 [資源] 估計工具來執行程式： 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>叫用從 Juptyer 筆記本估計工具的資源

使用 IQ # 魔術命令[% 估價](xref:microsoft.quantum.iqsharp.magic-ref.simulate)來執行 Q # 作業。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>以程式設計方式抓取估計的資料

除了 TSV 資料表以外，您還可以透過資源估計工具的屬性，以程式設計方式抓取執行期間預估的資源 `Data` 。 `Data`屬性會提供 `System.DataTable` 具有兩個數據行的實例： `Metric` 和，並以 `Sum` 度量的名稱編制索引。

下列程式碼會示範如何抓取和列印 `QubitClifford` `T` `CNOT` Q # 作業所使用的總數和運算：

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
|__CNOT__    |作業的執行計數 `CNOT` （也稱為控制的 Pauli X 作業）。|
|__QubitClifford__ |任何單一 qubit Clifford 和 Pauli 作業的執行計數。|
|__Measure (量值)__     |任何測量的執行計數。  |
|__R__    |任何單一 qubit 旋轉、排除 `T` 、Clifford 和 Pauli 作業的執行計數。  |
|__T__    |`T`作業和其 conjugates 的執行計數，包括 `T` 作業、T_x = .h 和 T_y = Hy Hy。  |
|__Depth__|由 Q # 作業執行的配量線路深度下限。 根據預設，深度度量只會計算網 `T` 關。 如需詳細資訊，請參閱[Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。   |
|__寬度__    |在執行 Q # 作業期間配置的最大 qubits 數目下限。 不可能同時達到__深度__和__寬度__的下限。  |
|__BorrowedWidth__    |在 Q # 作業內借用的 qubits 數目上限。  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供測量結果的機率

您可以 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 從 <xref:microsoft.quantum.diagnostics> 命名空間使用，以提供有關測量作業預期機率的資訊。 如需詳細資訊，請參閱[量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器

## <a name="see-also"></a>請參閱

- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子 Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator) 