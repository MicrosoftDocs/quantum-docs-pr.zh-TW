---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843974"
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