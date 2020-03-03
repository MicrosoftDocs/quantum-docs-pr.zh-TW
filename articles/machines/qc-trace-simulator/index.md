---
title: 量子電腦追蹤模擬器
description: 了解如何使用 Microsoft 量子電腦追蹤模擬器來對傳統程式碼進行偵錯，以及評估量子程式的資源需求。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 72c259933d2df8f79319e6c0c65ae181a9f9cff3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906078"
---
# <a name="quantum-trace-simulator"></a>量子追蹤模擬器

Microsoft 量子電腦追蹤模擬器會執行量子程式，而不會實際模擬量子電腦的狀態。  因此，追蹤模擬器可以執行使用數千個量子位元的量子程式。  追蹤模擬器適合用於兩種目的： 

* 對屬於量子程式一部分的傳統程式碼進行偵錯。 
* 估計要在量子電腦上執行指定的量子程式執行個體所需的資源。

追蹤模擬器會仰賴使用者在必須執行測量時所提供的其他資訊。 如需這方面的詳細資訊，請參閱[提供測量結果的機率](#providing-the-probability-of-measurement-outcomes)一節。 

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供測量結果的機率

量子演算法中會出現兩種測量。 第一種會扮演輔助角色，使用者通常知道結果的機率。 在此情況下，使用者可以從 <xref:microsoft.quantum.intrinsic> 命名空間撰寫 <xref:microsoft.quantum.intrinsic.assertprob>，以表達這項了解。 下列範例會加以說明：

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

追蹤模擬器在執行 `AssertProb` 時，會做出以下記錄：在 `source` 和 `q` 上測量 `PauliZ` 應該會有 0.5 的機率得到 `Zero` 的結果。 模擬器稍後執行 `M` 時，則會找到所記錄的結果機率值，而且 `M` 會有 0.5 的機率傳回 `Zero` 或 `One`。 對追蹤量子態的模擬器執行相同的程式碼時，這類模擬器會檢查 `AssertProb` 中提供的機率是否正確。

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>使用量子電腦追蹤模擬器來執行程式 

您可以將量子電腦追蹤模擬器視為只是另一個目標機器。 用來使用模擬器的 C# 驅動程式非常類似於任何其他量子模擬器的驅動程式： 

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

請注意，如果有至少一個測量未使用 `AssertProb` 加以標註，則模擬器會從 `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` 命名空間擲回 `UnconstrainedMeasurementException`。 如需詳細資訊，請參閱關於 [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) 的 API 文件。

除了執行量子程式外，追蹤模擬器還隨附五個元件，以偵測程式中的錯誤並執行量子程式資源估計： 

* [相異輸入檢查工具](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [不正確的量子位元使用檢查工具](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [基元操作計數器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [電路深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [電路寬度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

這些元件皆可透過在 `QCTraceSimulatorConfiguration` 中設定適當旗標來加以啟用。 對應的參考檔案中會提供有關使用這些元件的更多詳細資料。 如需特定詳細資料，請參閱關於 [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) 的 API 文件。

## <a name="see-also"></a>另請參閱
量子電腦[追蹤模擬器](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# 參考 

