---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700075"
---
# <a name="rotationphasesasreflectionphases-function"></a>RotationPhasesAsReflectionPhases 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


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