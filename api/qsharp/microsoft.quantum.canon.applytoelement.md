---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699211"
---
# <a name="applytoelement-operation"></a>ApplyToElement 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將作業套用至陣列的指定元素。

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>描述

指定作業 `op` 、索引 `index` 和目標陣列時，就會 `targets` 套用 `op(targets[index])` 。

## <a name="input"></a>輸入

### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

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

- [Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)