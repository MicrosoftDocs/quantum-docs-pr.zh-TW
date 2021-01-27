---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844608"
---
# <a name="applytoeacha-operation"></a>ApplyToEachA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


對暫存器中的每個元素套用單一量子位作業。
修飾詞 `A` 表示單一量子位作業為 adjointable。

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="singleelementoperation--t--unit--is-adj"></a>singleElementOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要套用至每個量子位的作業。


### <a name="register--t"></a>register： t []

要套用指定作業的量子位陣列。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

作業運作的目標。

## <a name="example"></a>範例

準備三量子位 $ \ket{+} $ 狀態：

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)