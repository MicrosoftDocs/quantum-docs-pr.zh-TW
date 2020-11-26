---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208936"
---
# <a name="applytoeachindexca-operation"></a>ApplyToEachIndexCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將單一量子位作業套用至暫存器中的每個索引元素。
修飾詞 `CA` 表示單一量子位作業是 adjointable 且可控制的。

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a>singleElementOperation： ([Int](xref:microsoft.quantum.lang-ref.int)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

要套用至每個量子位的作業。


### <a name="register--t"></a>register： t []

要套用指定作業的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個作業作用所在的目標。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)