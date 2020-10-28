---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699590"
---
# <a name="sumgeneratorsystems-function"></a><span data-ttu-id="286ea-102">SumGeneratorSystems 函式</span><span class="sxs-lookup"><span data-stu-id="286ea-102">SumGeneratorSystems function</span></span>

<span data-ttu-id="286ea-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="286ea-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="286ea-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="286ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="286ea-105">新增多個 `GeneratorSystem` 來建立新的 GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="286ea-105">Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.</span></span>

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="286ea-106">輸入</span><span class="sxs-lookup"><span data-stu-id="286ea-106">Input</span></span>

### <a name="generatorsystems--generatorsystem"></a><span data-ttu-id="286ea-107">generatorSystems： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span><span class="sxs-lookup"><span data-stu-id="286ea-107">generatorSystems : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]</span></span>

<span data-ttu-id="286ea-108">類型為 `GeneratorSystem[]` 的陣列。</span><span class="sxs-lookup"><span data-stu-id="286ea-108">An array of type `GeneratorSystem[]`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="286ea-109">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="286ea-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="286ea-110">`GeneratorSystem`代表系統的，這是輸入產生器系統的總和。</span><span class="sxs-lookup"><span data-stu-id="286ea-110">A `GeneratorSystem` representing a system that is the sum of the input generator systems.</span></span>

## <a name="see-also"></a><span data-ttu-id="286ea-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="286ea-111">See Also</span></span>

- [<span data-ttu-id="286ea-112">GeneratorSystem。</span><span class="sxs-lookup"><span data-stu-id="286ea-112">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)