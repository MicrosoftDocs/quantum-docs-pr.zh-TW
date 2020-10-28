---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699298"
---
# <a name="applyifelserc-operation"></a>ApplyIfElseRC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


根據傳統結果的值，套用兩個可控作業的其中一個。

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a>描述

因此 `result` ， `zeroOp` `zeroInput` 當等於時，會將作業套用至做為其輸入， `result` `Zero` 並適用 `oneOp(oneInput)` 于 `result == One` 。

## <a name="input"></a>輸入

### <a name="result--__invalidresult__"></a>結果： __無效 <Result>__

用來判斷是否已套用或的測量結果 `zeroOp` `oneOp` 。


### <a name="zeroop--t--unit-ctl"></a>zeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl

要在其上套用的可控制作業 `result == Zero` 。


### <a name="zeroinput--t"></a>zeroInput： t

要在何時提供的輸入 `zeroOp` `result == Zero` 。


### <a name="oneop--u--unit-ctl"></a>oneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl

要在其上套用的可控制作業 `result == One` 。


### <a name="oneinput--u"></a>oneInput： ' U

要在何時提供的輸入 `oneOp` `result == One` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型 `zeroOp` 。
### <a name="u"></a>' U

要有條件地套用之作業的輸入類型 `oneOp` 。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)