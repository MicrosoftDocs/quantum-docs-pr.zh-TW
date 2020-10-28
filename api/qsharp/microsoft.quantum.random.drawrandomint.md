---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700906"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

包： [](https://nuget.org/packages/)


在指定的內含範圍內繪製隨機整數。

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>輸入

### <a name="min--int"></a>最小值： [Int](xref:microsoft.quantum.lang-ref.int)

要繪製的最小整數。


### <a name="max--int"></a>max： [Int](xref:microsoft.quantum.lang-ref.int)

要繪製的最大整數。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

中包含範圍內的整數， `min` `max` 具有統一機率。

## <a name="remarks"></a>備註

如果為 `max <= min` ，則失敗。

## <a name="see-also"></a>另請參閱

- [DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)