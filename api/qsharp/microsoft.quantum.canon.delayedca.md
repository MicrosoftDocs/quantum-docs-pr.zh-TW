---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699027"
---
# <a name="delayedca-function"></a>DelayedCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


傳回以指定的引數套用指定作業的作業。

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>輸入

### <a name="op--t--unit-ctl--adj"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

套用傳回值的結果所要套用的作業


### <a name="arg--t"></a>arg： t

要套用作業的輸入 `op` 。



## <a name="output--unit--unit-ctl--adj"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

適用于輸入的新作業 `op``arg`

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要延遲之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delayed)
- [Canon. 延遲](xref:Microsoft.Quantum.Canon.Delay)