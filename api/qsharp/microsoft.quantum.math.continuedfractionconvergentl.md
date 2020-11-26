---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c10fcbbe63d3d4c7d6c56196768c1062be1ca350
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210925"
---
# <a name="continuedfractionconvergentl-function"></a>ContinuedFractionConvergentL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


找出最接近 `fraction` 分母小於或等於分母的接續分數 convergent `denominatorBound`

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a>輸入

### <a name="fraction--bigfraction"></a>分數： [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)




### <a name="denominatorbound--bigint"></a>denominatorBound： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigfraction"></a>輸出： [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)

最接近 `fraction` 小於分母或等於分母的最小分數 `denominatorBound`