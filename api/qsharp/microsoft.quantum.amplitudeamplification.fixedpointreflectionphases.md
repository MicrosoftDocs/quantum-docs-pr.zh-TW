---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845850"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases 函式

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>參考資料

我們會使用「具有最佳查詢數目的固定點波幅放大」中的階段

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 另請參閱「複合量子閘道的方法」
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) 格式的階段 `RotationPhases` 。