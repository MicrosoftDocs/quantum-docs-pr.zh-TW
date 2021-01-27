---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844766"
---
# <a name="applyquantumfouriertransform-operation"></a>ApplyQuantumFourierTransform 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在包含整數位節由小到大標記法的量子暫存器上執行量子傅立葉轉換。

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="qs--littleendian"></a>qs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

套用量子傅立葉轉換的量子暫存器



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

輸入和輸出假設是以位元組由小到大的編碼方式。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)