---
title: 量子運算中的 qubit
description: 深入瞭解 qubits，這是量子運算的基本資訊單位。
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: 833c9649b7fbcf8b9fde62c37246b9345fe59a92
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630345"
---
# <a name="the-qubit"></a><span data-ttu-id="d0b82-103">Qubit</span><span class="sxs-lookup"><span data-stu-id="d0b82-103">The Qubit</span></span>

<span data-ttu-id="d0b82-104">就像是傳統運算中的基本資訊物件， [*qubits*](https://en.wikipedia.org/wiki/Qubit) （配量位）是量子運算中資訊的基本物件。</span><span class="sxs-lookup"><span data-stu-id="d0b82-104">Just as bits are the fundamental object of information in classical computing, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (quantum bits) are the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="d0b82-105">若要瞭解這種對應，讓我們來看一下最簡單的範例：單一 qubit。</span><span class="sxs-lookup"><span data-stu-id="d0b82-105">To understand this correspondence, let's look at the simplest example: a single qubit.</span></span>

## <a name="representing-a-qubit"></a><span data-ttu-id="d0b82-106">代表 Qubit</span><span class="sxs-lookup"><span data-stu-id="d0b82-106">Representing a Qubit</span></span>

<span data-ttu-id="d0b82-107">雖然位或二進位數位的值可以是 $0 $ 或 $1 $ ，但 qubit 可以有一個值，也就是其中一個或量子重迭的 $0 $ 和 $1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-107">While a bit, or binary digit, can have value either $0$ or $1$, a qubit can have a value that is either of these or a quantum superposition of $0$ and $1$.</span></span>

<span data-ttu-id="d0b82-108">單一 qubit 的狀態可以由單元標準的二維資料行向量描述，也就是說，其專案的大小平方必須加總為 $1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-108">The state of a single qubit can be described by a two-dimensional column vector of unit norm, that is, the magnitude squared of its entries must sum to $1$.</span></span> <span data-ttu-id="d0b82-109">這個向量（稱為「配量狀態向量」）會保存描述一個 qubit 的量子系統所需的所有資訊，就像單一位一樣，可以保存描述二進位變數狀態所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="d0b82-109">This vector, called the quantum state vector, holds all the information needed to describe the one-qubit quantum system just as a single bit holds all of the information needed to describe the state of a binary variable.</span></span>

<span data-ttu-id="d0b82-110">具有標準 $1 之實數或複數的任何二維資料行向量，都 $ 代表 qubit 所持有的可能量子狀態。</span><span class="sxs-lookup"><span data-stu-id="d0b82-110">Any two-dimensional column vector of real or complex numbers with norm $1$ represents a possible quantum state held by a qubit.</span></span> <span data-ttu-id="d0b82-111">因此 bmatrix } \\ \\ bmatrix } ，如果 $ qubit $ 和 $ \Alpha $ 是滿足 $ | \Beta | ^ 2 + | \Alpha | ^ 2 = 1 的複數 $ ，$ \begin{\Alpha \Beta \end{$ 代表 \Beta 狀態。</span><span class="sxs-lookup"><span data-stu-id="d0b82-111">Thus $\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ represents a qubit state if $\alpha$ and $\beta$ are complex numbers satisfying $|\alpha|^2 + |\beta|^2 = 1$.</span></span> <span data-ttu-id="d0b82-112">代表 qubits 的有效量子狀態向量範例包括</span><span class="sxs-lookup"><span data-stu-id="d0b82-112">Some examples of valid quantum state vectors representing qubits include</span></span>

<span data-ttu-id="d0b82-113">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } 、\begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } 、\begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } 、\begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ bmatrix } 、\text { 和} \begin{\frac{1 bmatrix } } {\sqrt{2 } } \\ \\ \frac{i } {\sqrt{2 } } \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="d0b82-113">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$</span></span>

