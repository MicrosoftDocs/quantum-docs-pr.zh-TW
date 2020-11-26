---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193007"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回指定內含範圍的統一散發。

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>輸入

### <a name="min--int"></a>最小值： [Int](xref:microsoft.quantum.lang-ref.int)

要繪製的最小整數。


### <a name="max--int"></a>max： [Int](xref:microsoft.quantum.lang-ref.int)

要繪製的最大整數。



## <a name="output--discretedistribution"></a>輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

隨機 variates 是中包含範圍內之整數的分佈， `min` 其 `max` 具有統一機率。

## <a name="remarks"></a>備註

如果為 `max <= min` ，則失敗。

## <a name="see-also"></a>另請參閱

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)