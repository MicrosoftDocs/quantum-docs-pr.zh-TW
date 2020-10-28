---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700126"
---
# <a name="applyamplitudeamplification-operation"></a>ApplyAmplitudeAmplification 操作

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


在指定的暫存器上套用振幅放大，並使用一組指定的階段和 oracle 來反映初始和最終狀態。

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
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

