---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699091"
---
# <a name="boundc-function"></a>BoundC 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。
修飾詞 `C` 表示陣列中的所有作業都是可控制的。

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="operations--t--unit-ctl"></a>作業： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl []

要在指定的輸入上執行的一連串作業。



## <a name="output--t--unit-ctl"></a>Output： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl

在其輸入上依序執行每個指定作業的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列中的每個作業所作用的目標。

## <a name="see-also"></a>另請參閱

- [Canon 系結](xref:Microsoft.Quantum.Canon.Bound)