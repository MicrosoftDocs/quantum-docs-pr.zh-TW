---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: bcaab28e99d3d61f4a36da866321d28f3dc4bd53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699062"
---
# <a name="conjugatedbya-function"></a>ConjugatedByA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


指定外部和內部作業時，會傳回由外部作業 conjugates 內部作業的新作業。

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a>輸入

### <a name="outeroperation--t--unit-adj"></a>outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

作業 $U $，其應用於共軛 $V $。 請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。


### <a name="inneroperation--t--unit-adj"></a>innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

作業 $V $ 正在 conjugated。



## <a name="output--t--unit-adj"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

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