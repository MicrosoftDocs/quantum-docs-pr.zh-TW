---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190610"
---
# <a name="applyouterttkadder-operation"></a>ApplyOuterTTKAdder 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將 RippleCarryAdderTTK 的外部作業實作為內部作業，以建立完整的對應程式。

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderTTK。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderTTK。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。
  https://arxiv.org/abs/0910.2530