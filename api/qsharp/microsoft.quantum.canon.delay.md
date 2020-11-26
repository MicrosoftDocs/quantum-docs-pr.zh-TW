---
uid: Microsoft.Quantum.Canon.Delay
title: 延遲操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4f45527faa49f79fccff3892e928fed09f9f0bc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216501"
---
# <a name="delay-operation"></a>延遲操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


套用具有延遲的指定作業。

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>描述

如果有作業和該作業的輸入，則會在提供額外的輸入之後套用作業。
尤其是，運算式 `Delay(op, arg, _)` 是 `op` 在呼叫時套用的作業 `arg` 。
運算式 `Delay(op,arg,_)` 允許延遲的應用程式 `op` 。

## <a name="input"></a>輸入

### <a name="op--t--u"></a>op： t => ' U 

要套用的作業。


### <a name="arg--t"></a>arg： t

要套用作業的輸入。


### <a name="aux--unit"></a>aux： [Unit](xref:microsoft.quantum.lang-ref.unit)

使用部分應用程式來延遲作業應用程式的引數。



## <a name="output--u"></a>輸出： ' U



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要延遲之作業的輸入類型。
### <a name="u"></a>' U

要延遲之作業的傳回型別。

## <a name="see-also"></a>另請參閱

- [Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Canon. DelayA](xref:Microsoft.Quantum.Canon.DelayA)
- [Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delayed)