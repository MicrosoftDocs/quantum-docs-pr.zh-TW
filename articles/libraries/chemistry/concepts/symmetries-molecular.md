---
title: 分子積分的 Symmetries |Microsoft Docs
description: 分子積分概念檔 Symmetries
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442390"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="bd241-103">分子積分的 Symmetries</span><span class="sxs-lookup"><span data-stu-id="bd241-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="bd241-104">Coulomb Hamiltonian 的固有對稱性，這是[電子系統的配量模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中所提供的 Hamiltonian，其中描述 electrons 與彼此互動和 nuclei，因而導致數個 symmetries利用來壓縮 Hamiltonian 中的詞彙。</span><span class="sxs-lookup"><span data-stu-id="bd241-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="bd241-105">在一般情況下，如果沒有針對基礎函數 $ \ psi_j $ 提出進一步的假設，我們只會將 \begin{equation} h_ {pqrs} = h_ {qpsr}，\tag{★} \label{eq： hpqrs} \end{equation}，這可立即從量子模型中的積分看到[電子系統](xref:microsoft.quantum.chemistry.concepts.quantummodels)注意到，如果 $p、q $ 和 $r，s $ 是從反 commutation 中互換，則其值會保持相同。</span><span class="sxs-lookup"><span data-stu-id="bd241-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="bd241-106">如果我們假設 orbitals 是實值（因為它們是針對高斯 orbital 基底），則我們會進一步 \begin{equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {spqr} = h_ {qrsp} .\tag {★} \label{eq： hpqrsreal} \end{方程式} 假設有這類假設，我們可以使用上述 symmetries 來減少儲存 Hamiltonian 的矩陣元素所需的資料（以 $8 $ 的係數表示）。雖然這樣做會讓以一致的方式匯入資料，稍微更具挑戰性。</span><span class="sxs-lookup"><span data-stu-id="bd241-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="bd241-107">幸運的是，Hamiltonian 模擬程式庫有一些副程式，可以用來從[LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)或直接從[NWChem](http://www.nwchem-sw.org/index.php/Main_Page)匯入整數檔案。</span><span class="sxs-lookup"><span data-stu-id="bd241-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="bd241-108">分子 orbital 整數（也就是 $h\_{pq} $ 和 $h\_{pqrs} $ 詞彙），例如使用 `OrbitalIntegral` 類型，這會提供一些實用的函式來表示此對稱。</span><span class="sxs-lookup"><span data-stu-id="bd241-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

<span data-ttu-id="bd241-109">除了列舉所有數值完全相同的 orbital 整數，包含在 `OrbitalIntegral` 所代表的 Hamiltonian 中的所有微調 orbital 索引清單也可能產生如下。</span><span class="sxs-lookup"><span data-stu-id="bd241-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="bd241-110">從分子的 Hamiltonians 建立 Fermionic 的</span><span class="sxs-lookup"><span data-stu-id="bd241-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="bd241-111">不是藉由加入 `FermionTerm`來建立 Fermionic Hamiltonian，而是會自動新增對應到每個 orbital 整數的所有詞彙。</span><span class="sxs-lookup"><span data-stu-id="bd241-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="bd241-112">例如，下列程式碼會自動列舉所有 permutational symmetries，並以標準順序排序詞彙：</span><span class="sxs-lookup"><span data-stu-id="bd241-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
