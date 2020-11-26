---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: _JordanWignerClusterOperatorFunction 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 023ac4a6aaee8e3d0514a471c33c575b86004b15
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203818"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a>_JordanWignerClusterOperatorFunction 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


將 dynamical 產生器表示為一組 simulatable 閘道，並以 JordanWigner 為基礎進行擴充。

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>輸入

### <a name="generatorindex--generatorindex"></a>generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

要以 JordanWigner 中的單一演進表示的產生器索引。



## <a name="output--evolutionunitary"></a>輸出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

， `EvolutionUnitary` 表示由 ' generatorIndex ' 所參考之詞彙的時間演進。