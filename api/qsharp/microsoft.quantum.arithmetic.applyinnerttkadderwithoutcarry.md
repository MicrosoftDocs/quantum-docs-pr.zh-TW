---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700042"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a>ApplyInnerTTKAdderWithoutCarry 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


執行作業 RippleCarryAdderNoCarryTTK 的內部加法函數。 這是使用外部作業 conjugated 的內部作業，用來建立完整的加入程式。

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderNoCarryTTK。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderNoCarryTTK。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

指定的受控制作業會使用作業的對稱和相互取消，以改善將控制項加入至每個作業的預設執行。

## <a name="references"></a>參考

- Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。
  https://arxiv.org/abs/0910.2530