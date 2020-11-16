---
title: 取得能階估計值
description: '逐步解說 Q# 可評估分子 hydrogen 能源等級值的程式範例。'
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 81fba0c52c854d61f9143659795fb4d3c3cee8b9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691529"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="d734c-103">取得能階估計值</span><span class="sxs-lookup"><span data-stu-id="d734c-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="d734c-104">估計能源等級的價值是量子化學的其中一個主要應用程式。</span><span class="sxs-lookup"><span data-stu-id="d734c-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="d734c-105">本文概述如何針對分子 hydrogen 的標準範例來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="d734c-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="d734c-106">本節中所參考的範例位於 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) 化學範例存放庫中。</span><span class="sxs-lookup"><span data-stu-id="d734c-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="d734c-107">示範的更多視覺效果範例會繪製輸出 [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) 。</span><span class="sxs-lookup"><span data-stu-id="d734c-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="d734c-108">估計分子 hydrogen 的能源價值</span><span class="sxs-lookup"><span data-stu-id="d734c-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="d734c-109">第一個步驟是建立代表分子 hydrogen 的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="d734c-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="d734c-110">雖然您可以使用 NWChem 工具來進行建立，但為了簡潔起見，此範例會手動新增 Hamiltonian 詞彙。</span><span class="sxs-lookup"><span data-stu-id="d734c-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="d734c-111">模擬 Hamiltonian 需要將 fermion 運算子轉換成量子位運算子。</span><span class="sxs-lookup"><span data-stu-id="d734c-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="d734c-112">這項轉換會透過 Jordan-Wigner 編碼來執行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d734c-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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

<span data-ttu-id="d734c-113">接著， `qSharpData` 將代表 Hamiltonian 的傳遞至函式 `TrotterStepOracle` 。</span><span class="sxs-lookup"><span data-stu-id="d734c-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="d734c-114">`TrotterStepOracle` 傳回與 Hamiltonian 即時演進接近的量子運算。</span><span class="sxs-lookup"><span data-stu-id="d734c-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="d734c-115">如需詳細資訊，請參閱 [模擬 Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)。</span><span class="sxs-lookup"><span data-stu-id="d734c-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="d734c-116">此時，您可以使用標準程式庫的 [階段估計演算法](xref:microsoft.quantum.libraries.characterization) ，利用先前的模擬來學習地面狀態能源。</span><span class="sxs-lookup"><span data-stu-id="d734c-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="d734c-117">這需要針對量子地面狀態準備良好的近似值。</span><span class="sxs-lookup"><span data-stu-id="d734c-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="d734c-118">這類近似值的建議會在架構中提供 [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 。</span><span class="sxs-lookup"><span data-stu-id="d734c-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="d734c-119">但是，如果不存在這些建議，則預設方法會將數個 `hamiltonian.NElectrons` 電子新增至大量，以將對角單一 electron 的詞彙氫化降至最低。</span><span class="sxs-lookup"><span data-stu-id="d734c-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="d734c-120">階段估計函式和作業會以 DocFX 標記法的形式提供于 [量子](xref:Microsoft.Quantum.Characterization) 命名空間中。</span><span class="sxs-lookup"><span data-stu-id="d734c-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization) namespace.</span></span>

<span data-ttu-id="d734c-121">下列程式碼片段顯示化學模擬程式庫的即時演進輸出如何與量子階段估計整合。</span><span class="sxs-lookup"><span data-stu-id="d734c-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="d734c-122">您現在可以 Q# 從主機程式叫用程式碼。</span><span class="sxs-lookup"><span data-stu-id="d734c-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="d734c-123">下列 c # 程式碼會建立完整狀態模擬器，並執行 `GetEnergyByTrotterization` 以取得地面狀態的能源。</span><span class="sxs-lookup"><span data-stu-id="d734c-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="d734c-124">作業會傳回兩個參數：</span><span class="sxs-lookup"><span data-stu-id="d734c-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="d734c-125">`energyEst` 是地面狀態能源的估計值，且應 `-1.137` 平均接近。</span><span class="sxs-lookup"><span data-stu-id="d734c-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="d734c-126">`phaseEst` 是階段估計演算法所傳回的原始階段。</span><span class="sxs-lookup"><span data-stu-id="d734c-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="d734c-127">這有助於在因值太大而發生別名時進行診斷 `trotterStep` 。</span><span class="sxs-lookup"><span data-stu-id="d734c-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
