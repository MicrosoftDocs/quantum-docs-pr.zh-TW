---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: _JWOptimizedZZTerm 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700367"
---
# <a name="_jwoptimizedzzterm-operation"></a>_JWOptimizedZZTerm 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

包： [](https://nuget.org/packages/)


依所述的 ZZ 詞彙套用時間演進 `GeneratorIndex` 。

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="term--generatorindex"></a>詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` 代表 ZZ 詞彙。


### <a name="stepsize--double"></a>stepSize： [Double](xref:microsoft.quantum.lang-ref.double)

時間演進的持續時間。


### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian 的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

