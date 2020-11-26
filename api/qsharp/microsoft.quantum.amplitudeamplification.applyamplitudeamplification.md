---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: 0b40f94633bb43df5e64cd16d5ac8e12bcd1cc4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191562"
---
# <a name="applyamplitudeamplification-operation"></a>ApplyAmplitudeAmplification 操作

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在指定的暫存器上套用振幅放大，並使用一組指定的階段和 oracle 來反映初始和最終狀態。

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="phases--reflectionphases"></a>階段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

一組階段，描述振幅放大演算法之每個步驟的部分反射。 如需範例，請參閱 @"microsoft.quantum.amplitudeamplification.standardreflectionphases"。


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

反映初始狀態的 oracle。


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

反映預期最終狀態的 oracle。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要在其上執行振幅放大的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

