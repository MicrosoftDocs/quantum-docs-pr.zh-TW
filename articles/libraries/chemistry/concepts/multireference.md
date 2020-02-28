---
title: 關聯波函數
description: 瞭解 wavefunctions 中使用 Microsoft 量子化學程式庫的動態和非動態相互關聯。
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904429"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="ace3a-103">關聯波函數</span><span class="sxs-lookup"><span data-stu-id="ace3a-103">Correlated wavefunctions</span></span>

<span data-ttu-id="ace3a-104">對於許多系統而言，特別是接近均衡幾何的[Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock)理論會透過單一行列式參考狀態，提供分子屬性的定性描述。</span><span class="sxs-lookup"><span data-stu-id="ace3a-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="ace3a-105">不過，若要達到量化精確度，必須同時考慮相互關聯的效果。</span><span class="sxs-lookup"><span data-stu-id="ace3a-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="ace3a-106">在此內容中，請務必在動態和非動態相互關聯之間 dinstinguish。</span><span class="sxs-lookup"><span data-stu-id="ace3a-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="ace3a-107">Dynamical 相互關聯是從 electrons 的趨勢引發，例如因為 interelectronic repulsion。</span><span class="sxs-lookup"><span data-stu-id="ace3a-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="ace3a-108">您可以從參考狀態中考慮 electrons 的 excitations，以模型化此效果。</span><span class="sxs-lookup"><span data-stu-id="ace3a-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="ace3a-109">當 wavefunction 是由兩個或多個預備順序的設定所組成時，就會發生非動態相互關聯，即使只是為了達到系統的定性描述也一樣。</span><span class="sxs-lookup"><span data-stu-id="ace3a-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="ace3a-110">這會重迭 determinants，而且是 multireference wavefunction 的範例。</span><span class="sxs-lookup"><span data-stu-id="ace3a-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="ace3a-111">化學程式庫提供一種方式，可將 multireference 問題的預備順序 wavefunction 指定為 determinants 的重迭。</span><span class="sxs-lookup"><span data-stu-id="ace3a-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="ace3a-112">這種方法稱為 sparse multireference wavefunctions，在只有少數幾個元件足以指定重迭時才有效。</span><span class="sxs-lookup"><span data-stu-id="ace3a-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="ace3a-113">此程式庫也會提供方法，透過一般化的單一結合叢集深入，在單一行列式參考之上包含動態相互關聯。</span><span class="sxs-lookup"><span data-stu-id="ace3a-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="ace3a-114">此外，它也會在量子電腦上，構造產生這些狀態的配量線路。</span><span class="sxs-lookup"><span data-stu-id="ace3a-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="ace3a-115">這些狀態可能會在[Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中指定，而且我們也提供透過化學程式庫手動指定這些狀態的功能。</span><span class="sxs-lookup"><span data-stu-id="ace3a-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="ace3a-116">稀疏多重參考 wavefunction</span><span class="sxs-lookup"><span data-stu-id="ace3a-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="ace3a-117">可以將多重參考狀態 $ \ket{\ psi_ {\rm {MCSCF}}} $ 明確指定為 $N $-electron Slater determininants 的線性組合。</span><span class="sxs-lookup"><span data-stu-id="ace3a-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="ace3a-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1，i_2，\cdots，i_N} a ^ \ dagger_ {i_1} \cdots a ^ \ dagger_ {i_2} \ket dagger_。{0}</span><span class="sxs-lookup"><span data-stu-id="ace3a-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="ace3a-119">\end{align} 例如，state $ \propto （0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0.2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5） \ket{0}$ 可以在化學程式庫中指定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ace3a-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
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
<span data-ttu-id="ace3a-120">只有在需要指定幾個元件時，重迭元件的明確表示才有效。</span><span class="sxs-lookup"><span data-stu-id="ace3a-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="ace3a-121">當需要許多元件來正確地捕捉所需的狀態時，應該避免使用這種標記法。</span><span class="sxs-lookup"><span data-stu-id="ace3a-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="ace3a-122">這是因為在量子電腦上準備此狀態的「配量」線路的閘道成本，其至少以重迭元件的數目為線性，且最多 quadratically 具有重迭 amplitudes 的一種標準。</span><span class="sxs-lookup"><span data-stu-id="ace3a-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="ace3a-123">單一結合-叢集 wavefunction</span><span class="sxs-lookup"><span data-stu-id="ace3a-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="ace3a-124">您也可以使用 chemistery 程式庫，指定單一的結合叢集 wavefunction $ \ket{\ psi_ {\rm {UCC}}} $。</span><span class="sxs-lookup"><span data-stu-id="ace3a-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="ace3a-125">在此情況下，我們有單一行列式的參考狀態，例如 $ \ket{\ psi_ {\rm{SCF}}} $。</span><span class="sxs-lookup"><span data-stu-id="ace3a-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="ace3a-126">接著，會透過以參考狀態為依據的單一運算子，指定 implicity 單一結合叢集 wavefunction 的元件。</span><span class="sxs-lookup"><span data-stu-id="ace3a-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="ace3a-127">這個單一運算子通常會寫成 $e ^ {T-T ^ \dagger} $，其中 $T-T ^ \dagger $ 是反 Hermitian 叢集運算子。</span><span class="sxs-lookup"><span data-stu-id="ace3a-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="ace3a-128">因此，\begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}。</span><span class="sxs-lookup"><span data-stu-id="ace3a-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="ace3a-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ace3a-129">\end{align}</span></span>

