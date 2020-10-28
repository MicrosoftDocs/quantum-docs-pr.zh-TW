---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697499"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="72632-102">_IdentityTimeDependentGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="72632-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="72632-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="72632-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="72632-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72632-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72632-105">傳回與 Hamiltonian 一致的產生器系統 `H(s) = 0` ，其中 `s` 是 schedule 參數。</span><span class="sxs-lookup"><span data-stu-id="72632-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="72632-106">輸入</span><span class="sxs-lookup"><span data-stu-id="72632-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="72632-107">排程： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72632-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72632-108">此輸入會被忽略，而且是為了與使用者定義型別一致而定義的 <xref:microsoft.quantum.canon.timedependentgeneratorsystem> 。</span><span class="sxs-lookup"><span data-stu-id="72632-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="72632-109">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="72632-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="72632-110">代表 Hamiltonian $H (s 的產生器系統) = $0 適用于所有 $s $。</span><span class="sxs-lookup"><span data-stu-id="72632-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>