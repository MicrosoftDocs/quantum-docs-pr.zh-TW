---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699337"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


將量子位陣列的同位計算為目標量子位。

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a>描述

如果陣列一開始是處於 state $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{target}}} $，則最終狀態是由 $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{target}}} $。

## <a name="input"></a>輸入

### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

計算同位的量子位陣列。


### <a name="targetqubit--qubit"></a>targetQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

' 量子位 ' 的同位檢查進行 xor 的最終量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

以下是相等的：

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

及

```qsharp
ApplyCNOTChain(qs);
```