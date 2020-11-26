---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: ApplyLEOperationOnPhaseLEA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 408bd4e5d7146a74d7aec233765a63b2086b8ede
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190848"
---
# <a name="applyleoperationonphaselea-operation"></a>ApplyLEOperationOnPhaseLEA 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.phaselittleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.littleendian> 。

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="op--littleendian--unit--is-adj"></a>op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要套用的作業。


### <a name="target--phaselittleendian"></a>目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

要套用作業的註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

註冊會透過使用來轉換成 `LittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyLEOperationonPhaseLE](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [Canon. ApplyLEOperationonPhaseLEC](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [Canon. ApplyLEOperationonPhaseLECA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)