---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192939"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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