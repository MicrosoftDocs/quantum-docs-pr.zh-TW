---
uid: Microsoft.Quantum.Random.ComplexDistribution
title: ComplexDistribution 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ComplexDistribution
qsharp.summary: Represents a univariate probability distribution over complex numbers.
ms.openlocfilehash: 51371cf6e699cb0be6e32f485054a9e92572991d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857832"
---
# <a name="complexdistribution-user-defined-type"></a>ComplexDistribution 使用者定義型別

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


表示複數的單變數機率分佈。

```qsharp

newtype ComplexDistribution = (Sample : (Unit => Microsoft.Quantum.Math.Complex));
```



## <a name="named-items"></a>命名專案

### <a name="sample--unit--complex"></a>範例： [單元](xref:microsoft.quantum.lang-ref.unit) => [複雜](xref:Microsoft.Quantum.Math.Complex) 



## <a name="see-also"></a>另請參閱

- [ContinuousDistribution。](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [DiscreteDistribution。](xref:Microsoft.Quantum.Random.DiscreteDistribution)
- [BigDiscreteDistribution。](xref:Microsoft.Quantum.Random.BigDiscreteDistribution)