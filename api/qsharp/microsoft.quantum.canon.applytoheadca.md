---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850603"
---
# <a name="applytoheadca-operation"></a>ApplyToHeadCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至陣列的第一個元素。

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

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
- [Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)