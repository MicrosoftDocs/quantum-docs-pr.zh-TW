---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699926"
---
# <a name="comparegreaterthanfxp-operation"></a>CompareGreaterThanFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


比較儲存在量子暫存器中的兩個固定點數位，並控制結果的翻轉。

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a>輸入

### <a name="fp1--fixedpoint"></a>fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

要比較的第一個固定點數位。


### <a name="fp2--fixedpoint"></a>fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

要比較的第二個固定點數位。


### <a name="result--qubit"></a>結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)

比較的結果。 如果為，則會翻轉 `fp1 > fp2` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

目前的執行需要兩個固定點數位具有相同的點位置和相同的量子位數目。