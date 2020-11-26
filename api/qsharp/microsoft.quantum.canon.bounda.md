---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216943"
---
# <a name="bounda-function"></a>BoundA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。
修飾詞 `A` 表示陣列中的所有作業都是 adjointable。

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>輸入

### <a name="operations--t--unit--is-adj"></a>作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 []

要在指定的輸入上執行的一連串作業。



## <a name="output--t--unit--is-adj"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

在其輸入上依序執行每個指定作業的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列中的每個作業所作用的目標。

## <a name="see-also"></a>另請參閱

- [Canon 系結](xref:Microsoft.Quantum.Canon.Bound)