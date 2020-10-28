---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699894"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>EvaluateEvenPolynomialFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


在固定點標記法中評估偶數多項式。

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

偶數多項式的係數，例如 double 陣列，也就是陣列 $ [a_0，a_1，...，a_k] $ 表示偶數多項式 $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $。


### <a name="fpx--fixedpoint"></a>fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

輸入要評估多項式的固定點數位。


### <a name="result--fixedpoint"></a>結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

輸出將保留 $P (x) $ 的固定點數位。 必須先處於 state $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

