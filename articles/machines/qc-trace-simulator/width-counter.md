---
title: 寬度計數器 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器概觀
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820363"
---
# <a name="width-counter"></a><span data-ttu-id="39120-103">Width 計數器</span><span class="sxs-lookup"><span data-stu-id="39120-103">Width Counter</span></span>

<span data-ttu-id="39120-104">`Width Counter` 會計算每個作業所配置和借用的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="39120-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="39120-105">`Microsoft.Quantum.Intrinsic` 命名空間中的所有作業都是以單一 qubit 旋轉、T 閘道、單一 qubit Clifford 閘道、CNOT-CONTAINS 閘道，以及多 qubit Pauli 可預見值的度量來表示。</span><span class="sxs-lookup"><span data-stu-id="39120-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="39120-106">某些基本作業可以配置額外的 qubits。</span><span class="sxs-lookup"><span data-stu-id="39120-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="39120-107">例如，將控制的 `X` 閘道或控制 `T` 閘道相乘。</span><span class="sxs-lookup"><span data-stu-id="39120-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="39120-108">讓我們計算乘以控制 `X` 閘道的實值所配置的額外 qubits 數目：</span><span class="sxs-lookup"><span data-stu-id="39120-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="39120-109">在C#程式內使用 Width 計數器</span><span class="sxs-lookup"><span data-stu-id="39120-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="39120-110">將受控制的 `X` 在總計5個 qubits 上，會配置2個輔助 qubits，而其輸入寬度會是5。</span><span class="sxs-lookup"><span data-stu-id="39120-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="39120-111">若要檢查是否為這種情況，我們可以使用下列C#程式：</span><span class="sxs-lookup"><span data-stu-id="39120-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="39120-112">程式的第一個部分會 `ApplyMultiControlledX`執行。</span><span class="sxs-lookup"><span data-stu-id="39120-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="39120-113">在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得已配置的 qubits 數目，以及控制 `X` 接收為輸入的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="39120-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="39120-114">最後，若要輸出由 width 計數器收集的所有統計資料（CSV 格式），我們可以使用下列內容：</span><span class="sxs-lookup"><span data-stu-id="39120-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="39120-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="39120-115">See also</span></span> ##

- <span data-ttu-id="39120-116">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="39120-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
