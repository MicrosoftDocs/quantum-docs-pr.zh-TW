---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 1de0248066aec531d78130703414067603ffd34d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191001"
---
# <a name="applyinnerttkadder-operation"></a>ApplyInnerTTKAdder 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


執行作業 RippleCarryAdderTTK 的內部加法函數。 這是使用外部作業 conjugated 的內部作業，用來建立完整的加入程式。

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderTTK。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderTTK。


### <a name="carry--qubit"></a>攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)

帶有量子位，是以總和的最高有效位進行 xor。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

指定的受控制作業會使用作業的對稱和相互取消，以改善將控制項加入至每個作業的預設執行。

## <a name="references"></a>參考

- Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。
  https://arxiv.org/abs/0910.2530