---
title: 取得能階估計值
description: 逐步解說 Q# 評估分子 hydrogen 能源等級值的範例程式。
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2df4b829a3f4946c6de6e6b80ad72a5bc192b2c
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869200"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="311e7-103">取得能階估計值</span><span class="sxs-lookup"><span data-stu-id="311e7-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="311e7-104">估計能源等級的值是量子化學的其中一個主要應用程式。</span><span class="sxs-lookup"><span data-stu-id="311e7-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="311e7-105">本文概述如何執行這項操作，以取得分子 hydrogen 的標準範例。</span><span class="sxs-lookup"><span data-stu-id="311e7-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="311e7-106">本節中所參考的範例位於 [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) 化學範例存放庫中。</span><span class="sxs-lookup"><span data-stu-id="311e7-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="311e7-107">繪製輸出的更多視覺效果範例就是 [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) 示範。</span><span class="sxs-lookup"><span data-stu-id="311e7-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="311e7-108">估計分子 hydrogen 的能源值</span><span class="sxs-lookup"><span data-stu-id="311e7-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="311e7-109">第一個步驟是建立代表分子 hydrogen 的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="311e7-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="311e7-110">雖然您可以使用 NWChem 工具來加以建立，但為了簡潔起見，此範例會手動新增 Hamiltonian 詞彙。</span><span class="sxs-lookup"><span data-stu-id="311e7-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

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

<span data-ttu-id="311e7-111">模擬 Hamiltonian 需要將 fermion 運算子轉換成 qubit 運算子。</span><span class="sxs-lookup"><span data-stu-id="311e7-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="311e7-112">這種轉換是透過 Wigner 編碼方式執行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="311e7-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

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

<span data-ttu-id="311e7-113">接下來， `qSharpData` 將代表 Hamiltonian 的傳遞至函式 `TrotterStepOracle` 。</span><span class="sxs-lookup"><span data-stu-id="311e7-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="311e7-114">`TrotterStepOracle`傳回接近 Hamiltonian 即時演進的量子運算。</span><span class="sxs-lookup"><span data-stu-id="311e7-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="311e7-115">如需詳細資訊，請參閱[模擬 Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms)。</span><span class="sxs-lookup"><span data-stu-id="311e7-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

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

<span data-ttu-id="311e7-116">此時，您可以使用標準程式庫的[階段估計演算法](xref:microsoft.quantum.libraries.characterization)，利用先前的模擬學習地面狀態能源。</span><span class="sxs-lookup"><span data-stu-id="311e7-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="311e7-117">這需要準備良好的量子地面狀態近似值。</span><span class="sxs-lookup"><span data-stu-id="311e7-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="311e7-118">架構中會提供這類近似值的建議 [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 。</span><span class="sxs-lookup"><span data-stu-id="311e7-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="311e7-119">不過，如果不存在這些建議，則預設方法會將數個 `hamiltonian.NElectrons` electrons 新增至大量，將 electron 詞彙 energies 的對角線降到最低。</span><span class="sxs-lookup"><span data-stu-id="311e7-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="311e7-120">階段估計函式和作業是以 DocFX 標記法的形式在[Microsoft 量子](xref:microsoft.quantum.characterization)命名空間中提供。</span><span class="sxs-lookup"><span data-stu-id="311e7-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:microsoft.quantum.characterization) namespace.</span></span>

<span data-ttu-id="311e7-121">下列程式碼片段顯示化學模擬程式庫的即時進化輸出如何與量子階段估計整合。</span><span class="sxs-lookup"><span data-stu-id="311e7-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

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

<span data-ttu-id="311e7-122">您現在可以叫 Q# 用主機程式中的程式碼。</span><span class="sxs-lookup"><span data-stu-id="311e7-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="311e7-123">下列 c # 程式碼會建立一個完整狀態的模擬器，並執行 `GetEnergyByTrotterization` 以取得地面狀態的能源。</span><span class="sxs-lookup"><span data-stu-id="311e7-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

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

<span data-ttu-id="311e7-124">作業會傳回兩個參數：</span><span class="sxs-lookup"><span data-stu-id="311e7-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="311e7-125">`energyEst`是地面州能源的估計值，而且應該接近 `-1.137` 平均。</span><span class="sxs-lookup"><span data-stu-id="311e7-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="311e7-126">`phaseEst`這是階段估計演算法所傳回的原始階段。</span><span class="sxs-lookup"><span data-stu-id="311e7-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="311e7-127">這很適合用於診斷因為值太大而發生的別名 `trotterStep` 。</span><span class="sxs-lookup"><span data-stu-id="311e7-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
