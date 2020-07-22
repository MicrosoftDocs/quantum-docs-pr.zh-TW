---
title: 深度計數器-量子開發工具組
description: '深入瞭解 Microsoft QDK depth 計數器，它會使用配量追蹤模擬器來收集在 Q # 程式中叫用之每項作業的深度計數。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 811e387fedf547d2681518ae0bb525c13dc84ff4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871122"
---
# <a name="quantum-trace-simulator-depth-counter"></a>量子追蹤模擬器：深度計數器

「深度」計數器是「量子開發工具組」[量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。
您可以使用它來收集計數，以代表在量副程式中叫用的每個作業深度下限。 

## <a name="depth-values"></a>深度值

根據預設，所有作業的深度為**0** ，但作業除外 `T` ，其深度為**1**。 這表示根據預設，只 `T` 會計算作業的深度（這通常是必要的）。 「深度」計數器會匯總並收集作業的[呼叫圖形](https://en.wikipedia.org/wiki/Call_graph)所有邊緣的統計資料。

所有的 <xref:microsoft.quantum.intrinsic> 作業都是以單一 qubit 旋轉、 <xref:microsoft.quantum.intrinsic.t> 作業、單一 qubit Clifford 作業、 <xref:microsoft.quantum.intrinsic.cnot> 作業和多 qubit Pauli 可預見值的測量來表示。 使用者可以透過的欄位，設定每個基本作業的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。

## <a name="invoking-the-depth-counter"></a>叫用深度計數器

若要使用深度計數器來執行配量追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例，將其 `UseDepthCounter` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用 `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>在 c # 主機程式中使用 depth 計數器

本節後面的 c # 範例會 `T` `CCNOT` 根據下列 Q # 範例程式碼，來計算作業的深度：

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

若要檢查 `CCNOT` 是否有 `T` 深度**5**而且 `ApplySampleWithCCNOT` 具有 `T` 深度**6**，請使用下列 c # 程式碼：

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

程式的第一個部分會執行 `ApplySampleWithCCNOT` 。 第二個部分使用 [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來抓取 `T` 和的深度 `CCNOT` `ApplySampleWithCCNOT` 。 

最後，您可以使用下列各項，以 CSV 格式輸出深度計數器所收集的所有統計資料：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>請參閱

- 量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API 參考。
