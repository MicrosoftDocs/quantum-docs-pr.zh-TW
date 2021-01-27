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
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>量子追蹤模擬器：不正確量子位使用檢查程式

不正確量子位使用檢查程式是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 您可以使用它來偵測由於無效量子位所造成之程式碼中的潛在錯誤。 

## <a name="invalid-qubits"></a>不正確量子位

請考慮下列 Q# 程式碼，以說明無效量子位使用檢查程式所偵測到的問題：

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

當您將作業套用 `H` 至時 `q[0]` ，它會指向已發行的量子位，這可能會導致未定義的行為。 當已啟用不正確量子位使用檢查程式時， `InvalidatedQubitsUseCheckerException` 如果程式將作業套用至已發行的量子位，則會擲回例外狀況。 如需詳細資訊，請參閱<xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>。

## <a name="invoking-the-invalidated-qubits-use-checker"></a>叫用不正確量子位使用檢查程式

若要使用不正確量子位使用檢查程式來執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseInvalidatedQubitsUseChecker` 屬性設為 **true**，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>在 c # 主機程式中使用不正確量子位 use 檢查程式

以下是 c # 主機程式的範例，這些程式會使用已啟用無效量子位使用檢查程式的量子追蹤模擬器： 

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

## <a name="see-also"></a>另請參閱

- 量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.InvalidatedQubitsUseCheckerException>API 參考。
