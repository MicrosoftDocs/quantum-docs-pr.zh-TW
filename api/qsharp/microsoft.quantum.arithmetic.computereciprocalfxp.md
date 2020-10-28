---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699910"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


計算固定點數位 $x $ 的 $ 1/x $。

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>輸入

### <a name="x--fixedpoint"></a>x： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

要反轉的固定點數位。


### <a name="result--fixedpoint"></a>結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

將保留結果的固定點數位。 必須初始化為 $ \ket{0.0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

