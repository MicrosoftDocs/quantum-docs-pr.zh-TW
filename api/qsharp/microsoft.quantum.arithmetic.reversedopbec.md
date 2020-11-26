---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5bafe71b665eda082eafbe06be1308d6b042db2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222264"
---
# <a name="reversedopbec-function"></a>ReversedOpBEC 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有一個使用位元組由大到小的輸入，則會傳回採用位元組由小到大輸入的新作業。

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="op--bigendian--unit--is-ctl"></a>op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

要反轉其輸入的作業。



## <a name="output--littleendian--unit--is-ctl"></a>輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

以位元組由大到小的暫存器形式接受其輸入的新作業。

## <a name="see-also"></a>另請參閱

- [ApplyReversedOpBEC。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [ReversedOpBE。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [ReversedOpBEA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [ReversedOpBECA。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)