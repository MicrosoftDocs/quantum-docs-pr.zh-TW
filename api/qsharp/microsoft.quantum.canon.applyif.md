---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699317"
---
# <a name="applyif-operation"></a>ApplyIf 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


在傳統位上套用條件運算。

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>描述

指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。 如果 `false` 為，則不會發生任何事 `target` 。

## <a name="input"></a>輸入

### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

有條件地套用的作業。


### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

此為布林值，可控制是否要套用 op。


### <a name="target--t"></a>目標： t

要套用作業的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)