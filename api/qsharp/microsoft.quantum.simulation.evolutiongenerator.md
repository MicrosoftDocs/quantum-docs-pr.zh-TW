---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: 98241f77bfbd73929896bb114fad060001016a86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856092"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="cbcb8-102">EvolutionGenerator 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="cbcb8-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="cbcb8-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cbcb8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cbcb8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbcb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbcb8-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以該基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="cbcb8-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="cbcb8-106">詞彙數目的最後一個參數。</span><span class="sxs-lookup"><span data-stu-id="cbcb8-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

