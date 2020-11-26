---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 75b6c0f09c0699b50d9ac1b0274e8074520fc241
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202646"
---
# <a name="applyreversedoplec-operation"></a>ApplyReversedOpLEC 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit--is-ctl"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

以位元組由小到大的暫存器為運算的作業。


### <a name="register--bigendian"></a>register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

要轉換的位元組由大到小的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [ApplyReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [ApplyReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)