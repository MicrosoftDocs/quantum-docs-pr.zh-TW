---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852371"
---
# <a name="operationpow-function"></a>OperationPow 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


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