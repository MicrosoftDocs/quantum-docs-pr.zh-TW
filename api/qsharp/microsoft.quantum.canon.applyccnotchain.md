---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699341"
---
# <a name="applyccnotchain-operation"></a>ApplyCCNOTChain 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


會在兩個量子位暫存器的對應位上執行控制的 CCNOT 閘道，其會在其中一個暫存器的下一個量子位上採取行動。
從兩個暫存器中位置0的量子位開始，在兩個登錄中都是控制項，CCNOT 會套用至目標暫存器位置1的量子位，然後由位置1上的量子位控制，在目標暫存器中的位置2的量子位上執行，依此類推，以目標量子位上的動作結束 `Length(nQubits)-1` 。

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位暫存器，僅供控制項使用。


### <a name="targets--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

量子位暫存器，用於控制項和做為目標。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

目標量子位註冊必須有一個以上的量子位。