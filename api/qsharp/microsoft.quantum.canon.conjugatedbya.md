---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: eaa104039b857f0469ddc0aaba97698eca20860d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207338"
---
# <a name="conjugatedbya-function"></a>ConjugatedByA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定外部和內部作業時，會傳回由外部作業 conjugates 內部作業的新作業。

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a>輸入

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

作業 $U $，其應用於共軛 $V $。 請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。


### <a name="inneroperation--t--unit--is-adj"></a>innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

作業 $V $ 正在 conjugated。



## <a name="output--t--unit--is-adj"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

由單一 $U ^ {\dagger} V U $ 表示其動作的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個內部和外部作業作用所在的目標型別。

## <a name="remarks"></a>備註

外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。

## <a name="see-also"></a>另請參閱

- [Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)