---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: f4f8a9265dc25305819da5ae1002f02b7efd1952
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203445"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a>TimeDependentTrotterSimulationAlgorithmImpl 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


執行多個 Trotter 步驟，以接近可解決時間相依薛丁格方程式的單一運算子。

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

在單一 Trotter 步驟中，模擬時間演進的持續時間。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 整合器的順序。 此值必須是1或偶數。


### <a name="maxtime--double"></a>maxTime： [Double](xref:microsoft.quantum.lang-ref.double)

模擬 $t 的總持續時間。


### <a name="evolutionschedule--evolutionschedule"></a>evolutionSchedule： [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)

要模擬之時間相依系統的完整描述。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位由模擬處理。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

