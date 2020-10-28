---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700374"
---
# <a name="_jwoptimizedfermionevolution-operation"></a>_JWOptimizedFermionEvolution 操作

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

包： [](https://nuget.org/packages/)


將 dynamical 產生器表示為一組 simulatable 閘道，並以 JWOptimized 為基礎進行擴充。

如需詳細資料，請參閱 Dynamical 產生器 [模型](../libraries/data-structures#dynamical-generator-modeling) 。

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

以 JWOptimized 為基礎的單一演進所呈現的產生器索引。


### <a name="stepsize--double"></a>stepSize： [Double](xref:microsoft.quantum.lang-ref.double)

中所參考之詞彙在時間演進期間的乘數 `generatorIndex` 。


### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

依照時間演進運算子註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

