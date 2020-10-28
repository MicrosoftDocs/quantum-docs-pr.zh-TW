---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700638"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


計算元組 $ (u，v) $，以 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 和 $a $ $b $ 最大公因數。 GCD 一律為正數。

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要計算的第一個擴充最大公除數


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

計算最大最大公除數的第二個數字



## <a name="output--intint"></a>輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) 

元組 $ (u、v) $ 和屬性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。

## <a name="references"></a>參考

- 這項實行是根據 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm