---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: 3a23c14e8181eeaf1614dab6f8aa5a002364c2b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847814"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="6eede-102">TimeDependentTrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="6eede-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="6eede-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6eede-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6eede-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6eede-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6eede-105">執行多個 Trotter 步驟，以接近可解決時間相依薛丁格方程式的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="6eede-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6eede-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6eede-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="6eede-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6eede-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6eede-108">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="6eede-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="6eede-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6eede-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6eede-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="6eede-110">Order of Trotter integrator.</span></span> <span data-ttu-id="6eede-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="6eede-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="6eede-112">maxTime： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6eede-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6eede-113">模擬 $t 的總持續時間。</span><span class="sxs-lookup"><span data-stu-id="6eede-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="6eede-114">evolutionSchedule： [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="6eede-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="6eede-115">要模擬之時間相依系統的完整描述。</span><span class="sxs-lookup"><span data-stu-id="6eede-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6eede-116">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6eede-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6eede-117">量子位由模擬處理。</span><span class="sxs-lookup"><span data-stu-id="6eede-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6eede-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6eede-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

