---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844963"
---
# <a name="applyifelsebca-operation"></a>ApplyIfElseBCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


根據傳統位的值，套用兩項單一作業的其中一個。

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

有一點 `bit` ，會在為時套用作業 `trueOp` `trueInput` 做為其 `bit` 輸入 `true` ，並 `falseOp(falseInput)` 在為時套用 `bit` `false` 。

## <a name="input"></a>輸入

### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

用來判斷是否已套用或的布林值 `trueOp` `falseOp` 。


### <a name="trueop--t--unit--is-adj--ctl"></a>trueOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

當為時要套用的單一 `bit` 作業 `true` 。


### <a name="trueinput--t"></a>trueInput： t

當為時，所要提供的輸入 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit--is-adj--ctl"></a>falseOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

當為時要套用的單一 `bit` 作業 `false` 。


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