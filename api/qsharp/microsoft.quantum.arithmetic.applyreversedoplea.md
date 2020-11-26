---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA
title: ApplyReversedOpLEA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: d5bc1b38500c449b58f8dafd640627b8e933e902
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202731"
---
# <a name="applyreversedoplea-operation"></a>ApplyReversedOpLEA 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。

```qsharp
operation ApplyReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit--is-adj"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

以位元組由小到大的暫存器為運算的作業。


### <a name="register--bigendian"></a>register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

要轉換的位元組由大到小的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [ApplyReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [ApplyReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)