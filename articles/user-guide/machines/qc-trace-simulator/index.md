---
title: 量子追蹤模擬器 - Quantum 開發套件
description: 了解如何使用 Microsoft 量子電腦追蹤模擬器來對傳統程式碼進行偵錯，以及評估 Q# 程式的資源需求。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: c01f01973ea08153cbfa35d87a588a4eae46f1b7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871105"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Microsoft Quantum 開發套件 (QDK) 量子追蹤模擬器

QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 類別會執行量子程式，而不會實際模擬量子電腦的狀態。 因此，量子追蹤模擬器能夠執行使用數千個量子位元的量子程式。  追蹤模擬器適合用於兩種目的： 

* 對屬於量子程式一部分的傳統程式碼進行偵錯。 
* 估計要在量子電腦上執行指定的量子程式執行個體所需的資源。 事實上，[資源估算器](xref:microsoft.quantum.machines.resources-estimator)是建立在追蹤模擬器上，且提供的計量較少。

## <a name="invoking-the-quantum-trace-simulator"></a>叫用量子追蹤模擬器

您可以使用量子追蹤模擬器來執行任何 Q# 作業。

就像其他目標機器一樣，您必須先建立 `QCTraceSimulator` 類別的執行個體，然後將其當做作業中 `Run` 方法的第一個參數傳遞。

請注意，不同於 `QuantumSimulator` 類別，`QCTraceSimulator` 類別不會實作 <xref:System.IDisposable> 介面，因此您不需要將其放在 `using` 陳述式內。

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
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供測量結果的機率

因為量子追蹤模擬器不會模擬實際的量子狀態，所以無法計算作業內測量結果的機率。 

因此，如果作業包含測量，您就必須使用來自 <xref:microsoft.quantum.diagnostics> 命名空間中的 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 作業，明確地提供這些機率。 下列範例會加以說明：

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

當量子追蹤模擬器遇到 `AssertMeasurementProbability`，會記錄在 `source` 上測量的 `PauliZ`，然後 `q` 應該會產生 `Zero` 的結果，且機率為 **0.5**。 當模擬器稍後執行 `M` 作業時，會尋找記錄的結果機率值，而 `M` 會傳回 `Zero` 或 `One`，且機率為 **0.5**。 對追蹤量子狀態的模擬器執行相同的程式碼時，模擬器會檢查 `AssertMeasurementProbability` 中提供的機率是否正確。

請注意，如果有至少一個測量作業未使用 `AssertMeasurementProbability` 加以標註，模擬器就會擲回 [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception)。

## <a name="quantum-trace-simulator-tools"></a>量子追蹤模擬器工具

QDK 有五個可搭配量子追蹤模擬器使用的工具，用來偵測程式中的錯誤，以及執行量子程式資源估計： 

|工具 | 描述 |
|-----| -----|
|[相異輸入檢查工具](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |檢查共用的量子位元是否有潛在的衝突 |
|[不正確的量子位元使用檢查工具](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |檢查程式是否將作業套用至已發行的量子位元 |
|[基元操作計數器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | 計算在量子程式中叫用的每個作業所使用的基本執行次數  |
|[深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |收集計數，此計數代表在量子程式中所叫用每個作業的深度下限   |
|[寬度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |計算量子程式中每個作業所配置和借用的量子佔元數目 |

這些工具的的啟用方式，都是要在 `QCTraceSimulatorConfiguration` 中設定適當的旗標，然後將設定傳遞給 `QCTraceSimulator` 宣告。 如需使用這些工具的詳細資訊，請參閱上方清單中的連結。 如需設定 `QCTraceSimulator` 的詳細資訊，請參閱 [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)。

## <a name="qctracesimulator-methods"></a>QCTraceSimulator 方法

`QCTraceSimulator` 有數個內建方法，可擷取在量子作業期間追蹤的計量值。 在[基元操作計數器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)、[深度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)、[寬度計數器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)文章中可以找到 [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 和 [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) 方法的範例。 如需所有可用方法的詳細資訊，請參閱 Q# API 參考資料中的 [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)。  

## <a name="see-also"></a>另請參閱

- [量子資源估算器](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli 模擬器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator) 