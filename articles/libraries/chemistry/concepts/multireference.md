---
title: 相互關聯的 wavefunctions |Microsoft Docs
description: 量子 Dynamics 概念檔
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 0b14f373d31c5b63e313e07810daf62d9195b1d3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184027"
---
# <a name="correlated-wavefunctions"></a>相互關聯的 wavefunctions

對於許多系統而言，特別是接近均衡幾何的[Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock)理論會透過單一行列式參考狀態，提供分子屬性的定性描述。 不過，若要達到量化精確度，必須同時考慮相互關聯的效果。 

在此內容中，請務必在動態和非動態相互關聯之間 dinstinguish。
Dynamical 相互關聯是從 electrons 的趨勢引發，例如因為 interelectronic repulsion。 您可以從參考狀態中考慮 electrons 的 excitations，以模型化此效果。 當 wavefunction 是由兩個或多個預備順序的設定所組成時，就會發生非動態相互關聯，即使只是為了達到系統的定性描述也一樣。
這會重迭 determinants，而且是 multireference wavefunction 的範例。

化學程式庫提供一種方式，可將 multireference 問題的預備順序 wavefunction 指定為 determinants 的重迭。 這種方法稱為 sparse multireference wavefunctions，在只有少數幾個元件足以指定重迭時才有效。 此程式庫也會提供方法，透過一般化的單一結合叢集深入，在單一行列式參考之上包含動態相互關聯。 此外，它也會在量子電腦上，構造產生這些狀態的配量線路。 這些狀態可能會在[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中指定，而且我們也提供透過化學程式庫手動指定這些狀態的功能。

## <a name="sparse-multi-reference-wavefunction"></a>稀疏多重參考 wavefunction
可以將多重參考狀態 $ \ket{\ psi_ {\rm {MCSCF}}} $ 明確指定為 $N $-electron Slater determininants 的線性組合。
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1，i_2，\cdots，i_N} a ^ \ dagger_ {i_1} \cdots a ^ \ dagger_ {i_2} \ket dagger_。
\end{align} 例如，state $ \propto （0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0.2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5） \ket{0}$ 可以在化學程式庫中指定，如下所示。
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
只有在需要指定幾個元件時，重迭元件的明確表示才有效。 當需要許多元件來正確地捕捉所需的狀態時，應該避免使用這種標記法。 這是因為在量子電腦上準備此狀態的「配量」線路的閘道成本，其至少以重迭元件的數目為線性，且最多 quadratically 具有重迭 amplitudes 的一種標準。

## <a name="unitary-coupled-cluster-wavefunction"></a>單一結合-叢集 wavefunction
您也可以使用 chemistery 程式庫，指定單一的結合叢集 wavefunction $ \ket{\ psi_ {\rm {UCC}}} $。 在此情況下，我們有單一行列式的參考狀態，例如 $ \ket{\ psi_ {\rm{SCF}}} $。 接著，會透過以參考狀態為依據的單一運算子，指定 implicity 單一結合叢集 wavefunction 的元件。
這個單一運算子通常會寫成 $e ^ {T-T ^ \dagger} $，其中 $T-T ^ \dagger $ 是反 Hermitian 叢集運算子。 因此，\begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}。
\end{align}

將叢集運算子 $T = T_1 + T_2 + \cdots $ 分割成部分也很常見，其中每個部分 $T _j $ 包含 $j $ body 詞彙。 在一般化的結合叢集理論中，單一主體叢集運算子（單一）的格式為 \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q，\end{align}

和兩個主體叢集運算子（雙精度浮點數）的形式為 \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {rs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s。
\end{align}

較高順序的詞彙（三、時等等）是可行的，但目前不受化學程式庫支援。

例如，let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket{0}$，然後讓 $T = 0.123 a ^ \ dagger_0 a_1 + 0.456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0.789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $。 然後，此狀態會在化學程式庫中具現化，如下所示。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

微調 convervation 可以明確地進行，改為指定 `SpinOrbital` 索引，而不是整數索引。 例如，let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1，\uparrow} a ^ \ dagger_ {2，\downarrow}\ket{0}$，並讓 $T = 0.123 a ^ \ dagger_ {0，\uparrow} a_ {1，\uparrow} + 0.456 a ^ \ dagger_ {0，\uparrow} a ^ \ dagger_ {3，\downarrow} a_ {1，\uparrow} a_ {2，\download-downarrow-circled}-0.789 a ^ \ dagger_ {3，\uparrow} a ^ \ dagger_ {2，\uparrow} a_ {1，\uparrow} a_ {0，\uparrow} $ 是微調 convserving。 然後，此狀態會在化學程式庫中具現化，如下所示。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

我們也提供一個便利函式，它會列舉所有微調對話的叢集運算子，這些運算子只會 annihilate 已取用的微調 orbitals 和激發，而僅限於未佔用的微調 orbitals。
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```