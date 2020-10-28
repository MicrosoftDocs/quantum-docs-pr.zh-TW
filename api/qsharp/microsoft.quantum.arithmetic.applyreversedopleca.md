---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA
title: ApplyReversedOpLECA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLECA
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 6e4edd30e33be1a8039b7fd6551470abee26ea27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699967"
---
# <a name="applyreversedopleca-operation"></a>ApplyReversedOpLECA 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。

```qsharp
operation ApplyReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit-ctl--adj"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

以位元組由小到大的暫存器為運算的作業。


### <a name="register--bigendian"></a>register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

要轉換的位元組由大到小的暫存器。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [ApplyReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [ApplyReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)