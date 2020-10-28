---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 4dc8bf4028e82d3e746779ae8c7d400dcbd3ea1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697479"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="65203-102">EvolutionSchedule 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="65203-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="65203-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="65203-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="65203-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65203-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65203-105">代表時間相依的 dynamical 產生器。</span><span class="sxs-lookup"><span data-stu-id="65203-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="65203-106">`Double`參數是 $ [0，1] $ 中的排程。</span><span class="sxs-lookup"><span data-stu-id="65203-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

