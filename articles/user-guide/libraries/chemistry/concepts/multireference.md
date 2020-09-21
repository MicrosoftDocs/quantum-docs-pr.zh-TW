---
title: 關聯波函數
description: 瞭解如何使用 Microsoft 量子化學程式庫，在波函數中進行動態和非動態的相互關聯。
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 420fc8e108852f6548e2147693e089f5ce970aa9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835480"
---
# <a name="correlated-wavefunctions"></a>關聯波函數

針對許多系統（特別是均衡幾何附近的部分）， [hf – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) 理論會透過單一行列式的參考狀態，提供分子屬性的相關描述。 不過，為了達到量化的精確度，您也必須考慮相互關聯效果。 

在此內容中，請務必在動態和非動態相互關聯之間 dinstinguish。
Dynamical 相互關聯是由電子的傾向造成，例如因為 interelectronic repulsion 而產生的。 您可以考慮從參考狀態中 excitations 電子，來模型化此效果。 當 wavefunction 由第零個順序的兩個或多個設定所組成時，即使只是為了達到系統的定性說明，也會發生非動態關聯性。
這會迭加強硬，而且是 multireference wavefunction 的範例。

化學程式庫提供一種方式，可將 multireference 問題的第零個順序 wavefunction 指定為強硬迭加。 這種方法（稱為「稀疏 multireference 波函數）在只有少陣列件足以指定迭加時有效。 此程式庫也會提供方法，以透過一般化的單一結合叢集 ansatz，在單一行列式參考之上包含動態關聯。 此外，它也會在量子電腦上建立產生這些狀態的量子線路。 這些狀態可以在 [Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中指定，而且我們也提供透過化學程式庫以手動方式指定這些狀態的功能。

## <a name="sparse-multi-reference-wavefunction"></a>稀疏多重參考 wavefunction
多重參考狀態 $ \ket{\ psi_ {\rm {MCSCF}}} $ 可以明確地指定為 $N $-electron Slater determininants 的線性組合。
\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1，i_2，\cdots，i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots {0} 。
\end{align} 例如，state $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0.2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ 可在化學程式庫中指定，如下所示。
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
只有在需要指定一些元件時，迭加元件的明確表示才有效。 當需要許多元件才能精確地捕捉預期狀態時，應該避免使用此標記法。 這種情況的原因是量子線路的閘道成本，可在量子電腦上備妥此狀態（最少以迭加元件的數目為線性調整），最多可使用迭加 amplitudes 的單一度量來進行 quadratically。

## <a name="unitary-coupled-cluster-wavefunction"></a>單一耦合-叢集 wavefunction
您也可以使用 chemistery 程式庫，指定單一的結合叢集 wavefunction $ \ket{\ psi_ {\rm {UCC}}} $。 在此情況下，我們有一個行列式的參考狀態，例如 $ \ket{\ psi_ {\rm{SCF}}} $。 然後，系統會透過可在參考狀態上執行的單一運算子，指定 implicity 單一結合叢集 wavefunction 的元件。
這個單一運算子通常會寫成 $e ^ {T-T ^ \dagger} $，其中 $T-T ^ \dagger $ 是反 Hermitian 叢集運算子。 因此，\begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}。
\end{align}

將叢集運算子 $T = T_1 + T_2 + \cdots $ 分成幾個部分也是很常見的情況，其中每個部分 $T _j $ 包含 $j $ body 詞彙。 在一般化的結合叢集理論中， (單一) 的單一主體叢集運算子格式為 \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q，\end{align}

和雙主體叢集運算子 (雙精度浮點數) 的格式為 \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {rs} a ^ \ dagger_p ^ \ dagger_q a_r a_s。
\end{align}

較高順序的詞彙 (三合一、時等 ) 是可行的，但目前化學程式庫並不支援。

例如，讓 $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $，並讓 $T = 0.123 a ^ \ dagger_0 a_1 + 0.456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0.789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $。 然後，此狀態會在化學程式庫中具現化，如下所示。
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

您可以改為明確地指定索引，而不是使用整數索引來進行微調 convervation `SpinOrbital` 。 例如，let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1，\uparrow} ^ \ dagger_ {2，\downarrow}\ket {0} $，並讓 $T = 0.123 a ^ \ dagger_ {0，\uparrow} a_ {1，\uparrow} + 0.456 a ^ \ dagger_ {0，\uparrow} a ^ \ dagger_ {3，\downarrow} a_ {1，\uparrow} a_ {2，\downarrow}-0.789 a ^ \ dagger_ {3，\uparrow} a ^ \ dagger_ {2，\uparrow} a_ {1，\uparrow} a_ {0，\uparrow} $ 為旋轉 convserving。 然後，此狀態會在化學程式庫中具現化，如下所示。
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

我們也提供了一個便利的函式，它會列舉 annihilate 只佔用 orbitals 和激發為僅限未佔用之旋轉 orbitals 的所有微調對話叢集運算子。
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
