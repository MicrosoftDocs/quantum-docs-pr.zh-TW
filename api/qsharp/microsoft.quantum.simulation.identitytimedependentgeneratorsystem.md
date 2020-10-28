---
uid: Microsoft.Quantum.Simulation.IdentityTimeDependentGeneratorSystem
title: IdentityTimeDependentGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.
ms.openlocfilehash: d51794aacbcf13ab567ff6be4f5d6b04581833bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700866"
---
# <a name="identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="9d892-102">IdentityTimeDependentGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="9d892-102">IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="9d892-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9d892-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9d892-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d892-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d892-105">傳回與 Hamiltonian 一致的時間相依產生器系統 `H(s) = 0` 。</span><span class="sxs-lookup"><span data-stu-id="9d892-105">Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.</span></span>

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="9d892-106">輸出： [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9d892-106">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="9d892-107">時間相依產生器系統，代表 Hamiltonian $H (s) = $0 的所有 $s $。</span><span class="sxs-lookup"><span data-stu-id="9d892-107">A time dependent generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>