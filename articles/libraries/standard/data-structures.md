---
title: 'Q # 標準程式庫-資料結構 |Microsoft Docs'
description: 'Q # 標準程式庫-資料結構'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e8b28561f1aba37cb5bf41c6176386d19bfacf06
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184503"
---
# <a name="data-structures-and-modeling"></a><span data-ttu-id="b9a5a-103">資料結構和模型化</span><span class="sxs-lookup"><span data-stu-id="b9a5a-103">Data Structures and Modeling</span></span> #

## <a name="classical-data-structures"></a><span data-ttu-id="b9a5a-104">傳統資料結構</span><span class="sxs-lookup"><span data-stu-id="b9a5a-104">Classical Data Structures</span></span> ##

<span data-ttu-id="b9a5a-105">除了用來表示量子概念的使用者定義型別之外，canon 也提供作業、函式和型別，來處理用於控制量子系統的傳統資料。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-105">Along with user-defined types for representing quantum concepts, the canon also provides operations, functions, and types for working with classical data used in the control of quantum systems.</span></span>
<span data-ttu-id="b9a5a-106">例如，<xref:microsoft.quantum.arrays.reversed> 函數會採用陣列做為輸入，並以反向順序傳回相同的陣列。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-106">For instance, the <xref:microsoft.quantum.arrays.reversed> function takes an array as input and returns the same array in reverse order.</span></span>
<span data-ttu-id="b9a5a-107">然後，這可以在 `Qubit[]` 類型的陣列上使用，以避免在整數的量子表示之間進行轉換時，必須套用不必要的 $ \operatorname{SWAP} $ 閘道。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-107">This can then be used on an array of type `Qubit[]` to avoid having to apply unnecessary $\operatorname{SWAP}$ gates when converting between quantum representations of integers.</span></span>
<span data-ttu-id="b9a5a-108">同樣地，我們在上一節中看到，`(Int, Int -> T)` 的表單類型可用於代表隨機存取集合，因此 <xref:microsoft.quantum.arrays.lookupfunction> 函式提供了從陣列類型來建立這類類型的 convienent 方式。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-108">Similarly, we saw in the previous section that types of the form `(Int, Int -> T)` can be useful for representing random access collections, so the <xref:microsoft.quantum.arrays.lookupfunction> function provides a convienent way of constructing such types from array types.</span></span>

### <a name="pairs"></a><span data-ttu-id="b9a5a-109">形式</span><span class="sxs-lookup"><span data-stu-id="b9a5a-109">Pairs</span></span> ###

<span data-ttu-id="b9a5a-110">Canon 支援配對的功能樣式表示法，藉由解構來補充存取元組：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-110">The canon supports functional-style notation for pairs, complementing accessing tuples by deconstruction:</span></span>

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a><span data-ttu-id="b9a5a-111">陣列</span><span class="sxs-lookup"><span data-stu-id="b9a5a-111">Arrays</span></span> ###

<span data-ttu-id="b9a5a-112">Canon 提供數個函式來運算元組。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-112">The canon provides several functions for manipulating arrays.</span></span>
<span data-ttu-id="b9a5a-113">這些函式具有型別參數化，因此可以與任何 Q # 型別的陣列搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-113">These functions are type-parameterized, and thus can be used with arrays of any Q# type.</span></span>
<span data-ttu-id="b9a5a-114">例如，<xref:microsoft.quantum.arrays.reversed> 函式會傳回新的陣列，其專案是從其輸入的反向順序。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-114">For instance, the <xref:microsoft.quantum.arrays.reversed> function returns a new array whose elements are in reverse order from its input.</span></span>
<span data-ttu-id="b9a5a-115">這可以用來變更呼叫作業時，配量暫存器的表示方式：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-115">This can be used to change how a quantum register is represented when calling operations:</span></span>

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

<span data-ttu-id="b9a5a-116">同樣地，<xref:microsoft.quantum.arrays.subarray> 函數可以用來重新排列或接受陣列元素的子集：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-116">Similarly, the <xref:microsoft.quantum.arrays.subarray> function can be used to reorder or take subsets of the elements of an array:</span></span>

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

<span data-ttu-id="b9a5a-117">結合流量控制時，陣列操作功能（例如 <xref:microsoft.quantum.arrays.zip>）可以提供強大的方式來表達量副程式：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-117">When combined with flow control, array manipulation functions such as <xref:microsoft.quantum.arrays.zip> can provide a powerful way to express quantum programs:</span></span>

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a><span data-ttu-id="b9a5a-118">Oracles</span><span class="sxs-lookup"><span data-stu-id="b9a5a-118">Oracles</span></span> ##

