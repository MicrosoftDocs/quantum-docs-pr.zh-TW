---
uid: Microsoft.Quantum.Random.DiscreteDistribution
title: DiscreteDistribution 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers.
ms.openlocfilehash: a3278d03dee9b30acd6fc6b61b94267adb4ae44f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851180"
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