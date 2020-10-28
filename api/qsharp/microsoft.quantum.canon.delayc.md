---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699037"
---
# <a name="delayc-operation"></a>DelayC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


套用具有延遲的指定作業。

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>描述

如果有作業和該作業的輸入，則會在提供額外的輸入之後套用作業。
尤其是，運算式 `Delay(op, arg, _)` 是 `op` 在呼叫時套用的作業 `arg` 。
運算式 `Delay(op,arg,_)` 允許延遲的應用程式 `op` 。

## <a name="input"></a>輸入

### <a name="op--t--unit-ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl

要套用的作業。


### <a name="arg--t"></a>arg： t

要套用作業的輸入。


### <a name="aux--unit"></a>aux： [Unit](xref:microsoft.quantum.lang-ref.unit)

使用部分應用程式來延遲作業應用程式的引數。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要延遲之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delay)
- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delayed)