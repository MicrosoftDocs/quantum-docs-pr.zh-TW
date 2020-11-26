---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217572"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至陣列的指定元素。

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>描述

指定作業 `op` 、索引 `index` 和目標陣列時，就會 `targets` 套用 `op(targets[index])` 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

要套用的作業。


### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)

目標陣列中的索引。


### <a name="targets--t"></a>目標： t []

可能目標的陣列 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)