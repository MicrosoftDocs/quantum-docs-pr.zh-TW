---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: 144a44448c9fda7a038b17ac7c49f63e8cc4dd55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699589"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a><span data-ttu-id="2924b-102">TimeDependentGeneratorSystem 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="2924b-102">TimeDependentGeneratorSystem user defined type</span></span>

<span data-ttu-id="2924b-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2924b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2924b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2924b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2924b-105">代表時間相依的 dynamical 產生器，做為函式在該時間的時間與 dynamical 產生器的值。</span><span class="sxs-lookup"><span data-stu-id="2924b-105">Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.</span></span>

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

