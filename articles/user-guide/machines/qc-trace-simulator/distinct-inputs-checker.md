---
title: 相異輸入檢查程式-量子開發工具組
description: 深入瞭解 Microsoft QDK distinct 輸入檢查工具，其會使用配量追蹤模擬器來檢查您的 Q 號碼程式碼是否有共用 qubits 的潛在衝突。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871139"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>量子追蹤模擬器：相異的輸入檢查

「相異輸入檢查」是「量子開發工具組」配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 您可以使用它來偵測因與共享 qubits 衝突所造成的程式碼中的潛在 bug。 

## <a name="conflicts-with-shared-qubits"></a>與共享 qubits 衝突

請考慮下列的 Q # 程式碼，以說明相異輸入檢查所偵測到的問題：

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

當您查看這個程式時，您可以假設它所呼叫的順序並不 `op1` `op2` 重要，因為 `q1` 和 `q2` 是不同的 qubits 和作業在不同的 qubits 回撥。 

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

請注意， `op1` 和 `op2` 都是使用部分應用程式取得，並共用 qubit。 當您 `ApplyBoth` 在此範例中呼叫時，作業的結果取決於和內部的順序， `op1` 而 `op2` `ApplyBoth` 不是您預期會發生的情況。 當您啟用「相異輸入檢查程式」時，它會偵測這類情況並擲回 `DistinctInputsCheckerException` 。 如需詳細資訊，請參閱 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q # API 程式庫中的。

## <a name="invoking-the-distinct-inputs-checker"></a>叫用相異的輸入檢查

若要使用相異的輸入檢查來執行配量追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例，將 `UseDistinctInputsChecker` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用 `QCTraceSimulatorConfiguration` 做為參數來建立新的實例。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>在 c # 主機程式中使用相異輸入檢查

以下是 c # 主機程式的範例，它會使用配量追蹤模擬器並啟用相異輸入檢查器：

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

## <a name="see-also"></a>請參閱

- 量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API 參考。
