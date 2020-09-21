---
title: 分子積分 Symmetries
description: 瞭解如何使用 Q# OrbitalIntegral 類型來列舉分子 symmetries。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ebb8e9bda06967d3cfa002a7d074933d9135ada
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833816"
---
# <a name="symmetries-of-molecular-integrals"></a>分子積分 Symmetries

Coulomb Hamiltonian 的固有對稱（即 [電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中所提供的 Hamiltonian），其說明電子與彼此互動和 nuclei 的互動，會導致許多可能被利用的 symmetries 來壓縮 Hamiltonian 中的詞彙。
一般情況下，如果沒有進一步假設基礎函式 $ \ psi_j $，則只有該 \begin{equation} h_ {pqrs} = h_ {qpsr}，\tag{★} \label{eq： hpqrs} \end{equation} 可以立即從 [適用于電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels) 中的積分看到，如果 $p、q $ 和 $r，s $ 是從反 commutation 交換。

如果我們假設 orbitals 是實值的 (，因為它們是針對高斯 orbital 基底) 那麼，我們會進一步讓 \begin{equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} spqr {h_} qrsp： hpqrsreal} \end{equation} 假設有這類假設，我們可以使用上述 symmetries 來減少儲存 Hamiltonian 矩陣元素所需的資料，其因素為 $8 $;雖然這樣做可讓您以一致的方式匯入資料，而稍微更具挑戰性。
幸運的是，Hamiltonian 模擬程式庫有一些副程式，可用來從 [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) 或直接從 [NWChem](http://www.nwchem-sw.org/index.php/Main_Page)匯入整數檔。

分子 orbital 的整數 (亦即 $h \_ {pq} $ 和 $h \_ {pqrs} $ 詞彙) 例如這些會使用 `OrbitalIntegral` 類型來表示，這會提供許多實用的函式來表示此對稱。
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

除了列舉所有以數位相同的 orbital 整數之外，可能產生的 Hamiltonian 中包含的所有微調 orbital 索引清單，如下所示 `OrbitalIntegral` 。
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>從分子的積分來建立 Fermionic Hamiltonian

`FermionTerm`與每個 orbital 整數對應的所有詞彙可能會自動加入，而不是藉由新增來建立 Fermionic Hamiltonian。
例如，下列程式碼會自動列舉所有的 permutational symmetries，並以標準順序排序詞彙： 
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
