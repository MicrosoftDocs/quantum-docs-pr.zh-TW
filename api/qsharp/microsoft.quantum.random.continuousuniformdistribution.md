---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697139"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

包： [](https://nuget.org/packages/)


傳回指定的內含間隔的統一散發。

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>輸入

### <a name="min--double"></a>最小值： [Double](xref:microsoft.quantum.lang-ref.double)

要繪製的最小實數。


### <a name="max--double"></a>max： [Double](xref:microsoft.quantum.lang-ref.double)

要繪製的最大實數數目。



## <a name="output--continuousdistribution"></a>輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

隨機 variates 的分佈，其隨機是的內含間隔中的實數（ `min` `max` 具有統一機率）。

## <a name="remarks"></a>備註

如果為 `max <= min` ，則失敗。

## <a name="see-also"></a>另請參閱

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)