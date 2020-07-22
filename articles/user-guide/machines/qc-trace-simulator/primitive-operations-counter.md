---
title: 基本操作計數器-量子開發工具組
description: '深入瞭解 Microsoft QDK 基本型別運算計數器，它會使用配量追蹤模擬器來追蹤 Q # 程式中的作業所使用的基本執行。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: ea022d499354f7cefd60da690466496e0ce7c336
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871020"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>量子追蹤模擬器：基本操作計數器

基本操作計數器是「量子開發工具組」配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 它會計算在量副程式中叫用的每個作業所使用的基本執行次數。 

所有 <xref:microsoft.quantum.intrinsic> 作業都是以單一 qubit 旋轉、T 作業、單一 Qubit Clifford 作業、cnot-contains 作業，以及多 Qubit Pauli 可預見值的度量來表示。 基本作業計數器會匯總並收集作業的[呼叫圖形](https://en.wikipedia.org/wiki/Call_graph)所有邊緣的統計資料。

## <a name="invoking-the-primitive-operation-counter"></a>叫用基本操作計數器

若要使用基本操作計數器來執行配量追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UsePrimitiveOperationsCounter` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>在 c # 主機程式中使用基本操作計數器

本節後面的 c # 範例 <xref:microsoft.quantum.intrinsic.t> 會 <xref:microsoft.quantum.intrinsic.ccnot> 根據下列 Q # 範例程式碼，計算要執行作業所需的作業數目：

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

若要檢查是否 `CCNOT` 需要七個 `T` 作業，且 `ApplySampleWithCCNOT` 執行八個 `T` 作業，請使用下列 c # 程式碼：

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

程式的第一個部分會執行 `ApplySampleWithCCNOT` 。 第二個部分使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來抓取執行的 `T` 作業數目 `ApplySampleWithCCNOT` ： 

當您 `GetMetric` 使用兩個型別參數呼叫時，它會傳回與指定的呼叫圖形邊緣相關聯的度量值。 在上述範例中，程式會呼叫 `Primitive.CCNOT` 中的作業 `ApplySampleWithCCNOT` ，因此呼叫圖形會包含邊緣 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。 

若要取出使用的 `CNOT` 作業數目，請新增下列程式程式碼：
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最後，您可以使用下列程式，以 CSV 格式輸出基本型操作計數器所收集的所有統計資料：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>請參閱

- 量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API 參考。