---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: 28ab492573b67e4aa42392e4ee499596b9c0225f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700962"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="3f8ea-102">EvolutionUnitary 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="3f8ea-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="3f8ea-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3f8ea-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3f8ea-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f8ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f8ea-105">表示單一時間演進運算子。</span><span class="sxs-lookup"><span data-stu-id="3f8ea-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="3f8ea-106">第一個參數是時間演進的持續時間，而第二個參數是由單一的量子位暫存器所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3f8ea-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

