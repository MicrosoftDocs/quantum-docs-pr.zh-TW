---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207002"
---
# <a name="delayedc-function"></a>DelayedC 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回以指定的引數套用指定作業的作業。

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="op--t--unit--is-ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

套用傳回值的結果所要套用的作業


### <a name="arg--t"></a>arg： t

要套用作業的輸入 `op` 。



## <a name="output--unit--unit--is-ctl"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

適用于輸入的新作業 `op``arg`

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要延遲之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delayed)
- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delay)