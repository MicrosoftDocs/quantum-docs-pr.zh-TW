---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208494"
---
# <a name="applytomosta-operation"></a>ApplyToMostA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至陣列的最後一個元素以外的所有專案。

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>描述

假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Most(targets))` 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-adj"></a>op： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要套用的作業。


### <a name="targets--t"></a>目標： t []

目標的陣列，其中最後一個只會套用到最後一個 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyToMost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)