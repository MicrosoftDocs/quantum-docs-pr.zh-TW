---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192990"
---
# <a name="drawcategorical-operation"></a>DrawCategorical 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


從 probablities 清單所指定的類別散發中，繪製隨機樣本。

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>描述

選取特定索引的機率與該索引的陣列元素值成正比。
會忽略等於零的陣列元素，而且永遠不會傳回其索引。 如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。

## <a name="input"></a>輸入

### <a name="probs--double"></a>probs： [Double](xref:microsoft.quantum.lang-ref.double)[]

浮點數的陣列，與選取每個索引的機率成正比。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

整數 $i $ 具有機率 $ \Pr (i) = p_i/\ sum_i p_i $，其中 $p _i $ 是的 $i $ 第一個元素 `probs` 。

## <a name="see-also"></a>另請參閱

- [CategoricalDistribution。](xref:Microsoft.Quantum.Random.CategoricalDistribution)