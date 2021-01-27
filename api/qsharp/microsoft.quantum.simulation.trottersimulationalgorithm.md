---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithm
title: TrotterSimulationAlgorithm 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithm
qsharp.summary: '`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.'
ms.openlocfilehash: b2cc9c29cbb40809540d143fcefd7cb0838bfea7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847781"
---
# <a name="trottersimulationalgorithm-function"></a><span data-ttu-id="c8989-102">TrotterSimulationAlgorithm 函式</span><span class="sxs-lookup"><span data-stu-id="c8989-102">TrotterSimulationAlgorithm function</span></span>

<span data-ttu-id="c8989-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="c8989-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="c8989-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8989-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8989-105">`SimulationAlgorithm` 使用 Trotter – Suzuki 分解來大約時間演進運算子 _exp (-iHt)_ 的函式。</span><span class="sxs-lookup"><span data-stu-id="c8989-105">`SimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate the time-evolution operator _exp(-iHt)_.</span></span>

```qsharp
function TrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.SimulationAlgorithm
```


## <a name="input"></a><span data-ttu-id="c8989-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c8989-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="c8989-107">trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c8989-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c8989-108">在單一 Trotter 步驟中，模擬時間演進的持續時間。</span><span class="sxs-lookup"><span data-stu-id="c8989-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="c8989-109">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8989-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8989-110">Trotter 整合器的順序。</span><span class="sxs-lookup"><span data-stu-id="c8989-110">Order of Trotter integrator.</span></span> <span data-ttu-id="c8989-111">此值必須是1或偶數。</span><span class="sxs-lookup"><span data-stu-id="c8989-111">This must be either 1 or an even number.</span></span>



## <a name="output--simulationalgorithm"></a><span data-ttu-id="c8989-112">輸出： [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span><span class="sxs-lookup"><span data-stu-id="c8989-112">Output : [SimulationAlgorithm](xref:Microsoft.Quantum.Simulation.SimulationAlgorithm)</span></span>

<span data-ttu-id="c8989-113">`SimulationAlgorithm` 型別。</span><span class="sxs-lookup"><span data-stu-id="c8989-113">A `SimulationAlgorithm` type.</span></span>