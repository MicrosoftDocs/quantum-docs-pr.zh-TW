---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystems
title: InterpolateGeneratorSystems 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystems
qsharp.summary: Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.
ms.openlocfilehash: 9881c27577023dafff0bfc6d961877db44fec0eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697463"
---
# <a name="interpolategeneratorsystems-function"></a><span data-ttu-id="79a7c-102">InterpolateGeneratorSystems 函式</span><span class="sxs-lookup"><span data-stu-id="79a7c-102">InterpolateGeneratorSystems function</span></span>

<span data-ttu-id="79a7c-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="79a7c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="79a7c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79a7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79a7c-105">傳回， `TimeDependentGeneratorSystem` 表示兩秒之間的線性插補 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="79a7c-105">Returns a `TimeDependentGeneratorSystem` representing the linear interpolation between two `GeneratorSystem`s.</span></span>

```qsharp
function InterpolateGeneratorSystems (generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="79a7c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="79a7c-106">Input</span></span>

### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="79a7c-107">generatorSystemStart： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="79a7c-107">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="79a7c-108">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="79a7c-108">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="79a7c-109">generatorSystemEnd： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="79a7c-109">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="79a7c-110">結束 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="79a7c-110">The end `GeneratorSystem`.</span></span>



## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="79a7c-111">輸出： [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="79a7c-111">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="79a7c-112">`TimeDependentGeneratorSystem`，表示系統，其為輸入產生器系統的總和，且權數 $ (1-s) $ on `generatorSystemStart` 和權數 $s $ on `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="79a7c-112">A `TimeDependentGeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="79a7c-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="79a7c-113">See Also</span></span>

- [<span data-ttu-id="79a7c-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="79a7c-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)
- [<span data-ttu-id="79a7c-115">TimeDependentGeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="79a7c-115">Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)