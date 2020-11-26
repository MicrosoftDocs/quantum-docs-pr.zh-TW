---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192905"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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