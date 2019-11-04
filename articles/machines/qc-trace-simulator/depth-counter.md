---
title: 深度計數器 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器的總覽
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184894"
---
# <a name="depth-counter"></a><span data-ttu-id="6724a-103">深度計數器</span><span class="sxs-lookup"><span data-stu-id="6724a-103">Depth Counter</span></span>

<span data-ttu-id="6724a-104">`Depth Counter` 是「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」的一部分。</span><span class="sxs-lookup"><span data-stu-id="6724a-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="6724a-105">它可用來收集配量程式中所叫用之每個作業的深度計數。</span><span class="sxs-lookup"><span data-stu-id="6724a-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="6724a-106"><xref:microsoft.quantum.intrinsic> 的所有作業都是以單一 qubit 旋轉、T 閘道、單一 qubit Clifford 閘道、CNOT-CONTAINS 閘道，以及多 qubit Pauli 可預見值的度量來表示。</span><span class="sxs-lookup"><span data-stu-id="6724a-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="6724a-107">使用者可以透過 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>的 [`gateTimes`] 欄位，設定每個基本作業的深度。</span><span class="sxs-lookup"><span data-stu-id="6724a-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="6724a-108">根據預設，除了具有深度1的 T 閘道以外，所有作業都有深度0。</span><span class="sxs-lookup"><span data-stu-id="6724a-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="6724a-109">這表示根據預設，只會計算運算的 T 深度（這通常是必要的）。</span><span class="sxs-lookup"><span data-stu-id="6724a-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="6724a-110">收集的統計資料會在作業呼叫圖形的所有邊緣進行匯總。</span><span class="sxs-lookup"><span data-stu-id="6724a-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="6724a-111">讓我們現在計算 <xref:microsoft.quantum.intrinsic.ccnot> 作業的 <xref:microsoft.quantum.intrinsic.t> 深度。</span><span class="sxs-lookup"><span data-stu-id="6724a-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="6724a-112">我們將使用下列 Q # 驅動程式代碼：</span><span class="sxs-lookup"><span data-stu-id="6724a-112">We will use the following Q# driver code:</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="6724a-113">在C#程式內使用深度計數器</span><span class="sxs-lookup"><span data-stu-id="6724a-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="6724a-114">若要確認 `CCNOT` 具有 `T` 深度5，且 `CCNOTDriver` 具有 `T` 深度6，我們可以使用C#下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="6724a-114">To check that `CCNOT` has `T` depth 5 and `CCNOTDriver` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="6724a-115">程式的第一個部分會 `CCNOTDriver`執行。</span><span class="sxs-lookup"><span data-stu-id="6724a-115">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="6724a-116">在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得 `CCNOT` 和 `CCNOTDriver`的 `T` 深度：</span><span class="sxs-lookup"><span data-stu-id="6724a-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `CCNOTDriver`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="6724a-117">最後，若要輸出 `Depth Counter` CSV 格式收集的所有統計資料，我們可以使用下列內容：</span><span class="sxs-lookup"><span data-stu-id="6724a-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="6724a-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="6724a-118">See also</span></span> ##

- <span data-ttu-id="6724a-119">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="6724a-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
