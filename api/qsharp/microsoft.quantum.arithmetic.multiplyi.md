---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222502"
---
# <a name="multiplyi-operation"></a>MultiplyI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)


將整數乘以 `xs` 整數 `ys` 並將結果儲存在中 `result` ，這一開始必須是零。

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit 被乘數 (LittleEndian) 


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit 乘數 (LittleEndian) 


### <a name="result--littleendian"></a>結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ 2n $ bit result (LittleEndian) ，必須先處於 state $ \ket {0} $。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

使用標準的 shift 和 add 方法來執行乘法。
藉由將 $x _i $ 複製到控制項量子位上的 ancilla 量子位，然後控制 ancilla 量子位的加法，來改善受控制版本。