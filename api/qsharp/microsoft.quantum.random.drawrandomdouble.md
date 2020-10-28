---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700714"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

包： [](https://nuget.org/packages/)


以指定的內含間隔繪製隨機實數。

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>輸入

### <a name="min--double"></a>最小值： [Double](xref:microsoft.quantum.lang-ref.double)

要繪製的最小實數。


### <a name="max--double"></a>max： [Double](xref:microsoft.quantum.lang-ref.double)

要繪製的最大實數數目。



## <a name="output--double"></a>輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

的內含間隔中的隨機實數， `min` `max` 具有統一機率。

## <a name="remarks"></a>備註

如果為 `max <= min` ，則失敗。

## <a name="see-also"></a>另請參閱

- [ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)