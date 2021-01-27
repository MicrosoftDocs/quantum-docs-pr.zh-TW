---
uid: Microsoft.Quantum.Simulation.SimulationAlgorithm
title: SimulationAlgorithm 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SimulationAlgorithm
qsharp.summary: >-
  Represents a time-independent simulation algorithm.

  A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator> to unitary time evolution for some time-interval.
ms.openlocfilehash: d7b233ee76d79072f59ecfd001245848cb780eec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851034"
---
# <a name="simulationalgorithm-user-defined-type"></a><span data-ttu-id="c4cfc-102">SimulationAlgorithm 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="c4cfc-102">SimulationAlgorithm user defined type</span></span>

<span data-ttu-id="c4cfc-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c4cfc-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c4cfc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4cfc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4cfc-105">表示與時間無關的模擬演算法。</span><span class="sxs-lookup"><span data-stu-id="c4cfc-105">Represents a time-independent simulation algorithm.</span></span>

<span data-ttu-id="c4cfc-106">與時間無關的模擬技巧可將 <xref:microsoft.quantum.simulation.evolutiongenerator></span><span class="sxs-lookup"><span data-stu-id="c4cfc-106">A time-independent simulation technique converts an <xref:microsoft.quantum.simulation.evolutiongenerator></span></span>
<span data-ttu-id="c4cfc-107">針對某個時間間隔的單一時間演進。</span><span class="sxs-lookup"><span data-stu-id="c4cfc-107">to unitary time evolution for some time-interval.</span></span>

```qsharp

newtype SimulationAlgorithm = (((Double, Microsoft.Quantum.Simulation.EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl));
```

