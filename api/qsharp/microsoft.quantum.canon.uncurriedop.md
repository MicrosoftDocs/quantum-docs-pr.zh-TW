---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698799"
---
# <a name="uncurriedop-function"></a>UncurriedOp 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


假設有一個會傳回作業的函式，會傳回新的作業，它會將這兩個輸入視為一個元組。

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>輸入

### <a name="curriedop--t---u--unit"></a>curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 

傳回作業的函數。



## <a name="output--tu--unit"></a>輸出： ( t，' U) => [單位](xref:microsoft.quantum.lang-ref.unit) 

`op`相當於的新作業 `op(t, u)` `(curriedOp(t))(u)` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

局部調用的第一個輸入類型。
### <a name="u"></a>' U

局部調用的第二個輸入型別。

## <a name="see-also"></a>另請參閱

- [Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)