---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699891"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>EvaluateOddPolynomialFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


評估固定點標記法中的奇多項式。

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

奇多項式的係數，例如 double 陣列，也就是陣列 $ [a_0，a_1，...，a_k] $ 代表奇數多項式 $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $。


### <a name="fpx--fixedpoint"></a>fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

輸入要評估多項式的固定點數位。


### <a name="result--fixedpoint"></a>結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

輸出將保留 P (x) 的固定點數位。 必須先處於 state $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

