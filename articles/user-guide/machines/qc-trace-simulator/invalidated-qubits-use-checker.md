---
title: 不正確的量子位元使用檢查工具
description: '深入瞭解 Microsoft QDK 失效的 Qubits Use 檢查工具，其會檢查您的 Q # 程式碼是否有潛在的無效 Qubits。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274572"
---
# <a name="invalidated-qubits-use-checker"></a>不正確 Qubits Use 檢查工具

`Invalidated Qubits Use Checker`是「量子電腦[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分，專門用來偵測程式碼中的潛在 bug。 請考慮下列的 Q # 程式碼，以說明所偵測到的問題 `Invalidated Qubits Use Checker` 。

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

當套用到時， `H` `q[0]` 它會指向已發行的 qubit。 這可能會導致未定義的行為。 當 `Invalidated Qubits Use Checker` 啟用時，如果作業套用 `InvalidatedQubitsUseCheckerException` 至已發行的 qubit，則會擲回例外狀況。 如需詳細資訊，請參閱[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 檔。

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>在 c # 程式中使用不正確 Qubits Use 檢查工具

以下是使用已啟用之配量電腦的 c # 驅動程式程式碼範例 `Trace
Simulator` `Invalidated Qubits Use Checker` ： 

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

此類別會 `QCTraceSimulatorConfiguration` 儲存量子電腦追蹤模擬器的設定，並可提供作為此函式的引數 `QCTraceSimulator` 。 當 `useInvalidatedQubitsUseChecker` 設定為 true 時， `Invalidated Qubits Use Checker` 就會啟用。 如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 檔。

## <a name="see-also"></a>另請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
