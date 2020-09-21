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
# <a name="correlated-wavefunctions"></a><span data-ttu-id="b2c6f-103">關聯波函數</span><span class="sxs-lookup"><span data-stu-id="b2c6f-103">Correlated wavefunctions</span></span>

<span data-ttu-id="b2c6f-104">針對許多系統（特別是均衡幾何附近的部分）， [hf – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) 理論會透過單一行列式的參考狀態，提供分子屬性的相關描述。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="b2c6f-105">不過，為了達到量化的精確度，您也必須考慮相互關聯效果。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="b2c6f-106">在此內容中，請務必在動態和非動態相互關聯之間 dinstinguish。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="b2c6f-107">Dynamical 相互關聯是由電子的傾向造成，例如因為 interelectronic repulsion 而產生的。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="b2c6f-108">您可以考慮從參考狀態中 excitations 電子，來模型化此效果。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="b2c6f-109">當 wavefunction 由第零個順序的兩個或多個設定所組成時，即使只是為了達到系統的定性說明，也會發生非動態關聯性。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="b2c6f-110">這會迭加強硬，而且是 multireference wavefunction 的範例。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="b2c6f-111">化學程式庫提供一種方式，可將 multireference 問題的第零個順序 wavefunction 指定為強硬迭加。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="b2c6f-112">這種方法（稱為「稀疏 multireference 波函數）在只有少陣列件足以指定迭加時有效。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="b2c6f-113">此程式庫也會提供方法，以透過一般化的單一結合叢集 ansatz，在單一行列式參考之上包含動態關聯。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="b2c6f-114">此外，它也會在量子電腦上建立產生這些狀態的量子線路。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="b2c6f-115">這些狀態可以在 [Broombridge 架構](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)中指定，而且我們也提供透過化學程式庫以手動方式指定這些狀態的功能。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="b2c6f-116">稀疏多重參考 wavefunction</span><span class="sxs-lookup"><span data-stu-id="b2c6f-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="b2c6f-117">多重參考狀態 $ \ket{\ psi_ {\rm {MCSCF}}} $ 可以明確地指定為 $N $-electron Slater determininants 的線性組合。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="b2c6f-118">\begin{align} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1，i_2，\cdots，i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots {0} 。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="b2c6f-119">\end{align} 例如，state $ \propto (0.1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0.2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ 可在化學程式庫中指定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
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
<span data-ttu-id="b2c6f-120">只有在需要指定一些元件時，迭加元件的明確表示才有效。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="b2c6f-121">當需要許多元件才能精確地捕捉預期狀態時，應該避免使用此標記法。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="b2c6f-122">這種情況的原因是量子線路的閘道成本，可在量子電腦上備妥此狀態（最少以迭加元件的數目為線性調整），最多可使用迭加 amplitudes 的單一度量來進行 quadratically。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="b2c6f-123">單一耦合-叢集 wavefunction</span><span class="sxs-lookup"><span data-stu-id="b2c6f-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="b2c6f-124">您也可以使用 chemistery 程式庫，指定單一的結合叢集 wavefunction $ \ket{\ psi_ {\rm {UCC}}} $。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="b2c6f-125">在此情況下，我們有一個行列式的參考狀態，例如 $ \ket{\ psi_ {\rm{SCF}}} $。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="b2c6f-126">然後，系統會透過可在參考狀態上執行的單一運算子，指定 implicity 單一結合叢集 wavefunction 的元件。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="b2c6f-127">這個單一運算子通常會寫成 $e ^ {T-T ^ \dagger} $，其中 $T-T ^ \dagger $ 是反 Hermitian 叢集運算子。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="b2c6f-128">因此，\begin{align} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="b2c6f-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b2c6f-129">\end{align}</span></span>

<span data-ttu-id="b2c6f-130">將叢集運算子 $T = T_1 + T_2 + \cdots $ 分成幾個部分也是很常見的情況，其中每個部分 $T _j $ 包含 $j $ body 詞彙。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="b2c6f-131">在一般化的結合叢集理論中， (單一) 的單一主體叢集運算子格式為 \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q，\end{align}</span><span class="sxs-lookup"><span data-stu-id="b2c6f-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="b2c6f-132">和雙主體叢集運算子 (雙精度浮點數) 的格式為 \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {rs} a ^ \ dagger_p ^ \ dagger_q a_r a_s。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="b2c6f-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b2c6f-133">\end{align}</span></span>

<span data-ttu-id="b2c6f-134">較高順序的詞彙 (三合一、時等 ) 是可行的，但目前化學程式庫並不支援。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="b2c6f-135">例如，讓 $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $，並讓 $T = 0.123 a ^ \ dagger_0 a_1 + 0.456 a ^ \ dagger_0a ^ \ dagger_3 a_1 a_2-0.789 a ^ \ dagger_3a ^ \ dagger_2 a_1 a_0 $。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="b2c6f-136">然後，此狀態會在化學程式庫中具現化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-136">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="b2c6f-137">您可以改為明確地指定索引，而不是使用整數索引來進行微調 convervation `SpinOrbital` 。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="b2c6f-138">例如，let $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1，\uparrow} ^ \ dagger_ {2，\downarrow}\ket {0} $，並讓 $T = 0.123 a ^ \ dagger_ {0，\uparrow} a_ {1，\uparrow} + 0.456 a ^ \ dagger_ {0，\uparrow} a ^ \ dagger_ {3，\downarrow} a_ {1，\uparrow} a_ {2，\downarrow}-0.789 a ^ \ dagger_ {3，\uparrow} a ^ \ dagger_ {2，\uparrow} a_ {1，\uparrow} a_ {0，\uparrow} $ 為旋轉 convserving。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="b2c6f-139">然後，此狀態會在化學程式庫中具現化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-139">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="b2c6f-140">我們也提供了一個便利的函式，它會列舉 annihilate 只佔用 orbitals 和激發為僅限未佔用之旋轉 orbitals 的所有微調對話叢集運算子。</span><span class="sxs-lookup"><span data-stu-id="b2c6f-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
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
