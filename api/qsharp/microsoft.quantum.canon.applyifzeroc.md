---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699283"
---
# <a name="applyifzeroc-operation"></a>ApplyIfZeroC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將以傳統結果值為零的可控作業套用。

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a>描述

指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `Zero` 。 如果 `One` 為，則不會發生任何事 `target` 。
尾碼 `C` 表示要套用的作業是可控制的。

## <a name="input"></a>輸入

### <a name="result--__invalidresult__"></a>結果： __無效 <Result>__

控制是否套用 op 的測量結果。


### <a name="op--t--unit-ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl

有條件地套用的作業。


### <a name="target--t"></a>目標： t

要套用作業的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)