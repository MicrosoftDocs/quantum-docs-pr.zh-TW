---
title: Distinct inputs checker | Quantum computer trace simulator | Microsoft Docs
description: Overview of quantum computer trace simulator
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 0df28f6d74279db4678c3485a23a9341680eec52
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184690"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="a4914-103">Distinct Inputs Checker</span><span class="sxs-lookup"><span data-stu-id="a4914-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="a4914-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="a4914-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="a4914-105">It is designed for detecting potential bugs in the code.</span><span class="sxs-lookup"><span data-stu-id="a4914-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="a4914-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span><span class="sxs-lookup"><span data-stu-id="a4914-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="a4914-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span><span class="sxs-lookup"><span data-stu-id="a4914-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="a4914-108">Let us now consider an example, where this operation is used:</span><span class="sxs-lookup"><span data-stu-id="a4914-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation DisctinctQubitCaptured2Test () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

<span data-ttu-id="a4914-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span><span class="sxs-lookup"><span data-stu-id="a4914-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="a4914-110">When the user calls `DoBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `DoBoth`.</span><span class="sxs-lookup"><span data-stu-id="a4914-110">When the user calls `DoBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `DoBoth`.</span></span> <span data-ttu-id="a4914-111">This is definitely not what the user would expect to happen.</span><span class="sxs-lookup"><span data-stu-id="a4914-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="a4914-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="a4914-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="a4914-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span><span class="sxs-lookup"><span data-stu-id="a4914-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="a4914-114">Using the Distinct Inputs Checker in your C# Program</span><span class="sxs-lookup"><span data-stu-id="a4914-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="a4914-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span><span class="sxs-lookup"><span data-stu-id="a4914-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="a4914-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span><span class="sxs-lookup"><span data-stu-id="a4914-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="a4914-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span><span class="sxs-lookup"><span data-stu-id="a4914-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="a4914-118">如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="a4914-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4914-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="a4914-119">See also</span></span>

- <span data-ttu-id="a4914-120">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="a4914-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
