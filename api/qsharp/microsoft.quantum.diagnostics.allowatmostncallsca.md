---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698178"
---
# <a name="allowatmostncallsca-operation"></a>AllowAtMostNCallsCA 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


在呼叫此作業和其 adjoint 之間，判斷指定的作業最多隻會呼叫一次特定的次數。

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="ntimes--int"></a>nTimes： [Int](xref:microsoft.quantum.lang-ref.int)

可能呼叫的最大次數 `op` 。


### <a name="op--tinput--toutput-adj--ctl"></a>op： ' TInput => ' Toutput> 形容詞 + Ctl

要限制其呼叫的作業。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

失敗時要顯示的訊息。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>' Toutput>



## <a name="remarks"></a>備註

在不支援此作業的目標上，此作業可能會取代為無作業。