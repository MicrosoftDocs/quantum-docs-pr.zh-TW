---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: PauliEvolutionFunction 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: 9b12dc4a05c99aad319799f8c6526cd3085e6dcd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847975"
---
# <a name="paulievolutionfunction-function"></a><span data-ttu-id="0b4c1-102">PauliEvolutionFunction 函式</span><span class="sxs-lookup"><span data-stu-id="0b4c1-102">PauliEvolutionFunction function</span></span>

<span data-ttu-id="0b4c1-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0b4c1-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0b4c1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b4c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b4c1-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 Pauli 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="0b4c1-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="0b4c1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0b4c1-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="0b4c1-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0b4c1-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0b4c1-108">以 Pauli 為基礎的單一演進所呈現的產生器索引。</span><span class="sxs-lookup"><span data-stu-id="0b4c1-108">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="0b4c1-109">輸出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="0b4c1-109">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="0b4c1-110">， `EvolutionUnitary` 表示由 ' generatorIndex ' 所參考之詞彙的時間演進。</span><span class="sxs-lookup"><span data-stu-id="0b4c1-110">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>