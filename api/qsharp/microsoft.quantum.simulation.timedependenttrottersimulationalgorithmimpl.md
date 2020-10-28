---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699586"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="1f5bd-102">TimeDependentTrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="1f5bd-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="1f5bd-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f5bd-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f5bd-105">執行多個 Trotter 步驟，以接近可解決時間相依薛丁格方程式的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1f5bd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1f5bd-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="1f5bd-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f5bd-108">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="1f5bd-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f5bd-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-110">Order of Trotter integrator.</span></span> <span data-ttu-id="1f5bd-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="1f5bd-112">maxTime： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f5bd-113">模擬 $t 的總持續時間。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="1f5bd-114">evolutionSchedule： [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="1f5bd-115">要模擬之時間相依系統的完整描述。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1f5bd-116">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f5bd-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f5bd-117">量子位由模擬處理。</span><span class="sxs-lookup"><span data-stu-id="1f5bd-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f5bd-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f5bd-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

