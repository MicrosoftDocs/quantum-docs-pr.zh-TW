---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701106"
---
# <a name="trottersimulationalgorithmimpl-operation"></a>TrotterSimulationAlgorithmImpl 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


重複呼叫以 `TrotterStep` 接近時間演進運算子 exp ( _-iHt_ ) 。

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

在單一 Trotter 步驟中，模擬時間演進的持續時間。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 整合器的順序。 此值必須是1或偶數。


### <a name="maxtime--double"></a>maxTime： [Double](xref:microsoft.quantum.lang-ref.double)

模擬 $t 的總持續時間。


### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

要模擬之系統的完整描述。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位由模擬處理。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

