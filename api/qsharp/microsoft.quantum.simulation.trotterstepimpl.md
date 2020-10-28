---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701095"
---
# <a name="trotterstepimpl-operation"></a><span data-ttu-id="ff0ae-102">TrotterStepImpl 操作</span><span class="sxs-lookup"><span data-stu-id="ff0ae-102">TrotterStepImpl operation</span></span>

<span data-ttu-id="ff0ae-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ff0ae-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ff0ae-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff0ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff0ae-105">藉由包含在中的詞彙，實現時間演進 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="ff0ae-105">Implements time-evolution by a term contained in a `GeneratorSystem`.</span></span>

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ff0ae-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ff0ae-106">Input</span></span>

### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="ff0ae-107">evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="ff0ae-107">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="ff0ae-108">要模擬之系統的完整描述。</span><span class="sxs-lookup"><span data-stu-id="ff0ae-108">A complete description of the system to be simulated.</span></span>


### <a name="idx--int"></a><span data-ttu-id="ff0ae-109">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ff0ae-109">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ff0ae-110">描述系統中詞彙的整數索引。</span><span class="sxs-lookup"><span data-stu-id="ff0ae-110">Integer index to a term in the described system.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ff0ae-111">stepsize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff0ae-111">stepsize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff0ae-112">依詞彙編制索引之時間週期的乘數 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="ff0ae-112">Multiplier on duration of time-evolution by term indexed by `idx`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ff0ae-113">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ff0ae-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ff0ae-114">量子位由模擬處理。</span><span class="sxs-lookup"><span data-stu-id="ff0ae-114">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff0ae-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff0ae-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

