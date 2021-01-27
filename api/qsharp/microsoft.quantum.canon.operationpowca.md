---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852314"
---
# <a name="operationpowca-function"></a>OperationPowCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


對電源引發運算。
修飾詞 `A` 表示作業可控制且 adjointable。

亦即，假設 $U $ 的作業代表閘道，則會傳回新的作業 $U ^ m $ 表示 power $m $。

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>輸入

### <a name="op--t--unit--is-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

作業 $U $ 代表要重複的閘道。


### <a name="power--int"></a>電源： [Int](xref:microsoft.quantum.lang-ref.int)

要重複 $U $ 的次數。



## <a name="output--t--unit--is-adj--ctl"></a>輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

代表 $U ^ m $ 的新作業，其中 $m = \texttt{power} $。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要支援之作業的型別。

## <a name="see-also"></a>另請參閱

- [Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)