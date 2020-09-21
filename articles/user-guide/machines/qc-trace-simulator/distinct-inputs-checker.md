---
title: 相異輸入檢查程式-量子開發工具組
description: 深入瞭解 Microsoft QDK 相異輸入檢查工具，其使用量子追蹤模擬器來檢查您 Q# 的程式碼是否有與共享量子位的潛在衝突。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: bcb0bc92a546279496d27ad9b8c5f943ac133e2a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833456"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="85830-103">量子追蹤模擬器：相異輸入檢查程式</span><span class="sxs-lookup"><span data-stu-id="85830-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="85830-104">相異輸入檢查工具是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="85830-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="85830-105">您可以使用它來偵測由於與共享量子位衝突所造成的程式碼中可能的 bug。</span><span class="sxs-lookup"><span data-stu-id="85830-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="85830-106">與共享量子位衝突</span><span class="sxs-lookup"><span data-stu-id="85830-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="85830-107">請考慮下列 Q# 程式碼片段，以說明相異輸入檢查程式所偵測到的問題：</span><span class="sxs-lookup"><span data-stu-id="85830-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="85830-108">當您查看這個程式時，您可以假設它的呼叫順序 `op1` 並不 `op2` 重要，因為 `q1` 和 `q2` 是不同的量子位和作業在不同的量子位上叫用。</span><span class="sxs-lookup"><span data-stu-id="85830-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="85830-109">現在，請考慮下列範例：</span><span class="sxs-lookup"><span data-stu-id="85830-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="85830-110">請注意， `op1` 和 `op2` 都是使用部分應用程式取得，而且共用量子位。</span><span class="sxs-lookup"><span data-stu-id="85830-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="85830-111">當您 `ApplyBoth` 在此範例中呼叫時，作業的結果取決於 `op1` 您預期會發生的順序和 `op2` 內部 `ApplyBoth` 。</span><span class="sxs-lookup"><span data-stu-id="85830-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="85830-112">當您啟用相異輸入檢查工具時，它會偵測這種情況，並擲回 `DistinctInputsCheckerException` 。</span><span class="sxs-lookup"><span data-stu-id="85830-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="85830-113">如需詳細資訊，請參閱 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API 程式庫中的 Q# 。</span><span class="sxs-lookup"><span data-stu-id="85830-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="85830-114">叫用相異輸入檢查工具</span><span class="sxs-lookup"><span data-stu-id="85830-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="85830-115">若要使用相異的輸入檢查程式來執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseDistinctInputsChecker` 屬性設為 **true**，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="85830-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="85830-116">使用 c # 主機程式中的相異輸入檢查工具</span><span class="sxs-lookup"><span data-stu-id="85830-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="85830-117">以下是 c # 主機程式的範例，此程式會使用已啟用相異輸入檢查程式的量子追蹤模擬器：</span><span class="sxs-lookup"><span data-stu-id="85830-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="85830-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="85830-118">See also</span></span>

- <span data-ttu-id="85830-119">量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。</span><span class="sxs-lookup"><span data-stu-id="85830-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="85830-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="85830-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="85830-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="85830-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="85830-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API 參考。</span><span class="sxs-lookup"><span data-stu-id="85830-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
