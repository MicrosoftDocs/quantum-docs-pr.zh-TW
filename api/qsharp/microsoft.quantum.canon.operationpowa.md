---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698935"
---
# <a name="operationpowa-function"></a>OperationPowA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


對電源引發運算。
修飾詞 `A` 表示作業 adjointable。

亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>輸入

### <a name="op--t--unit-adj"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

作業 $U $ 代表要重複的閘道。


### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

要重複 $U $ 的次數。



## <a name="output--t--unit-adj"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要支援之作業的型別。

## <a name="see-also"></a>另請參閱

- [Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)