---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698951"
---
# <a name="operationpow-function"></a>OperationPow 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


對電源引發運算。

亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>輸入

### <a name="op--t--unit"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

作業 $U $ 代表要重複的閘道。


### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

要重複 $U $ 的次數。



## <a name="output--t--unit"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 

代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要支援之作業的型別。

## <a name="see-also"></a>另請參閱

- [Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)