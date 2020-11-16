---
title: 模擬 Hamiltonian Dynamics
description: 瞭解如何使用 Trotter-Suzuki 公式和量子位化來處理 Hamiltonian 模擬。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: a303d54476e42b98a14c6b452227b0e1346567c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691883"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="b1d8e-103">模擬 Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="b1d8e-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="b1d8e-104">一旦將 Hamiltonian 表示為基本運算子的總和後，就可以使用已知技術的主機，將 dynamics 編譯成基本閘道作業。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="b1d8e-105">有三種有效率的方法，包括 Trotter – Suzuki 公式、unitaries 的線性組合和量子位化。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="b1d8e-106">我們將在下面說明這三種方法，並提供 Q# 如何使用 Hamiltonian 模擬程式庫來執行這些方法的具體範例。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="b1d8e-107">Trotter – Suzuki 公式</span><span class="sxs-lookup"><span data-stu-id="b1d8e-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="b1d8e-108">Trotter-Suzuki 公式背後的構想很簡單：以簡單的方式來表達 Hamiltonian，以簡化 Hamiltonian，然後將總演進大約視為這些更簡單演進的順序。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="b1d8e-109">尤其是，讓 $H = \ sum_ {j = 1} ^ m H_j $ Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="b1d8e-110">然後，$ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2) ，$ $，這表示如果 $t \ll $1，則此近似值中的錯誤會變成可忽略。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="b1d8e-111">請注意，如果 $e ^ {-i H t} $ 是一般的指數，則此近似值中的錯誤不會 $O (m ^ 2 t ^ 2) $：它會是零。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="b1d8e-112">發生此錯誤的原因是 $e ^ {-iHt} $ 是運算子指數，因此使用此公式時發生錯誤，因為 $H _j $ 詞彙不會在 (， *例如* $H _j H_k \ne H_k H_j $ 一般) 。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute ( *i.e.* , $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="b1d8e-113">如果 $t $ 是大型的，Trotter – Suzuki 公式仍然可以用來將動態模擬為一系列簡短的步驟來精確地模擬。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="b1d8e-114">讓 $r $ 成為在時間演進中所採取的步驟數目，因此每次步驟都是針對時間 $t/r $ 執行。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="b1d8e-115">接著，我們有了 $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left ( \ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r) $ $ 表示如果 $r $ 調整為 $m ^ 2 t ^ 2/\ epsilon $，則在任何 $ \epsilon>$0 中最多可以有 $ \epsilon $ 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="b1d8e-116">您可以藉由建立一連串運算子指數來建立更精確的近似值，以取消錯誤詞彙。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="b1d8e-117">最簡單的這類公式，第二個順序 Trotter-Suzuki 公式，採用 "$ U_2 (t) = \left ( \ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2r} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2r} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2) $ $ $r $ 以 $m ^ {3/2} t ^ {3/2}/\sqrt {\ epsilon} $ 進行調整，可針對任何 $ \epsilon>$0 建立小於 $ \epsilon $ 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="b1d8e-118">甚至更高順序的公式（特別是 ($ 2k $) $k>$0 的第一個順序）可以用遞迴方式進行： $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t) ] ^ 2 U_ {2k-2} ( [1-4s_k] t) [U_ {2k-2} (s_k \~ t) ] ^ 2 = e ^ {-iHt} + O ( # B11 m t) ^ {2k + 1}/r ^ {2k} ) ，$ $，其中 $s _k = (4-4 ^ {1/ (2k-1) } ) ^ {-1} $。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="b1d8e-119">最簡單的是下列第四個順序 ($k = $2) 公式，最初是由 Suzuki 所引進： $ $ U_4 (t) = [U_2 (s_2 \~ t) ] ^ 2 U_2 ( [1-4s_2] t) [U_2 (s_2 \~ t) ] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/r ^ 4) ，$ $，其中 $s _2 = (4-4 ^ {1/3} ) ^ {-1} $。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="b1d8e-120">一般情況下，任意高序位的公式都可以用同樣的方式進行結構化;不過，使用較複雜的整合者所產生的成本，通常會比大部分實際問題的第四個程式的優點更高。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="b1d8e-121">為了讓上述策略正常運作，我們需要有方法來模擬 $e ^ {-iH_j t} $ 的廣泛類別。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="b1d8e-122">我們可以在這裡使用的最簡單 Hamiltonian 系列是 Pauli 操作員。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="b1d8e-123">您可以輕鬆地模擬 Pauli 運算子，因為它們可以使用 Clifford 作業來 diagonalized， (是量子運算) 的標準閘道。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="b1d8e-124">此外，一旦 diagonalized 之後，就可以藉由計算其作用所在量子位的同位來找到其特徵值。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="b1d8e-125">例如，$ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H) ，$ $，其中 $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="b1d8e-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="b1d8e-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="b1d8e-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="b1d8e-127">0 & 0 & e ^ {it} & 0 </span><span class="sxs-lookup"><span data-stu-id="b1d8e-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="b1d8e-128">0 & 0 & 0 & e ^ {-it} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="b1d8e-129">$ $ 這裡、$e ^ {-iHt} \ket {00} = e ^ {it} \ket {00} $ 和 $e ^ {-iHt} \ket {01} = e ^ {-it} \ket {01} $，這可能是因為 $0 $ 的同位檢查是 $0 $，而位字串 $1 $ 的同位檢查為 $1 $ 的結果。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="b1d8e-130">Pauli 運算子的指數可以使用作業直接實作為 Q# <xref:Microsoft.Quantum.Intrinsic.Exp> ：</span><span class="sxs-lookup"><span data-stu-id="b1d8e-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:Microsoft.Quantum.Intrinsic.Exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="b1d8e-131">針對 Fermionic Hamiltonian， [約旦– Wigner 分解](xref:microsoft.quantum.chemistry.concepts.jordanwigner) 可方便地將 Hamiltonian 對應到 Pauli 運算子的總和。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="b1d8e-132">這表示您可以輕鬆地調整上述方法來模擬化學。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="b1d8e-133">以下是在化學中執行這類模擬的簡單範例，而不是在 Jordan-Wigner 標記法中手動迴圈執行。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how running such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="b1d8e-134">我們的起點是 Fermionic Hamiltonian 的 [約旦 Wigner 編碼](xref:microsoft.quantum.chemistry.concepts.jordanwigner) ，以程式碼形式以類別的實例來表示 `JordanWignerEncoding` 。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

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

