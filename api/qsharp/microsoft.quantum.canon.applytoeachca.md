---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699217"
---
# <a name="applytoeachca-operation"></a>ApplyToEachCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


對暫存器中的每個元素套用單一量子位作業。
修飾詞 `CA` 表示單一量子位作業是可控制且 adjointable 的。

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>輸入

### <a name="singleelementoperation--t--unit-adj--ctl"></a>singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

要套用至每個量子位的作業。


### <a name="register--t"></a>register： t []

要套用指定作業的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

作業運作的目標。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)