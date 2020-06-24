---
title: 深度計數器
description: 深入瞭解 Microsoft QDK Depth 計數器，它會收集在量副程式中叫用的每個作業深度計數。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274587"
---
# <a name="depth-counter"></a><span data-ttu-id="500ec-103">深度計數器</span><span class="sxs-lookup"><span data-stu-id="500ec-103">Depth Counter</span></span>

<span data-ttu-id="500ec-104">`Depth Counter`是量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="500ec-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="500ec-105">它可用來收集配量程式中所叫用之每個作業的深度計數。</span><span class="sxs-lookup"><span data-stu-id="500ec-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="500ec-106">所有的作業 <xref:microsoft.quantum.intrinsic> 都是以單一 qubit 旋轉、T 閘道、單一 Qubit Clifford 閘道、cnot-contains 閘道，以及多 Qubit Pauli 可預見值的度量來表示。</span><span class="sxs-lookup"><span data-stu-id="500ec-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="500ec-107">使用者可以透過的欄位，設定每個基本作業的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。</span><span class="sxs-lookup"><span data-stu-id="500ec-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="500ec-108">根據預設，除了具有深度1的 T 閘道以外，所有作業都有深度0。</span><span class="sxs-lookup"><span data-stu-id="500ec-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="500ec-109">這表示根據預設，只會計算運算的 T 深度（這通常是必要的）。</span><span class="sxs-lookup"><span data-stu-id="500ec-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="500ec-110">收集的統計資料會在作業呼叫圖形的所有邊緣進行匯總。</span><span class="sxs-lookup"><span data-stu-id="500ec-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="500ec-111">現在讓我們來計算作業的 <xref:microsoft.quantum.intrinsic.t> 深度 <xref:microsoft.quantum.intrinsic.ccnot> 。</span><span class="sxs-lookup"><span data-stu-id="500ec-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="500ec-112">我們將使用下列 Q # 範例程式碼：</span><span class="sxs-lookup"><span data-stu-id="500ec-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="500ec-113">在 c # 程式中使用深度計數器</span><span class="sxs-lookup"><span data-stu-id="500ec-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="500ec-114">若要檢查 `CCNOT` 是否有 `T` 深度5而且 `ApplySampleWithCCNOT` 有 `T` 深度6，我們可以使用下列 c # 程式碼：</span><span class="sxs-lookup"><span data-stu-id="500ec-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

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

<span data-ttu-id="500ec-115">程式的第一個部分會執行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="500ec-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="500ec-116">在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得 `T` 和的 `CCNOT` 深度 `ApplySampleWithCCNOT` ：</span><span class="sxs-lookup"><span data-stu-id="500ec-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="500ec-117">最後，若要輸出以 CSV 格式收集的所有統計資料， `Depth Counter` 我們可以使用下列方法：</span><span class="sxs-lookup"><span data-stu-id="500ec-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="500ec-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="500ec-118">See also</span></span> ##

- <span data-ttu-id="500ec-119">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="500ec-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
