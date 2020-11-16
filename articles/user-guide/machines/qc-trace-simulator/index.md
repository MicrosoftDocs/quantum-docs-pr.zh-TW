---
title: 量子追蹤模擬器 - Quantum 開發套件
description: '了解如何使用 Microsoft 量子電腦追蹤模擬器來對傳統程式碼進行偵錯，以及評估 Q# 程式的資源需求。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 2e2d9f8494d8709fba34123793cecce4011b609a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690826"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="eb41f-103">Microsoft Quantum 開發套件 (QDK) 量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="eb41f-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="eb41f-104">QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 類別會執行量子程式，而不會實際模擬量子電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="eb41f-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="eb41f-105">因此，量子追蹤模擬器能夠執行使用數千個量子位元的量子程式。</span><span class="sxs-lookup"><span data-stu-id="eb41f-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="eb41f-106">追蹤模擬器適合用於兩種目的：</span><span class="sxs-lookup"><span data-stu-id="eb41f-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="eb41f-107">對屬於量子程式一部分的傳統程式碼進行偵錯。</span><span class="sxs-lookup"><span data-stu-id="eb41f-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="eb41f-108">估計要在量子電腦上執行指定的量子程式執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="eb41f-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="eb41f-109">事實上，[資源估算器](xref:microsoft.quantum.machines.resources-estimator)是建立在追蹤模擬器上，且提供的計量較少。</span><span class="sxs-lookup"><span data-stu-id="eb41f-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="eb41f-110">叫用量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="eb41f-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="eb41f-111">您可以使用量子追蹤模擬器來執行任何 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="eb41f-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="eb41f-112">就像其他目標機器一樣，您必須先建立 `QCTraceSimulator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。</span><span class="sxs-lookup"><span data-stu-id="eb41f-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="eb41f-113">請注意，不同於 `QuantumSimulator` 類別，`QCTraceSimulator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。</span><span class="sxs-lookup"><span data-stu-id="eb41f-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="eb41f-114">提供測量結果的機率</span><span class="sxs-lookup"><span data-stu-id="eb41f-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="eb41f-115">因為量子追蹤模擬器不會模擬實際的量子狀態，所以無法計算作業內測量結果的機率。</span><span class="sxs-lookup"><span data-stu-id="eb41f-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="eb41f-116">因此，如果作業包含測量，您就必須使用來自 <xref:Microsoft.Quantum.Diagnostics> 命名空間中的 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 作業，明確地提供這些機率。</span><span class="sxs-lookup"><span data-stu-id="eb41f-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation from the <xref:Microsoft.Quantum.Diagnostics> namespace.</span></span> <span data-ttu-id="eb41f-117">下列範例會加以說明：</span><span class="sxs-lookup"><span data-stu-id="eb41f-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="eb41f-118">當量子追蹤模擬器遇到 `AssertMeasurementProbability`，會記錄在 `source` 上測量的 `PauliZ`，然後 `q` 應該會產生 `Zero` 的結果，且機率為 **0.5** 。</span><span class="sxs-lookup"><span data-stu-id="eb41f-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5** .</span></span> <span data-ttu-id="eb41f-119">當模擬器稍後執行 `M` 作業時，會尋找記錄的結果機率值，而 `M` 會傳回 `Zero` 或 `One`，且機率為 **0.5** 。</span><span class="sxs-lookup"><span data-stu-id="eb41f-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5** .</span></span> <span data-ttu-id="eb41f-120">對追蹤量子狀態的模擬器執行相同的程式碼時，模擬器會檢查 `AssertMeasurementProbability` 中提供的機率是否正確。</span><span class="sxs-lookup"><span data-stu-id="eb41f-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="eb41f-121">請注意，如果有至少一個測量作業未使用 `AssertMeasurementProbability` 加以標註，模擬器就會擲回 [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception)。</span><span class="sxs-lookup"><span data-stu-id="eb41f-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="eb41f-122">量子追蹤模擬器工具</span><span class="sxs-lookup"><span data-stu-id="eb41f-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="eb41f-123">QDK 有五個可搭配量子追蹤模擬器使用的工具，用來偵測程式中的錯誤，以及執行量子程式資源估計：</span><span class="sxs-lookup"><span data-stu-id="eb41f-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="eb41f-124">工具</span><span class="sxs-lookup"><span data-stu-id="eb41f-124">Tool</span></span> | <span data-ttu-id="eb41f-125">描述</span><span class="sxs-lookup"><span data-stu-id="eb41f-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="eb41f-126">相異輸入檢查工具</span><span class="sxs-lookup"><span data-stu-id="eb41f-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="eb41f-127">檢查共用的量子位元是否有潛在的衝突</span><span class="sxs-lookup"><span data-stu-id="eb41f-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="eb41f-128">不正確的量子位元使用檢查工具</span><span class="sxs-lookup"><span data-stu-id="eb41f-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="eb41f-129">檢查程式是否將作業套用至已發行的量子位元</span><span class="sxs-lookup"><span data-stu-id="eb41f-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="eb41f-130">基元操作計數器</span><span class="sxs-lookup"><span data-stu-id="eb41f-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="eb41f-131">計算在量子程式中叫用的每個作業所使用的基本次數</span><span class="sxs-lookup"><span data-stu-id="eb41f-131">Counts the number of primitives used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="eb41f-132">深度計數器</span><span class="sxs-lookup"><span data-stu-id="eb41f-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="eb41f-133">收集計數，此計數代表在量子程式中所叫用每個作業的深度下限</span><span class="sxs-lookup"><span data-stu-id="eb41f-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="eb41f-134">寬度計數器</span><span class="sxs-lookup"><span data-stu-id="eb41f-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="eb41f-135">計算量子程式中每個作業所配置和借用的量子佔元數目</span><span class="sxs-lookup"><span data-stu-id="eb41f-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="eb41f-136">這些工具的的啟用方式，都是要在 `QCTraceSimulatorConfiguration` 中設定適當的旗標，然後將設定傳遞給 `QCTraceSimulator` 宣告。</span><span class="sxs-lookup"><span data-stu-id="eb41f-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="eb41f-137">如需使用這些工具的詳細資訊，請參閱上方清單中的連結。</span><span class="sxs-lookup"><span data-stu-id="eb41f-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="eb41f-138">如需設定 `QCTraceSimulator` 的詳細資訊，請參閱 [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="eb41f-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="eb41f-139">QCTraceSimulator 方法</span><span class="sxs-lookup"><span data-stu-id="eb41f-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="eb41f-140">`QCTraceSimulator` 有數個內建方法，可擷取在量子作業期間追蹤的計量值。</span><span class="sxs-lookup"><span data-stu-id="eb41f-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="eb41f-141">在[基元操作計數器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)、[深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)、[寬度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)文章中可以找到 [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 和 [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) 方法的範例。</span><span class="sxs-lookup"><span data-stu-id="eb41f-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="eb41f-142">如需所有可用方法的詳細資訊，請參閱 Q# API 參考資料中的 [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)。</span><span class="sxs-lookup"><span data-stu-id="eb41f-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="eb41f-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eb41f-143">See also</span></span>

- [<span data-ttu-id="eb41f-144">量子資源估算器</span><span class="sxs-lookup"><span data-stu-id="eb41f-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="eb41f-145">量子 Toffoli 模擬器</span><span class="sxs-lookup"><span data-stu-id="eb41f-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="eb41f-146">量子完整狀態模擬器</span><span class="sxs-lookup"><span data-stu-id="eb41f-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 