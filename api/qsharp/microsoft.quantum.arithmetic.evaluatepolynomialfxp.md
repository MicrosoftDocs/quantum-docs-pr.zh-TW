---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699887"
---
# <a name="evaluatepolynomialfxp-operation"></a>EvaluatePolynomialFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


在固定點標記法中評估多項式。

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

多項式的係數做為雙精度浮點數陣列，也就是多項式 $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $ 的陣列 $ [a_0，a_1，...，a_d] $。


### <a name="fpx--fixedpoint"></a>fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

輸入要評估多項式的固定點數位。


### <a name="result--fixedpoint"></a>結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

輸出將保留 $P (x) $ 的固定點數位。 必須先處於 state $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

