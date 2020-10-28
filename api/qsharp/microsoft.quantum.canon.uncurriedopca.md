---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698790"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。
修飾詞 `CA` 表示作業可控制且 adjointable。

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>輸入

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp： t-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

傳回作業的函數。



## <a name="output--tu--unit-ctl--adj"></a>輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞

`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

局部擴充函數的第一個引數類型。
### <a name="u"></a>' U

局部擴充函數的第二個引數類型。

## <a name="see-also"></a>另請參閱

- [Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)