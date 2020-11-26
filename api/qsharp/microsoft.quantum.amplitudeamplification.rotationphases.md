---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191358"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases 使用者定義型別

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以振幅放大的一連串單一量子位旋轉的階段。

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>備註

第一個參數是反映的階段陣列，以單一量子位旋轉的乘積表示。
[ G.H. 低、I. L。 Chuang， https://arxiv.org/abs/1707.05391 ]。