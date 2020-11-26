---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 71b6b87a44f541e5379d8de8a3562febbfa49e1d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222162"
---
# <a name="reversedoplea-function"></a>ReversedOpLEA 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有一個作業採用位元組由小到大的輸入，則會傳回採用位元組由大到小的輸入的新作業。

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit--is-adj"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要反轉其輸入的作業。



## <a name="output--bigendian--unit--is-adj"></a>輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

以位元組由大到小的暫存器形式接受其輸入的新作業。

## <a name="see-also"></a>另請參閱

- [ApplyReversedOpLEA。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [ReversedOpLE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [ReversedOpLEC。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [ReversedOpLECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)