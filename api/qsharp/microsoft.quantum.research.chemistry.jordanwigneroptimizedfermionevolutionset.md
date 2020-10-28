---
uid: Microsoft.Quantum.Research.Chemistry.JordanWignerOptimizedFermionEvolutionSet
title: JordanWignerOptimizedFermionEvolutionSet 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JordanWignerOptimizedFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: d2d916655b7538b39d5739d67dbb3fc9920cf67a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700186"
---
# <a name="jordanwigneroptimizedfermionevolutionset-function"></a>JordanWignerOptimizedFermionEvolutionSet 函式

命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。

包： [](https://nuget.org/packages/)


將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。

```qsharp
function JordanWignerOptimizedFermionEvolutionSet (parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="input"></a>輸入

### <a name="parityqubit--qubit"></a>parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)

量子位，決定時間演進的正負號。



## <a name="output--evolutionset"></a>輸出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

將 `EvolutionSet` `GeneratorIndex` JWOptimized 基礎對應至 ' EvolutionUnitary 的。