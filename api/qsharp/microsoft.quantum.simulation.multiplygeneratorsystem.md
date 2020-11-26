---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229149"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="2507a-102">MultiplyGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="2507a-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="2507a-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2507a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2507a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2507a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2507a-105">將中所有詞彙的係數相乘 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="2507a-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="2507a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2507a-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="2507a-107">乘數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2507a-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2507a-108">係數上的乘數。</span><span class="sxs-lookup"><span data-stu-id="2507a-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="2507a-109">generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2507a-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="2507a-110">要相乘的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="2507a-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="2507a-111">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="2507a-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="2507a-112">， `GeneratorSystem` 代表係數較大的系統 `multiplier` 。</span><span class="sxs-lookup"><span data-stu-id="2507a-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="2507a-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2507a-113">See Also</span></span>

- [<span data-ttu-id="2507a-114">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="2507a-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)