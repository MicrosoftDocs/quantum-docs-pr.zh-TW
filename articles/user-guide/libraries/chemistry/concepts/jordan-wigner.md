---
title: 約旦-Wigner 標記法
description: 深入瞭解 Wigner 標記法，這會將 Hamiltonian 操作員對應到可在量子電腦上更容易執行的單一矩陣。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833851"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="63f24-103">約旦-Wigner 標記法</span><span class="sxs-lookup"><span data-stu-id="63f24-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="63f24-104">雖然第二個量化 Hamiltonian 是以 $a ^ \dagger $ (建立) 和 $a $ (annihilation) 方便表示，但這些作業不是量子電腦中的基本作業。</span><span class="sxs-lookup"><span data-stu-id="63f24-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="63f24-105">因此，如果我們希望它在量子電腦上執行，我們必須將操作員對應到可在量子電腦上執行的單一矩陣。</span><span class="sxs-lookup"><span data-stu-id="63f24-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="63f24-106">約旦– Wigner 標記法會提供一種地圖。</span><span class="sxs-lookup"><span data-stu-id="63f24-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="63f24-107">不過，其他的 Bravyi – Kitaev 標記法也存在，而且有其各自的優點和缺點。</span><span class="sxs-lookup"><span data-stu-id="63f24-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="63f24-108">Wigner 標記法的主要優點是它的簡化方式。</span><span class="sxs-lookup"><span data-stu-id="63f24-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="63f24-109">約旦 Wigner 標記法是要衍生的正向。</span><span class="sxs-lookup"><span data-stu-id="63f24-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="63f24-110">回想一下，state $ \ket {0} _j $ 表示微調 orbital $j $ 是空的，而 $ \ket {1} _j $ 表示它已被佔用。</span><span class="sxs-lookup"><span data-stu-id="63f24-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="63f24-111">這表示量子位可以自然地儲存特定微調 orbital 的職業。</span><span class="sxs-lookup"><span data-stu-id="63f24-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="63f24-112">然後，$a ^ \ dagger_j \ket {0} _j = \ket {1} _j $ 和 $a ^ \ dagger_j \ket {1} _j = $0。</span><span class="sxs-lookup"><span data-stu-id="63f24-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="63f24-113">您可以輕鬆地確認 \begin{align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} 、\nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} 、\end{align}，其中 $X _j $ 和 $Y _j $ 是以 Pauli $X $ 為目標的量子位 $Y $ 和-$j $ 運算子。</span><span class="sxs-lookup"><span data-stu-id="63f24-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>

>[!NOTE]
> <span data-ttu-id="63f24-114">在 Q# $ \ket {0} $ 狀態中，代表 $Z $ 運算子的 + 1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="63f24-114">In Q# the $\ket{0}$ state represents the +1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="63f24-115">在物理 $ \ket $ 的某些區域中， {0} 代表低能量地面狀態，因此是 $Z $ 運算子的-1 eigenstate。</span><span class="sxs-lookup"><span data-stu-id="63f24-115">In some areas of physics $\ket{0}$ represents the low-energy ground state and thus the -1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="63f24-116">因此，某些公式可能與熱門的文獻不同。</span><span class="sxs-lookup"><span data-stu-id="63f24-116">Therefore some formulas might differ from popular literature.</span></span>

<span data-ttu-id="63f24-117">在化學程式庫中，我們使用 $ \ket {0} $ 表示空的旋轉 orbital。</span><span class="sxs-lookup"><span data-stu-id="63f24-117">In the chemistry library we use $\ket{0}$ to represent an unoccupied spin-orbital.</span></span>
<span data-ttu-id="63f24-118">這會顯示單一微調 orbital 很容易以量子電腦瞭解的單一矩陣來表示建立和 annihilation 運算子。</span><span class="sxs-lookup"><span data-stu-id="63f24-118">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="63f24-119">請注意，雖然 $X $ 和 $Y $ 是單一 $a ^ \dagger $，而 $a $ 則否。</span><span class="sxs-lookup"><span data-stu-id="63f24-119">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="63f24-120">稍後我們會看到這不會造成模擬的挑戰。</span><span class="sxs-lookup"><span data-stu-id="63f24-120">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="63f24-121">其中一個問題是，雖然上述結構適用于單一微調 orbital，但是具有兩個或多個微調 orbitals 的系統會失敗。</span><span class="sxs-lookup"><span data-stu-id="63f24-121">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="63f24-122">由於 Fermions 是 antisymmetic，我們知道 $a ^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k 任何 dagger_j $ 和 $j $ 的 ^ \ $k $。</span><span class="sxs-lookup"><span data-stu-id="63f24-122">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="63f24-123">不過，$ $ \left ( \frac{X_j-iY_j} {2} \right) \left ( \frac{X_k-iY_k} {2} \right) = \left ( \frac{X_k-iY_k} {2} \right) \left ( \frac{X_j-iY_j} {2} \right) 。</span><span class="sxs-lookup"><span data-stu-id="63f24-123">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="63f24-124">$ $ 換言之，兩個建立運算子不會視需要進行反上運算。</span><span class="sxs-lookup"><span data-stu-id="63f24-124">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="63f24-125">您可以直接在種粗糙的方式中解決此情況。</span><span class="sxs-lookup"><span data-stu-id="63f24-125">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="63f24-126">修正程式是要注意的是，Pauli 運算子自然是反上的。</span><span class="sxs-lookup"><span data-stu-id="63f24-126">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="63f24-127">尤其是，$XZ =-ZX $ 和 $YZ =-ZY $。</span><span class="sxs-lookup"><span data-stu-id="63f24-127">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="63f24-128">因此，藉由將 $Z $ 運算子 interspersing 到運算子的結構中，我們可以模擬正確的反 commutation。</span><span class="sxs-lookup"><span data-stu-id="63f24-128">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="63f24-129">完整的結構如下所示：</span><span class="sxs-lookup"><span data-stu-id="63f24-129">The full construction is as follows:</span></span> 