<span data-ttu-id="b9a5a-119">在[階段估計](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm)和[振幅放大](https://en.wikipedia.org/wiki/Amplitude_amplification)文獻中，oracle 的概念通常會出現。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-119">In the [phase estimation](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) and [amplitude amplification](https://en.wikipedia.org/wiki/Amplitude_amplification) literature the concept of an oracle appears frequently.</span></span>
<span data-ttu-id="b9a5a-120">這裡的 oracle 一詞指的是黑箱量子副程式，它會在一組 qubits 上運作，並以階段傳回答案。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-120">Here the term oracle refers to a blackbox quantum subroutine that acts upon a set of qubits and returns the answer as a phase.</span></span>
<span data-ttu-id="b9a5a-121">您通常可以將此副程式視為接受 oracle 的量子演算法輸入，除了其他一些參數之外，也會套用一系列的量子作業，並將此量子副程式的呼叫視為基本閘道。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-121">This subroutine often can be thought of as an input to a quantum algorithm that accepts the oracle, in addition to some other parameters, and applies a series of quantum operations and treating a call to this quantum subroutine as if it were a fundamental gate.</span></span>
<span data-ttu-id="b9a5a-122">很明顯地，若要實際執行較大的演算法，必須提供 oracle 的實體分解，但不需要這樣的分解，就能瞭解呼叫 oracle 的演算法。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-122">Obviously, in order to actually implement the larger algorithm a concrete decomposition of the oracle into fundamental gates must be provided but such a decomposition is not needed in order to understand the algorithm that calls the oracle.</span></span>
<span data-ttu-id="b9a5a-123">在 Q # 中，此抽象概念是藉由使用該作業為第一個類別的值來表示，因此作業可以用黑箱的方式傳遞至配量演算法的實現。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-123">In Q#, this abstraction is represented by using that operations are first-class values, such that operations can be passed to implementations of quantum algorithms in a black-box manner.</span></span>
<span data-ttu-id="b9a5a-124">此外，使用者定義的型別也用來以型別安全的方式標記不同的 oracle 標記法，因而難以意外人們不同種類的黑色方塊作業。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-124">Moreover, user-defined types are used to label the different oracle representations in a type-safe way, making it difficult to accidently conflate different kinds of black box operations.</span></span>

<span data-ttu-id="b9a5a-125">這類 oracles 會出現在許多不同的內容中，包括著名的範例，例如[Grover 的搜尋](https://en.wikipedia.org/wiki/Grover%27s_algorithm)和量子模擬演算法。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-125">Such oracles appear in a number of different contexts, including famous examples such as [Grover's search](https://en.wikipedia.org/wiki/Grover%27s_algorithm) and quantum simulation algorithms.</span></span>
<span data-ttu-id="b9a5a-126">在這裡，我們只著重在兩個應用程式所需的 oracles：振幅放大和階段估計。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-126">Here we focus on the oracles needed for just two applications: amplitude amplification and phase estimation.</span></span>
<span data-ttu-id="b9a5a-127">我們會先討論振幅放大 oracles，再 proceding 至階段估計。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-127">We will first discuss amplitude amplification oracles before proceding to phase estimation.</span></span>

### <a name="amplitude-amplification-oracles"></a><span data-ttu-id="b9a5a-128">振幅放大 Oracles</span><span class="sxs-lookup"><span data-stu-id="b9a5a-128">Amplitude Amplification Oracles</span></span> ###

<span data-ttu-id="b9a5a-129">「波幅放大」演算法的目標，是要藉由套用一系列的狀態反射來執行初始狀態與最終狀態之間的旋轉。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-129">The amplitude amplification algorithm aims to perform a rotation between an initial state and a final state by applying a sequence of reflections of the state.</span></span>
<span data-ttu-id="b9a5a-130">為了讓演算法運作，它需要這兩種狀態的規格。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-130">In order for the algorithm to function, it needs a specification of both of these states.</span></span>
<span data-ttu-id="b9a5a-131">這些規格是由兩個 oracles 所提供。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-131">These specifications are given by two oracles.</span></span>
<span data-ttu-id="b9a5a-132">這些 oracles 的工作方式是將輸入分成兩個空格：「目標」子空間和「初始」子空間。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-132">These oracles work by breaking the inputs into two spaces, a "target" subspace and an "initial" subspace.</span></span>
<span data-ttu-id="b9a5a-133">Oracles 會識別這類 subspaces，類似于 Pauli 運算子如何藉由將 $ \pm $1 階段套用至這些空格，來識別兩個空格。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-133">The oracles identify such subspaces, similar to how Pauli operators identify two spaces, by applying a $\pm 1$ phase to these spaces.</span></span>
<span data-ttu-id="b9a5a-134">主要的差別在於，這些空間在此應用程式中不需要是半個空格。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-134">The main difference is that these spaces need not be half-spaces in this application.</span></span>
<span data-ttu-id="b9a5a-135">另請注意，這兩個 subspaces 通常不是互斥的，因為有兩個空間成員的向量。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-135">Also note that these two subspaces are not usually mutually exclusive: there will be vectors that are members of both spaces.</span></span>
<span data-ttu-id="b9a5a-136">如果不是 true，則幅度放大會沒有作用，因此我們需要初始子空間與目標子空間的非零重迭。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-136">If this were not true then amplitude amplification would have no effect so we need the initial subspace to have non-zero overlap with the target subspace.</span></span>

<span data-ttu-id="b9a5a-137">我們將代表我們需要的第一個 oracle，讓振幅放大 $P\_$0，並定義為具有下列動作。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-137">We will denote the first oracle that we need for amplitude amplification to be $P\_0$, defined to have the following action.</span></span>  <span data-ttu-id="b9a5a-138">對於 "子空間 $P 中的所有狀態 $ \ket{x} $\_0 \ket{x} =-\ket{x} $，而對於所有狀態 $ \ket{y} $ （不在此子空間中），我們 $P\_0 \ket{y} = \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-138">For all states $\ket{x}$ in the "initial" subspace $P\_0 \ket{x} = -\ket{x}$ and for all states $\ket{y}$ that are not in this subspace we have $P\_0 \ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="b9a5a-139">標示目標子空間（$P _1 $）的 oracle 會採用完全相同的格式。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-139">The oracle that marks the target subspace, $P_1$, takes exactly the same form.</span></span>
<span data-ttu-id="b9a5a-140">針對目標子空間中的所有狀態 $ \ket{x} $ （亦即，針對您想要演算法輸出的所有狀態），$P _1 \ ket {x} =-\ket{x} $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-140">For all states $\ket{x}$ in the target subspace (i.e., for all states that you'd like the algorithm to output), $P_1\ket{x} = -\ket{x}$.</span></span>
<span data-ttu-id="b9a5a-141">同樣地，針對不在目標子空間中的所有州 $ \ket{y} $ $P _1 \ ket {y} = \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-141">Similarly, for all states $\ket{y}$ that are not in the target subspace $P_1\ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="b9a5a-142">然後再結合這兩個反射來形成一個運算子，以制定振幅放大的單一步驟，$Q =-P_0 P_1 $，其中整體減號只在受控制的應用程式中考慮。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-142">These two reflections are then combined to form an operator that enacts a single step of amplitude amplification, $Q = -P_0 P_1$, where the overall minus sign is only important to consider in controlled applications.</span></span>
<span data-ttu-id="b9a5a-143">振幅放大接著會採用初始子空間中的初始狀態 $ \ket{\psi} $，然後執行 $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $ 來繼續進行。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-143">Amplitude amplification then proceeds by taking an initial state, $\ket{\psi}$ that is in the initial subspace and then performs $\ket{\psi} \mapsto Q^m \ket{\psi}$.</span></span>
<span data-ttu-id="b9a5a-144">執行這類反復專案可確保如果一個開始的初始狀態與已標記的空格重迭 $ \sin ^ 2 （\theta） $，則在 $m $ 反復專案之後，此重迭會變成 $ \sin ^ 2 （[2m + 1] \theta） $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-144">Performing such an iteration guarantees that if one starts with an initial state that has overlap $\sin^2(\theta)$ with the marked space then after $m$ iterations this overlap becomes $\sin^2([2m + 1] \theta)$.</span></span>
<span data-ttu-id="b9a5a-145">因此，我們通常會想要選擇 $m $ 成為免費的參數，例如 $ [2m + 1] \theta = \ pi/2 $;不過，這類嚴格的選擇對於某些形式的振幅放大（例如，固定點波幅放大）而言並不重要。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-145">We therefore typically wish to choose $m$ to be a free parameter such that $[2m+1]\theta = \pi/2$; however, such rigid choices are not as important for some forms of amplitude amplification such as fixed point amplitude amplification.</span></span>
<span data-ttu-id="b9a5a-146">此程式可讓我們在標示的子空間中準備狀態，方法是使用對標記函式 quadratically 較少的查詢，以及在嚴格的傳統裝置上進行狀態準備功能。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-146">This process allows us to prepare a state in the marked subspace using quadratically fewer queries to the marking function and the state preparation function than would be possible on a strictly classical device.</span></span>
<span data-ttu-id="b9a5a-147">這就是為什麼振幅放大是許多量子運算應用程式的重要建立區塊。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-147">This is why amplitude amplification is a significant building block for many applications of quantum computing.</span></span>

<span data-ttu-id="b9a5a-148">為了瞭解如何使用演算法，提供可提供 oracles 結構的範例會很有用。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-148">In order to understand how to use the algorithm, it is useful to provide an example that gives a construction of the oracles.</span></span>  <span data-ttu-id="b9a5a-149">請考慮在此設定中執行 Grover 的資料庫搜尋演算法。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-149">Consider performing Grover's algorithm for database searches in this setting.</span></span>
<span data-ttu-id="b9a5a-150">在 Grover 的搜尋中，目標是將 state $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket{0}$ 轉換成其中一個（可能）已標記的狀態。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-150">In Grover's search the goal is to transform the state $\ket{+}^{\otimes n} = H^{\otimes n} \ket{0}$ into one of (potentially) many marked states.</span></span>
<span data-ttu-id="b9a5a-151">為了進一步簡化，讓我們來看看唯一標示的狀態是 $ \ket{0}$ 的情況。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-151">To further simplify, let's just look at the case where the only marked state is $\ket{0}$.</span></span>
<span data-ttu-id="b9a5a-152">然後我們設計了兩個 oracles：一個只會將初始狀態 $ \ket{+} ^ {\otimes n} $ 標記為減號，另一個標記標記為狀態 $ \ket{0}$ 加上減號。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-152">Then we have design two oracles: one that only marks the initial state $\ket{+}^{\otimes n}$ with a minus sign and another that marks the marked state $\ket{0}$ with a minus sign.</span></span>
<span data-ttu-id="b9a5a-153">第二個閘道可以使用下列進程作業來執行，方法是使用 canon 中的控制流程作業：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-153">The latter gate can be implemented using the following process operation, by using the control flow operations in the canon:</span></span>

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

<span data-ttu-id="b9a5a-154">這個 oracle 就是 <xref:microsoft.quantum.canon.rall1> 作業的特殊案例，可讓您透過任意階段旋轉，而不是反映案例 $ \phi = \pi $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-154">This oracle is then a special case of the <xref:microsoft.quantum.canon.rall1> operation, which allows for rotating by an arbitrary phase instead of the reflection case $\phi = \pi$.</span></span>
<span data-ttu-id="b9a5a-155">在此情況下，`RAll1` 類似于 <xref:microsoft.quantum.intrinsic.r1> 序言作業，因為它會旋轉大約 $ \ket{11\cdots1} $，而不是單一 qubit 狀態 $ \ket{1}$。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-155">In this case, `RAll1` is similar to the <xref:microsoft.quantum.intrinsic.r1> prelude operation, in that it rotates about $\ket{11\cdots1}$ instead of the single-qubit state $\ket{1}$.</span></span>

<span data-ttu-id="b9a5a-156">標記初始子空間的 oracle 會以類似的方式進行結構化。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-156">The oracle that marks the initial subspace can be constructed similarly.</span></span>
<span data-ttu-id="b9a5a-157">在 虛擬代碼：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-157">In pseudocode:</span></span>

1. <span data-ttu-id="b9a5a-158">將 $H $ 閘道套用到每個 qubit。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-158">Apply $H$ gates to every qubit.</span></span>
2. <span data-ttu-id="b9a5a-159">將 $X $ 閘道套用到每個 qubit。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-159">Apply $X$ gates to every qubit.</span></span>
3. <span data-ttu-id="b9a5a-160">將 $n-$1 控制的 $Z $-閘道套用至 $n ^ {\text{th}} $ qubit。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-160">Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.</span></span>
4. <span data-ttu-id="b9a5a-161">將 $X $ 閘道套用到每個 qubit。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-161">Apply $X$ gates to every qubit.</span></span>
5. <span data-ttu-id="b9a5a-162">將 $H $ 閘道套用到每個 qubit。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-162">Apply $H$ gates to every qubit.</span></span>

<span data-ttu-id="b9a5a-163">這次，我們也會示範如何使用 <xref:microsoft.quantum.canon.applywith> 搭配上述的 <xref:microsoft.quantum.canon.rall1> 操作：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-163">This time, we also demonstrate using <xref:microsoft.quantum.canon.applywith> together with the <xref:microsoft.quantum.canon.rall1> operation discussed above:</span></span>

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

<span data-ttu-id="b9a5a-164">然後，我們可以將這兩個 oracles 合併在一起，並以決定性的方式將 $ \ket{+} ^ {\otimes n} $ 轉換成 $ \ket{0}$，並使用與 $ Hadamard ^ n} $ （ie $m \sqrt{2 \propto ^ n} $）成正比的幾層 \Sqrt{2 閘道在觀察到結果 $0 $ 之前，您必須先準備並測量初始狀態，以不具決定性的方式來準備 $ \ket{0}$ 狀態，而不是大約 $ 2 ^ n $ 層。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-164">We can then combine these two oracles together to rotate between the two states and deterministically transform $\ket{+}^{\otimes n}$ to $\ket{0}$ using a number of layers of Hadamard gates that is proportional to $\sqrt{2^n}$ (ie $m\propto \sqrt{2^n}$) versus the roughly $2^n$ layers that would be needed to non-deterministically prepare the $\ket{0}$ state by preparing and measuring the initial state until the outcome $0$ is observed.</span></span>

### <a name="phase-estimation-oracles"></a><span data-ttu-id="b9a5a-165">階段估計 Oracles</span><span class="sxs-lookup"><span data-stu-id="b9a5a-165">Phase Estimation Oracles</span></span> ###

<span data-ttu-id="b9a5a-166">針對階段估計，oracles 會更自然。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-166">For phase estimation the oracles are somewhat more natural.</span></span>
<span data-ttu-id="b9a5a-167">階段估計的目標是設計一個副程式，它能夠從單一矩陣的特徵值進行取樣。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-167">The aim in phase estimation is to design a subroutine that is capable of sampling from the eigenvalues of a unitary matrix.</span></span>
<span data-ttu-id="b9a5a-168">這個方法是在量子模擬中不可或缺，因為在化學和材質科學中，有許多實體問題，這些特徵值提供了配量系統的狀態 energies，可提供我們有關階段圖表的重要資訊適用于分子驅使分子的材質和反應 dynamics。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-168">This method is indispensible in quantum simulation because for many physical problems in chemistry and material science these eigenvalues give the ground-state energies of quantum systems which provides us valuable information about the phase diagrams of materials and reaction dynamics for molecules.</span></span>
<span data-ttu-id="b9a5a-169">階段估計的每個類別都需要輸入單一。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-169">Every flavor of phase estimation needs an input unitary.</span></span>
<span data-ttu-id="b9a5a-170">這個單一的程式通常是由兩種 oracles 類型的其中一種來描述。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-170">This unitary is customarily described by one of two types of oracles.</span></span>

> [!TIP]
> <span data-ttu-id="b9a5a-171">以下所述的兩個 oracle 類型都涵蓋在範例中。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-171">Both of the oracle types described below are covered in the samples.</span></span>
> <span data-ttu-id="b9a5a-172">若要深入瞭解連續查詢 oracles，請參閱[ **PhaseEstimation**範例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation)。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-172">To learn more about continuous query oracles, please see the [**PhaseEstimation** sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation).</span></span>
> <span data-ttu-id="b9a5a-173">若要深入瞭解離散查詢 oracles，請參閱[ **IsingPhaseEstimation**範例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation)。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-173">To learn more about discrete query oracles, please see the [**IsingPhaseEstimation** sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation).</span></span>

<span data-ttu-id="b9a5a-174">第一種類型的 oracle，我們稱之為獨立查詢 oracle，並以使用者定義型別來表示 <xref:microsoft.quantum.oracles.discreteoracle>，只牽涉到單一的矩陣。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-174">The first type of oracle, which we call a discrete query oracle and represent with the user-defined type <xref:microsoft.quantum.oracles.discreteoracle>, simply involves a unitary matrix.</span></span>
<span data-ttu-id="b9a5a-175">如果 $U $ 是我們想要預估其特徵值的單一，則適用于 $U $ 的 oracle 只是執行 $U $ 之副程式的一個獨立元件。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-175">If $U$ is the unitary whose eigenvalues we wish to estimate then the oracle for $U$ is simply a stand-in for a subroutine that implements $U$.</span></span>
<span data-ttu-id="b9a5a-176">例如，您可以使用 $U $，將上面定義的 oracle $Q $ 視為用於振幅估計。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-176">For example, one could take $U$ to be the oracle $Q$ defined above for amplitude estimation.</span></span>
<span data-ttu-id="b9a5a-177">此矩陣的特徵值可用來估計初始和目標狀態（$ \sin ^ 2 （\theta） $ 之間的重迭），使用 quadratically 較少的樣本，而不是其他所需。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-177">The eigenvalues of this matrix can be used to estimate the overlap between the initial and target states, $\sin^2(\theta)$, using quadratically fewer samples than one would need otherwise.</span></span>
<span data-ttu-id="b9a5a-178">這會獲得使用 Grover oracle $Q $ 做為輸入，以作為幅度估計的標記，來進行階段估計的應用。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-178">This earns the application of phase estimation using the Grover oracle $Q$ as input the moniker of amplitude estimation.</span></span>
<span data-ttu-id="b9a5a-179">在量子測量中廣泛使用的另一個常見應用程式包含估計較小的旋轉角度。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-179">Another common application, widely used in quantum metrology, involves estimating a small rotation angle.</span></span>
<span data-ttu-id="b9a5a-180">換句話說，我們想要針對未知的旋轉閘道估計 $ \theta $，其格式為 $R _z （\theta） $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-180">In other words, we wish to estimate $\theta$ for an unknown rotation gate of the form $R_z(\theta)$.</span></span>
<span data-ttu-id="b9a5a-181">在這種情況下，我們要與之互動的副程式是 $ $ \begin{align} U & = R_z （\theta） \\\\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\\\ 0 & e ^ {i \theta/2} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-181">In such cases, the subroutine that we would interact with in order to learn this fixed value of $\theta$ for the gate is $$ \begin{align} U & = R_z(\theta) \\\\ & = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i\theta/2} \end{bmatrix}.</span></span>
<span data-ttu-id="b9a5a-182">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b9a5a-182">\end{align} $$</span></span>

<span data-ttu-id="b9a5a-183">第二種類型的 oracle 在階段估計中使用的是連續查詢 oracle，以 <xref:microsoft.quantum.oracles.continuousoracle> 類型表示。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-183">The second type of oracle used in phase estimation is the continuous query oracle, represented by the <xref:microsoft.quantum.oracles.continuousoracle> type.</span></span>
<span data-ttu-id="b9a5a-184">針對階段估計的連續查詢 oracle 會採用 $U （t） $ 的形式，其中 $t $ 是傳統方式的已知實數。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-184">A continuous query oracle for phase estimation takes the form $U(t)$ where $t$ is a classically known real number.</span></span>
<span data-ttu-id="b9a5a-185">如果我們讓 $U $ 是固定的，則持續查詢 oracle 會採用 $U （t） = U ^ t $ 的格式。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-185">If we let $U$ be a fixed unitary then the continuous query oracle takes the form $U(t) = U^t$.</span></span>
<span data-ttu-id="b9a5a-186">這可讓我們查詢矩陣（例如 $ \sqrt{U} $），而無法直接在離散查詢模型中執行。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-186">This allows us to query matrices such as $\sqrt{U}$, which could not be implemented directly in the discrete query model.</span></span>

<span data-ttu-id="b9a5a-187">當您不探查特定的單一，而想要瞭解單一的產生器屬性時，這種類型的 oracle 就很有價值。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-187">This type of oracle is valuable when you're not probing a particular unitary, but rather wish to learn the properties of the generator of the unitary.</span></span>
<span data-ttu-id="b9a5a-188">例如，在 dynamical 量子模擬中，其目標是要針對 Hermitian 矩陣 $H $ 和進化時間 $t $，設計大致接近 $U （t） = e ^ {-i H t} $ 的配量線路。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-188">For example, in dynamical quantum simulation the goal is to devise quantum circuits that closely approximate $U(t)=e^{-i H t}$ for a Hermitian matrix $H$ and evolution time $t$.</span></span>
<span data-ttu-id="b9a5a-189">$U （t） $ 的特徵值與 $H $ 的特徵值直接相關。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-189">The eigenvalues of $U(t)$ are directly related to the eigenvalues of $H$.</span></span>
<span data-ttu-id="b9a5a-190">若要查看此情況，請考慮 $H $： $H \ket{E} = E\ket {E} $ 的 eigenvector，然後很容易就能從矩陣指數的電源序列定義中看出 $U （t） \ket{E} = e ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-190">To see this, consider an eigenvector of $H$: $H \ket{E} = E\ket{E}$ then it is easy to see from the power-series definition of the matrix exponential that $U(t) \ket{E} = e^{i\phi}\ket{E}= e^{-iEt}\ket{E}$.</span></span>
<span data-ttu-id="b9a5a-191">因此，估計 $U （t） $ 的 eigenphase 會提供 eigenvalue $E $，假設 eigenvector $ \ket{E} $ 已輸入至階段估計演算法。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-191">Thus estimating the eigenphase of $U(t)$ gives the eigenvalue $E$ assuming the eigenvector $\ket{E}$ is input into the phase estimation algorithm.</span></span>
<span data-ttu-id="b9a5a-192">不過，在此情況下，您可以選擇使用者的值 $t $，因為 $t $ 的任何夠小的值，eigenvalue $E $ 可以透過 $E =-\ phi/t $ 來唯一反轉。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-192">However, in this case the value $t$ can be chosen at the user's discretion since for any sufficiently small value of $t$ the eigenvalue $E$ can be uniquely inverted through $E=-\phi/t$.</span></span>
<span data-ttu-id="b9a5a-193">由於量子模擬方法提供執行小數進化的能力，因此在查詢單一時，這會授與階段估計演算法額外的自由度，特別是在離散查詢模型只允許 unitaries 的表單 $U ^ j $若要針對 integer $j $ 進行連續查詢，oracle 可以讓我們針對任何實際值 $t $，將 $U ^ t $ 的格式近似 unitaries。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-193">Since quantum simulation methods provide the ability to perform a fractional evolution, this grants phase estimation algorithms an additional freedom when querying the unitary, specifically while the discrete query model allows only unitaries of the form $U^j$ to applied for integer $j$ the continuous query oracle allows us to approximate unitaries of the form $U^t$ for any real valued $t$.</span></span>
<span data-ttu-id="b9a5a-194">這一點很重要，因為它可讓我們選擇精確的實驗，以提供最多有關 $E $;而以離散查詢為基礎的方法，則必須在演算法中選擇最適合的整數查詢，以做出危害。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-194">This is important to squeeze every last ounce of efficiency out of phase estimation algorithms because it allows us to choose precisely the experiment that would provide the most information about $E$; whereas methods based on discrete queries must make do with compromising by choosing the best integer number of queries in the algorithm.</span></span>

<span data-ttu-id="b9a5a-195">做為具體的範例，請考慮估計不是閘道旋轉角度的問題，而是旋轉量子系統的 procession 頻率。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-195">As a concrete example of this, consider the problem of estimating not the rotation angle of a gate but the procession frequency of a rotating quantum system.</span></span>
<span data-ttu-id="b9a5a-196">描述這類配量 dynamics 的單一是 $U （t） = R_z （2 \ omega t） $ 來進行進化時間 $t $ 和 unknown frequency $ \omega $。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-196">The unitary that describes such quantum dynamics is $U(t)=R_z(2\omega t)$ for evolution time $t$ and unknown frequency $\omega$.</span></span>
<span data-ttu-id="b9a5a-197">在此內容中，我們可以使用單一 $R _z $ 閘道來模擬任何 $t $ 的 $U （t） $，因此不需要將自己限制為只有單一的個別查詢。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-197">In this context, we can simulate $U(t)$ for any $t$ using a single $R_z$ gate and as such do not need to restrict ourselves to only discrete queries to the unitary.</span></span>
<span data-ttu-id="b9a5a-198">這類連續模型也具有大於 $ 2 \ pi $ 的屬性，可以從使用連續查詢的階段估計程式中學習，因為其他會以對數函數的分支剪切來遮罩的階段資訊可以從 $t $ 的非接近值上執行的實驗結果中顯示。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-198">Such a continuous model also has the property that frequencies greater than $2\pi$ can be learned from phase estimation processes that use continuous queries because phase information that would otherwise be masked by the branch-cuts of the logarithm function can be revealed from the results of experiments performed on non-commensurate values of $t$.</span></span>
<span data-ttu-id="b9a5a-199">因此，對於這類問題而言，oracle 估計的持續查詢模型不只適合，而是針對離散查詢模型。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-199">Thus for problems such as this continuous query models for the phase estimation oracle are not only appropriate but are also preferable to the discrete query model.</span></span>
<span data-ttu-id="b9a5a-200">基於此原因，Q # 具有兩種查詢形式的功能，並將其保留給使用者，以根據其需求和可用的 oracle 類型來決定階段估計演算法。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-200">For this reason Q# has functionality for both forms of queries and leave it to the user to decide upon a phase estimation algorithm to fit their needs and the type of oracle that is available.</span></span>

## <a name="dynamical-generator-modeling"></a><span data-ttu-id="b9a5a-201">Dynamical 產生器模型</span><span class="sxs-lookup"><span data-stu-id="b9a5a-201">Dynamical Generator Modeling</span></span> ##

<span data-ttu-id="b9a5a-202">時間進化的產生器會描述狀態如何隨著時間進化。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-202">Generators of time-evolution describe how states evolve through time.</span></span> <span data-ttu-id="b9a5a-203">例如，配量狀態 $ \ket{\psi} $ 的 dynamics 是由 Schrödinger 方程式 $ $ \begin{align} i\frac {d \ket{\psi （t）}} {d t} & = H \ket{\psi （t）}、\end{align} $ $ 加上 Hermitian 矩陣 $H $ （稱為 Hamiltonian）所控管，做為的產生器行動.</span><span class="sxs-lookup"><span data-stu-id="b9a5a-203">For instance, the dynamics of a quantum state $\ket{\psi}$ is governed by the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = H \ket{\psi(t)}, \end{align} $$ with a Hermitian matrix $H$, known as the Hamiltonian, as the generator of motion.</span></span> <span data-ttu-id="b9a5a-204">指定初始狀態 $ \ket{\psi （0）} $ （時間 $t = $0）時，此方程式的正式方案 $t $ 可能是寫入 $ $ \begin{align} \ket{\psi （t）} = U （t） \ket{\psi （0）}，\end{align} $ $，其中矩陣指數 $U （t） = e ^ {-i H t} $ 稱為單一時間進化運算子。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-204">Given an initial state $\ket{\psi(0)}$ at time $t=0$, the formal solution to this equation at time $t$ may be, in principle, written $$ \begin{align} \ket{\psi(t)} = U(t)\ket{\psi(0)}, \end{align} $$ where the matrix exponential $U(t)=e^{-i H t}$ is known as the unitary time-evolution operator.</span></span> <span data-ttu-id="b9a5a-205">雖然我們將焦點放在下列表單的產生器，但我們強調此概念更廣泛地套用，例如模擬開放的量子系統，或更多抽象的差異方程式。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-205">Though we focus on generators of this form in the following, we emphasize that the concept applies more broadly, such as to the simulation of open quantum systems, or to more abstract differential equations.</span></span>

<span data-ttu-id="b9a5a-206">Dynamical 模擬的主要目標是針對在量子電腦的 qubits 中編碼的某些配量狀態，執行時間進化運算子。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-206">A primary goal of dynamical simulation is to implement the time-evolution operator on some quantum state encoded in qubits of a quantum computer.</span></span>  <span data-ttu-id="b9a5a-207">在許多情況下，Hamiltonian 可能會細分為一些 $d $ 簡單的詞彙的總和</span><span class="sxs-lookup"><span data-stu-id="b9a5a-207">In many cases, the Hamiltonian may be broken into a sum of some $d$ simpler terms</span></span>

<span data-ttu-id="b9a5a-208">$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b9a5a-208">$$ \begin{align} H & = \sum^{d-1}_{j=0} H_j, \end{align} $$</span></span>

<span data-ttu-id="b9a5a-209">而每個詞彙的時間進化只是在量子電腦上輕鬆執行。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-209">where time-evolution by each term alone is easy to implement on a quantum computer.</span></span> <span data-ttu-id="b9a5a-210">例如，如果 $H _j $ 是 Pauli $X _1X_2 $ 運算子會在 qubit register `qubits`的第1個和第2個元素上執行，則任何時間的時間演進 $t $ 都可以藉由呼叫作業 `Exp([PauliX,PauliX], t, qubits[1..2])`（其簽章 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`）來完成。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-210">For instance, if $H_j$ is a Pauli $X_1X_2$ operator acting on the 1st and 2nd elements of the qubit register `qubits`, time-evolution by it for any time $t$ may be implemented simply by calling the operation `Exp([PauliX,PauliX], t, qubits[1..2])`, which has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="b9a5a-211">如稍後在 Hamiltonian 模擬中所討論，其中一個解決方案就是以較簡單的作業順序 $H $ 來預估時間演進</span><span class="sxs-lookup"><span data-stu-id="b9a5a-211">As discussed later in Hamiltonian Simulation, one solution then is to approximate time-evolution by $H$ with a sequence of simpler operations</span></span>

<span data-ttu-id="b9a5a-212">$ $ \begin{align} U （t） & = \left （e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right） ^ {r} + \mathcal{O} （d ^ 2 \ max_j \\|H\_j\\| ^ 2 t ^ 2/r），\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b9a5a-212">$$ \begin{align} U(t) & = \left( e^{-iH\_0 t / r} e^{-iH\_1 t / r} \cdots e^{-iH\_{d-1} t / r} \right)^{r} + \mathcal{O}(d^2 \max_j \\|H\_j\\|^2 t^2/r), \end{align} $$</span></span>

<span data-ttu-id="b9a5a-213">其中 $r 的整數 > $0 控制近似值錯誤。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-213">where the integer $r > 0$ controls the approximation error.</span></span>

<span data-ttu-id="b9a5a-214">Dynamical 產生器模型程式庫提供一個架構，可根據簡單的產生器，有系統地編碼複雜的產生器。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-214">The dynamical generator modeling library provides a framework for systematically encoding complicated generators in terms of simpler generators.</span></span> <span data-ttu-id="b9a5a-215">如此一來，您就可以將這類描述傳遞給模擬程式庫，以透過選擇的模擬演算法來執行時間演進，並自動處理許多細節。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-215">Such a description may then be passed to, say, the simulation library to implement time-evolution by a simulation algorithm of choice, with many details automatically taken care of.</span></span>

> [!TIP]
> <span data-ttu-id="b9a5a-216">以下所述的 dynamical 產生器程式庫已涵蓋在範例中。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-216">The dynamical generator library described below is covered in the samples.</span></span> <span data-ttu-id="b9a5a-217">如需以 Ising 模型為基礎的範例，請參閱[ **IsingGenerators**範例](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators)。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-217">For an example based on the Ising model, please see the [**IsingGenerators** sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators).</span></span>
> <span data-ttu-id="b9a5a-218">如需以分子 Hydrogen 為基礎的範例，請參閱[**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine)和[**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI)範例。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-218">For an example based on molecular Hydrogen, please see the [**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine) and [**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI) samples.</span></span>

### <a name="complete-description-of-a-generator"></a><span data-ttu-id="b9a5a-219">產生器的完整描述</span><span class="sxs-lookup"><span data-stu-id="b9a5a-219">Complete Description of a Generator</span></span> ###

<span data-ttu-id="b9a5a-220">在最上層，Hamiltonian 的完整描述包含在包含兩個元件的 `EvolutionGenerator` 使用者自訂類型中：</span><span class="sxs-lookup"><span data-stu-id="b9a5a-220">At the top level, a complete description of a Hamiltonian is contained in the `EvolutionGenerator` user-defined type which has two components.:</span></span>

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

<span data-ttu-id="b9a5a-221">`GeneratorSystem` 的使用者定義型別是 Hamiltonian 的傳統描述。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-221">The `GeneratorSystem` user-defined type is a classical description of the Hamiltonian.</span></span>

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

<span data-ttu-id="b9a5a-222">元組的第一個元素 `Int` 會儲存 Hamiltonian 中 $d $ 的詞彙數目，而第二個元素 `(Int -> GeneratorIndex)` 是將 $\{0、1,..., d-1\}$ 中的整數索引對應至唯一識別每個的 `GeneratorIndex` 使用者定義類型的函式。Hamiltonian 中的基本詞彙。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-222">The first element `Int` of the tuple stores the number of terms $d$ in the Hamiltonian, and the second element `(Int -> GeneratorIndex)` is a function that maps an integer index in $\{0,1,...,d-1\}$ to a `GeneratorIndex` user-defined type which uniquely identifies each primitive term in the Hamiltonian.</span></span> <span data-ttu-id="b9a5a-223">請注意，藉由將 Hamiltonian 中的詞彙集合表示為函式，而不是陣列 `GeneratorIndex[]`，這可讓您即時計算 `GeneratorIndex`，這在以大量詞彙描述 Hamiltonians 時特別有用。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-223">Note that by expressing the collection of terms in the Hamiltonian as a function rather than as an array `GeneratorIndex[]`, this allows for on-the-fly computation of the `GeneratorIndex` which is especially useful when describing Hamiltonians with a large number of terms.</span></span>

<span data-ttu-id="b9a5a-224">十分，我們不會對 `GeneratorIndex` 所識別的基本型詞彙做一些容易模擬的慣例。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-224">Crucially, we do not impose a convention on what primitive terms identified by the `GeneratorIndex` are easy-to-simulate.</span></span> <span data-ttu-id="b9a5a-225">比方說，基本詞彙可以是 Pauli 運算子，如上所述，但它們也可以 Fermionic 在量子化學模擬中常用的 annihilation 和建立運算子。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-225">For instance, primitive terms could be Pauli operators as discussed above, but they could also be Fermionic annihilation and creation operators commonly used in quantum chemistry simulation.</span></span> <span data-ttu-id="b9a5a-226">`GeneratorIndex` 本身並沒有意義，因為它不會描述它所指向之詞彙的時間演進如何實作為配量線路。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-226">By itself, a `GeneratorIndex` is meaningless as it does not describe how time-evolution by the term it points to may be implemented as a quantum circuit.</span></span>

<span data-ttu-id="b9a5a-227">這是藉由指定 `EvolutionSet` 的使用者定義型別來解決，將從某個標準集合中繪製的任何 `GeneratorIndex`對應到單一運算子，也就是以量子線路表示的 `EvolutionUnitary`。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-227">This is resolved by specifying an `EvolutionSet` user-defined type that maps any `GeneratorIndex`, drawn from some canonical set, to a unitary operator, the `EvolutionUnitary`, expressed as a quantum circuit.</span></span> <span data-ttu-id="b9a5a-228">`EvolutionSet` 定義了 `GeneratorIndex` 結構化方式的慣例，也會定義一組可能的 `GeneratorIndex`。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-228">The `EvolutionSet` defines the convention of how a `GeneratorIndex` is structured, and also defines the set of possible `GeneratorIndex`.</span></span>

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a><span data-ttu-id="b9a5a-229">Pauli 運算子產生器</span><span class="sxs-lookup"><span data-stu-id="b9a5a-229">Pauli Operator Generators</span></span> ###

<span data-ttu-id="b9a5a-230">產生器的具體和有用範例是 Hamiltonians，這是 Pauli 運算子的總和，每一個都可能有不同的係數。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-230">A concrete and useful example of generators are Hamiltonians that are a sum of Pauli operators, each possibly with a different coefficient.</span></span>
<span data-ttu-id="b9a5a-231">$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j、\end{align} $ $，其中每個 $ \hat H_j $ 現在都是從 Pauli 群組繪製而來。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-231">$$ \begin{align} H & = \sum^{d-1}_{j=0} a_j H_j, \end{align} $$ where each $\hat H_j$ is now drawn from the Pauli group.</span></span> <span data-ttu-id="b9a5a-232">針對這類系統，我們會提供 `EvolutionSet` 類型的 `PauliEvolutionSet()`，定義 Pauli 群組的元素和係數如何由具有下列簽章的 `GeneratorIndex`來識別。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-232">For such systems, we provide the `PauliEvolutionSet()` of type `EvolutionSet` that defines a convention for how an element of the Pauli group and a coefficient may be identified by a `GeneratorIndex`, which has the following signature.</span></span>

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

<span data-ttu-id="b9a5a-233">在編碼中，第一個參數 `Int[]` 會指定 Pauli 字串，其中 $ \hat I\rightarrow $0、$ \hat X\rightarrow $1、$ \hat Y\rightarrow $2 和 $ \hat Z\rightarrow $3。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-233">In our encoding, the first parameter `Int[]` specifies a Pauli string, where $\hat I\rightarrow 0$, $\hat X\rightarrow 1$, $\hat Y\rightarrow 2$, and $\hat Z\rightarrow 3$.</span></span> <span data-ttu-id="b9a5a-234">第二個參數 `Double[]` 會將 Pauli 字串的係數儲存在 Hamiltonian 中。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-234">The second parameter `Double[]` stores the coefficient of the Pauli string in the Hamiltonian.</span></span> <span data-ttu-id="b9a5a-235">請注意，只會使用這個陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-235">Note that only the first element of this array is used.</span></span> <span data-ttu-id="b9a5a-236">第三個參數 `Int[]` 為此 Pauli 字串作用所在的 qubits 編制索引，而且不能有重複的元素。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-236">The third parameter `Int[]` indexes the qubits that this Pauli string acts on, and must have no duplicate elements.</span></span> <span data-ttu-id="b9a5a-237">因此，Hamiltonian 詞彙 $0.4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ 可能會以</span><span class="sxs-lookup"><span data-stu-id="b9a5a-237">Thus the Hamiltonian term $0.4 \hat X_0 \hat Y_8\hat I_2\hat Z_1$ may be represented as</span></span>

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

<span data-ttu-id="b9a5a-238">`PauliEvolutionSet()` 是將此表單的任何 `GeneratorIndex` 對應至具有下列簽章之 `EvolutionUnitary` 的函式。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-238">The `PauliEvolutionSet()` is a function that maps any `GeneratorIndex` of this form to an `EvolutionUnitary` with the following signature.</span></span>

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

<span data-ttu-id="b9a5a-239">第一個參數代表持續時間，將會乘以單一進化的 `GeneratorIndex`中的係數。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-239">The first parameter represents a time-duration, that will be multiplied by the coefficient in the `GeneratorIndex`, of unitary evolution.</span></span> <span data-ttu-id="b9a5a-240">第二個參數是單一作用所在的 qubit 註冊。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-240">The second parameter is the qubit register the unitary acts on.</span></span> 

### <a name="time-dependent-generators"></a><span data-ttu-id="b9a5a-241">時間相依的產生器</span><span class="sxs-lookup"><span data-stu-id="b9a5a-241">Time-Dependent Generators</span></span> ###

<span data-ttu-id="b9a5a-242">在許多情況下，我們也會想要將時間相依的產生器模型化，如 Schrödinger 的方程式 $ $ \begin{align} i\frac {d \ket{\psi （t）}} {d t} & = \hat H （t） \ket{\psi （t）}，\end{align} $ $，其中產生器 $ \hat H （t） $ 現在是時間相依。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-242">In many cases, we are also interested in modelling time-dependent generators, as might occur in the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = \hat H(t) \ket{\psi(t)}, \end{align} $$ where the generator $\hat H(t)$ is now time-dependent.</span></span> <span data-ttu-id="b9a5a-243">從上述與時間無關的產生器到此案例的延伸模組相當簡單。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-243">The extension from the time-independent generators above to this case is straightforward.</span></span> <span data-ttu-id="b9a5a-244">我們會改為使用 `GeneratorSystemTimeDependent` 的使用者定義型別，而不是有固定的 `GeneratorSystem` 描述所有時間 $t $ 的 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-244">Rather than having a fixed `GeneratorSystem` describing the Hamiltonian for all times $t$, we instead have the `GeneratorSystemTimeDependent` user-defined type.</span></span>

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

<span data-ttu-id="b9a5a-245">第一個參數是連續的排程參數 $s \in [0，1] $，而此類型的函式會傳回該排程的 `GeneratorSystem`。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-245">The first parameter is a continuous schedule parameter $s\in [0,1]$, and functions of this type return a `GeneratorSystem` for that schedule.</span></span> <span data-ttu-id="b9a5a-246">請注意，[排程] 參數可能會與實體時間參數（例如 $s = t/T $）呈線性相關，$T $ 的總模擬時間。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-246">Note that the schedule parameter may be linearly related to the physical time parameter e.g. $s = t / T$, for some total time of simulation $T$.</span></span> <span data-ttu-id="b9a5a-247">不過，一般情況下，這不需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-247">In general however, this need not be the case.</span></span>

<span data-ttu-id="b9a5a-248">同樣地，此產生器的完整描述需要 `EvolutionSet`，因此我們定義了 `EvolutionSchedule` 的使用者定義型別。</span><span class="sxs-lookup"><span data-stu-id="b9a5a-248">Similarly, a complete description of this generator requires an `EvolutionSet`, and so we define an `EvolutionSchedule` user-defined type.</span></span>

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```