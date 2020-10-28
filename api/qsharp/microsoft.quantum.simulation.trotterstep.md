---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701103"
---
# <a name="trotterstep-function"></a>TrotterStep 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


藉由 `EvolutionGenerator` 使用 Trotter – Suzuki 分解中所述的系統，來執行時間演進的單一時間。

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

要模擬之系統的完整描述。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 整合器的順序。 此值必須是1或偶數。


### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

在單一 Trotter 步驟中，模擬時間演進的持續時間。



## <a name="output--qubit--unit-adj--ctl"></a>Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

單一作業，其近似于持續時間的單一步驟 `trotterStepSize` 。

## <a name="remarks"></a>備註

如需 Trotter – Suzuki 分解的詳細資訊，請參閱依 [時間排序的組合](/quantum/libraries/control-flow#time-ordered-composition)。