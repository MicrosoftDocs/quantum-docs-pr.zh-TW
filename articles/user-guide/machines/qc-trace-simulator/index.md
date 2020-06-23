---
title: 量子電腦追蹤模擬器
description: 了解如何使用 Microsoft 量子電腦追蹤模擬器來對傳統程式碼進行偵錯，以及評估量子程式的資源需求。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 4cec688da35951271d87396d9b6a8fed744defc6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273245"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="85cca-103">量子追蹤模擬器</span><span class="sxs-lookup"><span data-stu-id="85cca-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="85cca-104">Microsoft 量子電腦追蹤模擬器會執行量子程式，而不會實際模擬量子電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="85cca-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="85cca-105">因此，追蹤模擬器可以執行使用數千個量子位元的量子程式。</span><span class="sxs-lookup"><span data-stu-id="85cca-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="85cca-106">追蹤模擬器適合用於兩種目的：</span><span class="sxs-lookup"><span data-stu-id="85cca-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="85cca-107">對屬於量子程式一部分的傳統程式碼進行偵錯。</span><span class="sxs-lookup"><span data-stu-id="85cca-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="85cca-108">估計要在量子電腦上執行指定的量子程式執行個體所需的資源。</span><span class="sxs-lookup"><span data-stu-id="85cca-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="85cca-109">追蹤模擬器會仰賴使用者在必須執行測量時所提供的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="85cca-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="85cca-110">如需這方面的詳細資訊，請參閱[提供測量結果的機率](#providing-the-probability-of-measurement-outcomes)一節。</span><span class="sxs-lookup"><span data-stu-id="85cca-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="85cca-111">提供測量結果的機率</span><span class="sxs-lookup"><span data-stu-id="85cca-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="85cca-112">量子演算法中會出現兩種測量。</span><span class="sxs-lookup"><span data-stu-id="85cca-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="85cca-113">第一種會扮演輔助角色，使用者通常知道結果的機率。</span><span class="sxs-lookup"><span data-stu-id="85cca-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="85cca-114">在此情況下，使用者可以從 <xref:microsoft.quantum.intrinsic> 命名空間撰寫 <xref:microsoft.quantum.intrinsic.assertprob>，以表達這項了解。</span><span class="sxs-lookup"><span data-stu-id="85cca-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="85cca-115">下列範例會加以說明：</span><span class="sxs-lookup"><span data-stu-id="85cca-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="85cca-116">追蹤模擬器在執行 `AssertProb` 時，會做出以下記錄：在 `source` 和 `q` 上測量 `PauliZ` 應該會有 0.5 的機率得到 `Zero` 的結果。</span><span class="sxs-lookup"><span data-stu-id="85cca-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="85cca-117">模擬器稍後執行 `M` 時，則會找到所記錄的結果機率值，而且 `M` 會有 0.5 的機率傳回 `Zero` 或 `One`。</span><span class="sxs-lookup"><span data-stu-id="85cca-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="85cca-118">對追蹤量子態的模擬器執行相同的程式碼時，這類模擬器會檢查 `AssertProb` 中提供的機率是否正確。</span><span class="sxs-lookup"><span data-stu-id="85cca-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="85cca-119">使用量子電腦追蹤模擬器來執行程式</span><span class="sxs-lookup"><span data-stu-id="85cca-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="85cca-120">您可以將量子電腦追蹤模擬器視為只是另一個目標機器。</span><span class="sxs-lookup"><span data-stu-id="85cca-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="85cca-121">用來使用模擬器的 C# 驅動程式非常類似於任何其他量子模擬器的驅動程式：</span><span class="sxs-lookup"><span data-stu-id="85cca-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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

<span data-ttu-id="85cca-122">請注意，如果有至少一個測量未使用 `AssertProb` 加以標註，則模擬器會從 `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` 命名空間擲回 `UnconstrainedMeasurementException`。</span><span class="sxs-lookup"><span data-stu-id="85cca-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="85cca-123">如需詳細資訊，請參閱關於 [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) 的 API 文件。</span><span class="sxs-lookup"><span data-stu-id="85cca-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="85cca-124">除了執行量子程式外，追蹤模擬器還隨附五個元件，以偵測程式中的錯誤並執行量子程式資源估計：</span><span class="sxs-lookup"><span data-stu-id="85cca-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="85cca-125">相異輸入檢查工具</span><span class="sxs-lookup"><span data-stu-id="85cca-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="85cca-126">不正確的量子位元使用檢查工具</span><span class="sxs-lookup"><span data-stu-id="85cca-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="85cca-127">基元操作計數器</span><span class="sxs-lookup"><span data-stu-id="85cca-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="85cca-128">電路深度計數器</span><span class="sxs-lookup"><span data-stu-id="85cca-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="85cca-129">電路寬度計數器</span><span class="sxs-lookup"><span data-stu-id="85cca-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="85cca-130">這些元件皆可透過在 `QCTraceSimulatorConfiguration` 中設定適當旗標來加以啟用。</span><span class="sxs-lookup"><span data-stu-id="85cca-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="85cca-131">對應的參考檔案中會提供有關使用這些元件的更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="85cca-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="85cca-132">如需特定詳細資料，請參閱關於 [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) 的 API 文件。</span><span class="sxs-lookup"><span data-stu-id="85cca-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="85cca-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85cca-133">See also</span></span>
<span data-ttu-id="85cca-134">量子電腦[追蹤模擬器](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# 參考</span><span class="sxs-lookup"><span data-stu-id="85cca-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

