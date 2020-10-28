---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699214"
---
# <a name="applytoeachindexc-operation"></a>ApplyToEachIndexC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將單一量子位作業套用至暫存器中的每個索引元素。
修飾詞 `C` 表示單一量子位作業是可控制的。

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>輸入

### <a name="singleelementoperation--intt--unit-ctl"></a>singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要套用至每個量子位的作業。


### <a name="register--t"></a>register： t []

要套用指定作業的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個作業作用所在的目標。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)