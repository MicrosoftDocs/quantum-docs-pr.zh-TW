---
title: 分子積分 Symmetries
description: 瞭解如何使用 Q# OrbitalIntegral 類型來列舉分子 symmetries。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2622285fd95eddf0d70402ae99dd18bfd8c38087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858829"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="79fdb-103">分子積分 Symmetries</span><span class="sxs-lookup"><span data-stu-id="79fdb-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="79fdb-104">Coulomb Hamiltonian 的固有對稱（即 [電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中所提供的 Hamiltonian），其說明電子與彼此互動和 nuclei 的互動，會導致許多可能被利用的 symmetries 來壓縮 Hamiltonian 中的詞彙。</span><span class="sxs-lookup"><span data-stu-id="79fdb-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="79fdb-105">一般情況下，如果沒有進一步假設基礎函式 $ \ psi_j $，則只有該 \begin{equation} h_ {pqrs} = h_ {qpsr}，\tag{★} \label{eq： hpqrs} \end{equation} 可以立即從 [適用于電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels) 中的積分看到，如果 $p、q $ 和 $r，s $ 是從反 commutation 交換。</span><span class="sxs-lookup"><span data-stu-id="79fdb-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="79fdb-106">如果我們假設 orbitals 是實值的 (，因為它們是針對高斯 orbital 基底) 那麼，我們會進一步讓 \begin{equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} spqr {h_} qrsp： hpqrsreal} \end{equation} 假設有這類假設，我們可以使用上述 symmetries 來減少儲存 Hamiltonian 矩陣元素所需的資料，其因素為 $8 $;雖然這樣做可讓您以一致的方式匯入資料，而稍微更具挑戰性。</span><span class="sxs-lookup"><span data-stu-id="79fdb-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="79fdb-107">幸運的是，Hamiltonian 模擬程式庫有一些副程式，可用來從 [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) 或直接從 [NWChem](http://www.nwchem-sw.org/index.php/Main_Page)匯入整數檔。</span><span class="sxs-lookup"><span data-stu-id="79fdb-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="79fdb-108">分子 orbital 的整數 (亦即 $h \_ {pq} $ 和 $h \_ {pqrs} $ 詞彙) 例如這些會使用 `OrbitalIntegral` 類型來表示，這會提供許多實用的函式來表示此對稱。</span><span class="sxs-lookup"><span data-stu-id="79fdb-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
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

<span data-ttu-id="79fdb-109">除了列舉所有以數位相同的 orbital 整數之外，可能產生的 Hamiltonian 中包含的所有微調 orbital 索引清單，如下所示 `OrbitalIntegral` 。</span><span class="sxs-lookup"><span data-stu-id="79fdb-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="79fdb-110">從分子的積分來建立 Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="79fdb-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="79fdb-111">`FermionTerm`與每個 orbital 整數對應的所有詞彙可能會自動加入，而不是藉由新增來建立 Fermionic Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="79fdb-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="79fdb-112">例如，下列程式碼會自動列舉所有的 permutational symmetries，並以標準順序排序詞彙：</span><span class="sxs-lookup"><span data-stu-id="79fdb-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
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
