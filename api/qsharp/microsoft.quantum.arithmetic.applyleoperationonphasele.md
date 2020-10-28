---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: ApplyLEOperationOnPhaseLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: ff8e9424b1fc179f25ca926520338a4bbbcd04c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700038"
---
# <a name="applyleoperationonphasele-operation"></a>ApplyLEOperationOnPhaseLE 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.phaselittleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.littleendian> 。

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要套用的作業。


### <a name="target--phaselittleendian"></a>目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

要套用作業的註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

註冊會透過使用來轉換成 `LittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyLEOperationonPhaseLEA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [Canon. ApplyLEOperationonPhaseLEC](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [Canon. ApplyLEOperationonPhaseLECA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)