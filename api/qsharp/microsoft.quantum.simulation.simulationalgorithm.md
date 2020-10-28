---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: SimulationAlgorithm 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: 9127a936bbf7a212e712645eabdf49fefc7a97d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701166"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="35cf8-102">SimulationAlgorithm 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="35cf8-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="35cf8-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="35cf8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="35cf8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35cf8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35cf8-105">表示與時間無關的模擬演算法。</span><span class="sxs-lookup"><span data-stu-id="35cf8-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="35cf8-106">與時間無關的模擬技巧可將 <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="35cf8-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="35cf8-107">針對某個時間間隔的單一時間演進。</span><span class="sxs-lookup"><span data-stu-id="35cf8-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

