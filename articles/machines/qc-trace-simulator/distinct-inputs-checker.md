---
title: 相異的輸入檢查
description: '深入瞭解 Microsoft QDK Distinct 輸入檢查工具，其會檢查您的 Q # 程式碼是否有與共享 qubits 的潛在衝突。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907098"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="feb7d-103">相異的輸入檢查</span><span class="sxs-lookup"><span data-stu-id="feb7d-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="feb7d-104">`Distinct Inputs Checker` 是「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」的一部分。</span><span class="sxs-lookup"><span data-stu-id="feb7d-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="feb7d-105">其設計目的是要偵測程式碼中的潛在 bug。</span><span class="sxs-lookup"><span data-stu-id="feb7d-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="feb7d-106">請考慮下列 Q 號碼程式碼，以說明此套件所偵測到的問題：</span><span class="sxs-lookup"><span data-stu-id="feb7d-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="feb7d-107">當使用者查看這個程式時，他們會假設呼叫 `op1` 和 `op2` 的順序並不重要，因為 `q1` 和 `q2` 是不同的 qubits 和作業在不同的 qubits 向下。</span><span class="sxs-lookup"><span data-stu-id="feb7d-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="feb7d-108">現在讓我們來看一個範例，其中會使用此作業：</span><span class="sxs-lookup"><span data-stu-id="feb7d-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="feb7d-109">現在 `op1` 和 `op2` 都是使用部分應用程式取得，並共用 qubit。</span><span class="sxs-lookup"><span data-stu-id="feb7d-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="feb7d-110">當使用者呼叫上述範例中的 `ApplyBoth` 時，作業的結果將取決於 `ApplyBoth`內 `op1` 和 `op2` 的順序。</span><span class="sxs-lookup"><span data-stu-id="feb7d-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="feb7d-111">這絕對不是使用者預期會發生的情況。</span><span class="sxs-lookup"><span data-stu-id="feb7d-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="feb7d-112">`Distinct Inputs Checker` 會在啟用時偵測到這類情況，而且將會擲回 `DistinctInputsCheckerException`。</span><span class="sxs-lookup"><span data-stu-id="feb7d-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="feb7d-113">如需詳細資訊，請參閱[DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="feb7d-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="feb7d-114">在您C#的程式中使用相異的輸入檢查</span><span class="sxs-lookup"><span data-stu-id="feb7d-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="feb7d-115">以下是在啟用 `Distinct Inputs Checker` 的C#情況下，使用配量電腦追蹤模擬器的驅動程式代碼範例：</span><span class="sxs-lookup"><span data-stu-id="feb7d-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="feb7d-116">類別 `QCTraceSimulatorConfiguration` 會儲存配量電腦追蹤模擬器的設定，而且可以當做 `QCTraceSimulator` 的引數提供。</span><span class="sxs-lookup"><span data-stu-id="feb7d-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="feb7d-117">當 `useDistinctInputsChecker` 設定為 true 時，就會啟用 `Distinct Inputs Checker`。</span><span class="sxs-lookup"><span data-stu-id="feb7d-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="feb7d-118">如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="feb7d-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="feb7d-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="feb7d-119">See also</span></span>

- <span data-ttu-id="feb7d-120">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="feb7d-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
