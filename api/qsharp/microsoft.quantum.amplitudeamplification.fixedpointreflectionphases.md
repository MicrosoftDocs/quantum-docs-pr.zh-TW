---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700106"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


計算固定點振幅放大的部分反映階段。

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>輸入

### <a name="nqueries--int"></a>nQueries： [Int](xref:microsoft.quantum.lang-ref.int)

Oracle 狀態準備的查詢數目。 必須是奇數整數。


### <a name="successmin--double"></a>successMin： [Double](xref:microsoft.quantum.lang-ref.double)

目標最小成功機率。



## <a name="output--reflectionphases"></a>輸出： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

可用於固定點振幅放大量子演算法實的階段陣列。

## <a name="references"></a>參考

我們會使用「具有最佳查詢數目的固定點波幅放大」中的階段

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 另請參閱「複合量子閘道的方法」
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) 格式的階段 `RotationPhases` 。