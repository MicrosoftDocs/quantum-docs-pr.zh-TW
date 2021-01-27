---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 4d2e04513c96c6e5f41e85f1df685e91e2973098
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858099"
---
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在具有統一排程的兩個產生器之間進行插補，傳回在產生的時間相依產生器下將模擬演進套用至量子位暫存器的作業。

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="interpolationtime--double"></a>interpolationTime： [Double](xref:microsoft.quantum.lang-ref.double)

執行插補的時間。


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart： [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

用來模擬演進的初始產生器。


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd： [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

用來模擬演進的最終產生器。


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm： [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

時間相依的模擬演算法，將在統一插補排程期間用來模擬演進。



## <a name="output--qubit--unit--is-adj--ctl"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl



## <a name="remarks"></a>備註

如果選擇的插補時間符合 adiabatic 條件，則此函式會傳回執行最終 dynamical 產生器之 adiabatic 狀態準備的作業。