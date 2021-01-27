---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: ea160bb9a0a8bb5106c3e37a6a16155bad71dd25
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856050"
---
# <a name="evolutionunitary-user-defined-type"></a><span data-ttu-id="7a91d-102">EvolutionUnitary 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="7a91d-102">EvolutionUnitary user defined type</span></span>

<span data-ttu-id="7a91d-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7a91d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7a91d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a91d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a91d-105">表示單一時間演進運算子。</span><span class="sxs-lookup"><span data-stu-id="7a91d-105">Represents a unitary time-evolution operator.</span></span>

<span data-ttu-id="7a91d-106">第一個參數是時間演進的持續時間，而第二個參數是由單一的量子位暫存器所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="7a91d-106">The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.</span></span>

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

