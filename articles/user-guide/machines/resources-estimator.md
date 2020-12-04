---
title: 量子資源估算器-量子開發工具組
description: 深入瞭解 Microsoft QDK resources 估算器，其預估在量子電腦上執行特定作業實例所需的資源 Q# 。
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: de425c2d91c6528b13c3bedd81acb4b4273ed711
ms.sourcegitcommit: 7c687495a79d75ae9e029e5a41baec84d9e07bb0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "96604638"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>量子開發工具組 (QDK) 資源估算器

顧名思義，類別會估計在 `ResourcesEstimator` 量子電腦上執行某項作業的指定實例所需的資源 Q# 。 它是藉由執行量子操作來完成，而不實際模擬量子電腦的狀態;基於這個原因，它會針對 Q# 使用上千個量子位的作業預估資源，前提是程式碼的傳統部分在合理的時間內執行。

資源估算器建置於 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器之上，它提供了一組更豐富的計量和工具來協助您進行調試 Q# 程式。

## <a name="invoking-and-running-the-resources-estimator"></a>叫用和執行資源估算器

您可以使用 [資源] 估算器來執行任何作業 Q# 。 如需其他詳細資訊，請參閱 [執行 Q# 程式的方法](xref:microsoft.quantum.guide.host-programs)。

### <a name="invoking-the-resources-estimator-from-c"></a>叫用從 C 估算器的資源# 

就像其他目標機器一樣，您必須先建立 `ResourcesEstimator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。

請注意，不同於 `QuantumSimulator` 類別，`ResourcesEstimator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。

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

如範例所示，會 `ResourcesEstimator` 提供 `ToTSV()` 方法，此方法會產生一個具有定位字元分隔值的資料表 (TSV) 。 您可以將資料表儲存至檔案，或將它顯示在主控台進行分析。 以下是先前程式的輸出範例：

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
> `ResourcesEstimator`實例不會在每次執行時重設其計算。 如果您使用相同的實例來執行另一個作業，它會使用現有的結果來匯總新的結果。 如果您需要重設執行之間的計算，請針對每次執行建立新的實例。

### <a name="invoking-the-resources-estimator-from-python"></a>從 Python 叫用資源估算器

使用匯入作業，從 Python 程式庫使用 [estimate_resources ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>從命令列叫用資源估算器

Q#從命令列執行程式時，請使用 **--** 模擬器 (或 **-s** 快速鍵) 參數來指定 `ResourcesEstimator` 目的電腦。 下列命令會使用資源估算器來執行程式： 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>從 Juptyer 筆記本叫用資源估算器

使用 I Q# 魔術命令 [% 估計](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 來執行此作業 Q# 。

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>以程式設計方式取出預估資料

除了 TSV 資料表以外，您也可以透過程式設計方式，透過 [資源] 估算器的屬性，在執行期間取得估計的資源 `Data` 。 `Data`屬性提供 `System.DataTable` 具有兩個數據行的實例： `Metric` 和 `Sum` ，由度量的名稱索引。

下列程式碼示範如何取出和列印工作所使用的總 `QubitClifford` 次數 `T` 和 `CNOT` 作業 Q# ：

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

資源估算器會追蹤下列計量：

|計量|描述|
|----|----|
|__CNOT__    |作業的執行計數 `CNOT` (也稱為受控 Pauli X 作業) 。|
|__QubitClifford__ |任何單一量子位 Clifford 和 Pauli 作業的執行計數。|
|__Measure__    |任何測量的執行計數。  |
|__R__    |任何單一量子位旋轉、排除 `T` 、Clifford 和 Pauli 作業的執行計數。  |
|__T__    |作業的執行計數 `T` 和其 conjugates，包括 `T` 作業、T_x = .h 和 T_y = Hy Hy。  |
|__深度__|作業所執行的量子線路深度 Q# (請參閱 [以下](#depth-width-and-qubitcount)) 。 根據預設，深度度量只會計算網 `T` 關。 如需詳細資訊，請參閱 [深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。   |
|__寬度__|作業所執行的量子電路寬度 Q# (請參閱 [以下](#depth-width-and-qubitcount)) 。 根據預設，深度度量只會計算網 `T` 關。 如需詳細資訊，請參閱 [Width 計數器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。   |
|__QubitCount__    |作業執行期間所配置的最大量子位數目下限 Q# 。 此計量可能與 __深度__ (不相容，請參閱下面的) 。  |
|__BorrowedWidth__    |在作業內借用的量子位數目上限 Q# 。  |


## <a name="depth-width-and-qubitcount"></a>深度、寬度和 QubitCount

報告的深度和寬度估計值彼此相容。
 (先前兩個數字都是可達成的，但深度和寬度都需要不同的電路。 ) 這組中的計量目前可由相同的線路同時達成。

系統會報告下列計量：

__深度：__ 針對根作業，它會假設特定的閘道時間來執行它。
針對呼叫的作業或後續的作業-在最新的量子位可用性時間與作業結束之間的時間差異。

__寬度：__ 針對根本操作（量子位實際用來執行它的數目） (和作業，它會呼叫) 。
針對呼叫的作業或後續作業-已使用的量子位數目，以及在作業開始時使用的量子位數目。

請注意，重複使用的量子位並不會影響到這個數位。
亦即，如果在作業 A 開始之前已釋出幾個量子位，而且此作業要求的所有量子位都是藉由重複使用先前的發行量子位來滿足) 的 (和作業，則作業 A 的寬度會回報為0。 成功的借用量子位不會影響到寬度。

__QubitCount：__ 若為根作業，則為執行此作業所需的最小量子位數目 (以及從中呼叫的作業) 。
針對呼叫的作業或後續的作業，也就是足以個別執行此作業的量子位數目下限。 此數目不包含輸入量子位。 它包含借用量子位。

支援兩種作業模式。 您可以藉由設定 QCTraceSimulatorConfiguration OptimizeDepth 來選取模式。

__OptimizeDepth = true：__ QubitManager 不建議量子位重複使用，並且會在每次要求量子位時配置新的量子位。 針對根操作 __深度__ ，會變成 (下限) 的最小深度。 此深度會回報相容的 __寬度__ ， (可以同時) 。 請注意，此寬度在此深度中可能不是最佳的。 __QubitCount__ 可能會比根作業的寬度低，因為它會假設重複使用。

__OptimizeDepth = false：__ 建議 QubitManager 使用量子位，並在配置新的量子位之前重複使用已發行的。 針對根作業 __寬度__ ，會變成最小寬度 (下限) 。 您可以在其上取得相容 __深度__ 的報告。 __QubitCount__ 將與根本作業的 __寬度__ 相同（假設沒有借用）。

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供測量結果的機率

您可以 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 從 <xref:Microsoft.Quantum.Diagnostics> 命名空間使用，以提供有關測量運算之預期機率的資訊。 如需詳細資訊，請參閱[量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器

## <a name="see-also"></a>另請參閱

- [量子追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [量子 Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator) 
