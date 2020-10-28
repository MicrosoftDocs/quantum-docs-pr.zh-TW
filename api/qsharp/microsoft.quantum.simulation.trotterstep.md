---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701103"
---
# <a name="trotterstep-function"></a><span data-ttu-id="c304b-102">TrotterStep 函式</span><span class="sxs-lookup"><span data-stu-id="c304b-102">TrotterStep function</span></span>

<span data-ttu-id="c304b-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c304b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c304b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c304b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c304b-105">藉由 `EvolutionGenerator` 使用 Trotter – Suzuki 分解中所述的系統，來執行時間演進的單一時間。</span><span class="sxs-lookup"><span data-stu-id="c304b-105">Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.</span></span>

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c304b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c304b-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="c304b-107">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="c304b-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="c304b-108">要模擬之系統的完整描述。</span><span class="sxs-lookup"><span data-stu-id="c304b-108">A complete description of the system to be simulated.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c304b-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c304b-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c304b-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="c304b-110">Order of Trotter integrator.</span></span> <span data-ttu-id="c304b-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="c304b-111">This must be either 1 or an even number.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="c304b-112">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c304b-112">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c304b-113">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="c304b-113">Duration of simulated time-evolution in single Trotter step.</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="c304b-114">Output： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c304b-114">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c304b-115">單一作業，其近似于持續時間的單一步驟 `trotterStepSize` 。</span><span class="sxs-lookup"><span data-stu-id="c304b-115">Unitary operation that approximates a single step of time-evolution for duration `trotterStepSize`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c304b-116">備註</span><span class="sxs-lookup"><span data-stu-id="c304b-116">Remarks</span></span>

<span data-ttu-id="c304b-117">如需 Trotter – Suzuki 分解的詳細資訊，請參閱依 [時間排序的組合](/quantum/libraries/control-flow#time-ordered-composition)。</span><span class="sxs-lookup"><span data-stu-id="c304b-117">For more on the Trotter–Suzuki decomposition, see [Time-Ordered Composition](/quantum/libraries/control-flow#time-ordered-composition).</span></span>