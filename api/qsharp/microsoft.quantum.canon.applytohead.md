---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e5fc439f48a5c7e527b7805c35cce18eca3ab36
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699177"
---
# <a name="applytohead-operation"></a>ApplyToHead 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將作業套用至陣列的第一個元素。

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>描述

假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。

## <a name="input"></a>輸入

### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

要套用的作業。


### <a name="targets--t"></a>目標： t []

目標的陣列，其中第一個會套用至 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)