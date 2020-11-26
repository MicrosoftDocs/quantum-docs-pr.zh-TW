---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216620"
---
# <a name="curriedop-function"></a>CurriedOp 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回兩個輸入之作業的局部擴充版本。

亦即，假設有兩個輸入的作業，此函式會將 Curry 的 isomorphism $f (x，y) \equiv f (x) # B4 y) $ 傳回一個輸入的作業，以傳回一個輸入的運算。

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>輸入

### <a name="op--tu--unit"></a>op： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit) 

其輸入為成對的作業。



## <a name="output--t---u--unit"></a>輸出： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 

接受一組第一個專案的作業，並傳回可接受做為其輸入的作業，該作業會將原始作業的輸入的第二個元素做為其輸入。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

成對定義之函式的第一個元件型別。
### <a name="u"></a>' U

成對定義之函式的第二個元件類型。

## <a name="remarks"></a>備註

以下是相等的：

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```