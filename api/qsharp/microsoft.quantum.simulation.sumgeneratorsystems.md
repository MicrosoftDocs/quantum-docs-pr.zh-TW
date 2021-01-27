---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: 0e64d2b599c55c19711208670030fd01e09aff7e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851026"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="66450-102">SumGeneratorSystems 函式</span><span class="sxs-lookup"><span data-stu-id="66450-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="66450-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="66450-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="66450-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66450-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66450-105">新增多個 `GeneratorSystem` 來建立新的 GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="66450-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="66450-106">輸入</span><span class="sxs-lookup"><span data-stu-id="66450-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="66450-107">generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="66450-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="66450-108">類型為 `GeneratorSystem[]` 的陣列。</span><span class="sxs-lookup"><span data-stu-id="66450-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="66450-109">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="66450-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="66450-110">`GeneratorSystem`代表系統的，這是輸入產生器系統的總和。</span><span class="sxs-lookup"><span data-stu-id="66450-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="66450-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66450-111">See Also</span></span>

- [<span data-ttu-id="66450-112">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="66450-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)