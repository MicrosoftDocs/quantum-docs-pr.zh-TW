---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: adccad53e8d874cb2879d7005711624bbcc69201
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190763"
---
# <a name="applyphaseleoperationonle-operation"></a>ApplyPhaseLEOperationOnLE 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.littleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.phaselittleendian> 。

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="op--phaselittleendian--unit"></a>op： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要套用的作業。


### <a name="target--littleendian"></a>目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要套用作業的註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

註冊會透過使用來轉換成 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Canon. ApplyPhaseLEOperationonLECA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)