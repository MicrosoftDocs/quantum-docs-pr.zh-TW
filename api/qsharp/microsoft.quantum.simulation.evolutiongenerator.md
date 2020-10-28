---
uid: Microsoft.Quantum.Simulation.EvolutionGenerator
title: EvolutionGenerator 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionGenerator
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.

  Last parameter for number of terms.
ms.openlocfilehash: be741216bf99305bf5f1d149c815e98aba36aad1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697483"
---
# <a name="evolutiongenerator-user-defined-type"></a><span data-ttu-id="edf61-102">EvolutionGenerator 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="edf61-102">EvolutionGenerator user defined type</span></span>

<span data-ttu-id="edf61-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="edf61-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="edf61-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="edf61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="edf61-105">將 dynamical 產生器表示為一組 simulatable 閘道，並以該基礎進行擴充。</span><span class="sxs-lookup"><span data-stu-id="edf61-105">Represents a dynamical generator as a set of simulatable gates and an expansion in terms of that basis.</span></span>

<span data-ttu-id="edf61-106">詞彙數目的最後一個參數。</span><span class="sxs-lookup"><span data-stu-id="edf61-106">Last parameter for number of terms.</span></span>

```qsharp

newtype EvolutionGenerator = (Microsoft.Quantum.Simulation.EvolutionSet, Microsoft.Quantum.Simulation.GeneratorSystem);
```

