---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699986"
---
# <a name="applyreversedopbec-operation"></a>ApplyReversedOpBEC 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="op--bigendian--unit-ctl"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

在位元組由大到小的暫存器上運作的作業。


### <a name="register--littleendian"></a>register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要轉換的位元組由大到小的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [ApplyReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [ApplyReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)