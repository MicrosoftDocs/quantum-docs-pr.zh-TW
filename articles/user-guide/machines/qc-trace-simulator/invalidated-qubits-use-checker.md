---
title: 不正確量子位使用檢查程式-量子開發工具組
description: 深入瞭解 Microsoft QDK 不正確量子位使用檢查程式，它會使用量子追蹤模擬器來檢查您 Q# 的程式碼是否有可能是不正確量子位。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9014097ace7c9f19d93a92372da40f71fa7f87ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858614"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="13541-103">量子追蹤模擬器：不正確量子位使用檢查程式</span><span class="sxs-lookup"><span data-stu-id="13541-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="13541-104">不正確量子位使用檢查程式是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="13541-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="13541-105">您可以使用它來偵測由於無效量子位所造成之程式碼中的潛在錯誤。</span><span class="sxs-lookup"><span data-stu-id="13541-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="13541-106">不正確量子位</span><span class="sxs-lookup"><span data-stu-id="13541-106">Invalid qubits</span></span>

<span data-ttu-id="13541-107">請考慮下列 Q# 程式碼，以說明無效量子位使用檢查程式所偵測到的問題：</span><span class="sxs-lookup"><span data-stu-id="13541-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="13541-108">當您將作業套用 `H` 至時 `q[0]` ，它會指向已發行的量子位，這可能會導致未定義的行為。</span><span class="sxs-lookup"><span data-stu-id="13541-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="13541-109">當已啟用不正確量子位使用檢查程式時， `InvalidatedQubitsUseCheckerException` 如果程式將作業套用至已發行的量子位，則會擲回例外狀況。</span><span class="sxs-lookup"><span data-stu-id="13541-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="13541-110">如需詳細資訊，請參閱<xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>。</span><span class="sxs-lookup"><span data-stu-id="13541-110">For more information, see <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="13541-111">叫用不正確量子位使用檢查程式</span><span class="sxs-lookup"><span data-stu-id="13541-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="13541-112">若要使用不正確量子位使用檢查程式來執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseInvalidatedQubitsUseChecker` 屬性設為 **true**，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="13541-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="13541-113">在 c # 主機程式中使用不正確量子位 use 檢查程式</span><span class="sxs-lookup"><span data-stu-id="13541-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="13541-114">以下是 c # 主機程式的範例，這些程式會使用已啟用無效量子位使用檢查程式的量子追蹤模擬器：</span><span class="sxs-lookup"><span data-stu-id="13541-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="13541-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13541-115">See also</span></span>

- <span data-ttu-id="13541-116">量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。</span><span class="sxs-lookup"><span data-stu-id="13541-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="13541-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="13541-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="13541-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="13541-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="13541-119"><xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>API 參考。</span><span class="sxs-lookup"><span data-stu-id="13541-119">The <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException> API reference.</span></span>
