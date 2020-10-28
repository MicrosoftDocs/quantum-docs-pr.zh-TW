---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699221"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


對暫存器中的每個元素套用單一量子位作業。
修飾詞 `A` 表示單一量子位作業為 adjointable。

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a>輸入

### <a name="singleelementoperation--t--unit-adj"></a>singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要套用至每個量子位的作業。


### <a name="register--t"></a>register： t []

要套用指定作業的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

作業運作的目標。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)