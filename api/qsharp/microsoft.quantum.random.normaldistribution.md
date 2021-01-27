---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814174"
---
# <a name="normaldistribution-function"></a>NormalDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回具有給定平均值和變異數的一般分佈。

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>輸入

### <a name="mean--double"></a>平均： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)




### <a name="variance--double"></a>變異數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)





## <a name="output--continuousdistribution"></a>輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>範例

下列範例會從一般分佈以平均2和標準差0.1 繪製10個樣本：

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a>另請參閱

- [StandardNormalDistribution。](xref:Microsoft.Quantum.Random.StandardNormalDistribution)