<span data-ttu-id="d0b82-114">量子狀態向量 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ 和 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ 接受特殊角色。</span><span class="sxs-lookup"><span data-stu-id="d0b82-114">The quantum state vectors $\begin{bmatrix} 1 \\\\  0 \end{bmatrix}$ and $\begin{bmatrix} 0 \\\\  1 \end{bmatrix}$ take a special role.</span></span> <span data-ttu-id="d0b82-115">這兩個向量會形成向量空間的基礎，以描述 qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="d0b82-115">These two vectors form a basis for the vector space that describes the qubit's state.</span></span> <span data-ttu-id="d0b82-116">這表示任何量子狀態向量都可以撰寫為這些基礎向量的總和。</span><span class="sxs-lookup"><span data-stu-id="d0b82-116">This means that any quantum state vector can be written as a sum of these basis vectors.</span></span> <span data-ttu-id="d0b82-117">具體而言，vector $ \begin{ bmatrix } x \\ \\ y \end{ bmatrix } $ 可以撰寫為 $x \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } + y \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="d0b82-117">Specifically, the vector $\begin{bmatrix} x \\\\  y \end{bmatrix}$ can be written as $x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\  1 \end{bmatrix}$.</span></span> <span data-ttu-id="d0b82-118">雖然這些向量的任何旋轉都可做為 qubit 的有效基礎，但我們選擇以*計算為基礎*來進行這項工作的許可權。</span><span class="sxs-lookup"><span data-stu-id="d0b82-118">While any rotation of these vectors would serve as a perfectly valid basis for the qubit, we choose to privilege this one, by calling it the *computational basis*.</span></span>

<span data-ttu-id="d0b82-119">我們會採用這兩個配量狀態來對應傳統位的兩個狀態，亦即 $0 $ 和 $1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-119">We take these two quantum states to correspond to the two states of a classical bit, namely $0$ and $1$.</span></span> <span data-ttu-id="d0b82-120">標準慣例是選擇</span><span class="sxs-lookup"><span data-stu-id="d0b82-120">The standard convention is to choose</span></span>

<span data-ttu-id="d0b82-121">$ $0 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ，\qquad 1 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } ，$ $</span><span class="sxs-lookup"><span data-stu-id="d0b82-121">$$0\equiv \begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \qquad 1 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix},$$</span></span>

<span data-ttu-id="d0b82-122">雖然相反的選擇也同樣可行。</span><span class="sxs-lookup"><span data-stu-id="d0b82-122">although the opposite choice could equally well be taken.</span></span> <span data-ttu-id="d0b82-123">因此，不限數量的單一 qubit 量子狀態向量，只有兩個對應到傳統位的狀態;所有其他的配量狀態則否。</span><span class="sxs-lookup"><span data-stu-id="d0b82-123">Thus, out of the infinite number of possible single-qubit quantum state vectors, only two correspond to states of classical bits; all other quantum states do not.</span></span>

## <a name="measuring-a-qubit"></a><span data-ttu-id="d0b82-124">測量 Qubit</span><span class="sxs-lookup"><span data-stu-id="d0b82-124">Measuring a Qubit</span></span>

<span data-ttu-id="d0b82-125">既然我們已經知道如何呈現 qubit，我們可以藉由討論[*測量*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)概念來取得這些狀態所代表的部分直覺。</span><span class="sxs-lookup"><span data-stu-id="d0b82-125">Now that we know how to represent a qubit, we can gain some intuition for what these states represent by discussing the concept of [*measurement*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics).</span></span> <span data-ttu-id="d0b82-126">量測會對應到 qubit 上「尋找」的非正式想法，這會立即折迭量子狀態為兩個傳統狀態 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ 或 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $ 的其中一個。</span><span class="sxs-lookup"><span data-stu-id="d0b82-126">A measurement corresponds to the informal idea of “looking” at a qubit, which immediately collapses the quantum state to one of the two classical states  $\begin{bmatrix} 1 \\\\  0 \end{bmatrix}$ or  $\begin{bmatrix} 0 \\\\  1 \end{bmatrix}$.</span></span> <span data-ttu-id="d0b82-127">測量由量子狀態向量 $ \begin{\Alpha \Beta \end{$ 所指定的 qubit 時 bmatrix } \\ \\ bmatrix } ，我們會取得機率為 $ $ | \Alpha ^ 2 的結果 $0 | $ ，以及機率 $ 為 $ | \Beta ^ 2 的結果 $1 | $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-127">When a qubit given by the quantum state vector  $\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ is measured, we obtain the outcome $0$ with probability $|\alpha|^2$ and the outcome $1$  with probability $|\beta|^2$.</span></span> <span data-ttu-id="d0b82-128">在結果 $0 上 $ ，qubit 的新狀態是 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $; 在結果 $1 上， $ 其狀態為 $ \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="d0b82-128">On outcome $0$, the qubit's new state is $\begin{bmatrix} 1 \\\\  0 \end{bmatrix}$; on outcome $1$ its state is $\begin{bmatrix} 0 \\\\  1 \end{bmatrix}$.</span></span> <span data-ttu-id="d0b82-129">請注意， $ 由於正規化條件 $ | \Alpha | ^ 2 + | \Beta | ^ 2 = 1，這些機率會加總為 $1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-129">Note that these probabilities sum up to $1$ because of the normalization condition $|\alpha|^2 + |\beta|^2 = 1$.</span></span>

