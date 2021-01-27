---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: d70bea8fcb5bd82ddad6dcd2b67c3eb178283bb3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857870"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a>JWOptimizedFermionEvolutionFunction 函式

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學


將 dynamical 產生器表示為一組 simulatable 閘道，並以 JWOptimized 為基礎進行擴充。

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>輸入

### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

以 JWOptimized 為基礎的單一演進所呈現的產生器索引。


### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。



## <a name="output--evolutionunitary"></a>輸出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

， `EvolutionUnitary` 表示由 ' generatorIndex ' 所參考之詞彙的時間演進。