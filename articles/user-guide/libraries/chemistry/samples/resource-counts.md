---
title: 取得資源計數
description: 瞭解如何使用量子追蹤模擬器取得資源估計。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: 35c16e622a390b730ad7385efcc365c212e981fe
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869319"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="9c255-103">取得資源計數</span><span class="sxs-lookup"><span data-stu-id="9c255-103">Obtaining resource counts</span></span>

<span data-ttu-id="9c255-104">在傳統電腦上模擬 $n $ qubits 的成本，會以 $n $ 來以指數方式調整。</span><span class="sxs-lookup"><span data-stu-id="9c255-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="9c255-105">這會大幅限制我們可以使用全狀態模擬器執行的量子化學模擬大小。</span><span class="sxs-lookup"><span data-stu-id="9c255-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="9c255-106">對於化學的大型實例，我們可能會取得有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="9c255-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="9c255-107">在這裡，我們將探討如何使用[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器，以自動化的方式來取得模擬化學的資源成本（例如 T 閘道或 cnot-contains 閘道的數目）。</span><span class="sxs-lookup"><span data-stu-id="9c255-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="9c255-108">這類資訊會通知我們，當量子電腦可能夠大，足以執行這些量子化學演算法時。</span><span class="sxs-lookup"><span data-stu-id="9c255-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="9c255-109">如需參考，請參閱提供的 `GetGateCount` 範例。</span><span class="sxs-lookup"><span data-stu-id="9c255-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="9c255-110">假設我們已經有一個 `FermionHamiltonian` 實例，例如從 Broombridge 架構載入，如[從檔案載入](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)中所述。</span><span class="sxs-lookup"><span data-stu-id="9c255-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="9c255-111">取得資源估計的語法幾乎等同于在完整狀態模擬器上執行演算法。</span><span class="sxs-lookup"><span data-stu-id="9c255-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="9c255-112">我們只選擇不同的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="9c255-112">We simply choose a different target machine.</span></span> <span data-ttu-id="9c255-113">基於資源估計的目的，它會後綴評估單一 Trotter 步驟的成本，或 Qubitization 技術所建立的量子行程。</span><span class="sxs-lookup"><span data-stu-id="9c255-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="9c255-114">叫用這些演算法的樣板如下所示。</span><span class="sxs-lookup"><span data-stu-id="9c255-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="9c255-115">我們現在會設定追蹤模擬器來追蹤我們感興趣的資源。</span><span class="sxs-lookup"><span data-stu-id="9c255-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="9c255-116">在此情況下，我們會將旗標設定為，以計算基本的量子作業 `usePrimitiveOperationsCounter` `true` 。</span><span class="sxs-lookup"><span data-stu-id="9c255-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="9c255-117">技術詳細資料 `throwOnUnconstraintMeasurement` 會設定為 `false` ，以避免在程式 Q# 代碼未正確判斷提示結果的機率（如果有執行）時的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="9c255-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="9c255-118">我們現在會從驅動程式執行配量演算法，如下所示。</span><span class="sxs-lookup"><span data-stu-id="9c255-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```