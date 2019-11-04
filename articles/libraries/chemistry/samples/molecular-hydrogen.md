---
title: 取得能源等級估計 |Microsoft Docs
description: 取得能源等級估計檔
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
ms.openlocfilehash: 32f18ea479a2c65eee2b0e16788dc9f0fabd5372
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185540"
---
## <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="58b66-103">取得能源等級估計</span><span class="sxs-lookup"><span data-stu-id="58b66-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="58b66-104">估計能源等級的值是量子化學的其中一個主要應用程式。</span><span class="sxs-lookup"><span data-stu-id="58b66-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="58b66-105">在這裡，我們將概述如何執行這項作業，以瞭解分子 Hydrogen 的標準範例。</span><span class="sxs-lookup"><span data-stu-id="58b66-105">Here, we outline how this may be performed for the canonical example of molecular Hydrogen.</span></span> <span data-ttu-id="58b66-106">本節中所參考的範例 `MolecularHydrogen` 在化學範例存放庫中。</span><span class="sxs-lookup"><span data-stu-id="58b66-106">The sample referenced in this section is `MolecularHydrogen` in the chemistry samples repository.</span></span> <span data-ttu-id="58b66-107">繪製輸出的更多視覺效果範例是 `MolecularHydrogenGUI` 示範。</span><span class="sxs-lookup"><span data-stu-id="58b66-107">A more visual example that plots the output is the `MolecularHydrogenGUI` demo.</span></span>

<span data-ttu-id="58b66-108">我們的第一個步驟是建立代表分子 Hydrogen 的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="58b66-108">Our first step is to construct the Hamiltonian representing molecular Hydrogen.</span></span> <span data-ttu-id="58b66-109">雖然這可以透過 NWChem 工具來建立，但我們會在此範例中手動新增 Hamiltonian 詞彙以求簡潔。</span><span class="sxs-lookup"><span data-stu-id="58b66-109">Though this can be constructed through the NWChem tool, we manually add Hamiltonian terms for brevity in this sample.</span></span>

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

    // We initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="58b66-110">模擬 Hamiltonian 需要我們將 fermion 運算子轉換成 qubit 運算子。</span><span class="sxs-lookup"><span data-stu-id="58b66-110">Simulating the Hamiltonian requires us to convert the fermion operators to qubit operators.</span></span> <span data-ttu-id="58b66-111">這種轉換是透過 Wigner 編碼方式執行，如下所示。</span><span class="sxs-lookup"><span data-stu-id="58b66-111">This conversion is performed through the Jordan-Wigner encoding as follows.</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // We also need to create an input quantum state to this Hamiltonian.
    // Let us use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="58b66-112">我們現在會將代表 Hamiltonian 的 `qSharpData` 傳遞至[模擬 Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms)的 `TrotterStepOracle` 函數。</span><span class="sxs-lookup"><span data-stu-id="58b66-112">We now pass the `qSharpData` representing the Hamiltonian to the `TrotterStepOracle` function in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms).</span></span> <span data-ttu-id="58b66-113">`TrotterStepOracle` 傳回的量子作業，會接近 Hamiltonian 的即時進化。</span><span class="sxs-lookup"><span data-stu-id="58b66-113">`TrotterStepOracle` returns a quantum operation that approximates the real time-evolution of the Hamiltonian.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="58b66-114">我們現在可以使用標準程式庫的階段估計演算法，利用上述模擬來學習地面狀態能源。</span><span class="sxs-lookup"><span data-stu-id="58b66-114">We can now use the standard library's phase estimation algorithms to learn the ground state energy using the above simulation.</span></span> <span data-ttu-id="58b66-115">這需要準備良好的量子地面狀態近似值。</span><span class="sxs-lookup"><span data-stu-id="58b66-115">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="58b66-116">`Broombridge` 的架構中會提供這類近似值的建議，但這些建議不存在，預設方法會將一些 `hamiltonian.NElectrons` electrons 新增至大量，以將對角線 electron 詞彙 energies 降到最低。</span><span class="sxs-lookup"><span data-stu-id="58b66-116">Suggestions for such approximations are provided in the `Broombridge` schema, but absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to  greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="58b66-117">階段估計函式和作業位於[Microsoft 量子命名空間](xref:microsoft.quantum.characterization in DocFX notation)中。</span><span class="sxs-lookup"><span data-stu-id="58b66-117">The phase estimation functions and operations are located in the [Microsoft.Quantum.Characterization namespace](xref:microsoft.quantum.characterization in DocFX notation).</span></span>

<span data-ttu-id="58b66-118">下列程式碼片段顯示化學模擬程式庫的即時進化輸出如何與量子階段估計整合。</span><span class="sxs-lookup"><span data-stu-id="58b66-118">The following snippet shows how the real time-evolution output by the chemistry simulation library may be integrated with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined below.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // We use the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // We obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // We return both the estimated phase, and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="58b66-119">現在可以從驅動程式叫用此 Q # 代碼。</span><span class="sxs-lookup"><span data-stu-id="58b66-119">This Q# code may now be invoke from the driver program.</span></span> <span data-ttu-id="58b66-120">在下列中，我們會建立一個完整狀態的模擬器，並執行 `GetEnergyByTrotterization` 以取得地面狀態的能源。</span><span class="sxs-lookup"><span data-stu-id="58b66-120">In the following, we create a full-state simulator and run `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // We specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // We specify the step-size of the simulated time-evolution. This needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, let us run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular Hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="58b66-121">請注意，會傳回兩個參數。</span><span class="sxs-lookup"><span data-stu-id="58b66-121">Note that two parameters are returned.</span></span> <span data-ttu-id="58b66-122">`energyEst` 是基礎州能源的預估，而且應該平均地 `-1.137`。</span><span class="sxs-lookup"><span data-stu-id="58b66-122">`energyEst` is the estimate of the ground state energy, and should be around `-1.137` on average.</span></span> <span data-ttu-id="58b66-123">`phaseEst` 是階段估計演算法所傳回的原始階段，當因為太大 `trotterStep` 而發生別名時，會很有用。</span><span class="sxs-lookup"><span data-stu-id="58b66-123">`phaseEst` is the raw phase returned by the phase estimation algorithm, and is useful to diagnose when aliasing occurs due to a `trotterStep` that is too large.</span></span>
