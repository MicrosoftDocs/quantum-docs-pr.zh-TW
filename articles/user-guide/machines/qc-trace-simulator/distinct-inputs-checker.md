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
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>量子追蹤模擬器：相異輸入檢查程式

相異輸入檢查工具是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 您可以使用它來偵測由於與共享量子位衝突所造成的程式碼中可能的 bug。 

## <a name="conflicts-with-shared-qubits"></a>與共享量子位衝突

請考慮下列 Q# 程式碼片段，以說明相異輸入檢查程式所偵測到的問題：

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

當您查看這個程式時，您可以假設它的呼叫順序 `op1` 並不 `op2` 重要，因為 `q1` 和 `q2` 是不同的量子位和作業在不同的量子位上叫用。 

現在，請考慮下列範例：

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

請注意， `op1` 和 `op2` 都是使用部分應用程式取得，而且共用量子位。 當您 `ApplyBoth` 在此範例中呼叫時，作業的結果取決於 `op1` 您預期會發生的順序和 `op2` 內部 `ApplyBoth` 。 當您啟用相異輸入檢查工具時，它會偵測這種情況，並擲回 `DistinctInputsCheckerException` 。 如需詳細資訊，請參閱 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API 程式庫中的 Q# 。

## <a name="invoking-the-distinct-inputs-checker"></a>叫用相異輸入檢查工具

若要使用相異的輸入檢查程式來執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseDistinctInputsChecker` 屬性設為 **true**，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>使用 c # 主機程式中的相異輸入檢查工具

以下是 c # 主機程式的範例，此程式會使用已啟用相異輸入檢查程式的量子追蹤模擬器：

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

## <a name="see-also"></a>另請參閱

- 量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API 參考。
