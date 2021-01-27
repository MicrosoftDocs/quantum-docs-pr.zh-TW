---
uid: Microsoft.Quantum.Simulation.EvolutionSchedule
title: EvolutionSchedule 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionSchedule
qsharp.summary: >-
  Represents a time-dependent dynamical generator.

  The `Double` parameter is a schedule in $[0, 1]$.
ms.openlocfilehash: 345374fb8105f0f892eaef3bd2da0f0fa239c065
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814256"
---
# <a name="evolutionschedule-user-defined-type"></a><span data-ttu-id="94f0d-102">EvolutionSchedule 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="94f0d-102">EvolutionSchedule user defined type</span></span>

<span data-ttu-id="94f0d-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="94f0d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="94f0d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94f0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94f0d-105">代表時間相依的 dynamical 產生器。</span><span class="sxs-lookup"><span data-stu-id="94f0d-105">Represents a time-dependent dynamical generator.</span></span>

<span data-ttu-id="94f0d-106">`Double`參數是 $ [0，1] $ 中的排程。</span><span class="sxs-lookup"><span data-stu-id="94f0d-106">The `Double` parameter is a schedule in $[0, 1]$.</span></span>

```qsharp

newtype EvolutionSchedule = (Microsoft.Quantum.Simulation.EvolutionSet, (Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

