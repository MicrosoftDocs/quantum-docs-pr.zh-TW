---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699124"
---
# <a name="applywithc-operation"></a>ApplyWithC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


假設有兩個作業，請將其套用為另一個作業的 conjugated。

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a>描述

假設有兩個作業，分別由單一運算子 $U $ 和 $V $，則會以 $U ^ {\dagger} V U $ 的順序套用。 也就是說，這項作業會透過 $U $ conjugated，來實 $V $ 所指定的單一運算子。

## <a name="input"></a>輸入

### <a name="outeroperation--t--unit-adj"></a>outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

作業 $U $，其應用於共軛 $V $。 請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。


### <a name="inneroperation--t--unit-ctl"></a>innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl

作業 $V $ 正在 conjugated。


### <a name="target--t"></a>目標： t

要提供給外部和內部作業的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每個內部和外部作業作用所在的目標。

## <a name="remarks"></a>備註

外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)