---
title: 深度計數器 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器概觀
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820465"
---
# <a name="depth-counter"></a>深度計數器

`Depth Counter` 是「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」的一部分。
它可用來收集配量程式中所叫用之每個作業的深度計數。 <xref:microsoft.quantum.intrinsic> 的所有作業都是以單一 qubit 旋轉、T 閘道、單一 qubit Clifford 閘道、CNOT-CONTAINS 閘道，以及多 qubit Pauli 可預見值的度量來表示。 使用者可以透過 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>的 [`gateTimes`] 欄位，設定每個基本作業的深度。

根據預設，除了具有深度1的 T 閘道以外，所有作業都有深度0。 這表示根據預設，只會計算運算的 T 深度（這通常是必要的）。 收集的統計資料會在作業呼叫圖形的所有邊緣進行匯總。 

讓我們現在計算 <xref:microsoft.quantum.intrinsic.ccnot> 作業的 <xref:microsoft.quantum.intrinsic.t> 深度。 我們將使用下列 Q # 範例程式碼：

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>在C#程式內使用深度計數器

若要確認 `CCNOT` 具有 `T` 深度5，且 `ApplySampleWithCCNOT` 具有 `T` 深度6，我們可以使用C#下列程式碼：

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

程式的第一個部分會 `ApplySampleWithCCNOT`執行。 在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得 `CCNOT` 和 `ApplySampleWithCCNOT`的 `T` 深度： 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

最後，若要輸出 `Depth Counter` CSV 格式收集的所有統計資料，我們可以使用下列內容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
