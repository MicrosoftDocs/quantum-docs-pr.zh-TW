---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699229"
---
# <a name="applyseriesofopsca-operation"></a>ApplySeriesOfOpsCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


依序在陣列上套用 ops 清單和其目標。  (Adjoint + 控制) 

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>輸入

### <a name="listofops--t--unit-adj--ctl"></a>listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl []

要套用的 ops 清單（每個都有一個 t 陣列）。 它們會依序套用，最小的索引優先。
每個都必須同時具有 Adjoint 和控制仿函數。


### <a name="targets--int"></a>目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []

描述 op 目標的嵌套陣列。 每個陣列都應該包含描述要使用之索引的整數清單。


### <a name="register--t"></a>register： t []

要處理的量子位 register。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="see-also"></a>另請參閱

- [Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)