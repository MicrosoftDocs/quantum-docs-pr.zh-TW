---
title: 模擬 Hamiltonian Dynamics
description: 瞭解如何使用 Trotter-Plat'home co. 公式和 qubitization 來處理 Hamiltonian 模擬。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274659"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="ab9bb-103">模擬 Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="ab9bb-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="ab9bb-104">一旦將 Hamiltonian 表示為基本運算子的總和，就可以使用已知的技術主機，將 dynamics 編譯成基本閘道作業。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="ab9bb-105">有三種有效率的方法，包括 Trotter – Plat'home co. 公式、unitaries 和 qubitization 的線性組合。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="ab9bb-106">我們將在下面說明這三種方法，並提供具體的 Q # 範例，示範如何使用 Hamiltonian 模擬程式庫來執行這些方法。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="ab9bb-107">Trotter – Plat'home co. 公式</span><span class="sxs-lookup"><span data-stu-id="ab9bb-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="ab9bb-108">Trotter-Plat'home co. 公式背後的概念很簡單：將 Hamiltonian 表達為容易模擬 Hamiltonians 的總和，然後將總進化數估計為這些較簡單演變的一系列。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="ab9bb-109">特別是，let $H = \ sum_ {j = 1} ^ m H_j $ 是 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="ab9bb-110">然後，$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O （m ^ 2 t ^ 2），$ $，也就是說，如果 $t \ll $1，則此近似值中的錯誤會變成可忽略的。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="ab9bb-111">請注意，如果 $e ^ {-i H t} $ 是普通指數，則此近似值中的錯誤不會 $O （m ^ 2 t ^ 2） $：它會是零。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="ab9bb-112">之所以會發生此錯誤，是因為 $e ^ {-iHt} $ 是運算子指數，因此使用此公式時發生錯誤，因為 $H _j $ 詞彙不會向下計算（*亦即*$H _j H_k \ne H_k H_j $ 一般）。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="ab9bb-113">如果 $t $ 很大，則 Trotter – Plat'home co. 公式仍然可以藉由將其細分為一系列簡短的時間步驟，來正確模擬 dynamics。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="ab9bb-114">讓 $r $ 成為在時間演進期間所採取的步驟數，因此每次執行步驟時，$t/r $。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="ab9bb-115">然後，我們有 $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left （\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right） ^ r + O （m ^ 2 t ^ 2/r），$ $，這表示如果 $r $ 縮放為 $m ^ 2 t ^ 2/\ epsilon $，則最多可為任何 $ \epsilon>$0 的 $ \epsilon $ 建立錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="ab9bb-116">藉由建立一連串的運算子指數來建立更精確的近似值，使錯誤詞彙取消。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="ab9bb-117">最簡單的這類公式，第二個 order Trotter-Plat'home co. 公式，採用的格式為 $ $ U_2 （t） = \left （\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2r} \ right） ^ r = e ^ {-iHt} + O （m ^ 3 t ^ 3/r ^ 2），$ $ 可以針對任何 $ \epsilon>$0，選擇將 $r $ 調整為 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $，以小於 $ \epsilon $ 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="ab9bb-118">更高順序的公式（特別是 $ 2k $）第一次 $k>$0 的順序，可以遞迴方式進行： $ $ U_ {2k} （t） = [U_ {2k-2} （s_k \~ t）] ^ 2 U_ {2k-2} （[1-4s_k] t） [U_ {2k-2} （s_k \~ t）] ^ 2 = e ^ {-iHt} + O （（m t） ^ {2k + 1}/r ^ {2k}），$ $，其中 $s _k = （4-4 ^ {1/（2k-1）}） ^ {-1} $。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="ab9bb-119">最簡單的是下列第四個 order （$k = $2）公式，最初是由 Plat'home co. 所引進： $ $ U_4 （t） = [U_2 （s_2 \~ t）] ^ 2 U_2 （[1-4s_2] t） [U_2 （s_2 \~ t）] ^ 2 = e ^ {-iHt} + O （m ^ 5t ^ 5/r ^ 4），$ $ where $s _2 = （4-4 ^ {1/3}） ^ {-1} $。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="ab9bb-120">一般來說，任意高階的公式都可以類似地進行結構化;不過，使用較複雜的整合者所產生的成本，通常比大部分實際問題的第四個順序還多。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="ab9bb-121">為了讓上述策略正常執行，我們需要有一個方法可模擬 $e ^ {-iH_j t} $ 的寬類別。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="ab9bb-122">最簡單的 Hamiltonians 系列，而且最有用的是，我們可以在這裡使用 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="ab9bb-123">Pauli 運算子可以輕鬆模擬，因為它們可以使用 Clifford 作業來 diagonalized （在量子運算中是標準閘道）。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="ab9bb-124">此外，一旦 diagonalized，就可以藉由計算其作用所在 qubits 的同位來找到其特徵值。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="ab9bb-125">例如，$ $ e ^ {-iX\otimes X t} = （H\otimes H） e ^ {-iZ\otimes Z t} （H\otimes H），$ $，其中 $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0</span><span class="sxs-lookup"><span data-stu-id="ab9bb-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="ab9bb-126">0 & e ^ {i t} & 0 & 0</span><span class="sxs-lookup"><span data-stu-id="ab9bb-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="ab9bb-127">0 & 0 & e ^ {it} & 0</span><span class="sxs-lookup"><span data-stu-id="ab9bb-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="ab9bb-128">0 & 0 & 0 & e ^ {-it} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="ab9bb-129">$ $ 這裡，$e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ 和 $e ^ {-iHt} \ket {01} = e ^ {-it} \ket {01} $，這是因為 $0 $ 的同位檢查是 $0 $，而位字串 $1 $ 為 $1 $ 的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="ab9bb-130">Pauli 運算子的指數可以直接在 Q # 中使用作業來執行 <xref:microsoft.quantum.intrinsic.exp> ：</span><span class="sxs-lookup"><span data-stu-id="ab9bb-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="ab9bb-131">針對 Fermionic Hamiltonians，[[約旦– Wigner] 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner)可方便地將 Hamiltonian 對應到 Pauli 運算子的總和。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="ab9bb-132">這表示您可以輕鬆地調整上述方法來模擬化學。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="ab9bb-133">以下是在化學中執行這類模擬的簡單範例，而不是手動迴圈 Wigner 標記法中的所有 Pauli 詞彙。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="ab9bb-134">我們的起點是 Fermionic Hamiltonian 的[約旦– Wigner 編碼](xref:microsoft.quantum.chemistry.concepts.jordanwigner)，以程式碼表示為類別的實例 `JordanWignerEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="ab9bb-135">這種類型的 Wigner 標記法可供 Q # 模擬演算法取用，這種格式是使用者定義的型別 `JordanWignerEncodingData` 。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="ab9bb-136">在 Q # 中，此格式會傳遞至便利函式，此函數會 `TrotterStepOracle` 使用 Trotter （plat'home co. 整合器）（除了執行所需的其他參數）來傳回運算子將逼近時間演進。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

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

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="ab9bb-137">重要的是，這項實作為在[模擬使用量子電腦 Hamiltonians 的電子結構](https://arxiv.org/abs/1001.3855)時所討論的一些優化，並[改善量子化學](https://arxiv.org/abs/1403.1539)的配量演算法，以將所需的單一 qubit 旋轉數目降至最低，以及減少模擬錯誤。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="ab9bb-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="ab9bb-138">Qubitization</span></span>

<span data-ttu-id="ab9bb-139">Qubitization 是模擬的替代方法，它會使用來自量子的想法來模擬配量 dynamics。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="ab9bb-140">雖然 qubitization 需要比 Trotter 公式更多的 qubits，但是方法會透過進化時間和容錯來提供最佳的調整。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="ab9bb-141">基於這些理由，它已成為一般模擬 Hamiltonian dynamics 的一種方法，特別是為了解決電子結構問題。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="ab9bb-142">概括而言，qubitization 會透過下列步驟來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="ab9bb-143">首先，讓 $H = \ sum_j h_j H_j $ 適用于單一和 Hermitian $H _j $ 和 $h _j \ge $0。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="ab9bb-144">藉由執行一對反射，qubitization 會實作用等於 $ $W = e ^ {\pm i \cos ^ {-1} （h/| h | _1）}，$ $ where $ | h | _1 = \ sum_j | h_j | $ 的運算子。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="ab9bb-145">下一個步驟牽涉到從 $e ^ {i\pm \cos ^ {-1} （E_k/| h | _1）} $ 中轉換「行走」運算子的特徵值，其中 $E _k $ 是 $H $ to $e ^ {-iE_k t} $ 的特徵值。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="ab9bb-146">這可以使用各種量子單數值轉換方法來達成，包括[量子信號處理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="ab9bb-147">或者，如果只想要使用靜態數量（例如 Hamiltonian 的基礎狀態能源），則它會後綴將[階段估計](xref:microsoft.quantum.libraries.characterization)直接套用到 $W $，藉由採用結果的余弦值來估計結果中的地面狀態能源。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="ab9bb-148">這很重要，因為它允許 spectral 轉換執行傳統方式，而不是使用量子單數值轉換方法。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="ab9bb-149">在更詳細的層級上，qubitization 的執行需要兩個可提供 Hamiltonian 介面的副程式。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="ab9bb-150">不同于 Trotter – Plat'home co. 方法，這些副程式不是傳統的量子，而且其執行方式必須使用 logarithmically 比 Trotter 型模擬所需的 qubits 還多。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="ab9bb-151">Qubitization 使用的第一個量子副程式稱為 $ \operatorname{Select} $，其承諾是產生 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每個 $H _j $ 會假設為 Hermitian 和單一。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="ab9bb-152">雖然這看似嚴格，但請記得 Pauli 的運算子是 Hermitian 和單一的，因此量子化學模擬這類應用程式自然會落入此架構中。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="ab9bb-153">$ \Operatorname{Select} $ 作業（或許很驚訝）實際上是反映作業。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="ab9bb-154">這種情況可以看出，$ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $，因為每個 $H _j $ 是單一和 Hermitian，因此具有特徵值 $ \pm $1。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="ab9bb-155">第二個子程式稱為 $ \operatorname{Prepare} $。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="ab9bb-156">雖然選取作業提供 coherently 存取每個 Hamiltonian 詞彙的方法 $H _j $ 「準備」副程式提供了存取係數 $h _j $、\begin{equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="ab9bb-157">\end{equation} 接著，藉由使用 [乘以控制的階段] 閘道，我們會看到 $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \text{if} x = 0</span><span class="sxs-lookup"><span data-stu-id="ab9bb-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="ab9bb-158">\ket{x} & \text{otherwise} \end{cases}。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="ab9bb-159">$ \Operatorname{Prepare} $ 作業不會直接在 qubitization 中使用，而是用來執行有關狀態的反映，$ \operatorname{Prepare} $ 會建立 $ $ \begin{align} R &amp; = 1-2 \ 運算子名稱 {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} 。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="ab9bb-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="ab9bb-160">\end{align} $$</span></span>

<span data-ttu-id="ab9bb-161">您可以使用 $ \operatorname{Select} $ 和 $R $ 作業以 $ $ W = \operatorname{Select} R，$ $ 的角度來表示執行運算子（$W $），這會再次顯示為對 $e ^ {\pm i \cos ^ {-1} （H/| H | _1）} $ 的運算子。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="ab9bb-162">這些副程式在 Q # 中很容易設定。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="ab9bb-163">例如，假設有一個簡單的 qubit 橫向 Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="ab9bb-164">在此情況下，會叫用執行 $ \operatorname{Select} $ 作業的 Q # 程式碼 <xref:microsoft.quantum.canon.multiplexoperations> ，而 $ \operatorname{Prepare} $ 作業則可使用來執行 <xref:microsoft.quantum.preparation.preparearbitrarystate> 。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="ab9bb-165">如需模擬 Hubbard 模型的範例，請參閱[Q # 範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="ab9bb-166">針對任意化學問題手動指定這些步驟需要耗費大量的工作，這是使用化學程式庫來避免的。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="ab9bb-167">類似于上述的 Trotter – Plat'home co. 模擬演算法， `JordanWignerEncodingData` 會傳遞至方便的函式，該函數會傳回 `QubitizationOracle` 逐步執行運算子，以及其執行所需的其他參數。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="ab9bb-168">重要的是，此執行 <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> 適用于指定為 Pauli 字串線性組合的任意 Hamiltonians。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="ab9bb-169">使用來叫用針對化學模擬優化的版本 <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> 。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="ab9bb-170">這個版本經過優化，可將使用在配量線路中以編碼電子 Spectra 所討論的技術降到最低的 T 閘道數目[，並加上線性 T 複雜度](https://arxiv.org/abs/1805.03662)。</span><span class="sxs-lookup"><span data-stu-id="ab9bb-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
