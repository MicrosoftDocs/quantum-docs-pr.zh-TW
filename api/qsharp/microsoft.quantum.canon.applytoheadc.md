---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208596"
---
# <a name="applytoheadc-operation"></a>ApplyToHeadC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至陣列的第一個元素。

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>描述

假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

要套用的作業。


### <a name="targets--t"></a>目標： t []

目標的陣列，其中第一個會套用至 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)