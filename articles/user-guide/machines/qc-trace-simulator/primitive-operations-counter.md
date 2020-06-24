---
title: 基本操作計數器
description: 深入瞭解 Microsoft QDK 基本型別運算計數器，它會追蹤量副程式中的作業所使用的基本執行次數。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274568"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="83a0f-103">基本操作計數器</span><span class="sxs-lookup"><span data-stu-id="83a0f-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="83a0f-104">`Primitive Operations Counter`是量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="83a0f-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="83a0f-105">它會計算在量副程式中叫用的每個作業所使用的基本執行次數。</span><span class="sxs-lookup"><span data-stu-id="83a0f-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="83a0f-106">所有的作業 `Microsoft.Quantum.Intrinsic` 都是以單一 qubit 旋轉、T 閘道、單一 Qubit Clifford 閘道、cnot-contains 閘道，以及多 Qubit Pauli 可預見值的度量來表示。</span><span class="sxs-lookup"><span data-stu-id="83a0f-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="83a0f-107">收集的統計資料會在作業呼叫圖形的邊緣進行匯總。</span><span class="sxs-lookup"><span data-stu-id="83a0f-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="83a0f-108">讓我們現在計算 `T` 要執行此作業所需的閘道數目 `CCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="83a0f-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="83a0f-109">在 c # 程式中使用基本操作計數器</span><span class="sxs-lookup"><span data-stu-id="83a0f-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="83a0f-110">若要確認 `CCNOT` 確實需要 7 `T` 個閘道，並且 `ApplySampleWithCCNOT` 執行8個網 `T` 關，我們可以使用下列 c # 程式碼：</span><span class="sxs-lookup"><span data-stu-id="83a0f-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="83a0f-111">程式的第一個部分會執行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="83a0f-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="83a0f-112">在第二個部分中，我們會使用方法 `QCTraceSimulator.GetMetric` 來取得所執行的 T 閘道數目 `ApplySampleWithCCNOT` ：</span><span class="sxs-lookup"><span data-stu-id="83a0f-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="83a0f-113">當 `GetMetric` 使用兩個型別參數呼叫時，它會傳回與指定的呼叫圖形邊緣相關聯的度量值。</span><span class="sxs-lookup"><span data-stu-id="83a0f-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="83a0f-114">在我們的範例作業中 `Primitive.CCNOT` 呼叫 `ApplySampleWithCCNOT` ，因此呼叫圖形包含邊緣 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。</span><span class="sxs-lookup"><span data-stu-id="83a0f-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="83a0f-115">若要取得使用的網 `CNOT` 關數目，我們可以新增下列程式程式碼：</span><span class="sxs-lookup"><span data-stu-id="83a0f-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="83a0f-116">最後，若要輸出所有由閘道格式收集的統計資料，我們可以使用下列方法：</span><span class="sxs-lookup"><span data-stu-id="83a0f-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="83a0f-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="83a0f-117">See also</span></span> ##

- <span data-ttu-id="83a0f-118">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="83a0f-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
