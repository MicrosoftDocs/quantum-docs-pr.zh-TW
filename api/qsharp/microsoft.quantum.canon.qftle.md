---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698914"
---
# <a name="qftle-operation"></a>QFTLE 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


在包含整數位節由小到大標記法的量子暫存器上執行量子傅立葉轉換。

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="qs--littleendian"></a>qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

套用量子傅立葉轉換的量子暫存器



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

輸入和輸出假設是以位元組由小到大的編碼方式。

## <a name="see-also"></a>另請參閱

- [Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)