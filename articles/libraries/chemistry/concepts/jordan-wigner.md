---
title: 約旦-Wigner 標記法 |Microsoft Docs
description: 約旦-Wigner 表示概念檔
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: f34233bc17ff68a9e04256959f8d79be2682c34f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184044"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="145ce-103">約旦-Wigner 標記法</span><span class="sxs-lookup"><span data-stu-id="145ce-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="145ce-104">雖然第二個量化 Hamiltonians 在 $a ^ \dagger $ （建立）和 $a $ （annihilation）方面方便呈現，但這些作業不是量子電腦中的基本作業。</span><span class="sxs-lookup"><span data-stu-id="145ce-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="145ce-105">因此，如果我們想要在量子電腦上執行它們，我們需要將操作員對應到可在量子電腦上執行的單一矩陣。</span><span class="sxs-lookup"><span data-stu-id="145ce-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="145ce-106">約旦– Wigner 標記法會提供這種對應。</span><span class="sxs-lookup"><span data-stu-id="145ce-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="145ce-107">不過，其他人（例如 Bravyi – Kitaev 標記法）也存在，而且有自己的相對優點和缺點。</span><span class="sxs-lookup"><span data-stu-id="145ce-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="145ce-108">Wigner 標記法的主要優點是它的簡單性。</span><span class="sxs-lookup"><span data-stu-id="145ce-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="145ce-109">Wigner 標記法是直接衍生的。</span><span class="sxs-lookup"><span data-stu-id="145ce-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="145ce-110">回想一下，state $ \ket{0}_j $ 表示微調 orbital $j $ 是空的，而 $ \ket{1}_j $ 表示它已被佔用。</span><span class="sxs-lookup"><span data-stu-id="145ce-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="145ce-111">這表示 qubits 可以自然地儲存指定微調 orbital 的職業。</span><span class="sxs-lookup"><span data-stu-id="145ce-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="145ce-112">接著，$a ^ \ dagger_j \ket{0}_j = \ket{1}_j $ and $a ^ \ dagger_j \ket{1}_j = $0。</span><span class="sxs-lookup"><span data-stu-id="145ce-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="145ce-113">您可以輕鬆地確認 \begin{align} a ^ \ dagger_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}，\nonumber\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{bmatrix} = \frac{X_j-iY_j}{2}、\end{align}，其中 $X _j $ 和 $Y _j $ 是 Pauli $X $ 和-$Y $ 運算子，其作用於 qubit $j $。</span><span class="sxs-lookup"><span data-stu-id="145ce-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>
<span data-ttu-id="145ce-114">這表示針對單一微調 orbital，很容易就能根據量子電腦瞭解的單一矩陣來呈現建立和 annihilation 運算子。</span><span class="sxs-lookup"><span data-stu-id="145ce-114">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="145ce-115">請注意，雖然 $X $ 和 $Y $ 是單一 $a ^ \dagger $，而 $a $ 則不是。</span><span class="sxs-lookup"><span data-stu-id="145ce-115">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="145ce-116">我們稍後會看到這不會造成模擬的挑戰。</span><span class="sxs-lookup"><span data-stu-id="145ce-116">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="145ce-117">其中一個問題是，雖然上述的結構適用于單一微調 orbital，但有兩個或更多微調 orbitals 的系統會失敗。</span><span class="sxs-lookup"><span data-stu-id="145ce-117">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="145ce-118">由於 Fermions 是 antisymmetic，因此我們知道 $a ^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k 任何 dagger_j $ 和 $j $ 的 ^ \ $k $。</span><span class="sxs-lookup"><span data-stu-id="145ce-118">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="145ce-119">不過，$ $ \left （\frac{X_j-iY_j}{2}\right） \left （\frac{X_k-iY_k}{2}\right） = \left （\frac{X_k-iY_k}{2}\right） \left （\frac{X_j-iY_j}{2}\right）。</span><span class="sxs-lookup"><span data-stu-id="145ce-119">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="145ce-120">$ $ 換句話說，這兩個建立運算子不會視需要進行反上運算。</span><span class="sxs-lookup"><span data-stu-id="145ce-120">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="145ce-121">這可以在種粗糙的情況下，以簡單明瞭的方式來補救。</span><span class="sxs-lookup"><span data-stu-id="145ce-121">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="145ce-122">修正程式是要注意，Pauli 運算子自然地會進行反上運算。</span><span class="sxs-lookup"><span data-stu-id="145ce-122">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="145ce-123">特別是，$XZ =-ZX $ 和 $YZ =-ZY $。</span><span class="sxs-lookup"><span data-stu-id="145ce-123">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="145ce-124">因此，藉由將 $Z $ 運算子 interspersing 到運算子的結構中，我們可以模擬正確的反 commutation。</span><span class="sxs-lookup"><span data-stu-id="145ce-124">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="145ce-125">完整的結構如下所示：</span><span class="sxs-lookup"><span data-stu-id="145ce-125">The full construction is as follows:</span></span> 

