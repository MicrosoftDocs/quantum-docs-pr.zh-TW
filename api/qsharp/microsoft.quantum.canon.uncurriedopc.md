---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204584"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。
修飾詞 `C` 表示作業可控制。

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>輸入

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為 Ctl

傳回作業的函數。



## <a name="output--tu--unit--is-ctl"></a>輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

局部擴充函數的第一個引數類型。
### <a name="u"></a>' U

局部擴充函數的第二個引數類型。

## <a name="see-also"></a>另請參閱

- [Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)