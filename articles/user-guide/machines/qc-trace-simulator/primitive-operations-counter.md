---
title: 基本操作計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK 基本型別運算計數器，它會使用配量追蹤模擬器來追蹤程式中作業所使用的基本執行 Q# 。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868231"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="ee6f2-103">量子追蹤模擬器：基本操作計數器</span><span class="sxs-lookup"><span data-stu-id="ee6f2-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="ee6f2-104">基本操作計數器是「量子開發工具組」配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="ee6f2-105">它會計算在量副程式中叫用的每個作業所使用的基本執行次數。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="ee6f2-106">所有 <xref:microsoft.quantum.intrinsic> 作業都是以單一 qubit 旋轉、T 作業、單一 Qubit Clifford 作業、cnot-contains 作業，以及多 Qubit Pauli 可預見值的度量來表示。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-106">All <xref:microsoft.quantum.intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="ee6f2-107">基本作業計數器會匯總並收集作業的[呼叫圖形](https://en.wikipedia.org/wiki/Call_graph)所有邊緣的統計資料。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="ee6f2-108">叫用基本操作計數器</span><span class="sxs-lookup"><span data-stu-id="ee6f2-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="ee6f2-109">若要使用基本操作計數器來執行配量追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UsePrimitiveOperationsCounter` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="ee6f2-110">在 c # 主機程式中使用基本操作計數器</span><span class="sxs-lookup"><span data-stu-id="ee6f2-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="ee6f2-111">本節後面的 c # 範例 <xref:microsoft.quantum.intrinsic.t> 會 <xref:microsoft.quantum.intrinsic.ccnot> 根據下列範例程式碼，計算要執行作業所需的作業數目 Q# ：</span><span class="sxs-lookup"><span data-stu-id="ee6f2-111">The C# example that follows in this section counts how many <xref:microsoft.quantum.intrinsic.t> operations are needed to implement the <xref:microsoft.quantum.intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="ee6f2-112">若要檢查是否 `CCNOT` 需要七個 `T` 作業，且 `ApplySampleWithCCNOT` 執行八個 `T` 作業，請使用下列 c # 程式碼：</span><span class="sxs-lookup"><span data-stu-id="ee6f2-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

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

<span data-ttu-id="ee6f2-113">程式的第一個部分會執行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="ee6f2-114">第二個部分使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來抓取執行的 `T` 作業數目 `ApplySampleWithCCNOT` ：</span><span class="sxs-lookup"><span data-stu-id="ee6f2-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="ee6f2-115">當您 `GetMetric` 使用兩個型別參數呼叫時，它會傳回與指定的呼叫圖形邊緣相關聯的度量值。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="ee6f2-116">在上述範例中，程式會呼叫 `Primitive.CCNOT` 中的作業 `ApplySampleWithCCNOT` ，因此呼叫圖形會包含邊緣 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="ee6f2-117">若要取出使用的 `CNOT` 作業數目，請新增下列程式程式碼：</span><span class="sxs-lookup"><span data-stu-id="ee6f2-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="ee6f2-118">最後，您可以使用下列程式，以 CSV 格式輸出基本型操作計數器所收集的所有統計資料：</span><span class="sxs-lookup"><span data-stu-id="ee6f2-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="ee6f2-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee6f2-119">See also</span></span>

- <span data-ttu-id="ee6f2-120">量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="ee6f2-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="ee6f2-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="ee6f2-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API 參考。</span><span class="sxs-lookup"><span data-stu-id="ee6f2-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>