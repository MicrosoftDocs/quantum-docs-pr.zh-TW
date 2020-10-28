---
title: 基本操作計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK 基本作業計數器，它會使用量子追蹤模擬器來追蹤程式中作業所使用的基本進程 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690954"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>量子追蹤模擬器：基本操作計數器

基本操作計數器是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 它會計算量副程式中叫用的每個作業所使用的基本進程數目。 

所有 <xref:Microsoft.Quantum.Intrinsic> 作業都是以單一量子位的旋轉、T 運算、單一量子位 Clifford 作業、CNOT 作業以及多量子位 Pauli 可預見值的度量來表示。 基本操作計數器會匯總並收集作業 [呼叫圖形](https://en.wikipedia.org/wiki/Call_graph)所有邊緣的統計資料。

## <a name="invoking-the-primitive-operation-counter"></a>叫用基本操作計數器

若要使用基本操作計數器執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UsePrimitiveOperationsCounter` 屬性設為 **true** ，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>使用 c # 主機程式中的基本操作計數器

本節中的 c # 範例 <xref:Microsoft.Quantum.Intrinsic.T> 會 <xref:Microsoft.Quantum.Intrinsic.ccnot> 根據下列範例程式碼，計算執行作業所需的作業數目 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

若要檢查是否 `CCNOT` 需要七項 `T` 作業並 `ApplySampleWithCCNOT` 執行八個 `T` 作業，請使用下列 c # 程式碼：

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

程式的第一個部分會執行 `ApplySampleWithCCNOT` 。 第二個部分會使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來取出執行的 `T` 作業數目 `ApplySampleWithCCNOT` ： 

當您 `GetMetric` 使用兩個型別參數進行呼叫時，它會傳回與指定之呼叫圖形邊緣相關聯的度量值。 在上述範例中，程式會在中呼叫作業， `Primitive.CCNOT` `ApplySampleWithCCNOT` 因此呼叫圖形會包含邊緣 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。 

若要取出使用的 `CNOT` 作業數目，請新增下列程式程式碼：
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最後，您可以使用下列程式，以 CSV 格式輸出基本操作計數器收集的所有統計資料：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>請參閱

- 量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API 參考。