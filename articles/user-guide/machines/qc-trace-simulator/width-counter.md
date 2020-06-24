---
title: Width 計數器
description: 深入瞭解 Microsoft QDK Width 計數器，其會計算量副程式中每項作業所配置和借用的 qubits 數目。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274571"
---
# <a name="width-counter"></a>Width 計數器

會 `Width Counter` 計算每個作業所配置和借用的 qubits 數目。
`Microsoft.Quantum.Intrinsic`命名空間中的所有作業都是以單一 qubit 旋轉、T 閘道、單一 Qubit Clifford 閘道、cnot-contains 閘道，以及多 Qubit Pauli 可預見值的度量來表示。 某些基本作業可以配置額外的 qubits。 例如，乘以受控制的網 `X` 關或控制 `T` 的閘道。 讓我們計算乘以控制閘道的執行所配置的額外 qubits 數目 `X` ：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>在 c # 程式中使用 Width 計數器

`X`對總計5個 qubits 進行控制的運算會配置2個輔助 qubits，而其輸入寬度會是5。 若要檢查是否為這種情況，我們可以使用下列 c # 程式：

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

程式的第一個部分會執行 `ApplyMultiControlledX` 。 在第二個部分中，我們會使用方法 `QCTraceSimulator.GetMetric` 來取得已配置的 qubits 數目，以及受控制 `X` 接收為輸入的 qubits 數目。 

最後，若要輸出由 width 計數器收集的所有統計資料（CSV 格式），我們可以使用下列內容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>另請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
