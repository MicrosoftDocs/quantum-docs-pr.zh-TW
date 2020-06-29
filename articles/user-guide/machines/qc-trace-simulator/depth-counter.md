---
title: 深度計數器
description: 深入瞭解 Microsoft QDK Depth 計數器，它會收集在量副程式中叫用的每個作業深度計數。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415252"
---
# <a name="depth-counter"></a>深度計數器

`Depth Counter`是量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。
它可用來收集計數，以代表在量副程式中叫用的每個作業深度下限。 所有的作業 <xref:microsoft.quantum.intrinsic> 都是以單一 qubit 旋轉、T 閘道、單一 Qubit Clifford 閘道、cnot-contains 閘道，以及多 Qubit Pauli 可預見值的度量來表示。 使用者可以透過的欄位，設定每個基本作業的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。

根據預設，除了具有深度1的 T 閘道以外，所有作業都有深度0。 這表示根據預設，只會計算運算的 T 深度（這通常是必要的）。 收集的統計資料會在作業呼叫圖形的所有邊緣進行匯總。 

現在讓我們來計算作業的 <xref:microsoft.quantum.intrinsic.t> 深度 <xref:microsoft.quantum.intrinsic.ccnot> 。 我們將使用下列 Q # 範例程式碼：

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>在 c # 程式中使用深度計數器

若要檢查 `CCNOT` 是否有 `T` 深度5而且 `ApplySampleWithCCNOT` 有 `T` 深度6，我們可以使用下列 c # 程式碼：

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

程式的第一個部分會執行 `ApplySampleWithCCNOT` 。 在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得 `T` 和的 `CCNOT` 深度 `ApplySampleWithCCNOT` ： 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

最後，若要輸出以 CSV 格式收集的所有統計資料， `Depth Counter` 我們可以使用下列方法：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>另請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
