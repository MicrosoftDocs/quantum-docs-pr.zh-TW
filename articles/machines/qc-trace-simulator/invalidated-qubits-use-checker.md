---
title: 不正確的量子位元使用檢查工具
description: '深入瞭解 Microsoft QDK 失效的 Qubits Use 檢查工具，其會檢查您的 Q # 程式碼是否有潛在的無效 Qubits。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907064"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="f4208-103">不正確 Qubits Use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="f4208-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="f4208-104">`Invalidated Qubits Use Checker` 是針對偵測程式碼中的潛在 bug 而設計的量子電腦[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4208-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="f4208-105">請考慮下列的 Q # 程式碼，以說明 `Invalidated Qubits Use Checker`偵測到的問題。</span><span class="sxs-lookup"><span data-stu-id="f4208-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="f4208-106">當 `H` 套用到時 `q[0]` 會指向已發行的 qubit。</span><span class="sxs-lookup"><span data-stu-id="f4208-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="f4208-107">這可能會導致未定義的行為。</span><span class="sxs-lookup"><span data-stu-id="f4208-107">This can cause undefined behavior.</span></span> <span data-ttu-id="f4208-108">啟用 `Invalidated Qubits Use Checker` 時，如果將作業套用至已發行的 qubit，則會擲回例外狀況 `InvalidatedQubitsUseCheckerException`。</span><span class="sxs-lookup"><span data-stu-id="f4208-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="f4208-109">如需詳細資訊，請參閱[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="f4208-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="f4208-110">在您C#的程式中使用不正確 Qubits Use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="f4208-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="f4208-111">以下是在已啟用 `Invalidated Qubits Use Checker` C#的情況下，使用配量電腦 `Trace
Simulator` 的驅動程式代碼範例：</span><span class="sxs-lookup"><span data-stu-id="f4208-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="f4208-112">類別 `QCTraceSimulatorConfiguration` 會儲存配量電腦追蹤模擬器的設定，而且可以當做 `QCTraceSimulator` 的引數提供。</span><span class="sxs-lookup"><span data-stu-id="f4208-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="f4208-113">當 `useInvalidatedQubitsUseChecker` 設定為 true 時，就會啟用 `Invalidated Qubits Use Checker`。</span><span class="sxs-lookup"><span data-stu-id="f4208-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="f4208-114">如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 檔。</span><span class="sxs-lookup"><span data-stu-id="f4208-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4208-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f4208-115">See also</span></span> ##

- <span data-ttu-id="f4208-116">量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="f4208-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
