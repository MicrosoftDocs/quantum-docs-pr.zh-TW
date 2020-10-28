---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: TrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701106"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="2e422-102">TrotterSimulationAlgorithmImpl 操作</span><span class="sxs-lookup"><span data-stu-id="2e422-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="2e422-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2e422-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2e422-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e422-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e422-105">重複呼叫以 `TrotterStep` 接近時間演進運算子 exp ( _-iHt_ ) 。</span><span class="sxs-lookup"><span data-stu-id="2e422-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2e422-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2e422-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="2e422-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e422-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e422-108">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="2e422-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="2e422-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e422-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e422-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="2e422-110">Order of Trotter integrator.</span></span> <span data-ttu-id="2e422-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="2e422-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="2e422-112">maxTime： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e422-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e422-113">模擬 $t 的總持續時間。</span><span class="sxs-lookup"><span data-stu-id="2e422-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="2e422-114">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="2e422-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="2e422-115">要模擬之系統的完整描述。</span><span class="sxs-lookup"><span data-stu-id="2e422-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2e422-116">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2e422-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2e422-117">量子位由模擬處理。</span><span class="sxs-lookup"><span data-stu-id="2e422-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e422-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e422-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

