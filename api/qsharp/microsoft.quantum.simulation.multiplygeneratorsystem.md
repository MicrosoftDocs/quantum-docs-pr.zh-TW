---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699649"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="e5970-102">MultiplyGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="e5970-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="e5970-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e5970-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e5970-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5970-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5970-105">將中所有詞彙的係數相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="e5970-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e5970-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e5970-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="e5970-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5970-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5970-108">係數上的乘數。</span><span class="sxs-lookup"><span data-stu-id="e5970-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e5970-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e5970-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e5970-110">要相乘的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="e5970-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="e5970-111">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e5970-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e5970-112">， `GeneratorSystem` 代表係數較大的系統 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="e5970-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5970-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e5970-113">See Also</span></span>

- [<span data-ttu-id="e5970-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="e5970-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)