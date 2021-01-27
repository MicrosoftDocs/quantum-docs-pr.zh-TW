---
uid: Microsoft.Quantum.Random.BigDiscreteDistribution
title: BigDiscreteDistribution 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: BigDiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers of arbitrary size.
ms.openlocfilehash: de33b458b63a8c1f2c4af28dbb7db0b97367ce98
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855800"
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