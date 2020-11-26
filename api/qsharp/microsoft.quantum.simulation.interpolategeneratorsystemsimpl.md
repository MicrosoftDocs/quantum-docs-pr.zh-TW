---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 1ca9580ba603db8fee40e008a7ea51cb7a04d7d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229217"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="08f51-102">InterpolateGeneratorSystemsImpl 函式</span><span class="sxs-lookup"><span data-stu-id="08f51-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="08f51-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="08f51-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="08f51-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="08f51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="08f51-105">`GeneratorSystems`根據排程參數在 2 `s` 和 1 (內含) ，以線性方式在兩者之間進行插補。</span><span class="sxs-lookup"><span data-stu-id="08f51-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="08f51-106">輸入</span><span class="sxs-lookup"><span data-stu-id="08f51-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="08f51-107">排程： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="08f51-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="08f51-108">排程參數 $s \in [0，1] $。</span><span class="sxs-lookup"><span data-stu-id="08f51-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="08f51-109">generatorSystemStart： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="08f51-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="08f51-110">開始 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="08f51-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="08f51-111">generatorSystemEnd： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="08f51-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="08f51-112">結束 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="08f51-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="08f51-113">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="08f51-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="08f51-114">`GeneratorSystem`，表示系統，其為輸入產生器系統的總和，且權數 $ (1-s) $ on `generatorSystemStart` 和權數 $s $ on `generatorSystemEnd` 。</span><span class="sxs-lookup"><span data-stu-id="08f51-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="08f51-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="08f51-115">See Also</span></span>

- [<span data-ttu-id="08f51-116">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="08f51-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)