<span data-ttu-id="145ce-126">\begin{align} ^ \ dagger_1 & = \left （\frac{X-iY}{2}\right） \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1，\\\\ ^ \ dagger_2 & = Z\otimes\left （\frac{X-iY}{2}\right） \otimes 1 \ otimes 1 \otimes \cdots \otimes 1，\\\\ ^ \ dagger_3 & = Z\otimes Z\otimes \left （\frac{X-iY}{2}\right） \otimes 1 \otimes \cdots \otimes 1，\\\\ & \vdots\\\\ a ^ \ dagger_N & = Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimesZ\otimes \left （\frac{X-iY}{2}\right）。</span><span class="sxs-lookup"><span data-stu-id="145ce-126">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="145ce-127">\label{eq： JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="145ce-127">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="145ce-128">在 Pauli 運算子方面，表達數位運算子（$n _j $）也很方便。</span><span class="sxs-lookup"><span data-stu-id="145ce-128">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="145ce-129">幸好，$Z $ operators （稱為 Wigner 字串）的字串會在進行這項替代之後取消。</span><span class="sxs-lookup"><span data-stu-id="145ce-129">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="145ce-130">在執行此程式（並重新叫用 $X _jY_j = iZ_j $）之後，我們 \begin{equation} n_j = a ^ \ dagger_j a_j = \frac{（1-Z_j）}{2}。</span><span class="sxs-lookup"><span data-stu-id="145ce-130">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="145ce-131">\end{equation}</span><span class="sxs-lookup"><span data-stu-id="145ce-131">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="145ce-132">在約旦中建立 Hamiltonians-Wigner 標記法</span><span class="sxs-lookup"><span data-stu-id="145ce-132">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="145ce-133">一旦叫用 Wigner 標記法，將 Hamiltonian 轉換為 Pauli 運算子的總和，就會直接向前邁進。</span><span class="sxs-lookup"><span data-stu-id="145ce-133">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="145ce-134">其中一種方式就是將 Fermionic Hamiltonian 中的每個 $a ^ \dagger $ 和 $a $ 運算子取代為上述 Pauli 運算子的字串。</span><span class="sxs-lookup"><span data-stu-id="145ce-134">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="145ce-135">當其中一個執行此替代時，Hamiltonian 中只有五個詞彙類別。</span><span class="sxs-lookup"><span data-stu-id="145ce-135">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="145ce-136">這五個類別會對應到不同的方法，我們可以在 Hamiltonian 的單一主體和兩個內文詞彙中挑選 $p、q $ 和 $p、q、r、s $。</span><span class="sxs-lookup"><span data-stu-id="145ce-136">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="145ce-137">這五個類別，在 $p > q > r > s $ 和實值 orbitals 的情況下，</span><span class="sxs-lookup"><span data-stu-id="145ce-137">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="145ce-138">\begin{align} h_ {pp} a_p ^ \dagger a_p & = \ sum_p \frac{h_ {pp}}{2}（1-Z_p）\\\\ h_ {pq} （a_p ^ \dagger a_q + a ^ \ dagger_q a_p） & = \frac{h_ {pq}}{2}\left （\ prod_ {j = q + 1} ^ {p-1} Z_j \right） \left （X_pX_q + Y_pY_q \right）\\\\ h_ {pqqp} n_p n_q & = \frac{h_ {pqqp}}{4}\left （1-Z_p-Z_q + Z_pZ_q \right）\\\\ H_ {pqqr} & = \frac{h_ {pqqr}}{2}\left （\ prod_ {j =r + 1} ^ {p-1} Z_j \right） \left （X_pX_r + Y_pY_r \right） \left （\frac{1-Z_q}{2}\right）\\\\ H_ {pqrs} & = \frac{h_ {pqrs}}{8}\ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big （XXXX-XXYY +XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big） \end{align}</span><span class="sxs-lookup"><span data-stu-id="145ce-138">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="145ce-139">雖然只是以手動方式產生這類 Hamiltonians 需要套用這些取代規則，但在大型分子驅使分子中可能會包含數百萬 Hamiltonian 詞彙，這是不可行的。</span><span class="sxs-lookup"><span data-stu-id="145ce-139">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="145ce-140">或者，我們可以根據 Hamiltonian 的 `FermionHamiltonian` 標記法，自動建立 `JordanWignerEncoding`。</span><span class="sxs-lookup"><span data-stu-id="145ce-140">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="145ce-141">在此表單中建立 Hamiltonians 之後，我們可以使用一系列的量子模擬演算法，將 $e ^ {-iHt} $ 所產生的 dynamics 編譯成一系列的基本閘道（在某些使用者可定義的容錯範圍內）。</span><span class="sxs-lookup"><span data-stu-id="145ce-141">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="145ce-142">我們會在演算法檔中討論量子模擬、qubitization 和 Trotter – Plat'home co. 公式的兩個最常用方法。</span><span class="sxs-lookup"><span data-stu-id="145ce-142">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="145ce-143">我們會在 Hamiltonian 模擬程式庫中提供這兩種方法的執行。</span><span class="sxs-lookup"><span data-stu-id="145ce-143">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>