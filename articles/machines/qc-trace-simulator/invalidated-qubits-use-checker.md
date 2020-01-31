---
title: 不正確 qubits use 檢查工具 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器概觀
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820873"
---
# <a name="invalidated-qubits-use-checker"></a>不正確 Qubits Use 檢查工具

`Invalidated Qubits Use Checker` 是針對偵測程式碼中的潛在 bug 而設計的量子電腦[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。 請考慮下列的 Q # 程式碼，以說明 `Invalidated Qubits Use Checker`偵測到的問題。

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

當 `H` 套用到時 `q[0]` 會指向已發行的 qubit。 這可能會導致未定義的行為。 啟用 `Invalidated Qubits Use Checker` 時，如果將作業套用至已發行的 qubit，則會擲回例外狀況 `InvalidatedQubitsUseCheckerException`。 如需詳細資訊，請參閱[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 檔。

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>在您C#的程式中使用不正確 Qubits Use 檢查工具

以下是在已啟用 `Invalidated Qubits Use Checker` C#的情況下，使用配量電腦 `Trace
Simulator` 的驅動程式代碼範例： 

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

類別 `QCTraceSimulatorConfiguration` 會儲存配量電腦追蹤模擬器的設定，而且可以當做 `QCTraceSimulator` 的引數提供。 當 `useInvalidatedQubitsUseChecker` 設定為 true 時，就會啟用 `Invalidated Qubits Use Checker`。 如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 檔。

## <a name="see-also"></a>請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
