---
title: 深度計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK depth 計數器，它會使用量子追蹤模擬器來收集程式中所叫用的每個作業的深度計數 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692105"
---
# <a name="quantum-trace-simulator-depth-counter"></a>量子追蹤模擬器：深度計數器

深度計數器是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。
您可以使用它來收集計數，以代表在量副程式中叫用之每項作業的深度下限。 

## <a name="depth-values"></a>深度值

依預設，除了作業 **0** `T` （深度為 **1** ）之外，所有作業的深度都是0。 這表示，根據預設，只 `T` 會計算作業的深度 (這通常是) 的理想做法。 深度計數器會匯總並收集作業 [呼叫圖形](https://en.wikipedia.org/wiki/Call_graph)所有邊緣的統計資料。

所有 <xref:Microsoft.Quantum.Intrinsic> 作業都是以單一量子位的旋轉、 <xref:Microsoft.Quantum.Intrinsic.T> 作業、單一量子位 Clifford 作業、 <xref:Microsoft.Quantum.Intrinsic.CNOT> 作業以及多量子位 Pauli 可預見值的度量來表示。 使用者可以透過的欄位來設定每個基本作業的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。

## <a name="invoking-the-depth-counter"></a>叫用深度計數器

若要使用深度計數器執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將其屬性設定 `UseDepthCounter` 為 **true** ，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>使用 c # 主機程式中的深度計數器

本節後面的 c # 範例會 `T` `CCNOT` 根據下列範例程式碼來計算作業的深度 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

若要檢查 `CCNOT` 是否有 `T` 深度 **5** 並 `ApplySampleWithCCNOT` 有 `T` 深度 **6** ，請使用下列 c # 程式碼：

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

程式的第一個部分會執行 `ApplySampleWithCCNOT` 。 第二個部分會使用 [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來取得 `T` 和的 `CCNOT` 深度 `ApplySampleWithCCNOT` 。 

最後，您可以使用下列程式，以 CSV 格式輸出深度計數器收集的所有統計資料：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>請參閱

- 量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API 參考。
