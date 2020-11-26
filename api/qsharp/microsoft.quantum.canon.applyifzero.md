---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3b14ef8a1aa736fe096a21fe51be5a7c5bb1d09d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209428"
---
# <a name="applyifzero-operation"></a>ApplyIfZero 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將以傳統結果值為零的運算套用。

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>描述

指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `Zero` 。 如果 `One` 為，則不會發生任何事 `target` 。

## <a name="input"></a>輸入

### <a name="result--__invalidresult__"></a>結果：__無效 <Result>__

控制是否套用 op 的測量結果。


### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

有條件地套用的作業。


### <a name="target--t"></a>目標： t

要套用作業的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)