---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: d4589edaadf59bbfff432bf49be2ce14fcff6ed1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208103"
---
# <a name="applytosubregister-operation"></a>ApplyToSubregister 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

要套用至 subregister 的作業。


### <a name="idxs--int"></a>idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的陣列，表示將套用作業的量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊的作用。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. ApplyToSubregisterA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [Canon. ApplyToSubregisterC](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [Canon. ApplyToSubregisterCA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)