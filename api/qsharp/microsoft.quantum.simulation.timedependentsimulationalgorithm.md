---
uid: Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
title: TimeDependentSimulationAlgorithm 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentSimulationAlgorithm
qsharp.summary: >-
  Represents a time-dependent simulation algorithm.

  A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule> to unitary time-evolution for some time-interval.
ms.openlocfilehash: b495a9fd96c78872f84e8f8183105f6290f70655
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192514"
---
# <a name="timedependentsimulationalgorithm-user-defined-type"></a><span data-ttu-id="84add-102">TimeDependentSimulationAlgorithm 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="84add-102">TimeDependentSimulationAlgorithm user defined type</span></span>

<span data-ttu-id="84add-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="84add-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="84add-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84add-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84add-105">代表時間相依的模擬演算法。</span><span class="sxs-lookup"><span data-stu-id="84add-105">Represents a time-dependent simulation algorithm.</span></span>

<span data-ttu-id="84add-106">時間相依的模擬技巧可將 <xref:microsoft.quantum.simulation.evolutionschedule></span><span class="sxs-lookup"><span data-stu-id="84add-106">A time-dependent simulation technique converts an <xref:microsoft.quantum.simulation.evolutionschedule></span></span>
<span data-ttu-id="84add-107">針對某個時間間隔的單一時間演進。</span><span class="sxs-lookup"><span data-stu-id="84add-107">to unitary time-evolution for some time-interval.</span></span>

```qsharp

newtype TimeDependentSimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionSchedule, Qubit[]) => Unit is Adj + Ctl));
```

