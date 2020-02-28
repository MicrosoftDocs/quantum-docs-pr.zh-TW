---
title: Width 計數器
description: 深入瞭解 Microsoft QDK Width 計數器，其會計算量副程式中每項作業所配置和借用的 qubits 數目。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907081"
---
# <a name="width-counter"></a>Width 計數器

`Width Counter` 會計算每個作業所配置和借用的 qubits 數目。
`Microsoft.Quantum.Intrinsic` 命名空間中的所有作業都是以單一 qubit 旋轉、T 閘道、單一 qubit Clifford 閘道、CNOT-CONTAINS 閘道，以及多 qubit Pauli 可預見值的度量來表示。 某些基本作業可以配置額外的 qubits。 例如，將控制的 `X` 閘道或控制 `T` 閘道相乘。 讓我們計算乘以控制 `X` 閘道的實值所配置的額外 qubits 數目：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>在C#程式內使用 Width 計數器

將受控制的 `X` 在總計5個 qubits 上，會配置2個輔助 qubits，而其輸入寬度會是5。 若要檢查是否為這種情況，我們可以使用下列C#程式：

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

程式的第一個部分會 `ApplyMultiControlledX`執行。 在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得已配置的 qubits 數目，以及控制 `X` 接收為輸入的 qubits 數目。 

最後，若要輸出由 width 計數器收集的所有統計資料（CSV 格式），我們可以使用下列內容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>另請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
