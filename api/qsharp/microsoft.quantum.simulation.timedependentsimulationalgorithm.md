---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: 9d2a1a853005495b5a9df60ac1f0dcbfbdf7637f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701218"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="4e0eb-102">TimeDependentSimulationAlgorithm 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="4e0eb-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="4e0eb-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4e0eb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4e0eb-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e0eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e0eb-105">代表時間相依的模擬演算法。</span><span class="sxs-lookup"><span data-stu-id="4e0eb-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="4e0eb-106">時間相依的模擬技巧可將 <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="4e0eb-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="4e0eb-107">針對某個時間間隔的單一時間演進。</span><span class="sxs-lookup"><span data-stu-id="4e0eb-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