<span data-ttu-id="d0b82-130">測量的屬性也表示量子狀態向量的整體正負號無關。</span><span class="sxs-lookup"><span data-stu-id="d0b82-130">The properties of measurement also mean that the overall sign of the quantum state vector is irrelevant.</span></span> <span data-ttu-id="d0b82-131">否定向量相當於 $ \Alpha \rightarrow-\Alpha $ 和 $ \Beta \rightarrow-\Beta $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-131">Negating a vector is equivalent to $\alpha \rightarrow -\alpha$ and $\beta \rightarrow -\beta$.</span></span> <span data-ttu-id="d0b82-132">因為測量 $0 $ 和 $1 的機率 $ 取決於詞彙的大小平方，所以插入這類符號並不會改變機率。</span><span class="sxs-lookup"><span data-stu-id="d0b82-132">Because the probability of measuring $0$ and $1$ depends on the magnitude squared of the terms, inserting such signs does not change the probabilities whatsoever.</span></span> <span data-ttu-id="d0b82-133">這類階段通常稱為[ \`\` *全域階段*' '](https://en.wikipedia.org/wiki/Phase_factor) ，而更常見的格式可以是 $e ^ {i \phi } $，而不只是 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-133">Such phases are commonly called [\`\`*global phases*''](https://en.wikipedia.org/wiki/Phase_factor) and more generally can be of the form $e^{i \phi}$ rather than just $\pm 1$.</span></span>

<span data-ttu-id="d0b82-134">測量的最後一個重要屬性是，它不一定會損毀所有的量子狀態向量。</span><span class="sxs-lookup"><span data-stu-id="d0b82-134">A final important property of measurement is that it does not necessarily damage all quantum state vectors.</span></span> <span data-ttu-id="d0b82-135">如果我們以 state $ \begin{ bmatrix } 1 \\ \\ 0 \end{$ 的 qubit 開始 bmatrix } ，其對應于傳統狀態 $0 $ ，測量此狀態一律會產生結果 $0 $ ，並讓配量狀態維持不變。</span><span class="sxs-lookup"><span data-stu-id="d0b82-135">If we start with a qubit in the state $\begin{bmatrix} 1 \\\\  0 \end{bmatrix}$, which corresponds to the classical state $0$, measuring this state will always yield the outcome $0$ and leave the quantum state unchanged.</span></span> <span data-ttu-id="d0b82-136">就這一點而言，如果我們只有傳統位（也就是 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } $ 或 $ \begin{ bmatrix } 0 \\ \\ 1 \end{$ 的 qubits bmatrix } ），則測量不會損毀系統。</span><span class="sxs-lookup"><span data-stu-id="d0b82-136">In this sense, if we only have classical bits (i.e., qubits that are either $\begin{bmatrix}1 \\\\  0 \end{bmatrix}$ or $\begin{bmatrix}0 \\\\  1 \end{bmatrix}$) then measurement does not damage the system.</span></span> <span data-ttu-id="d0b82-137">這表示我們可以在量子電腦上複寫傳統資料，並將它操作，就像在傳統電腦上一樣。</span><span class="sxs-lookup"><span data-stu-id="d0b82-137">This means that we can replicate classical data and manipulate it on a quantum computer just as one could do on a classical computer.</span></span> <span data-ttu-id="d0b82-138">不過，若要一次儲存這兩個狀態的資訊，您可以將配量運算提升至傳統方式，並進一步 robs 量子電腦不加上複製量子資料的能力，另請參閱[不復制定理](https://en.wikipedia.org/wiki/No-cloning_theorem)。</span><span class="sxs-lookup"><span data-stu-id="d0b82-138">The ability, however, to store information in both states at once is what elevates quantum computing beyond what is possible classically and further robs quantum computers of the ability to copy quantum data indiscriminately, see also [the no-cloning theorem](https://en.wikipedia.org/wiki/No-cloning_theorem).</span></span>

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a><span data-ttu-id="d0b82-139">使用 Bloch 球體視覺化 Qubits 和轉換</span><span class="sxs-lookup"><span data-stu-id="d0b82-139">Visualizing Qubits and Transformations using the Bloch Sphere</span></span>

<span data-ttu-id="d0b82-140">Qubits 也可以使用[*Bloch 球體*](https://en.wikipedia.org/wiki/Bloch_sphere)標記法，以 $ 3 $ D 的形式呈現。</span><span class="sxs-lookup"><span data-stu-id="d0b82-140">Qubits may also be pictured in $3$D using the [*Bloch sphere*](https://en.wikipedia.org/wiki/Bloch_sphere) representation.</span></span>  <span data-ttu-id="d0b82-141">Bloch 球體提供一種方式來描述單一 qubit 的量子狀態（這是二維複雜向量），做為三維實值向量。</span><span class="sxs-lookup"><span data-stu-id="d0b82-141">The Bloch sphere gives a way of describing a single-qubit quantum state (which is a two-dimensional complex vector) as a three-dimensional real-valued vector.</span></span>  <span data-ttu-id="d0b82-142">這點很重要，因為它可讓我們將單一 qubit 狀態視覺化，並藉此開發可在瞭解多 qubit 狀態時很有價值的理由（其中可惜 Bloch 球體標記法會細分）。</span><span class="sxs-lookup"><span data-stu-id="d0b82-142">This is important because it allows us to visualize single-qubit states and thereby develop reasoning that can be invaluable in understanding multi-qubit states (where sadly the Bloch sphere representation breaks down).</span></span>  <span data-ttu-id="d0b82-143">Bloch 球體可以視覺化如下：</span><span class="sxs-lookup"><span data-stu-id="d0b82-143">The Bloch sphere can be visualized as follows:</span></span>

<!--- ![](.\media\bloch.svg){ width=50% } --->
<span data-ttu-id="d0b82-144">![Bloch 球體](~/media/concepts_bloch.png)</span><span class="sxs-lookup"><span data-stu-id="d0b82-144">![Bloch sphere](~/media/concepts_bloch.png)</span></span>

<span data-ttu-id="d0b82-145">此圖中的箭號顯示配量狀態向量的方向，而每個箭號的轉換都可以視為其中一個基線軸的旋轉。</span><span class="sxs-lookup"><span data-stu-id="d0b82-145">The arrows in this diagram show the direction in which the quantum state vector is pointing and each transformation of the arrow can be thought of as a rotation about one of the cardinal axes.</span></span>
<span data-ttu-id="d0b82-146">雖然將量子計算視為一系列旋轉是一個強大的直覺，但是使用此直覺來設計和描述演算法是很困難的。</span><span class="sxs-lookup"><span data-stu-id="d0b82-146">While thinking about a quantum computation as a sequence of rotations is a powerful intuition, it is challenging to use this intuition to design and describe algorithms.</span></span> <span data-ttu-id="d0b82-147">問 # 藉由提供描述這種旋轉的語言，來減輕這個問題。</span><span class="sxs-lookup"><span data-stu-id="d0b82-147">Q# alleviates this issue by providing a language for describing such rotations.</span></span>

## <a name="single-qubit-operations"></a><span data-ttu-id="d0b82-148">單一 Qubit 作業</span><span class="sxs-lookup"><span data-stu-id="d0b82-148">Single-Qubit Operations</span></span>

<span data-ttu-id="d0b82-149">量子電腦會套用一組通用的配量閘道來處理資料，以模擬配量狀態向量的任何旋轉。</span><span class="sxs-lookup"><span data-stu-id="d0b82-149">Quantum computers process data by applying a universal set of quantum gates that can emulate any rotation of the quantum state vector.</span></span>
<span data-ttu-id="d0b82-150">這種 universality 概念與傳統（也就是傳統）運算的 universality 概念類似，如果輸入位的每個轉換都可以使用有限長度的線路來執行，則會將閘道集視為通用。</span><span class="sxs-lookup"><span data-stu-id="d0b82-150">This notion of universality is akin to the notion of universality for traditional (i.e., classical) computing where a gate set is considered to be universal if every transformation of the input bits can be performed using a finite length circuit.</span></span>
<span data-ttu-id="d0b82-151">在量子運算中，我們允許在 qubit 上執行的有效轉換是單一轉換和測量。</span><span class="sxs-lookup"><span data-stu-id="d0b82-151">In quantum computing, the valid transformations that we are allowed to perform on a qubit are unitary transformations and measurement.</span></span>
<span data-ttu-id="d0b82-152">Adjoint 作業或複雜的共軛轉型對量子*運算*而言相當重要，因為它是用來反轉量子轉換的必要項。</span><span class="sxs-lookup"><span data-stu-id="d0b82-152">The *adjoint operation* or the complex conjugate transpose is of crucial importance to quantum computing because it is needed to invert quantum transformations.</span></span>
<span data-ttu-id="d0b82-153">問 # 藉由提供可自動將閘道序列編譯到其 adjoint 的方法來反映這一點，這可讓程式設計人員在許多情況下都不需要撰寫程式碼 adjoints。</span><span class="sxs-lookup"><span data-stu-id="d0b82-153">Q# reflects this by providing methods to automatically compile gate sequences to their adjoint, which saves the programmer from having to hand code adjoints in many cases.</span></span> <span data-ttu-id="d0b82-154">範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="d0b82-154">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

<span data-ttu-id="d0b82-155">雖然這是一個簡單的範例（如 <xref:microsoft.quantum.intrinsic.h> ）] 作業是自我 adjoint 的，但您可以看到這對於更複雜的 qubit 作業變得很有用。</span><span class="sxs-lookup"><span data-stu-id="d0b82-155">Although this is a trivial example (as the <xref:microsoft.quantum.intrinsic.h[!OP.NO-LOC(> operation is self-adjoint), you can see how this becomes invaluable for more complicated qubit operations.</span></span>
<span data-ttu-id="d0b82-156">如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="d0b82-156">For more information, see [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="d0b82-157">只有四個函式會將一個位對應到傳統電腦上的一個位。</span><span class="sxs-lookup"><span data-stu-id="d0b82-157">There are only four functions that map one bit to one bit on a classical computer.</span></span> <span data-ttu-id="d0b82-158">相反地，在量子電腦上的單一 qubit 上有無限數量的單一轉換。</span><span class="sxs-lookup"><span data-stu-id="d0b82-158">In contrast, there are an infinite number of unitary transformations on a single qubit on a quantum computer.</span></span> <span data-ttu-id="d0b82-159">因此，沒有一組有限的基本量子作業，稱為網[*關*](https://en.wikipedia.org/wiki/Quantum_logic_gate)，可以完全複寫量子運算中所允許的一組無限單一轉換。</span><span class="sxs-lookup"><span data-stu-id="d0b82-159">Therefore, no finite set of primitive quantum operations, called [*gates*](https://en.wikipedia.org/wiki/Quantum_logic_gate), can exactly replicate the infinite set of unitary transformations allowed in quantum computing.</span></span> <span data-ttu-id="d0b82-160">這表示與傳統運算不同的是，配量電腦無法完全使用有限數目的閘道來執行每個可能的量副程式。</span><span class="sxs-lookup"><span data-stu-id="d0b82-160">This means, unlike classical computing, it is impossible for a quantum computer to implement every possible quantum program exactly using a finite number of gates.</span></span> <span data-ttu-id="d0b82-161">因此，量子電腦不能在傳統電腦的相同意義上通用。</span><span class="sxs-lookup"><span data-stu-id="d0b82-161">Thus quantum computers cannot be universal in the same sense of classical computers.</span></span> <span data-ttu-id="d0b82-162">如此一來，當我們說出一組閘道是*通用*來進行配量運算時，我們實際上表示比傳統運算稍微弱一點。</span><span class="sxs-lookup"><span data-stu-id="d0b82-162">As a result, when we say that a set of gates is *universal* for quantum computing we actually mean something slightly weaker than we mean with classical computing.</span></span>
<span data-ttu-id="d0b82-163">針對 universality，我們需要配量電腦只在使用有限長度閘道序列的有限錯誤中，對每個單一矩陣進行*近似值*。</span><span class="sxs-lookup"><span data-stu-id="d0b82-163">For universality, we require that a quantum computer only *approximate* every unitary matrix within a finite error using a finite length gate sequence.</span></span>
<span data-ttu-id="d0b82-164">換句話說，如果有任何單一轉換可以從這個集合中的閘道乘積來撰寫，則一組閘道就是通用閘道集。</span><span class="sxs-lookup"><span data-stu-id="d0b82-164">In other words, a set of gates is a universal gate set if any unitary transformation can be approximately written as a product of gates from this set.</span></span> <span data-ttu-id="d0b82-165">針對任何指定的錯誤系結，我們需要有閘道 $G _ {1 } ，G_ {2 } ，\ldots，G_N $ 來自閘道集合，</span><span class="sxs-lookup"><span data-stu-id="d0b82-165">We require that for any prescribed error bound, there exist gates $G_{1}, G_{2},\ldots, G_N$ from the gate set such that</span></span>

<span data-ttu-id="d0b82-166">$ $ G_N G_ {N-1 } \cdots G_2 G_1 \Approx U. $ $</span><span class="sxs-lookup"><span data-stu-id="d0b82-166">$$ G_N G_{N-1} \cdots G_2 G_1 \approx U. $$</span></span>

<span data-ttu-id="d0b82-167">請注意，因為矩陣乘法的慣例是在此順序中的第一個閘道運算中，從右至左相乘，$G _N $ ，實際上是最後一個套用至量子狀態向量的作業。</span><span class="sxs-lookup"><span data-stu-id="d0b82-167">Note that because the convention for matrix multiplication is to multiply from right to left the first gate operation in this sequence, $G_N$, is actually the last one applied to the quantum state vector.</span></span> <span data-ttu-id="d0b82-168">更正式的說，這種閘道集是通用的，如果針對每個容錯 $ \epsilon>0 $ $G _1、\ldots G_N， $ 讓 $G _N \ldots G_1 和 $U 之間的距離 $ $ 最多為 $ \epsilon $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-168">More formally, we say that such a gate set is universal if for every error tolerance $\epsilon>0$ there exists $G_1,\ldots, G_N$ such that  the distance between $G_N\ldots G_1$ and $U$ is at most $\epsilon$.</span></span> <span data-ttu-id="d0b82-169">理想的情況是， $ 達到 $ \epsilon 的這個距離所需的 $N 值 $ 應該使用 $ 1/\ epsilon 來調整 poly-logarithmically $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-169">Ideally the value of $N$ needed to reach this distance of $\epsilon$ should scale poly-logarithmically with $1/\epsilon$.</span></span>

<span data-ttu-id="d0b82-170">這種通用閘道集在實務上看起來是什麼樣子？</span><span class="sxs-lookup"><span data-stu-id="d0b82-170">What does such a universal gate set look like in practice?</span></span>  <span data-ttu-id="d0b82-171">針對單一 qubit 閘道所設定的最簡單的通用閘道是由兩個閘道所組成： Hadamard 閘道 $H 和所謂的 $ $T 網 $ 關（也稱為 $ \ pi/8 網 $ 關）：</span><span class="sxs-lookup"><span data-stu-id="d0b82-171">The simplest such universal gate set for single-qubit gates consists of only two gates: the Hadamard gate $H$ and the so-called $T$-gate (also known as the $\pi/8$ gate):</span></span>

<span data-ttu-id="d0b82-172">$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } ，\qquad T = \begin{ bmatrix } 1 & 0 \\ \\ 0 & e ^ {i \ pi/4 } \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-172">$$ H=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 & 1 \\\\  1 &-1  \end{bmatrix},\qquad T=\begin{bmatrix} 1 & 0 \\\\  0 & e^{i\pi/4} \end{bmatrix}.</span></span>
$$

<span data-ttu-id="d0b82-173">不過，針對與量子錯誤更正相關的實際原因，考慮較大的閘道集（也就是可以使用 $H 和 $T 產生的）可能會更方便 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-173">However, for practical reasons related to quantum error correction it can be more convenient to consider a larger gate set, namely one that can be generated using $H$ and $T$.</span></span>
<span data-ttu-id="d0b82-174">我們可以將配量管制分類成兩個類別： Clifford 閘道和 $T 網 $ 關。</span><span class="sxs-lookup"><span data-stu-id="d0b82-174">We can classify the quantum gates into two categories: Clifford gates and the $T$-gate.</span></span>
<span data-ttu-id="d0b82-175">這種細分方式很有用，因為在許多量子錯誤更正配置中，所謂的 Clifford 閘道很容易實行，也就是說，它們在作業和 qubits 方面都只需要很少的資源來執行錯誤 tolerantly，而非 Clifford 的閘道則在需要容錯時相當昂貴。</span><span class="sxs-lookup"><span data-stu-id="d0b82-175">This subdivision is useful because in many quantum error correction schemes the so-called Clifford gates are easy to implement, that is they require very few resources in terms of operations and qubits to implement fault tolerantly, whereas non-Clifford gates are quite costly when requiring fault tolerance.</span></span> <span data-ttu-id="d0b82-176">[預設包含在 Q # 中](xref:microsoft.quantum.libraries.standard.prelude)的一組標準單一 qubit Clifford 閘道，包括</span><span class="sxs-lookup"><span data-stu-id="d0b82-176">The standard set of single-qubit Clifford gates, [included by default in Q#](xref:microsoft.quantum.libraries.standard.prelude), include</span></span>

<span data-ttu-id="d0b82-177">$ $ H = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 & 1 \\ \\ 1 &-1 \end{ bmatrix } ，\qquad S = \begin{ bmatrix } 1 & 0 \\ \\ 0 & i \end{ bmatrix } = T ^ 2，\qquad X = \begin{ bmatrix } 0 &1 \\ \\ 1 & 0 \end{ bmatrix } = HT ^ 4 小時，$ $</span><span class="sxs-lookup"><span data-stu-id="d0b82-177">$$ H=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 & 1 \\\\  1 &-1  \end{bmatrix} ,\qquad S =\begin{bmatrix} 1 & 0 \\\\  0 & i \end{bmatrix}= T^2,\qquad X=\begin{bmatrix} 0 &1 \\\\  1& 0 \end{bmatrix}= HT^4H, $$</span></span>

<span data-ttu-id="d0b82-178">$ $ Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \END{ bmatrix } = T ^ 2HT ^ 4 HT ^ 6，\qquad Z = \begin{ bmatrix } 1&0 \\\\ 0 & -1 \end{ bmatrix } = T ^ 4。</span><span class="sxs-lookup"><span data-stu-id="d0b82-178">$$ Y = \begin{bmatrix} 0 & -i \\\\  i & 0 \end{bmatrix}=T^2HT^4  HT^6, \qquad Z=\begin{bmatrix}1&0\\\\ 0&-1 \end{bmatrix}=T^4.</span></span>
$$

<span data-ttu-id="d0b82-179">這裡的作業 $X $ 、$Y $ 和 $Z $ 特別常使用，而且在其 creator Wolfgang Pauli 之後會命名為[*Pauli operators*](https://en.wikipedia.org/wiki/Pauli_matrices) 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-179">Here the operations $X$, $Y$ and $Z$ are used especially frequently and are named [*Pauli operators*](https://en.wikipedia.org/wiki/Pauli_matrices) after their creator Wolfgang Pauli.</span></span>
<span data-ttu-id="d0b82-180">與非 Clifford 閘道（$T 網 $ 關）結合，這些作業可以組成，以近似單一 qubit 上的任何單一轉換。</span><span class="sxs-lookup"><span data-stu-id="d0b82-180">Together with the non-Clifford gate (the $T$-gate), these operations can be composed to approximate any unitary transformation on a single qubit.</span></span>

<span data-ttu-id="d0b82-181">如需這些作業的詳細資訊、其 Bloch 球體標記法和 Q # 實作為，請參閱[內部作業和函數](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions)。</span><span class="sxs-lookup"><span data-stu-id="d0b82-181">For more information on these operations, their Bloch sphere representations and Q# implementations, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).</span></span>

<span data-ttu-id="d0b82-182">如需如何從這些基本專案建立單一轉換的範例，上述 Bloch 球體中所示的三個轉換對應至閘道序列 $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \mapsto HZH \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } $。</span><span class="sxs-lookup"><span data-stu-id="d0b82-182">As an example of how unitary transformations can be built from these primitives, the three transformations pictured in the Bloch spheres above correspond to the gate sequence $\begin{bmatrix} 1 \\\\  0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}$.</span></span>

<span data-ttu-id="d0b82-183">雖然先前的構成最常用的基本閘道，可描述堆疊邏輯層級的作業（請將邏輯層級視為配量演算法的層級），但在演算法層級上考慮較少的基本作業通常很方便，例如更接近函數描述層級的作業。</span><span class="sxs-lookup"><span data-stu-id="d0b82-183">While the previous constitute the most popular primitive gates for describing operations on the logical level of the stack (think of the logical level as the level of the quantum algorithm), it is often convenient to consider less basic operations at the algorithmic level, for example operations closer to a function description level.</span></span> <span data-ttu-id="d0b82-184">幸運的是，問 # 也有可用來執行較高層級 unitaries 的方法，而這可讓您在不明確分解所有專案到 Clifford 和 $T 閘道的情況下，執行高階演算法 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-184">Fortunately, Q# also has methods available for implementing higher-level unitaries, which in turn allow high-level algorithms to be implemented without explicitly decomposing everything down to Clifford and $T$-gates.</span></span>

<span data-ttu-id="d0b82-185">最簡單的這種基本類型就是單一的 qubit 旋轉。</span><span class="sxs-lookup"><span data-stu-id="d0b82-185">The simplest such primitive is the single qubit-rotation.</span></span> <span data-ttu-id="d0b82-186">通常會考慮三個單一 qubit 旋轉： $R _x $ 、$R _y $ 和 $R _z $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-186">Three single-qubit rotations are typically considered: $R_x$, $R_y$ and $R_z$.</span></span> <span data-ttu-id="d0b82-187">例如，若要以視覺化方式呈現旋轉 $R _x （\theta） $ 的動作，請想像以 Bloch 球體的 $X 軸方向來指向您的右方 $ ，並透過 $ theta/2 弧度的角度旋轉向量 $ 。</span><span class="sxs-lookup"><span data-stu-id="d0b82-187">To visualize the action of the rotation $R_x(\theta)$, for example, imagine pointing your right thumb along the direction of the $x$-axis of the Bloch sphere and rotating the vector with your hand through an angle of $\theta/2$ radians.</span></span> <span data-ttu-id="d0b82-188">這項令人困惑 $2 的原因是，在 $ 繪製于 Bloch 球體上時，垂直向量是 $ 180 ^ \circ $ ，但實際是 $ 90 ^ \circ 度，但 $ 幾何除外。</span><span class="sxs-lookup"><span data-stu-id="d0b82-188">This confusing factor of $2$ arises from the fact that orthogonal vectors are $180^\circ$ apart when plotted on the Bloch sphere, yet are actually $90^\circ$ degrees apart geometrically.</span></span> <span data-ttu-id="d0b82-189">對應的單一矩陣如下：</span><span class="sxs-lookup"><span data-stu-id="d0b82-189">The corresponding unitary matrices are:</span></span>

<span data-ttu-id="d0b82-190">\begin{align *} &R_z （\theta） = e ^ {-i\theta z/2 } = \begin{ bmatrix } e ^ {-i \ theta/2 } & 0 \\\\ 0 & e ^ {i \ theta/2 } \end{ bmatrix } ， \\ \\ &R_x （\theta） = e ^ {-i\theta x/2 } = HR_z （\theta） H = \begin{ bmatrix } \cos （\ theta/2） &-i\sin （\ theta/2） \\ \\ -i\sin （\ theta/2） & \cos （\ theta/2） \end{ bmatrix } ， \\ \\ &R_y （\theta） = e ^ {-i\theta y/2 } = SHR_z （\theta） HS ^ \dagger = \begin{ bmatrix } \cos （\ theta/2） &-\sin （\ theta/2） \\ \\ \sin （\ theta/2） & \cos （\ theta/2） \end{ bmatrix } . \end{align*}</span><span class="sxs-lookup"><span data-stu-id="d0b82-190">\begin{align *} &R_z(\theta) = e^{-i\theta Z/2} = \begin{bmatrix} e^{-i\theta/2} & 0\\\\  0& e^{i\theta/2} \end{bmatrix}, \\\\ &R_x(\theta) = e^{-i\theta X/2} = HR_z(\theta)H = \begin{bmatrix} \cos(\theta/2) & -i\sin(\theta/2)\\\\  -i\sin(\theta/2) & \cos(\theta/2) \end{bmatrix}, \\\\ &R_y(\theta) = e^{-i\theta Y/2} = SHR_z(\theta)HS^\dagger = \begin{bmatrix} \cos(\theta/2) & -\sin(\theta/2)\\\\  \sin(\theta/2) & \cos(\theta/2) \end{bmatrix}. \end{align*}</span></span>

<span data-ttu-id="d0b82-191">就像任何三個旋轉可以合併在一起，以在三個維度中執行任意旋轉，可以從 Bloch 球體標記法看出，任何單一矩陣也可以撰寫成三種旋轉的序列。</span><span class="sxs-lookup"><span data-stu-id="d0b82-191">Just as any three rotations can be combined together to perform an arbitrary rotation in three dimensions, it can be seen from the Bloch sphere representation that any unitary matrix can be written as a sequence of three rotations as well.</span></span> <span data-ttu-id="d0b82-192">具體而言，針對每個單一矩陣 $U $ 存在 $ \Alpha、\Beta、\gamma、\delta， $ 因此 $U = e ^ {i \alpha } R_x （\Beta） R_z （\gamma） R_x （\delta） $。</span><span class="sxs-lookup"><span data-stu-id="d0b82-192">Specifically, for every unitary matrix $U$ there exists $\alpha,\beta,\gamma,\delta$ such that $U= e^{i\alpha} R_x(\beta)R_z(\gamma)R_x(\delta)$.</span></span> <span data-ttu-id="d0b82-193">因此 $R _z （\theta） $ 和 $H $ 也會構成通用閘道集，因為 $ \theta $ 可以接受任何值。</span><span class="sxs-lookup"><span data-stu-id="d0b82-193">Thus $R_z(\theta)$ and $H$ also form a universal gate set although it is not a discrete set because $\theta$ can take any value.</span></span> <span data-ttu-id="d0b82-194">基於這個理由，以及由於配量模擬中的應用程式，這類連續閘道對於量子計算很重要，尤其是在量子演算法設計層級。</span><span class="sxs-lookup"><span data-stu-id="d0b82-194">For this reason, and due to applications in quantum simulation, such continuous gates are crucial for quantum computation, especially at the quantum algorithm design level.</span></span> <span data-ttu-id="d0b82-195">為了達到容錯硬體的執行，最終會將它們編譯成緊密接近這些旋轉的離散閘道序列。</span><span class="sxs-lookup"><span data-stu-id="d0b82-195">To achieve fault-tolerant hardware implementation, they will ultimately be compiled into discrete gate sequences that closely approximate these rotations.</span></span>
