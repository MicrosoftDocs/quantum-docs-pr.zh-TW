---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700059"
---
# <a name="addfxp-operation"></a>AddFxP 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


新增儲存在量子暫存器中的兩個固定點數位。

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>描述

假設有兩個固定點暫存器分別在狀態 $ \ket{f_1} $ 和 $ \ket{f_2} $ 中，則執行作業 $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $。

## <a name="input"></a>輸入

### <a name="fp1--fixedpoint"></a>fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

第一個固定點數位


### <a name="fp2--fixedpoint"></a>fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

第二個固定點數位將會更新，以包含兩個輸入的總和。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

目前的執行需要有兩個固定點數位，使其具有與最小有效位的相同點位置計數，亦即 $n _i $ 和 $p _i $ 必須相等。