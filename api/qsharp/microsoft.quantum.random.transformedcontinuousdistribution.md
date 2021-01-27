---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857762"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


指定連續散發時，會傳回由指定函式轉換原始的新散發。

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>輸入

### <a name="transform--double---double"></a>轉換： [雙](xref:microsoft.quantum.lang-ref.double) -> [精度浮點數](xref:microsoft.quantum.lang-ref.double)

將原始分佈的 variates 轉換成已轉換之分佈的函式。


### <a name="distribution--continuousdistribution"></a>散發： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

要轉換的原始散發。



## <a name="output--continuousdistribution"></a>輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

由指定的轉換相關的新散發 `distribution` `transform` 。

## <a name="example"></a>範例

下列兩個散發相同：

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```