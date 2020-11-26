---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216875"
---
# <a name="boundca-function"></a>BoundCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。
修飾詞 `CA` 指出陣列中的所有作業都是 adjointable 且可控制的。

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="operations--t--unit--is-adj--ctl"></a>作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []

要在指定的輸入上執行的一連串作業。



## <a name="output--t--unit--is-adj--ctl"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

在其輸入上依序執行每個指定作業的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列中的每個作業所作用的目標。

## <a name="see-also"></a>另請參閱

- [Canon 系結](xref:Microsoft.Quantum.Canon.Bound)