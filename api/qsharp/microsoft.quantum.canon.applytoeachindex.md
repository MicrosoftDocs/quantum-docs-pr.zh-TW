---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844600"
---
# <a name="applytoeachindex-operation"></a>ApplyToEachIndex 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將單一量子位作業套用至暫存器中的每個索引元素。

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a>輸入

### <a name="singleelementoperation--intt--unit"></a>singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit) 

要套用至每個量子位的作業。


### <a name="register--t"></a>register： t []

要套用指定作業的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個作業作用所在的目標。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [Canon. ApplyToEachIndexA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [Canon. ApplyToEachIndexC](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [Canon. ApplyToEachIndexCA](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)