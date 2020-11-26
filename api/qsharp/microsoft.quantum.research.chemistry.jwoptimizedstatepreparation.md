---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedStatePreparation
title: JWOptimizedStatePreparation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedStatePreparation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: a2e0c24eaa1f5326f2d531b4e7e55b2c440bc795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229846"
---
# <a name="jwoptimizedstatepreparation-operation"></a>JWOptimizedStatePreparation 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學


藉由佔用微調 orbitals，來準備試用狀態的簡單狀態

```qsharp
operation JWOptimizedStatePreparation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="qubitindices--int"></a>qubitIndices： [Int](xref:microsoft.quantum.lang-ref.int)[]

電子要佔用的量子位索引。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian 的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

