---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208630"
---
# <a name="applytoheada-operation"></a>ApplyToHeadA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至陣列的第一個元素。

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>描述

假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-adj"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要套用的作業。


### <a name="targets--t"></a>目標： t []

目標的陣列，其中第一個會套用至 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)