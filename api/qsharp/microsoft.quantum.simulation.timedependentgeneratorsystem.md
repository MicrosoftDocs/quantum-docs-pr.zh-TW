---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: b9b11a5850cbf9bc0b908f1644443611e91bb258
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192446"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="d9e79-102">TimeDependentGeneratorSystem 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="d9e79-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="d9e79-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="d9e79-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="d9e79-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9e79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9e79-105">代表時間相依的 dynamical 產生器，做為函式在該時間的時間與 dynamical 產生器的值。</span><span class="sxs-lookup"><span data-stu-id="d9e79-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

