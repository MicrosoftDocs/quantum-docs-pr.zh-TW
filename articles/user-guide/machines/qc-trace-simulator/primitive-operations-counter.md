---
title: 基本操作計數器
description: 深入瞭解 Microsoft QDK 基本型別運算計數器，它會追蹤量副程式中的作業所使用的基本執行次數。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274568"
---
# <a name="primitive-operations-counter"></a>基本操作計數器  

`Primitive Operations Counter`是量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的一部分。 它會計算在量副程式中叫用的每個作業所使用的基本執行次數。 所有的作業 `Microsoft.Quantum.Intrinsic` 都是以單一 qubit 旋轉、T 閘道、單一 Qubit Clifford 閘道、cnot-contains 閘道，以及多 Qubit Pauli 可預見值的度量來表示。 收集的統計資料會在作業呼叫圖形的邊緣進行匯總。 讓我們現在計算 `T` 要執行此作業所需的閘道數目 `CCNOT` 。 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>在 c # 程式中使用基本操作計數器

若要確認 `CCNOT` 確實需要 7 `T` 個閘道，並且 `ApplySampleWithCCNOT` 執行8個網 `T` 關，我們可以使用下列 c # 程式碼：

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

程式的第一個部分會執行 `ApplySampleWithCCNOT` 。 在第二個部分中，我們會使用方法 `QCTraceSimulator.GetMetric` 來取得所執行的 T 閘道數目 `ApplySampleWithCCNOT` ： 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

當 `GetMetric` 使用兩個型別參數呼叫時，它會傳回與指定的呼叫圖形邊緣相關聯的度量值。 在我們的範例作業中 `Primitive.CCNOT` 呼叫 `ApplySampleWithCCNOT` ，因此呼叫圖形包含邊緣 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。 

若要取得使用的網 `CNOT` 關數目，我們可以新增下列程式程式碼：
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最後，若要輸出所有由閘道格式收集的統計資料，我們可以使用下列方法：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>另請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
