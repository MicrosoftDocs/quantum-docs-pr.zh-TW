---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2a2eb7ee5b437ec5fb633bfb4bdccd0cb1d253ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208018"
---
# <a name="applytosubregisterc-operation"></a>ApplyToSubregisterC 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將作業套用至暫存器的 subregister，並使用其索引的陣列所指定的量子位。
修飾詞 `C` 表示作業可控制。

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit--is-ctl"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl

要套用至 subregister 的作業。


### <a name="idxs--int"></a>idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的陣列，表示將套用作業的量子位。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊的作用。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. ApplyToSubregister](xref:Microsoft.Quantum.Canon.ApplyToSubregister)