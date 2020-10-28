---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697571"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

包： [](https://nuget.org/packages/)


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