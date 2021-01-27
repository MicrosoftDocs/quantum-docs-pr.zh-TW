---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844521"
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

## <a name="example"></a>範例

以下是相等的：

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

及

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>另請參閱

- [Canon 系結](xref:Microsoft.Quantum.Canon.Bound)