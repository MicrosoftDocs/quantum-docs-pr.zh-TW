---
title: 寬度計數器-量子開發工具組
description: 深入瞭解 Microsoft QDK width 計數器，它會使用配量追蹤模擬器來計算程式中由作業所配置和借用的 qubits 數目 Q# 。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868197"
---
# <a name="quantum-trace-simulator-width-counter"></a>量子追蹤模擬器： width 計數器

[寬度] 計數器是 [量子開發工具組] 配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 您可以使用它來計算程式中每個作業所配置和借用的 qubits 數目 Q# 。 某些基本作業可以配置額外的 qubits，例如，將受控制的 `X` 作業或控制的 `T` 作業相乘。

## <a name="invoking-the-width-counter"></a>叫用 width 計數器

若要使用 width 計數器來執行配量追蹤模擬器，您必須建立 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 實例，將 `UseWidthCounter` 屬性設定為**true**，然後 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用做為參數來建立新的實例 `QCTraceSimulatorConfiguration` 。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>在 c # 主機程式中使用 width 計數器

本節後面的 c # 範例會 <xref:microsoft.quantum.intrinsic.x> 根據下列範例程式碼，計算乘以已控制作業的執行所配置的額外 qubits 數目 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

「乘以控制」作業的 <xref:microsoft.quantum.intrinsic.x> 作用總計為五個 qubits、配置兩個[輔助 qubits](xref:microsoft.quantum.glossary#ancilla)，且輸入寬度為**5**。 使用下列 c # 程式來驗證計數：

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

程式的第一個部分會執行此作業 `ApplyMultiControlledX` 。 第二個部分會使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法來抓取已配置的 qubits 數目，以及該作業 `Controlled X` 收到做為輸入的 qubits 數目。 

最後，您可以使用下列方式，輸出 width 計數器所收集的所有統計資料（CSV 格式）：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>另請參閱

- 量子開發工具組配量[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 參考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API 參考。
