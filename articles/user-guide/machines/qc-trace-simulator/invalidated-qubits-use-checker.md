---
title: 不正確 qubits use 檢查工具-量子開發工具組
description: 深入瞭解 Microsoft QDK 失效的 qubits use 檢查工具，其使用配量追蹤模擬器來檢查您的 Q 號碼程式碼是否有可能是不正確 qubits。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: fccf6d5784b587f4ad9b659e23027619acd06ffa
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871088"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="3caaa-103">量子追蹤模擬器：不正確 qubits use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="3caaa-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="3caaa-104">不正確 qubits use 檢查工具是「量子開發工具組」配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。</span><span class="sxs-lookup"><span data-stu-id="3caaa-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="3caaa-105">您可以使用它來偵測 qubits 無效所造成的程式碼中的潛在 bug。</span><span class="sxs-lookup"><span data-stu-id="3caaa-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="3caaa-106">不正確 qubits</span><span class="sxs-lookup"><span data-stu-id="3caaa-106">Invalid qubits</span></span>

<span data-ttu-id="3caaa-107">請考慮下列的 Q # 程式碼，以說明不正確 qubits use 檢查程式所偵測到的問題：</span><span class="sxs-lookup"><span data-stu-id="3caaa-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="3caaa-108">當您將作業套用 `H` 至時 `q[0]` ，它會指向已釋放的 qubit，這可能會造成未定義的行為。</span><span class="sxs-lookup"><span data-stu-id="3caaa-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="3caaa-109">當啟用了不正確 Qubits Use 檢查工具時， `InvalidatedQubitsUseCheckerException` 如果程式將作業套用至已發行的 qubit，它就會擲回例外狀況。</span><span class="sxs-lookup"><span data-stu-id="3caaa-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="3caaa-110">如需詳細資訊，請參閱 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> 。</span><span class="sxs-lookup"><span data-stu-id="3caaa-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="3caaa-111">叫用不正確 qubits use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="3caaa-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="3caaa-112">若要使用不正確 qubits use 檢查程式來執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseInvalidatedQubitsUseChecker` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用 `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。</span><span class="sxs-lookup"><span data-stu-id="3caaa-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="3caaa-113">在 c # 主機程式中使用不正確 qubits use 檢查工具</span><span class="sxs-lookup"><span data-stu-id="3caaa-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="3caaa-114">以下是 c # 主機程式的範例，其使用配量追蹤模擬器並啟用不正確 qubits use 檢查工具：</span><span class="sxs-lookup"><span data-stu-id="3caaa-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="3caaa-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="3caaa-115">See also</span></span>

- <span data-ttu-id="3caaa-116">量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。</span><span class="sxs-lookup"><span data-stu-id="3caaa-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="3caaa-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。</span><span class="sxs-lookup"><span data-stu-id="3caaa-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="3caaa-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。</span><span class="sxs-lookup"><span data-stu-id="3caaa-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="3caaa-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API 參考。</span><span class="sxs-lookup"><span data-stu-id="3caaa-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>