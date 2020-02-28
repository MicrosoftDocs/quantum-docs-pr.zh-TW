---
title: Hartree-Fock 理論
description: 深入瞭解 Hartree – Fock 理論，這是一種簡單的方式，可為量子系統建立初始狀態。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904446"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="60c5c-103">Hartree – Fock 理論</span><span class="sxs-lookup"><span data-stu-id="60c5c-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="60c5c-104">可能是「量子化學模擬」中最重要的數量是「接地」狀態，也就是 Hamiltonian 矩陣的最小能源 eigenvector。</span><span class="sxs-lookup"><span data-stu-id="60c5c-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="60c5c-105">這是因為大部分分子驅使分子的房間溫度數量（例如，反應速率）都是由配量狀態間的免費能源差異所構成，這會描述反應路徑中步驟的開始和結束，以及房間溫度（如中繼）狀態通常是「基礎」狀態。</span><span class="sxs-lookup"><span data-stu-id="60c5c-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="60c5c-106">雖然地面狀態通常難以學習（即使是使用量子電腦），因為它是以指數的大量設定進行散發。</span><span class="sxs-lookup"><span data-stu-id="60c5c-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="60c5c-107">可以學到的數量，例如地面省電。</span><span class="sxs-lookup"><span data-stu-id="60c5c-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="60c5c-108">例如，如果 $ \ket{\psi} $ 是任何純粹的量子狀態，則 \begin{equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{equation} 會提供系統在該狀態下的平均能源。</span><span class="sxs-lookup"><span data-stu-id="60c5c-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="60c5c-109">而地面狀態則是提供最小這類值的狀態。</span><span class="sxs-lookup"><span data-stu-id="60c5c-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="60c5c-110">因此，選擇盡可能接近實際狀態的狀態，非常重要的是直接評估能源（如同在 variational eigensolvers 中完成），或透過階段估計。</span><span class="sxs-lookup"><span data-stu-id="60c5c-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="60c5c-111">Hartree – Fock 理論提供了一種簡單的方式來建造量子系統的初始狀態。</span><span class="sxs-lookup"><span data-stu-id="60c5c-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="60c5c-112">它會針對量子系統的基礎狀態產生單一 Slater 行列式近似值。</span><span class="sxs-lookup"><span data-stu-id="60c5c-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="60c5c-113">為此，它會在 Fock 空間內尋找旋轉，以將地面狀態的能源降到最低。</span><span class="sxs-lookup"><span data-stu-id="60c5c-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="60c5c-114">特別是，針對 $N $ electrons 的系統，此方法會執行輪替 \begin{equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket{0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket{0}\defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket{0}，具有反 Hermitian 的 \end{equation} （亦即，$u =-u ^ \dagger $）矩陣 $u = \ sum_ {pq} u_ {pq} a ^ \ dagger_p a_q $。</span><span class="sxs-lookup"><span data-stu-id="60c5c-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="60c5c-115">請注意，矩陣 $u $ 代表 orbital 旋轉，而 $ \widetilde{a} ^ \ dagger_j $ 和 $ \widetilde{a} _j $ 代表 electrons 佔用 Hartree – Fock 分子微調-orbitals 的建立和 annihilation 運算子。</span><span class="sxs-lookup"><span data-stu-id="60c5c-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="60c5c-116">然後，$u $ 的矩陣經過優化，可將預期的能源 $ \bra{0} \ prod_ {j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \ dagger_k \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="60c5c-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="60c5c-117">雖然這類優化問題可能會很困難，但實際上 Hartree – Fock 演算法會快速地融合到優化問題的接近最佳解決方案，特別是均衡幾何中的封閉式 shell 分子驅使分子。</span><span class="sxs-lookup"><span data-stu-id="60c5c-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="60c5c-118">我們可以將這些狀態指定為 `FermionWavefunction` 物件的實例。</span><span class="sxs-lookup"><span data-stu-id="60c5c-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="60c5c-119">例如，狀態 $a ^ \ dagger_{1}^ \ dagger_{2}dagger_ \ket{6}$ 在化學程式庫中具現化，如下所示。{0}</span><span class="sxs-lookup"><span data-stu-id="60c5c-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="60c5c-120">您也可以使用 `SpinOrbital` 索引來為 wave 函數編制索引，然後將這些索引轉換成整數，如下所示。</span><span class="sxs-lookup"><span data-stu-id="60c5c-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="60c5c-121">Hartree 的最顯著功能– Fock 的理論是，它會產生 electrons 之間沒有會任何牽連的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="60c5c-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="60c5c-122">這表示它通常會提供分子系統屬性的適當定性描述。</span><span class="sxs-lookup"><span data-stu-id="60c5c-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="60c5c-123">Hartree-Fock 狀態也可以從 `FermionHamiltonian` 重建，如下所示。</span><span class="sxs-lookup"><span data-stu-id="60c5c-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="60c5c-124">不過，若要取得精確的結果，特別是針對強式相互關聯的系統，則會有超越 Hartree – Fock 理論的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="60c5c-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
