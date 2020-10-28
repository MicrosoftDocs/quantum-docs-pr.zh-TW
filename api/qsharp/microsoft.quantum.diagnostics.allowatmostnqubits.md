---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698175"
---
# <a name="allowatmostnqubits-operation"></a>AllowAtMostNQubits 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


在呼叫此作業和其 adjoint 之間，判斷最多可使用語句來配置指定數目的其他量子位。

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

可能配置的量子位數目上限。


### <a name="message--string"></a>message： [字串](xref:microsoft.quantum.lang-ref.string)

失敗時要顯示的訊息。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

在不支援此作業的目標上，此作業可能會取代為無作業。