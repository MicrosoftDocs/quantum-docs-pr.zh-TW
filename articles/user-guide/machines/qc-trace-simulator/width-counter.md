---
title: 寬度計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK width 計數器，它會使用配量追蹤模擬器來計算程式中由作業所配置和借用的 qubits 數目 Q# 。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868197"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="0fccc-103">量子追蹤模擬器： width 計數器</span><span class="sxs-lookup"><span data-stu-id="0fccc-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="0fccc-104">[寬度] 計數器是 [量子開發工具組] 配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="0fccc-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="0fccc-105">您可以使用它來計算程式中每個作業所配置和借用的 qubits 數目 Q# 。</span><span class="sxs-lookup"><span data-stu-id="0fccc-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="0fccc-106">某些基本作業可以配置額外的 qubits，例如，將受控制的 `X` 作業或控制的 `T` 作業相乘。</span><span class="sxs-lookup"><span data-stu-id="0fccc-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="0fccc-107">叫用 width 計數器</span><span class="sxs-lookup"><span data-stu-id="0fccc-107">Invoking the width counter</span></span>

<span data-ttu-id="0fccc-108">若要使用 width 計數器來執行配量追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例，將 `UseWidthCounter` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="0fccc-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="0fccc-109">在 c # 主機程式中使用 width 計數器</span><span class="sxs-lookup"><span data-stu-id="0fccc-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="0fccc-110">本節後面的 c # 範例會 <xref:microsoft.quantum.intrinsic.x> 根據下列範例程式碼，計算乘以已控制作業的執行所配置的額外 qubits 數目 Q# ：</span><span class="sxs-lookup"><span data-stu-id="0fccc-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="0fccc-111">「乘以控制」作業的 <xref:microsoft.quantum.intrinsic.x> 作用總計為五個 qubits、配置兩個[輔助 qubits](xref:microsoft.quantum.glossary#ancilla)，且輸入寬度為**5**。</span><span class="sxs-lookup"><span data-stu-id="0fccc-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="0fccc-112">使用下列 c # 程式來驗證計數：</span><span class="sxs-lookup"><span data-stu-id="0fccc-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="0fccc-113">程式的第一個部分會執行此作業 `ApplyMultiControlledX` 。</span><span class="sxs-lookup"><span data-stu-id="0fccc-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="0fccc-114">第二個部分會使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來抓取已配置的 qubits 數目，以及該作業 `Controlled X` 收到做為輸入的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="0fccc-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="0fccc-115">最後，您可以使用下列方式，輸出 width 計數器所收集的所有統計資料（CSV 格式）：</span><span class="sxs-lookup"><span data-stu-id="0fccc-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="0fccc-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0fccc-116">See also</span></span>

- <span data-ttu-id="0fccc-117">量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="0fccc-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="0fccc-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="0fccc-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="0fccc-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="0fccc-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="0fccc-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API 參考。</span><span class="sxs-lookup"><span data-stu-id="0fccc-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
