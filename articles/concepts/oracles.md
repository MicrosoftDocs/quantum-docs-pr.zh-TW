---
title: 量子 Oracle
description: 瞭解如何使用並定義用來做為其他演算法輸入的「量子 oracles」、「黑色箱」作業。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630324"
---
# <a name="quantum-oracles"></a><span data-ttu-id="c6882-103">量子 Oracles</span><span class="sxs-lookup"><span data-stu-id="c6882-103">Quantum Oracles</span></span>

<span data-ttu-id="c6882-104">Oracle $O $ 是「黑箱」作業，用來做為另一個演算法的輸入。</span><span class="sxs-lookup"><span data-stu-id="c6882-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="c6882-105">通常，這類作業會使用傳統函式來定義 $f： \\ {0，1 \\ } ^ n \to \\ {0，1 \\ } ^ m， $ 會採用 $n $ 位的二進位輸入，並產生 $m $ 位二進位輸出。</span><span class="sxs-lookup"><span data-stu-id="c6882-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="c6882-106">若要這麼做，請考慮特定的二進位輸入 $x = （x_ {0 } ，x_ {1 } ，\dots ..，x_ {n-1 } ） $。</span><span class="sxs-lookup"><span data-stu-id="c6882-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="c6882-107">我們可以將 qubit 狀態標示為 $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1} \otimes \cdots \otimes \ket{ } x_ {n-1 } } $。</span><span class="sxs-lookup"><span data-stu-id="c6882-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="c6882-108">我們可能會先嘗試定義 $O， $ 讓 $O \ket {x } = \ket{f （x）} $，但這有幾個問題。</span><span class="sxs-lookup"><span data-stu-id="c6882-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="c6882-109">首先，$f $ 可能會有不同大小的輸入和輸出（$n \ne m $ ），因此套用 $O $ 會變更註冊中的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="c6882-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="c6882-110">第二，即使 $n = m $ ，函式也可能無法反轉：如果某些 $x \ne y 的 $f （x） = f （y） $ $ ，則 $O \ket {x } = o \ket {y } $，但 $O ^ \dagger O \ket {x } \ne O ^ \dagger O \ket {y } $。</span><span class="sxs-lookup"><span data-stu-id="c6882-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="c6882-111">這表示我們無法 $O ^ \dagger 來建立 adjoint 作業 $ ，而且 oracles 必須為其定義 adjoint。</span><span class="sxs-lookup"><span data-stu-id="c6882-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="c6882-112">依其對計算基礎狀態的影響來定義 oracle</span><span class="sxs-lookup"><span data-stu-id="c6882-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="c6882-113">我們可以藉由引進 $m qubits 的第二個暫存器來處理這兩個問題， $ 以保存我們的解答。</span><span class="sxs-lookup"><span data-stu-id="c6882-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="c6882-114">然後，我們將定義 oracle 對所有計算基礎狀態的效果：針對所有 $x \in \\ {0，1 \\ } ^ n $ and $y \in \\ {0，1 \\ } ^ m $ ，</span><span class="sxs-lookup"><span data-stu-id="c6882-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="c6882-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-115">$$ \begin{align}</span></span>
    <span data-ttu-id="c6882-116">O （\ket{x } \otimes \ket{y } ） = \ket{x } \otimes \ket{y \oplus f （x）}。</span><span class="sxs-lookup"><span data-stu-id="c6882-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="c6882-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-117">\end{align}</span></span>
$$

<span data-ttu-id="c6882-118">現在 $O = O ^ \dagger $ by 結構，因此我們解決了先前的兩個問題。</span><span class="sxs-lookup"><span data-stu-id="c6882-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="c6882-119">若要查看 $O = O ^ {\dagger } $，請注意 $O ^ 2 = \boldone， $ 因為 $a \oplus b \oplus b = a $ 適用于所有 $a、b \in \{ 0、1 \} $。</span><span class="sxs-lookup"><span data-stu-id="c6882-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="c6882-120">因此，$O \ket{x } \ket{y \oplus f （x）} = \ket{x } \ket{y \oplus f （x） \oplus f （x）} = \ket{x } \ket{y } $。</span><span class="sxs-lookup"><span data-stu-id="c6882-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="c6882-121">重要的是，以這種方式為每個計算基礎狀態 $ \ket{x \ket{y $ 定義 oracle， } } 也會定義 $O $ 對任何其他狀態的作用。</span><span class="sxs-lookup"><span data-stu-id="c6882-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="c6882-122">這是從 $O $ （例如所有的配量作業）開始，在其作用的狀態下是線性的。</span><span class="sxs-lookup"><span data-stu-id="c6882-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="c6882-123">請考慮 Hadamard 作業，例如，它是由 $H \ket{0 } = \ket { +} $ 和 $H \ket{1 } = \ket { -} $ 所定義。</span><span class="sxs-lookup"><span data-stu-id="c6882-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="c6882-124">如果想知道 $H 如何 $ 在 $ \ket { +} $ 上運作，我們可以使用該 $H $ 是線性的。</span><span class="sxs-lookup"><span data-stu-id="c6882-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="c6882-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-125">$$ \begin{align}</span></span>
<span data-ttu-id="c6882-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } H （\ket{0 } + \ket{1 } ） = \frac{1 } {\sqrt{2 } } （H \ket {0 } + H \ket {1 } ） \\ \\ & = \frac{1 } {\sqrt{2 } } （\ket { +} + \ket { -}） = \frac12 （\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ） = \ket{0 } 。</span><span class="sxs-lookup"><span data-stu-id="c6882-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="c6882-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-127">\end{align}</span></span>
$$

