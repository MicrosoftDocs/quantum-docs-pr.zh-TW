---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700379"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

包： [](https://nuget.org/packages/)


傳回離散類別分佈，其中會明確指定指定結果的每個有限清單的機率。

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>輸入

### <a name="probs--double"></a>probs： [Double](xref:microsoft.quantum.lang-ref.double)[]

類別散發的每個結果的機率。
這些機率可能不會正規化，但全部都不能為負數。



## <a name="output--discretedistribution"></a>輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

具有機率的索引 `i` `probs[i] / sum` ，其中 `sum` 是指定的總和 `probs` `Fold(PlusD, 0.0, probs)` 。