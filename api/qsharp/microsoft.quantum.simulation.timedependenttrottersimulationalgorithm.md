---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: c827dd79af6f4b745adf8903ed2664d9e8255785
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858361"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a><span data-ttu-id="abe21-102">TimeDependentTrotterSimulationAlgorithm 函式</span><span class="sxs-lookup"><span data-stu-id="abe21-102">TimeDependentTrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="abe21-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="abe21-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="abe21-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abe21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abe21-105">`TimeDependentSimulationAlgorithm` 使用 Trotter – Suzuki 分解的函式，以接近可解決時間相依 Schrodinger 方程式的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="abe21-105">`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.</span></span>

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="abe21-106">輸入</span><span class="sxs-lookup"><span data-stu-id="abe21-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="abe21-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="abe21-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="abe21-108">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="abe21-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="abe21-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abe21-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abe21-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="abe21-110">Order of Trotter integrator.</span></span> <span data-ttu-id="abe21-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="abe21-111">This must be either 1 or an even number.</span></span>



## <a name="output--timedependentsimulationalgorithm"></a><span data-ttu-id="abe21-112">輸出： [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="abe21-112">Output : [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)</span></span>

<span data-ttu-id="abe21-113">`TimeDependentSimulationAlgorithm` 型別。</span><span class="sxs-lookup"><span data-stu-id="abe21-113">A `TimeDependentSimulationAlgorithm` type.</span></span>