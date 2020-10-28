---
uid: Microsoft.Quantum.Canon.QFT
title: QFT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698918"
---
# <a name="qft-operation"></a>QFT 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


在包含以大到小整數表示之整數的量子暫存器上執行量子傅立葉轉換。

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="qs--bigendian"></a>qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

套用量子傅立葉轉換的量子暫存器



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

輸入和輸出假設為位元組由大到小的編碼方式。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)