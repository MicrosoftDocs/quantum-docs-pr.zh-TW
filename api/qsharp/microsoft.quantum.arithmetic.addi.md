---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191018"
---
# <a name="addi-operation"></a>AddI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)


視的註冊大小而定，自動選擇 [包含] 或 [無] `ys` 。

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit 加數。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

至少有 $n $ 量子位的加數。 將會保留結果。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

