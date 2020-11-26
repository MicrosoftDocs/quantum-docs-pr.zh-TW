---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208851"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至陣列的指定元素。

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

指定作業 `op` 、索引 `index` 和目標陣列時，就會 `targets` 套用 `op(targets[index])` 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

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
- [Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)