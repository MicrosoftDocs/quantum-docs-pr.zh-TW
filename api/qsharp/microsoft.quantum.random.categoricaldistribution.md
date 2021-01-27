---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842354"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>範例

下列 Q # 程式碼會顯示0，機率為30%，而1的機率為70%：

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```