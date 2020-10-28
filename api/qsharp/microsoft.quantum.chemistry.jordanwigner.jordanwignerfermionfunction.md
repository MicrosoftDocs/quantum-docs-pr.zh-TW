---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 7d29393293acfc1748a1805f339951b1ff0f9b10
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698454"
---
# <a name="jordanwignerfermionfunction-function"></a>JordanWignerFermionFunction 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


將 dynamical 產生器表示為一組 simulatable 閘道，並以 JordanWigner 為基礎進行擴充。

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>輸入

### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

要以 JordanWigner 中的單一演進表示的產生器索引。



## <a name="output--evolutionunitary"></a>輸出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

， `EvolutionUnitary` 表示由 ' generatorIndex ' 所參考之詞彙的時間演進。