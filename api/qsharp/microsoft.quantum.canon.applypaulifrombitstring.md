---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699254"
---
# <a name="applypaulifrombitstring-operation"></a>ApplyPauliFromBitString 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


如果布林值陣列的對應位符合指定的輸入，則在陣列中的每個量子位上套用 Pauli 運算子。

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要套用至 `qubits[idx]` where 的 Pauli 運算子 `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果位為此值，則套用 Pauli


### <a name="bits--bool"></a>位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

布林值暫存器，指定應操作的對應量子位 `qubits`


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要選擇性地套用指定 Pauli 操作員的量子暫存器



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

布林陣列和量子暫存器的長度必須相等。