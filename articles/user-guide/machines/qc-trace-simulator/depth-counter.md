---
title: 深度計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK depth 計數器，它會使用量子追蹤模擬器來收集程式中所叫用的每個作業的深度計數 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859036"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="7e4e9-103">量子追蹤模擬器：深度計數器</span><span class="sxs-lookup"><span data-stu-id="7e4e9-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="7e4e9-104">深度計數器是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="7e4e9-105">您可以使用它來收集計數，以代表在量副程式中叫用之每項作業的深度下限。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="7e4e9-106">深度值</span><span class="sxs-lookup"><span data-stu-id="7e4e9-106">Depth values</span></span>

<span data-ttu-id="7e4e9-107">依預設，除了作業 `T` （深度為 **1**）之外，所有作業的深度都是0。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="7e4e9-108">這表示，根據預設，只 `T` 會計算作業的深度 (這通常是) 的理想做法。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="7e4e9-109">深度計數器會匯總並收集作業 [呼叫圖形](https://en.wikipedia.org/wiki/Call_graph)所有邊緣的統計資料。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="7e4e9-110">所有 <xref:Microsoft.Quantum.Intrinsic> 作業都是以單一量子位的旋轉、 <xref:Microsoft.Quantum.Intrinsic.T> 作業、單一量子位 Clifford 作業、 <xref:Microsoft.Quantum.Intrinsic.CNOT> 作業以及多量子位 Pauli 可預見值的度量來表示。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="7e4e9-111">使用者可以透過的欄位來設定每個基本作業的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="7e4e9-112">叫用深度計數器</span><span class="sxs-lookup"><span data-stu-id="7e4e9-112">Invoking the depth counter</span></span>

<span data-ttu-id="7e4e9-113">若要使用深度計數器執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將其屬性設定 `UseDepthCounter` 為 **true**，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="7e4e9-114">使用 c # 主機程式中的深度計數器</span><span class="sxs-lookup"><span data-stu-id="7e4e9-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="7e4e9-115">本節後面的 c # 範例會 `T` `CCNOT` 根據下列範例程式碼來計算作業的深度 Q# ：</span><span class="sxs-lookup"><span data-stu-id="7e4e9-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="7e4e9-116">若要檢查 `CCNOT` 是否有 `T` 深度 **5** 並 `ApplySampleWithCCNOT` 有 `T` 深度 **6**，請使用下列 c # 程式碼：</span><span class="sxs-lookup"><span data-stu-id="7e4e9-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

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

<span data-ttu-id="7e4e9-117">程式的第一個部分會執行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="7e4e9-118">第二個部分會使用 [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來取得 `T` 和的 `CCNOT` 深度 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="7e4e9-119">最後，您可以使用下列程式，以 CSV 格式輸出深度計數器收集的所有統計資料：</span><span class="sxs-lookup"><span data-stu-id="7e4e9-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="7e4e9-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7e4e9-120">See also</span></span>

- <span data-ttu-id="7e4e9-121">量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="7e4e9-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="7e4e9-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="7e4e9-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API 參考。</span><span class="sxs-lookup"><span data-stu-id="7e4e9-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
