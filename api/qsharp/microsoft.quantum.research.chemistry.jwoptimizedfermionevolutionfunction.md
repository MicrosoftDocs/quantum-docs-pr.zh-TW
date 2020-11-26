---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: JWOptimizedFermionEvolutionFunction 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229914"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a><span data-ttu-id="23fae-102">JWOptimizedFermionEvolutionFunction 函式</span><span class="sxs-lookup"><span data-stu-id="23fae-102">JWOptimizedFermionEvolutionFunction function</span></span>

<span data-ttu-id="23fae-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="23fae-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="23fae-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="23fae-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="23fae-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以 JWOptimized 為基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="23fae-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a><span data-ttu-id="23fae-106">輸入</span><span class="sxs-lookup"><span data-stu-id="23fae-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="23fae-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="23fae-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="23fae-108">以 JWOptimized 為基礎的單一演進所呈現的產生器索引。</span><span class="sxs-lookup"><span data-stu-id="23fae-108">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="23fae-109">parityQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="23fae-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="23fae-110">量子位，決定時間演進的正負號。</span><span class="sxs-lookup"><span data-stu-id="23fae-110">Qubit that determines the sign of time-evolution.</span></span>



## <a name="output--evolutionunitary"></a><span data-ttu-id="23fae-111">輸出： [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span><span class="sxs-lookup"><span data-stu-id="23fae-111">Output : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)</span></span>

<span data-ttu-id="23fae-112">， `EvolutionUnitary` 表示由 ' generatorIndex ' 所參考之詞彙的時間演進。</span><span class="sxs-lookup"><span data-stu-id="23fae-112">An `EvolutionUnitary` representing time-evolution by the term referenced in \`generatorIndex.</span></span>