<span data-ttu-id="b1d8e-135">模擬演算法取用的這種 Wigner 標記法格式 Q# 是使用者定義型別 `JordanWignerEncodingData` 。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="b1d8e-136">在中 Q# ，此格式會傳遞至方便 `TrotterStepOracle` 的函式，此函式會使用 Trotter （Suzuki 整合器）傳回運算子將逼近時間演進，以及其執行所需的其他參數。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its run.</span></span>

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

<span data-ttu-id="b1d8e-137">重要的是，這項實行會套用一些在 [模擬 Hamiltonian 使用量子電腦的電子結構](https://arxiv.org/abs/1001.3855) 時所討論的優化，並 [改善量子化學的量子演算法](https://arxiv.org/abs/1403.1539) ，以將所需的單一量子位輪替數目降至最低，並減少模擬錯誤。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="b1d8e-138">量子位化</span><span class="sxs-lookup"><span data-stu-id="b1d8e-138">Qubitization</span></span>

<span data-ttu-id="b1d8e-139">量子位化是模擬的替代方法，會使用量子逐步解說中的想法來模擬量子 dynamics。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="b1d8e-140">雖然量子位化需要比 Trotter 公式更多的量子位，但方法在演進時間和容錯能力上提供最佳調整。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="b1d8e-141">基於這些原因，它已成為一般模擬 Hamiltonian dynamics 的最常用方法，也是解決電子結構問題的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="b1d8e-142">概括而言，量子位化會透過下列步驟完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="b1d8e-143">首先，讓 $H = \ sum_j h_j H_j $ 適用于單一和 Hermitian $H _j $ 和 $h _j \ge $0。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="b1d8e-144">藉由執行一對反射，量子位化會實作用等於 $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1) }，$ $ （其中 $ | h | _1 = \ sum_j | h_j | $）的運算子。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="b1d8e-145">下一步是要將逐步運算子的特徵值從 $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1) } $ 中轉換，其中 $E _k $ 是 $H $ 到 $e ^ {-iE_k t} $ 的特徵值。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="b1d8e-146">您可以使用各種量子單數值轉換方法來達成此目的，包括 [量子信號處理](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="b1d8e-147">或者，如果只需要靜態數量 (例如 Hamiltonian 的地面狀態能源) 則它會後綴將 [階段估計](xref:microsoft.quantum.libraries.characterization) 直接套用至 $W $，藉由採取結果的余弦值，從結果中估計地面狀態的能源。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="b1d8e-148">這很重要，因為它可讓光譜轉換執行傳統方式，而不是使用量子單數值轉換方法。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="b1d8e-149">在更詳細的層級上，量子位化的執行需要兩個可提供 Hamiltonian 介面的副程式。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="b1d8e-150">與 Trotter （Suzuki）方法不同的是，這些副程式不是傳統的，且其執行必須使用 logarithmically 以上的量子位，而非以 Trotter 為基礎的模擬。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="b1d8e-151">量子位化使用的第一個量子副程式稱為 $ \operatorname{Select} $，並承諾產生 \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}，\end{equation}，其中每個 $H _j $ 會假設為 Hermitian 和單一。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="b1d8e-152">雖然這看起來可能會受到限制，但請記住，Pauli 運算子是 Hermitian 和單一的，因此量子化學模擬之類的應用程式自然會落在此架構中。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="b1d8e-153">$ \Operatorname{Select} $ 作業（可能很令人驚訝）實際上是反映運算。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="b1d8e-154">這可能是因為 $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $ 的事實，因為每個 $H _j $ 是單一和 Hermitian，因此具有特徵值 $ \pm $1。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="b1d8e-155">第二個子程式稱為 $ \operatorname{Prepare} $。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="b1d8e-156">雖然選取作業提供了時存取每個 Hamiltonian 詞彙的方法 $H _j $ 此準備副程式會提供方法來存取係數 $h _j $、\begin{equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="b1d8e-157">\end{equation} 然後，藉由使用已控制的階段閘道，我們會看到 $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{cases} \- \ket{x} & \text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="b1d8e-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="b1d8e-158">\ket{x} & \text{otherwise} \end{cases}。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="b1d8e-159">$ \Operatorname{Prepare} $ 作業不會直接在量子位化中使用，而是用來執行有關 $ \operatorname{Prepare} $ 建立 $ $ \begin{align} R &amp; = 1-2 \ 運算子名稱 {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} 之狀態的反映。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="b1d8e-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b1d8e-160">\end{align} $$</span></span>

<span data-ttu-id="b1d8e-161">您可以使用 $ \operatorname{Select} $ 和 $R $ 作業來表示「逐步運算子」（$W $），例如 $ $ W = \operatorname{Select} R、$ $，如此一來，就可以將相等的運算子 (最) 多等於 $e ^ {\pm i \cos ^ {-1} (H/| H | _1) } $。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="b1d8e-162">在中，您可以輕鬆地設定這些副程式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="b1d8e-163">例如，請考慮使用簡單的量子位橫向-Ising Hamiltonian，其中 $H = X_1 + X_2 + Z_1 Z_2 $。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="b1d8e-164">在此情況下，會叫用 Q# 執行 $ \operatorname{Select} $ 作業的程式碼 <xref:Microsoft.Quantum.Canon.MultiplexOperations> ，而 $ \operatorname{Prepare} $ 作業則可以使用來執行 <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState> 。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:Microsoft.Quantum.Canon.MultiplexOperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:Microsoft.Quantum.Preparation.PrepareArbitraryState>.</span></span>
<span data-ttu-id="b1d8e-165">您可以在[ Q# 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard)中找到包含模擬 Hubbard 模型的範例。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).</span></span>

<span data-ttu-id="b1d8e-166">針對任意化學問題手動指定這些步驟，需要投入大量的時間，這是使用化學程式庫避免的。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="b1d8e-167">類似于上述的 Trotter-Suzuki 模擬演算法， `JordanWignerEncodingData` 會傳遞至方便的函式，以傳回 `QubitizationOracle` 逐步運算子，以及執行所需的其他參數。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its run.</span></span>

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

<span data-ttu-id="b1d8e-168">重要的是，此執行 <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> 適用于指定為 Pauli 字串線性組合的任意 hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-168">Importantly, the implementation <xref:Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="b1d8e-169">使用針對化學模擬優化的版本 <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle> 。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-169">A version optimized for chemistry simulations is invoked using <xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle>.</span></span>
<span data-ttu-id="b1d8e-170">此版本已經過優化，可將使用在 [量子線路中使用編碼電子 Spectra 的技巧，以線性 t 複雜度進行編碼](https://arxiv.org/abs/1805.03662)，以最小化 t 閘道的數目。</span><span class="sxs-lookup"><span data-stu-id="b1d8e-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
