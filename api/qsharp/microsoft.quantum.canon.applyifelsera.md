---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: d0181d98a9867f71d8a8f8dea4331e5a13f9e59c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699302"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


根據傳統結果的值，套用兩個 adjointable 作業的其中一個。

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit
```


## <a name="description"></a>描述

因此 `result` ， `zeroOp` `zeroInput` 當等於時，會將作業套用至做為其輸入， `result` `Zero` 並適用 `oneOp(oneInput)` 于 `result == One` 。

## <a name="input"></a>輸入

### <a name="result--__invalidresult__"></a>結果： __無效 <Result>__

用來判斷是否已套用或的測量結果 `zeroOp` `oneOp` 。


### <a name="zeroop--t--unit-adj"></a>zeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要在其上套用的 adjointable 作業 `result == Zero` 。


### <a name="zeroinput--t"></a>zeroInput： t

要在何時提供的輸入 `zeroOp` `result == Zero` 。


### <a name="oneop--u--unit-adj"></a>oneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要在其上套用的 adjointable 作業 `result == One` 。


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