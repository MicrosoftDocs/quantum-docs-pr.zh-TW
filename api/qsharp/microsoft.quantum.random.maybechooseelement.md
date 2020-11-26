---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192854"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


由於有資料陣列和其索引的散發，因此會嘗試隨機播放專案。

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>輸入

### <a name="data--t"></a>data： t []

應從中選擇元素的陣列。


### <a name="indexdistribution--discretedistribution"></a>indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

的索引分佈 `data` 。



## <a name="output--boolt"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) 



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

