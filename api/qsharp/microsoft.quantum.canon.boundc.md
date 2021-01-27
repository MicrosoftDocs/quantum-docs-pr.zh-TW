---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841035"
---
# <a name="boundc-function"></a>BoundC 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對單一輸入的作業陣列，會產生依序執行每個指定作業的新作業。
修飾詞 `C` 表示陣列中的所有作業都是可控制的。

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="operations--t--unit--is-ctl"></a>作業： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl []

要在指定的輸入上執行的一連串作業。



## <a name="output--t--unit--is-ctl"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

在其輸入上依序執行每個指定作業的新作業。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

陣列中的每個作業所作用的目標。

## <a name="example"></a>範例

以下是相等的：

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

及

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>另請參閱

- [Canon 系結](xref:Microsoft.Quantum.Canon.Bound)