---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216909"
---
# <a name="ccontrolledc-function"></a>CControlledC 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在指定作業作業的情況下，會傳回新的作業，如果傳統的控制項位為 true，就會套用 op。 如果為，則不 `false` 會發生任何事。
修飾詞 `C` 表示作業可控制。

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="op--t--unit--is-ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

有條件地套用的作業。



## <a name="output--boolt--unit--is-ctl"></a>Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

如果傳統控制位為 true，則為 op 的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="see-also"></a>另請參閱

- [Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)