---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: 74d43344481c5a808e84ce9c9e36fa3e83cd0d89
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218660"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


根據傳統位的值，套用兩個 adjointable 作業的其中一個。

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>描述

有一點 `bit` ，會在為時套用作業 `trueOp` `trueInput` 做為其 `bit` 輸入 `true` ，並 `falseOp(falseInput)` 在為時套用 `bit` `false` 。

## <a name="input"></a>輸入

### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

用來判斷是否已套用或的布林值 `trueOp` `falseOp` 。


### <a name="trueop--t--unit--is-adj"></a>trueOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

當為時要套用的 adjointable `bit` 作業 `true` 。


### <a name="trueinput--t"></a>trueInput： t

當為時，所要提供的輸入 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit--is-adj"></a>falseOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

當為時要套用的 adjointable `bit` 作業 `false` 。


### <a name="falseinput--u"></a>falseInput： ' U

當為時，所要提供的輸入 `falseOp` `bit` `false` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型 `trueOp` 。
### <a name="u"></a>' U

要有條件地套用之作業的輸入類型 `falseOp` 。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)