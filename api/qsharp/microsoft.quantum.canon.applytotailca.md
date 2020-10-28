---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699130"
---
# <a name="applytotailca-operation"></a>ApplyToTailCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將作業套用至陣列的最後一個元素。

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>描述

假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Tail(targets))` 。

## <a name="input"></a>輸入

### <a name="op--t--unit-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

要套用的作業。


### <a name="targets--t"></a>目標： t []

目標的陣列，最後會將其套用至其中 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Canon. ApplyToTailA](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Canon. ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)