---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 7cb18e161dce3a52d7c9a0bf6a45d4818db2b849
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192463"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="d3780-102">SumGeneratorSystems 函式</span><span class="sxs-lookup"><span data-stu-id="d3780-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="d3780-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d3780-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d3780-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3780-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3780-105">新增多個 `GeneratorSystem` 來建立新的 GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="d3780-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="d3780-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d3780-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="d3780-107">generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="d3780-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="d3780-108">類型為 `GeneratorSystem[]` 的陣列。</span><span class="sxs-lookup"><span data-stu-id="d3780-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="d3780-109">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="d3780-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="d3780-110">`GeneratorSystem`代表系統的，這是輸入產生器系統的總和。</span><span class="sxs-lookup"><span data-stu-id="d3780-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3780-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d3780-111">See Also</span></span>

- [<span data-ttu-id="d3780-112">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="d3780-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)