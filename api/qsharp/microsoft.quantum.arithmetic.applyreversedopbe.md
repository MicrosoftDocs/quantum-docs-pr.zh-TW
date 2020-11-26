---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 6db1fcb7437d97b1e56c64165d1be523ed2df07a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202850"
---
# <a name="applyreversedopbe-operation"></a>ApplyReversedOpBE 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="op--bigendian--unit"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

在位元組由大到小的暫存器上運作的作業。


### <a name="register--littleendian"></a>register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要轉換的位元組由大到小的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [ApplyReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [ApplyReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)