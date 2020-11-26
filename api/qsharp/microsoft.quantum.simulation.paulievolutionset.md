---
uid: Microsoft.Quantum.Simulation.PauliEvolutionSet
title: PauliEvolutionSet 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: fb53b90b6ab5ce1003f66b68a8c2ad8b3631f627
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230340"
---
# <a name="paulievolutionset-function"></a>PauliEvolutionSet 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。

```qsharp
function PauliEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>輸出： [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

將 `EvolutionSet` `GeneratorIndex` Pauli 基礎對應至 ' EvolutionUnitary 的。

## <a name="remarks"></a>備註

這是由的部分應用程式所取得 <xref:microsoft.quantum.simulation.paulievolutionfunction> 。