<span data-ttu-id="63f24-130">\begin{align} ^ \ dagger_1 &= \left ( \frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1、 \\ \\ ^ \ dagger_2 &= Z\otimes\left ( \frac{x-iy} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1、 \\ \\ ^ \ dagger_3 &= Z\otimes Z\otimes \left ( \frac{x-iy} {2} \right) \otimes 1 \otimes \cdots \otimes 1、 \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left ( \frac{x-iy} {2} \right) 。</span><span class="sxs-lookup"><span data-stu-id="63f24-130">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="63f24-131">\label{eq： JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="63f24-131">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="63f24-132">以 Pauli 運算子表達數位運算子（$n _j $）也很方便。</span><span class="sxs-lookup"><span data-stu-id="63f24-132">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="63f24-133">幸好，$Z $ 運算子的字串 (稱為約旦 Wigner 字串) 在進行這項替代之後取消。</span><span class="sxs-lookup"><span data-stu-id="63f24-133">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="63f24-134">在執行此 (並重新叫用 $X _jY_j = iZ_j $) 之後，我們已 \begin{equation} n_j = a ^ \ dagger_j a_j = \frac{ (1-Z_j) } {2} 。</span><span class="sxs-lookup"><span data-stu-id="63f24-134">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="63f24-135">\end{equation}</span><span class="sxs-lookup"><span data-stu-id="63f24-135">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="63f24-136">以約旦 Wigner 標記法來建立 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="63f24-136">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="63f24-137">一旦叫用 Wigner 標記法，將 Hamiltonian 轉譯為 Pauli 運算子的總和是直接的。</span><span class="sxs-lookup"><span data-stu-id="63f24-137">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="63f24-138">其中一個只需要將 Fermionic Hamiltonian 中的每個 $a ^ \dagger $ 和 $a $ 運算子取代為上述 Pauli 運算子的字串。</span><span class="sxs-lookup"><span data-stu-id="63f24-138">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="63f24-139">當其中一個執行這項替換時，Hamiltonian 內只有五個詞彙類別。</span><span class="sxs-lookup"><span data-stu-id="63f24-139">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="63f24-140">這五個類別會對應到不同的方法，我們可以在 Hamiltonian 中挑選一個內文中的 $p、q $ 和 $p、q、r、s $，以及兩段內文。</span><span class="sxs-lookup"><span data-stu-id="63f24-140">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="63f24-141">這五個類別，在 $p>q>r>s $ 和實值 orbitals 的情況下，</span><span class="sxs-lookup"><span data-stu-id="63f24-141">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="63f24-142">\begin{align} h_ {pp} a_p ^ \dagger a_p &= \ sum_p \frac{h_ {pp}} {2} (1-Z_p) \\ \\ h_ {pq} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{h_ {pq}} {2} \left ( \ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left ( X_pX_q + Y_pY_q \right) \\ \\ h_ {pqqp} n_p n_q &= \frac{h_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{h_ {pqqr}} {2} \left ( \ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left ( X_pX_r + Y_pY_r \right) \left ( \frac{1-Z_q} {2} \right) \\ \\ H_ {pqrs} &= \frac{h_ {pqrs}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}</span><span class="sxs-lookup"><span data-stu-id="63f24-142">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="63f24-143">雖然以手動方式產生此類 Hamiltonian 只需要套用這些取代規則，但是針對大型分子（可以包含數百萬個 Hamiltonian 詞彙）並不可行。</span><span class="sxs-lookup"><span data-stu-id="63f24-143">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="63f24-144">或者，我們可以自動建立 `JordanWignerEncoding` 指定的 `FermionHamiltonian` Hamiltonian 標記法。</span><span class="sxs-lookup"><span data-stu-id="63f24-144">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="63f24-145">以這種形式建立 Hamiltonian 之後，我們就可以使用量子模擬演算法的主機，將由 $e ^ {-iHt} $ 產生的 dynamics，編譯成一系列的基本閘道， (在某些使用者可定義的誤差容錯) 內。</span><span class="sxs-lookup"><span data-stu-id="63f24-145">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="63f24-146">我們將在演算法檔中討論量子模擬、量子位化和 Trotter – Suzuki 公式的兩個最常用方法。</span><span class="sxs-lookup"><span data-stu-id="63f24-146">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="63f24-147">我們在 Hamiltonian 模擬程式庫中提供這兩種方法的執行方式。</span><span class="sxs-lookup"><span data-stu-id="63f24-147">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>
