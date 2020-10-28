---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699559"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


假設有一個使用位元組由大到小的輸入，則會傳回採用位元組由小到大輸入的新作業。

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>輸入

### <a name="op--bigendian--unit-adj"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要反轉其輸入的作業。



## <a name="output--littleendian--unit-adj"></a>輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

以位元組由大到小的暫存器形式接受其輸入的新作業。

## <a name="see-also"></a>另請參閱

- [ApplyReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [ReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [ReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [ReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)