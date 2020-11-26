---
uid: Microsoft.Quantum.Random.BigDiscreteDistribution
title: BigDiscreteDistribution 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: BigDiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers of arbitrary size.
ms.openlocfilehash: add39f057b209bb19336a2af3d08aefcf8e1e11e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193194"
---
# <a name="bigdiscretedistribution-user-defined-type"></a>BigDiscreteDistribution 使用者定義型別

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


代表任意大小之整數的單變數機率分佈。

```qsharp

newtype BigDiscreteDistribution = (Sample : (Unit => BigInt));
```



## <a name="named-items"></a>命名專案

### <a name="sample--unit--bigint"></a>範例： [Unit](xref:microsoft.quantum.lang-ref.unit) => [BigInt](xref:microsoft.quantum.lang-ref.bigint) 



## <a name="see-also"></a>另請參閱

- [ContinuousDistribution。](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [ComplexDistribution。](xref:Microsoft.Quantum.Random.ComplexDistribution)
- [DiscreteDistribution。](xref:Microsoft.Quantum.Random.DiscreteDistribution)