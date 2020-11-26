---
uid: Microsoft.Quantum.Random.DiscreteDistribution
title: DiscreteDistribution 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers.
ms.openlocfilehash: d492c86a6d72144695e1d0c2a94e8fe64cf1d3ef
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193041"
---
# <a name="discretedistribution-user-defined-type"></a>DiscreteDistribution 使用者定義型別

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


表示透過整數的單變數機率分佈。

```qsharp

newtype DiscreteDistribution = (Sample : (Unit => Int));
```



## <a name="named-items"></a>命名專案

### <a name="sample--unit--int"></a>範例： [單位](xref:microsoft.quantum.lang-ref.unit) => [Int](xref:microsoft.quantum.lang-ref.int) 



## <a name="see-also"></a>另請參閱

- [ContinuousDistribution。](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [ComplexDistribution。](xref:Microsoft.Quantum.Random.ComplexDistribution)
- [BigDiscreteDistribution。](xref:Microsoft.Quantum.Random.BigDiscreteDistribution)