<span data-ttu-id="c6882-128">在定義 oracle $O 的情況下 $ ，我們可以同樣地使用 { $n + m qubits 上的任何 state $ \ket \psi } $ $ 可以撰寫為</span><span class="sxs-lookup"><span data-stu-id="c6882-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="c6882-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-129">$$ \begin{align}</span></span>
<span data-ttu-id="c6882-130">\ket { \psi } & = \ sum_ {x \in \\ {0，1 \\ } ^ n，y \in \\ {0，1 \\ } ^ m } \Alpha （x，y） \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="c6882-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="c6882-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-131">\end{align}</span></span>
$$

<span data-ttu-id="c6882-132">其中，$ \Alpha： \\ {0，1 \\ } ^ n \times \\ {0，1 \\ } ^ m \to \mathbb{C } $ 代表 state $ \ket { \psi $ 的係數 } 。</span><span class="sxs-lookup"><span data-stu-id="c6882-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="c6882-133">因此，</span><span class="sxs-lookup"><span data-stu-id="c6882-133">Thus,</span></span>

<span data-ttu-id="c6882-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-134">$$ \begin{align}</span></span>
<span data-ttu-id="c6882-135">O \ket { \psi } & = O \ sum_ {x \in \\ {0，1 \\ } ^ n，y \in \\ {0，1 \\ } ^ m } \Alpha （x，y） \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0，1 \\ } ^ n，y \in \\ {0，1 \\ } ^ m } \Alpha （x，y） O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0，1 \\ } ^ n，y \in \\ {0，1} \\ ^ m } \Alpha （x，y） \ket{x \ket{y } \oplus f （x）}。</span><span class="sxs-lookup"><span data-stu-id="c6882-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="c6882-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="c6882-137">階段 oracles</span><span class="sxs-lookup"><span data-stu-id="c6882-137">Phase oracles</span></span>
<span data-ttu-id="c6882-138">或者，我們可以根據 $O 的輸入套用階段，將 $f 編碼 $ 成 oracle $O $ _phase_ $ 。</span><span class="sxs-lookup"><span data-stu-id="c6882-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="c6882-139">例如，我們可能會定義 $O $ ，例如 $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="c6882-140">O \ket{x } = （-1） ^ {f （x）} \ket{x } 。</span><span class="sxs-lookup"><span data-stu-id="c6882-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="c6882-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-141">\end{align}</span></span>
<span data-ttu-id="c6882-142">$ $ 如果 oracle 階段在一開始是以計算基礎狀態 $ \ket{x } $ 進行操作，則此階段為全域階段，因此無法觀察。</span><span class="sxs-lookup"><span data-stu-id="c6882-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="c6882-143">但是，如果套用至重迭或做為受控制的作業，這類 oracle 可能是非常強大的資源。</span><span class="sxs-lookup"><span data-stu-id="c6882-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="c6882-144">例如，假設有一個階段 orcale $O _f $ 單一 qubit 函數 $f $ 。</span><span class="sxs-lookup"><span data-stu-id="c6882-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="c6882-145">然後，$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="c6882-146">O_f \ket { +} & = O_f （\ket{0 } + \ket{1 } ）/\sqrt{2 } \\ \\ & = （（-1） ^ {f （0）} \ket{0 } + （-1） ^ {f （1）} \ket{1 } ）/\sqrt{2 } \\ \\ & = （-1） ^ {f （0）} （\ket{0 } + （-1） ^ {f （1）-f （0）} \ket{1 } ）/\sqrt{2 } \\ \\ & = （-1） ^ {f （0）} Z ^ {f （0）-f （1）} \ket { +}。</span><span class="sxs-lookup"><span data-stu-id="c6882-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="c6882-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c6882-147">\end{align}</span></span>
$$

<span data-ttu-id="c6882-148">更常見的情況是，可以放寬了 oracles 的兩個觀點來代表傳回實數的傳統函式，而不只是單一位。</span><span class="sxs-lookup"><span data-stu-id="c6882-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="c6882-149">選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用此 oracle。</span><span class="sxs-lookup"><span data-stu-id="c6882-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="c6882-150">例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依賴以第一種方式實作為的 oracle，而[Grover 的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依賴以第二種方式實施的 oracle。</span><span class="sxs-lookup"><span data-stu-id="c6882-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="c6882-151">如需更多詳細資訊，建議您在[Gilyén *et al*1711.00465](https://arxiv.org/abs/1711.00465)中進行討論。</span><span class="sxs-lookup"><span data-stu-id="c6882-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
