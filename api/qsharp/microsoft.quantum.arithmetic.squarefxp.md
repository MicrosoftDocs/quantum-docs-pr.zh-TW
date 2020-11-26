---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: 8d08cb51e3a7ae892b23be0adbb7cdf3ee0f4de5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221873"
---
# <a name="squarefxp-operation"></a>SquareFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)


將固定點數位的平方。

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="fp--fixedpoint"></a>fp： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

固定點數位。


### <a name="result--fixedpoint"></a>結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

結果固定點數必須一開始就是狀態 $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

