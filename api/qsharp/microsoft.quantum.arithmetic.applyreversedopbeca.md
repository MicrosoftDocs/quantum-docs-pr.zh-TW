---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: ApplyReversedOpBECA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 71e99d3390a2e510fd7ed28f3f6d8ed43b3ca7e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843572"
---
# <a name="applyreversedopbeca-operation"></a>ApplyReversedOpBECA 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="op--bigendian--unit--is-adj--ctl"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

在位元組由大到小的暫存器上運作的作業。


### <a name="register--littleendian"></a>register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要轉換的位元組由大到小的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [ApplyReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [ApplyReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)