---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191188"
---
# <a name="rotationphasesasreflectionphases-function"></a>RotationPhasesAsReflectionPhases 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將指定為單一量子位旋轉的階段，轉換為指定為部分反射的階段。

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>輸入

### <a name="rotphases--rotationphases"></a>rotPhases： [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)

要轉換成部分反射的單一量子位旋轉陣列。



## <a name="output--reflectionphases"></a>輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

執行指定為部分反射之階段的作業。

## <a name="references"></a>參考

我們會使用中的慣例

- [ *G.H. Low，Chuang*](https://arxiv.org/abs/1707.05391) ，以將單一量子位的旋轉階段與反映運算子階段相關聯。