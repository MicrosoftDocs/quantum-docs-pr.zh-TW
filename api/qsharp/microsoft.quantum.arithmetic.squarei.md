---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221856"
---
# <a name="squarei-operation"></a>SquareI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)


將整數的平方計算 `xs` 為 `result` ，一開始必須為零。

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ 位數位到平方 (LittleEndian) 


### <a name="result--littleendian"></a>結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ 2n $ bit result (LittleEndian) ，必須先處於 state $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

使用標準的 shift 和 add 方法來計算方形。 相較于在套用一般乘數然後復原複製作業之前，會先複製 xs 的正向解決方案，節省 $n-$1 量子位。