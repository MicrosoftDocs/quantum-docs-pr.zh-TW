---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 316c8f22a16859ebb439824eda9a5aa02c750b5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191120"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


計算標準振幅放大的部分反映階段。

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>輸入

### <a name="niterations--int"></a>nIterations： [Int](xref:microsoft.quantum.lang-ref.int)

要為其產生部分反映階段的波幅放大反覆運算數目。



## <a name="output--reflectionphases"></a>輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

執行指定為部分反射之階段的作業

## <a name="remarks"></a>備註

所有階段都是 $ \pi $，但第一次反映有關「啟動狀態」和「上次反映」的目標狀態，也就是 $0 $。