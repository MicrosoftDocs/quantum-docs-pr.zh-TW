---
title: 寬度計數器-量子開發工具組
description: '深入瞭解 Microsoft QDK width 計數器，它會使用量子追蹤模擬器來計算程式中的作業所配置和借用的量子位數目 :::no-loc(Q#)::: 。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691118"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="eaf39-103">量子追蹤模擬器：寬度計數器</span><span class="sxs-lookup"><span data-stu-id="eaf39-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="eaf39-104">寬度計數器是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="eaf39-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="eaf39-105">您可以使用它來計算程式中每項作業所配置和借用的量子位數目 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="eaf39-105">You can use it to count the number of qubits allocated and borrowed by each operation in a :::no-loc(Q#)::: program.</span></span> <span data-ttu-id="eaf39-106">某些基本作業可以配置額外的量子位，例如，將控制的 `X` 作業或控制的 `T` 作業相乘。</span><span class="sxs-lookup"><span data-stu-id="eaf39-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="eaf39-107">叫用寬度計數器</span><span class="sxs-lookup"><span data-stu-id="eaf39-107">Invoking the width counter</span></span>

<span data-ttu-id="eaf39-108">若要使用 width 計數器執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseWidthCounter` 屬性設為 **true** ，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="eaf39-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="eaf39-109">在 c # 主機程式中使用 width 計數器</span><span class="sxs-lookup"><span data-stu-id="eaf39-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="eaf39-110">本節後面的 c # 範例會 <xref:Microsoft.Quantum.Intrinsic.X> 根據下列範例程式碼，來計算由乘法受控制作業所配置的額外量子位數目 :::no-loc(Q#)::: ：</span><span class="sxs-lookup"><span data-stu-id="eaf39-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="eaf39-111">相乘控制的作業會 <xref:Microsoft.Quantum.Intrinsic.X> 在總共五個量子位上運作，配置兩個 [附屬量子位](xref:microsoft.quantum.glossary#ancilla)，且輸入寬度為 **5** 。</span><span class="sxs-lookup"><span data-stu-id="eaf39-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5** .</span></span> <span data-ttu-id="eaf39-112">使用下列 c # 程式來確認計數：</span><span class="sxs-lookup"><span data-stu-id="eaf39-112">Use the following C# program to verify the counts:</span></span>

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

<span data-ttu-id="eaf39-113">程式的第一個部分會執行作業 `ApplyMultiControlledX` 。</span><span class="sxs-lookup"><span data-stu-id="eaf39-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="eaf39-114">第二個部分會使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來取出已配置的量子位數目，以及作業接收的量子位數目 `Controlled X` 作為輸入。</span><span class="sxs-lookup"><span data-stu-id="eaf39-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="eaf39-115">最後，您可以使用下列程式，以 CSV 格式輸出 width 計數器所收集的所有統計資料：</span><span class="sxs-lookup"><span data-stu-id="eaf39-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="eaf39-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="eaf39-116">See also</span></span>

- <span data-ttu-id="eaf39-117">量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。</span><span class="sxs-lookup"><span data-stu-id="eaf39-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="eaf39-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="eaf39-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="eaf39-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="eaf39-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="eaf39-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API 參考。</span><span class="sxs-lookup"><span data-stu-id="eaf39-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
