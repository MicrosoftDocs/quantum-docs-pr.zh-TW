---
title: 寬度計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK width 計數器，它會使用量子追蹤模擬器來計算程式中的作業所配置和借用的量子位數目 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835939"
---
# <a name="quantum-trace-simulator-width-counter"></a>量子追蹤模擬器：寬度計數器

寬度計數器是量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 您可以使用它來計算程式中每項作業所配置和借用的量子位數目 Q# 。 某些基本作業可以配置額外的量子位，例如，將控制的 `X` 作業或控制的 `T` 作業相乘。

## <a name="invoking-the-width-counter"></a>叫用寬度計數器

若要使用 width 計數器執行量子追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例、將 `UseWidthCounter` 屬性設為 **true**，然後以 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>在 c # 主機程式中使用 width 計數器

本節後面的 c # 範例會 <xref:microsoft.quantum.intrinsic.x> 根據下列範例程式碼，來計算由乘法受控制作業所配置的額外量子位數目 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

相乘控制的作業會 <xref:microsoft.quantum.intrinsic.x> 在總共五個量子位上運作，配置兩個 [附屬量子位](xref:microsoft.quantum.glossary#ancilla)，且輸入寬度為 **5**。 使用下列 c # 程式來確認計數：

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

程式的第一個部分會執行作業 `ApplyMultiControlledX` 。 第二個部分會使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來取出已配置的量子位數目，以及作業接收的量子位數目 `Controlled X` 作為輸入。 

最後，您可以使用下列程式，以 CSV 格式輸出 width 計數器所收集的所有統計資料：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>另請參閱

- 量子開發工具組 [量子追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 模擬器總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API 參考。
