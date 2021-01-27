---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c5316c13ce499da88c0d5c45b9d8c5e3a8c6162d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853865"
---
# <a name="continuedfractionconvergenti-function"></a>ContinuedFractionConvergentI 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


找出最接近 `fraction` 分母小於或等於分母的接續分數 convergent `denominatorBound`

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a>輸入

### <a name="fraction--fraction"></a>分數： [分數](xref:Microsoft.Quantum.Math.Fraction)




### <a name="denominatorbound--int"></a>denominatorBound： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--fraction"></a>輸出： [分數](xref:Microsoft.Quantum.Math.Fraction)

最接近 `fraction` 小於分母或等於分母的最小分數 `denominatorBound`