---
title: 基本操作計數器 |量子電腦追蹤模擬器 |Microsoft Docs
description: 量子電腦追蹤模擬器的總覽
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184877"
---
# <a name="primitive-operations-counter"></a>基本操作計數器  

`Primitive Operations Counter` 是「量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器」的一部分。 它會計算在量副程式中叫用的每個作業所使用的基本執行次數。 `Microsoft.Quantum.Primitive` 的所有作業都是以單一 qubit 旋轉、T 閘道、單一 qubit Clifford 閘道、CNOT-CONTAINS 閘道，以及多 qubit Pauli 可預見值的度量來表示。 收集的統計資料會在作業呼叫圖形的邊緣進行匯總。 讓我們現在計算出需要多少 `T` 閘道來執行 `CCNOT` 作業。 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>在C#程式內使用基本操作計數器

若要確認 `CCNOT` 確實需要 7 `T` 閘道，而且 `CCNOTDriver` 執行8個 `T` 閘道，我們C#可以使用下列程式碼：

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

程式的第一個部分會 `CCNOTDriver`執行。 在第二個部分中，我們使用方法 `QCTraceSimulator.GetMetric` 來取得 `CCNOTDriver`所執行的 T 閘道數目： 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

當使用兩個型別參數呼叫 `GetMetric` 時，它會傳回與指定的呼叫圖形邊緣相關聯的度量值。 在我們的 `Primitive.CCNOT` 範例作業中，會在 `CCNOTDriver` 內呼叫，因此呼叫圖形會包含邊緣 `<Primitive.CCNOT,CCNOTDriver>`。 

若要取得使用的 `CNOT` 閘道數目，我們可以新增下列程式程式碼：
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

最後，若要輸出所有由閘道格式收集的統計資料，我們可以使用下列方法：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>請參閱 ##

- 量子電腦[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器的總覽。
