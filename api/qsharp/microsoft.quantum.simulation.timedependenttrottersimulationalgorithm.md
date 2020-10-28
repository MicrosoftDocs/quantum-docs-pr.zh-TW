---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699588"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="7d17a-102">TimeDependentTrotterSimulationAlgorithm 函式</span><span class="sxs-lookup"><span data-stu-id="7d17a-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="7d17a-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7d17a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7d17a-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7d17a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7d17a-105">`TimeDependentSimulationAlgorithm` 使用 Trotter – Suzuki 分解的函式，以接近可解決時間相依 Schrodinger 方程式的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="7d17a-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="7d17a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7d17a-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="7d17a-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7d17a-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7d17a-108">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="7d17a-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="7d17a-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d17a-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d17a-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="7d17a-110">Order of Trotter integrator.</span></span> <span data-ttu-id="7d17a-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="7d17a-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="7d17a-112">輸出： [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="7d17a-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="7d17a-113">`TimeDependentSimulationAlgorithm` 型別。</span><span class="sxs-lookup"><span data-stu-id="7d17a-113">A `TimeDependentSimulationAlgorithm` type.</span></span>