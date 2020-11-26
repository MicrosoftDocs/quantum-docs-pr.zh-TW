---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEC
title: ReversedOpLEC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEC
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 8c91391691b23786df02ae2a35264b578dccad41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222077"
---
# <a name="reversedoplec-function"></a>ReversedOpLEC 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有一個作業採用位元組由小到大的輸入，則會傳回採用位元組由大到小的輸入的新作業。

```qsharp
function ReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit--is-ctl"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

要反轉其輸入的作業。



## <a name="output--bigendian--unit--is-ctl"></a>輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

以位元組由大到小的暫存器形式接受其輸入的新作業。

## <a name="see-also"></a>另請參閱

- [ApplyReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [ReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [ReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [ReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)