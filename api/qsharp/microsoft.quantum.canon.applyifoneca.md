---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 8b27a192c66a127fe5a8acfbba7b78314988bf2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844919"
---
# <a name="applyifoneca-operation"></a>ApplyIfOneCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對傳統結果值套用條件為一的單一作業。

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `One` 。 如果 `Zero` 為，則不會發生任何事 `target` 。
尾碼 `CA` 表示要套用的作業是單一 (可控制和 adjointable) 。

## <a name="input"></a>輸入

### <a name="result--__invalidresult__"></a>結果：__無效 <Result>__

控制是否套用 op 的測量結果。


### <a name="op--t--unit--is-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

有條件地套用的作業。


### <a name="target--t"></a>目標： t

要套用作業的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Canon. ApplyIfOneA](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Canon. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)