---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 941d66a936ef1a2ac76230d14ca8437ac2a4a049
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857891"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a>JordanWignerOptimizedFermionEvolutionSet 函式

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學


將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a>輸入

### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。



## <a name="output--evolutionset"></a>輸出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

將 `EvolutionSet` `GeneratorIndex` JWOptimized 基礎對應至 ' EvolutionUnitary 的。