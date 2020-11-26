---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: ee47637996313fe1b77c76f00b08417dac956247
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230577"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="9d0c7-102">InterpolateGeneratorSystems 函式</span><span class="sxs-lookup"><span data-stu-id="9d0c7-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="9d0c7-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9d0c7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9d0c7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d0c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d0c7-105">傳回， `TimeDependentGeneratorSystem` 表示兩秒之間的線性插補 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="9d0c7-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="9d0c7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9d0c7-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="9d0c7-107">generatorSystemStart： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9d0c7-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9d0c7-108">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="9d0c7-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="9d0c7-109">generatorSystemEnd： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9d0c7-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9d0c7-110">結束 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="9d0c7-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="9d0c7-111">輸出： [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9d0c7-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="9d0c7-112">`TimeDependentGeneratorSystem`，表示系統，其為輸入產生器系統的總和，且權數 $ (1-s) $ on `generatorSystemStart` 和權數 $s $ on `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="9d0c7-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d0c7-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d0c7-113">See Also</span></span>

- [<span data-ttu-id="9d0c7-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="9d0c7-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="9d0c7-115">TimeDependentGeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="9d0c7-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)