---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700635"
---
# <a name="extendedgreatestcommondivisorl-function"></a>ExtendedGreatestCommonDivisorL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


計算元組 $ (u，v) $，以 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 和 $a $ $b $ 最大公因數。 GCD 一律為正數。

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>輸入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要計算的第一個擴充最大公除數


### <a name="b--bigint"></a>b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

計算最大最大公除數的第二個數字



## <a name="output--bigintbigint"></a>輸出： ([Bigint](xref:microsoft.quantum.lang-ref.bigint)、[Bigint](xref:microsoft.quantum.lang-ref.bigint)) 

元組 $ (u、v) $ 和屬性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。

## <a name="references"></a>參考

- 這項實行是根據 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm