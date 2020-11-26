---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: bc6c3c6656da319fce9c7c48824dbc4ad75ccc83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203410"
---
# <a name="trotterstepimpl-operation"></a>TrotterStepImpl 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


藉由包含在中的詞彙，實現時間演進 `GeneratorSystem` 。

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

要模擬之系統的完整描述。


### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

描述系統中詞彙的整數索引。


### <a name="stepsize--double"></a>stepsize： [Double](xref:microsoft.quantum.lang-ref.double)

依詞彙編制索引之時間週期的乘數 `idx` 。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位由模擬處理。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

