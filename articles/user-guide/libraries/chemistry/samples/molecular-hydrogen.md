---
title: 取得能階估計值
description: 逐步解說 Q# 可評估分子 hydrogen 能源等級值的程式範例。
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: 05506f4099de754cd02d81fbd9200f2de091e37e
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759727"
---
# <a name="obtaining-energy-level-estimates"></a>取得能階估計值
估計能源等級的價值是量子化學的其中一個主要應用程式。 本文概述如何針對分子 hydrogen 的標準範例來執行此操作。 本節中所參考的範例位於 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) 化學範例存放庫中。 示範的更多視覺效果範例會繪製輸出 [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) 。

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>估計分子 hydrogen 的能源價值

第一個步驟是建立代表分子 hydrogen 的 Hamiltonian。 雖然您可以使用 NWChem 工具來進行建立，但為了簡潔起見，此範例會手動新增 Hamiltonian 詞彙。

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

模擬 Hamiltonian 需要將 fermion 運算子轉換成量子位運算子。 這項轉換會透過 Wigner 編碼來執行，如下所示：

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

接著， `qSharpData` 將代表 Hamiltonian 的傳遞至函式 `TrotterStepOracle` 。 `TrotterStepOracle` 傳回與 Hamiltonian 即時演進接近的量子運算。 如需詳細資訊，請參閱 [模擬 Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)。

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

此時，您可以使用標準程式庫的 [階段估計演算法](xref:microsoft.quantum.libraries.characterization) ，利用先前的模擬來學習地面狀態能源。 這需要針對量子地面狀態準備良好的近似值。 這類近似值的建議會在架構中提供 [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 。 但是，如果不存在這些建議，則預設方法會將數個 `hamiltonian.NElectrons` 電子新增至大量，以將對角單一 electron 的詞彙氫化降至最低。 階段估計函式和作業會以 DocFX 標記法的形式提供于 [量子](xref:microsoft.quantum.characterization) 命名空間中。

下列程式碼片段顯示化學模擬程式庫的即時演進輸出如何與量子階段估計整合。

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

您現在可以 Q# 從主機程式叫用程式碼。 下列 c # 程式碼會建立完整狀態模擬器，並執行 `GetEnergyByTrotterization` 以取得地面狀態的能源。

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

作業會傳回兩個參數： 

- `energyEst` 是地面狀態能源的估計值，且應 `-1.137` 平均接近。 
- `phaseEst` 是階段估計演算法所傳回的原始階段。 這有助於在因值太大而發生別名時進行診斷 `trotterStep` 。
