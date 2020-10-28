---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699159"
---
# <a name="applytopartition-operation"></a>ApplyToPartition 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將一組作業套用至註冊的指定分割區分成兩個部分。

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubitqubit--unit"></a>op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 

要套用至指定資料分割的作業配對。


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)

要放入資料分割第一個部分的目標量子位數目。
其餘的量子位會組成資料分割的第二個部分。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

由指定的兩項作業進行分割並操作的量子位登錄。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [Canon. ApplyToPartitionA](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Canon. ApplyToPartitionC](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Canon. ApplyToPartitionCA](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)