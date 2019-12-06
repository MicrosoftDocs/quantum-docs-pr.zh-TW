---
title: 相異輸入檢查程式 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器概觀
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: ce3f156a84a4509781a74c9276b953c79670a756
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864299"
---
# <a name="distinct-inputs-checker"></a>相異的輸入檢查

`Distinct Inputs Checker` 是「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」的一部分。 其設計目的是要偵測程式碼中的潛在 bug。 請考慮下列 Q 號碼程式碼，以說明此套件所偵測到的問題：

```qsharp
operation DoBoth(q1 : Qubit, q2 : Qubit, op1 : (Qubit => Unit), op2 : (Qubit => Unit)) : Unit {

    op1(q1);
    op2(q2);
}
```

當使用者查看這個程式時，他們會假設呼叫 `op1` 和 `op2` 的順序並不重要，因為 `q1` 和 `q2` 是不同的 qubits 和作業在不同的 qubits 向下。 現在讓我們來看一個範例，其中會使用此作業：

```qsharp
operation CapturedQubits () : Unit {

    using (q = Qubit[3]) {
        let op1 = CNOT(_, q[1]);
        let op2 = CNOT(q[1], _);
        DoBoth(q[0], q[2], op1, op2);
    }
}
```

現在 `op1` 和 `op2` 都是使用部分應用程式取得，並共用 qubit。 當使用者呼叫上述範例中的 `DoBoth` 時，作業的結果將取決於 `DoBoth`內 `op1` 和 `op2` 的順序。 這絕對不是使用者預期會發生的情況。 `Distinct Inputs Checker` 會在啟用時偵測到這類情況，而且將會擲回 `DistinctInputsCheckerException`。 如需詳細資訊，請參閱[DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)上的 API 檔。

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>在您C#的程式中使用相異的輸入檢查

以下是在啟用 `Distinct Inputs Checker` 的C#情況下，使用配量電腦追蹤模擬器的驅動程式代碼範例：

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

類別 `QCTraceSimulatorConfiguration` 會儲存配量電腦追蹤模擬器的設定，而且可以當做 `QCTraceSimulator` 的引數提供。 當 `useDistinctInputsChecker` 設定為 true 時，就會啟用 `Distinct Inputs Checker`。 如需詳細資訊，請參閱[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)上的 API 檔。

## <a name="see-also"></a>請參閱

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
