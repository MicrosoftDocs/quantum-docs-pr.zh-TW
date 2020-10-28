---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d9f0d17c091ae771702e4047d17e1769d6bb294
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700187"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a>_JWOptimizedPQandPQQRTerm 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

包： [](https://nuget.org/packages/)


依所述的 PQ 或 PQQR 詞彙套用時間演進 `GeneratorIndex` 。

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="term--generatorindex"></a>詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` 代表 PQ 或 PQQr 詞彙。


### <a name="stepsize--double"></a>stepSize： [Double](xref:microsoft.quantum.lang-ref.double)

時間演進的持續時間。


### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian 的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

