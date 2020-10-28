---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700079"
---
# <a name="rotationphases-user-defined-type"></a>RotationPhases 使用者定義型別

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


以振幅放大的一連串單一量子位旋轉的階段。

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>備註

第一個參數是反映的階段陣列，以單一量子位旋轉的乘積表示。
[ G.H. 低、I. L。 Chuang， https://arxiv.org/abs/1707.05391 ]。