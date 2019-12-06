---
title: 不正確 qubits use 檢查工具 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器概觀
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 283cc7d7d88f731f40fa396c38ae5ea8dd90537f
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863175"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="8b5de-103">不正確 Qubits Use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="8b5de-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="8b5de-104">`Invalidated Qubits Use Checker` 是針對偵測程式碼中的潛在 bug 而設計的量子電腦[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。</span><span class="sxs-lookup"><span data-stu-id="8b5de-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="8b5de-105">請考慮下列的 Q # 程式碼，以說明 `Invalidated Qubits Use Checker`偵測到的問題。</span><span class="sxs-lookup"><span data-stu-id="8b5de-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="8b5de-106">當 `H` 套用到時 `q[0]` 會指向已發行的 qubit。</span><span class="sxs-lookup"><span data-stu-id="8b5de-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="8b5de-107">這可能會導致未定義的行為。</span><span class="sxs-lookup"><span data-stu-id="8b5de-107">This can cause undefined behavior.</span></span> <span data-ttu-id="8b5de-108">啟用 `Invalidated Qubits Use Checker` 時，如果將作業套用至已發行的 qubit，則會擲回例外狀況 `InvalidatedQubitsUseCheckerException`。</span><span class="sxs-lookup"><span data-stu-id="8b5de-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="8b5de-109">如需詳細資訊，請參閱[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="8b5de-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="8b5de-110">在您C#的程式中使用不正確 Qubits Use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="8b5de-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="8b5de-111">以下是在已啟用 `Invalidated Qubits Use Checker` C#的情況下，使用配量電腦 `Trace
Simulator` 的驅動程式代碼範例：</span><span class="sxs-lookup"><span data-stu-id="8b5de-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="8b5de-112">類別 `QCTraceSimulatorConfiguration` 會儲存配量電腦追蹤模擬器的設定，而且可以當做 `QCTraceSimulator` 的引數提供。</span><span class="sxs-lookup"><span data-stu-id="8b5de-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="8b5de-113">當 `useInvalidatedQubitsUseChecker` 設定為 true 時，就會啟用 `Invalidated Qubits Use Checker`。</span><span class="sxs-lookup"><span data-stu-id="8b5de-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="8b5de-114">如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="8b5de-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b5de-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="8b5de-115">See also</span></span> ##

- <span data-ttu-id="8b5de-116">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="8b5de-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
