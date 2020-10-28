---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698886"
---
# <a name="restrictedtosubregister-function"></a>RestrictedToSubregister 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將作業限制為暫存器的索引陣列，亦即 subregister。

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

要限制為 subregister 的作業。


### <a name="idxs--int"></a>idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的陣列，表示將限制作業的量子位。



## <a name="output--qubit--unit"></a>輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 



## <a name="see-also"></a>另請參閱

- [Canon. RestrictedToSubregisterA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [Canon. RestrictedToSubregisterC](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [Canon. RestrictedToSubregisterCA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)