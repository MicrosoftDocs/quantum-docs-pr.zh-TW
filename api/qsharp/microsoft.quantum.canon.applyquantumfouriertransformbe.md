---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 39db7b4c69f7f06418ec257c013837c65b9cc67a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209038"
---
# <a name="applyquantumfouriertransformbe-operation"></a>ApplyQuantumFourierTransformBE 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在包含以大到小整數表示之整數的量子暫存器上執行量子傅立葉轉換。

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="qs--bigendian"></a>qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

套用量子傅立葉轉換的量子暫存器



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

輸入和輸出假設為位元組由大到小的編碼方式。

## <a name="see-also"></a>另請參閱

- [Canon. ApproximateQFT](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)