<span data-ttu-id="ace3a-130">將叢集運算子 $T = T_1 + T_2 + \cdots $ 分割成部分也很常見，其中每個部分 $T _j $ 包含 $j $ body 詞彙。</span><span class="sxs-lookup"><span data-stu-id="ace3a-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="ace3a-131">在一般化的結合叢集理論中，單一主體叢集運算子（單一）的格式為 \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q，\end{align}</span><span class="sxs-lookup"><span data-stu-id="ace3a-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="ace3a-132">和兩個主體叢集運算子（雙精度浮點數）的形式為 \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {rs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s。</span><span class="sxs-lookup"><span data-stu-id="ace3a-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="ace3a-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ace3a-133">\end{align}</span></span>

<span data-ttu-id="ace3a-134">較高順序的詞彙（三、時等等）是可行的，但目前不受化學程式庫支援。</span><span class="sxs-lookup"><span data-stu-id="ace3a-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="ace3a-135">例如，let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket{0}$，然後讓 $T = 0.123 a ^ \ dagger_0 a_1 + 0.456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0.789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $。</span><span class="sxs-lookup"><span data-stu-id="ace3a-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="ace3a-136">然後，此狀態會在化學程式庫中具現化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ace3a-136">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="ace3a-137">微調 convervation 可以明確地進行，改為指定 `SpinOrbital` 索引，而不是整數索引。</span><span class="sxs-lookup"><span data-stu-id="ace3a-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="ace3a-138">例如，let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1，\uparrow} a ^ \ dagger_ {2，\downarrow}\ket{0}$，然後讓 $T = 0.123 a ^ \ dagger_ {0，\uparrow} a_ {1，\uparrow} + 0.456 a ^ dagger_ {0，\uparrow} a ^ \ dagger_ {3，\downarrow} a_ {1，\uparrow} a_ {2，\downarrow}-0.789 a ^ \ dagger_ {3，\uparrow} a ^ \ dagger_ {2，\uparrow} a_ {1，\uparrow} a_ {0，\uparrow} $ 是微調 convserving。</span><span class="sxs-lookup"><span data-stu-id="ace3a-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="ace3a-139">然後，此狀態會在化學程式庫中具現化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ace3a-139">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="ace3a-140">我們也提供一個便利函式，它會列舉所有微調對話的叢集運算子，這些運算子只會 annihilate 已取用的微調 orbitals 和激發，而僅限於未佔用的微調 orbitals。</span><span class="sxs-lookup"><span data-stu-id="ace3a-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
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
