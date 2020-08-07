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
# <a name="obtaining-resource-counts"></a>取得資源計數

在傳統電腦上模擬 $n $ qubits 的成本，會以 $n $ 來以指數方式調整。 這會大幅限制我們可以使用全狀態模擬器執行的量子化學模擬大小。 對於化學的大型實例，我們可能會取得有用的資訊。 在這裡，我們將探討如何使用[追蹤](xref:microsoft.quantum.machines.qc-trace-simulator.intro)模擬器，以自動化的方式來取得模擬化學的資源成本（例如 T 閘道或 cnot-contains 閘道的數目）。 這類資訊會通知我們，當量子電腦可能夠大，足以執行這些量子化學演算法時。 如需參考，請參閱提供的 `GetGateCount` 範例。

假設我們已經有一個 `FermionHamiltonian` 實例，例如從 Broombridge 架構載入，如[從檔案載入](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)中所述。 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

取得資源估計的語法幾乎等同于在完整狀態模擬器上執行演算法。 我們只選擇不同的目的電腦。 基於資源估計的目的，它會後綴評估單一 Trotter 步驟的成本，或 Qubitization 技術所建立的量子行程。 叫用這些演算法的樣板如下所示。

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

我們現在會設定追蹤模擬器來追蹤我們感興趣的資源。 在此情況下，我們會將旗標設定為，以計算基本的量子作業 `usePrimitiveOperationsCounter` `true` 。 技術詳細資料 `throwOnUnconstraintMeasurement` 會設定為 `false` ，以避免在程式 Q# 代碼未正確判斷提示結果的機率（如果有執行）時的例外狀況。

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

我們現在會從驅動程式執行配量演算法，如下所示。

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