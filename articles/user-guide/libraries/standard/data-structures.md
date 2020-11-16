---
title: '標準程式庫中的資料結構 Q#'
description: '深入瞭解 Microsoft 標準程式庫中的資料結構、oracle 和 dynamical 產生器 Q# 。'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: c3ce5d531618c269d15be3e4eb58ecbb597a022c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692233"
---
# <a name="data-structures-and-modeling"></a><span data-ttu-id="18b92-103">資料結構與模型化</span><span class="sxs-lookup"><span data-stu-id="18b92-103">Data Structures and Modeling</span></span> #

## <a name="classical-data-structures"></a><span data-ttu-id="18b92-104">傳統資料結構</span><span class="sxs-lookup"><span data-stu-id="18b92-104">Classical Data Structures</span></span> ##

<span data-ttu-id="18b92-105">除了用來表示量子概念的使用者定義型別之外，canon 還提供作業、函式和型別，以使用用於量子系統控制中的傳統資料。</span><span class="sxs-lookup"><span data-stu-id="18b92-105">Along with user-defined types for representing quantum concepts, the canon also provides operations, functions, and types for working with classical data used in the control of quantum systems.</span></span>
<span data-ttu-id="18b92-106">例如，函 <xref:Microsoft.Quantum.Arrays.Reversed> 式會採用陣列做為輸入，並以反向順序傳回相同的陣列。</span><span class="sxs-lookup"><span data-stu-id="18b92-106">For instance, the <xref:Microsoft.Quantum.Arrays.Reversed> function takes an array as input and returns the same array in reverse order.</span></span>
<span data-ttu-id="18b92-107">然後可以在型別的陣列上使用 `Qubit[]` ，以避免在整數的量子表示之間轉換時，必須套用不必要的 $ \operatorname{SWAP} $ 管制。</span><span class="sxs-lookup"><span data-stu-id="18b92-107">This can then be used on an array of type `Qubit[]` to avoid having to apply unnecessary $\operatorname{SWAP}$ gates when converting between quantum representations of integers.</span></span>
<span data-ttu-id="18b92-108">同樣地，在上一節中，我們在上一節中看到，表單的類型 `(Int, Int -> T)` 可以用來表示隨機存取集合，因此函式會 <xref:Microsoft.Quantum.Arrays.LookupFunction> 提供便利的方式來從陣列類型中建立這類類型。</span><span class="sxs-lookup"><span data-stu-id="18b92-108">Similarly, we saw in the previous section that types of the form `(Int, Int -> T)` can be useful for representing random access collections, so the <xref:Microsoft.Quantum.Arrays.LookupFunction> function provides a convenient way of constructing such types from array types.</span></span>

### <a name="pairs"></a><span data-ttu-id="18b92-109">對</span><span class="sxs-lookup"><span data-stu-id="18b92-109">Pairs</span></span> ###

<span data-ttu-id="18b92-110">Canon 支援對成對的函式樣式表示法，並藉由解構來補充存取元組：</span><span class="sxs-lookup"><span data-stu-id="18b92-110">The canon supports functional-style notation for pairs, complementing accessing tuples by deconstruction:</span></span>

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a><span data-ttu-id="18b92-111">陣列</span><span class="sxs-lookup"><span data-stu-id="18b92-111">Arrays</span></span> ###

<span data-ttu-id="18b92-112">Canon 提供數個函式來處理陣列。</span><span class="sxs-lookup"><span data-stu-id="18b92-112">The canon provides several functions for manipulating arrays.</span></span>
<span data-ttu-id="18b92-113">這些函式是以類型參數化，因此可以與任何類型的陣列一起使用 Q# 。</span><span class="sxs-lookup"><span data-stu-id="18b92-113">These functions are type-parameterized, and thus can be used with arrays of any Q# type.</span></span>
<span data-ttu-id="18b92-114">例如，函式 <xref:Microsoft.Quantum.Arrays.Reversed> 會傳回新的陣列，其專案是從其輸入的反向順序。</span><span class="sxs-lookup"><span data-stu-id="18b92-114">For instance, the <xref:Microsoft.Quantum.Arrays.Reversed> function returns a new array whose elements are in reverse order from its input.</span></span>
<span data-ttu-id="18b92-115">這可以用來變更在呼叫作業時如何表示量子暫存器：</span><span class="sxs-lookup"><span data-stu-id="18b92-115">This can be used to change how a quantum register is represented when calling operations:</span></span>

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

<span data-ttu-id="18b92-116">同樣地，函 <xref:Microsoft.Quantum.Arrays.Subarray> 式可以用來重新排列或取得陣列元素的子集：</span><span class="sxs-lookup"><span data-stu-id="18b92-116">Similarly, the <xref:Microsoft.Quantum.Arrays.Subarray> function can be used to reorder or take subsets of the elements of an array:</span></span>

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

<span data-ttu-id="18b92-117">結合 flow 控制項時，陣列操作函式（例如） <xref:Microsoft.Quantum.Arrays.Zipped> 可以提供強大的方式來表達量副程式：</span><span class="sxs-lookup"><span data-stu-id="18b92-117">When combined with flow control, array manipulation functions such as <xref:Microsoft.Quantum.Arrays.Zipped> can provide a powerful way to express quantum programs:</span></span>

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zipped([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a><span data-ttu-id="18b92-118">神 諭</span><span class="sxs-lookup"><span data-stu-id="18b92-118">Oracles</span></span> ##

<span data-ttu-id="18b92-119">在 [階段估計](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) 和 [振幅放大](https://en.wikipedia.org/wiki/Amplitude_amplification) 的文獻中，oracle 的概念經常出現。</span><span class="sxs-lookup"><span data-stu-id="18b92-119">In the [phase estimation](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) and [amplitude amplification](https://en.wikipedia.org/wiki/Amplitude_amplification) literature the concept of an oracle appears frequently.</span></span>
<span data-ttu-id="18b92-120">Oracle 這一詞是指一組黑箱量子副程式，可在一組量子位上運作，並以階段傳回答案。</span><span class="sxs-lookup"><span data-stu-id="18b92-120">Here the term oracle refers to a blackbox quantum subroutine that acts upon a set of qubits and returns the answer as a phase.</span></span>
<span data-ttu-id="18b92-121">這個副程式通常可以被視為接受 oracle 的量子演算法的輸入，除了其他一些參數之外，還會套用一連串的量子作業，並將呼叫視為基本閘道。</span><span class="sxs-lookup"><span data-stu-id="18b92-121">This subroutine often can be thought of as an input to a quantum algorithm that accepts the oracle, in addition to some other parameters, and applies a series of quantum operations and treating a call to this quantum subroutine as if it were a fundamental gate.</span></span>
<span data-ttu-id="18b92-122">很明顯地，若要實際實施較大型的演算法，必須提供 oracle 到基本閘道的具體分解，但這類分解不需要用來瞭解呼叫 oracle 的演算法。</span><span class="sxs-lookup"><span data-stu-id="18b92-122">Obviously, in order to actually implement the larger algorithm a concrete decomposition of the oracle into fundamental gates must be provided but such a decomposition is not needed in order to understand the algorithm that calls the oracle.</span></span>
<span data-ttu-id="18b92-123">在中 Q# ，這個抽象是使用該作業為第一級的值來表示，如此一來，就能以黑箱的方式將作業傳遞給量子演算法的執行。</span><span class="sxs-lookup"><span data-stu-id="18b92-123">In Q#, this abstraction is represented by using that operations are first-class values, such that operations can be passed to implementations of quantum algorithms in a black-box manner.</span></span>
<span data-ttu-id="18b92-124">此外，使用者定義型別是用來以型別安全的方式來標記不同的 oracle 標記法，因此很難不慎人們不同種類的黑色方塊作業。</span><span class="sxs-lookup"><span data-stu-id="18b92-124">Moreover, user-defined types are used to label the different oracle representations in a type-safe way, making it difficult to accidentally conflate different kinds of black box operations.</span></span>

<span data-ttu-id="18b92-125">這類 oracle 出現在許多不同的內容中，包括著名的範例，例如 [格羅弗的搜尋](https://en.wikipedia.org/wiki/Grover%27s_algorithm) 和量子模擬演算法。</span><span class="sxs-lookup"><span data-stu-id="18b92-125">Such oracles appear in a number of different contexts, including famous examples such as [Grover's search](https://en.wikipedia.org/wiki/Grover%27s_algorithm) and quantum simulation algorithms.</span></span>
<span data-ttu-id="18b92-126">在這裡，我們將焦點放在兩個應用程式所需的 oracle：振幅放大和階段估計。</span><span class="sxs-lookup"><span data-stu-id="18b92-126">Here we focus on the oracles needed for just two applications: amplitude amplification and phase estimation.</span></span>
<span data-ttu-id="18b92-127">我們將先討論振幅放大 oracle，再繼續進行階段估計。</span><span class="sxs-lookup"><span data-stu-id="18b92-127">We will first discuss amplitude amplification oracles before proceeding to phase estimation.</span></span>

### <a name="amplitude-amplification-oracles"></a><span data-ttu-id="18b92-128">振幅放大 Oracle</span><span class="sxs-lookup"><span data-stu-id="18b92-128">Amplitude Amplification Oracles</span></span> ###

<span data-ttu-id="18b92-129">振幅放大演算法的目標是藉由套用一系列狀態的反射來執行初始狀態與最終狀態之間的旋轉。</span><span class="sxs-lookup"><span data-stu-id="18b92-129">The amplitude amplification algorithm aims to perform a rotation between an initial state and a final state by applying a sequence of reflections of the state.</span></span>
<span data-ttu-id="18b92-130">為了讓演算法運作，它需要這兩種狀態的規格。</span><span class="sxs-lookup"><span data-stu-id="18b92-130">In order for the algorithm to function, it needs a specification of both of these states.</span></span>
<span data-ttu-id="18b92-131">這些規格是由兩個 oracle 所提供。</span><span class="sxs-lookup"><span data-stu-id="18b92-131">These specifications are given by two oracles.</span></span>
<span data-ttu-id="18b92-132">這些 oracle 的運作方式是將輸入分成兩個空格：「目標」子空間和「初始」子空間。</span><span class="sxs-lookup"><span data-stu-id="18b92-132">These oracles work by breaking the inputs into two spaces, a "target" subspace and an "initial" subspace.</span></span>
<span data-ttu-id="18b92-133">Oracle 會識別這類 subspaces，類似于 Pauli 運算子如何藉由將 $ \pm $1 階段套用至這些空間來識別兩個空格。</span><span class="sxs-lookup"><span data-stu-id="18b92-133">The oracles identify such subspaces, similar to how Pauli operators identify two spaces, by applying a $\pm 1$ phase to these spaces.</span></span>
<span data-ttu-id="18b92-134">主要的差別在於，這些空間在此應用程式中不需要是半空白。</span><span class="sxs-lookup"><span data-stu-id="18b92-134">The main difference is that these spaces need not be half-spaces in this application.</span></span>
<span data-ttu-id="18b92-135">另請注意，這兩個 subspaces 通常不會互斥：兩個區域的成員都是。</span><span class="sxs-lookup"><span data-stu-id="18b92-135">Also note that these two subspaces are not usually mutually exclusive: there will be vectors that are members of both spaces.</span></span>
<span data-ttu-id="18b92-136">如果不是 true，則幅度放大不會有任何作用，因此我們需要初始子空間與目標子空間有非零的重迭。</span><span class="sxs-lookup"><span data-stu-id="18b92-136">If this were not true then amplitude amplification would have no effect so we need the initial subspace to have non-zero overlap with the target subspace.</span></span>

<span data-ttu-id="18b92-137">我們會將幅度放大所需的第一個 oracle 表示為 $P \_ $0，定義為具有下列動作。</span><span class="sxs-lookup"><span data-stu-id="18b92-137">We will denote the first oracle that we need for amplitude amplification to be $P\_0$, defined to have the following action.</span></span>  <span data-ttu-id="18b92-138">針對 "初始" 子空間中的所有狀態 $ \ket{x} $ $P \_ 0 \ket{x} =-\ket{x} $，而針對所有不在此 \ket{y} 中的狀態 $ 子空間 $，我們有 $P \_ 0 \ket{y} = \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="18b92-138">For all states $\ket{x}$ in the "initial" subspace $P\_0 \ket{x} = -\ket{x}$ and for all states $\ket{y}$ that are not in this subspace we have $P\_0 \ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="18b92-139">將目標子空間標示 $P _1 $ 的 oracle 會採用完全相同的格式。</span><span class="sxs-lookup"><span data-stu-id="18b92-139">The oracle that marks the target subspace, $P_1$, takes exactly the same form.</span></span>
<span data-ttu-id="18b92-140">針對目標子空間中的所有狀態 $ \ket{x} $ (亦即，您希望演算法輸出) 的所有狀態，$P _1 \ ket {x} =-\ket{x} $。</span><span class="sxs-lookup"><span data-stu-id="18b92-140">For all states $\ket{x}$ in the target subspace (i.e., for all states that you'd like the algorithm to output), $P_1\ket{x} = -\ket{x}$.</span></span>
<span data-ttu-id="18b92-141">同樣地，對於不在目標子空間中的所有州 $ \ket{y} $，$P _1 \ ket {y} = \ket{y} $。</span><span class="sxs-lookup"><span data-stu-id="18b92-141">Similarly, for all states $\ket{y}$ that are not in the target subspace $P_1\ket{y} = \ket{y}$.</span></span>
<span data-ttu-id="18b92-142">這兩個反射接著會合並來形成一個運算子，該運算子會制定幅度放大的單一步驟，$Q =-P_0 P_1 $，其中整體的負號只需要在受控制的應用程式中考慮。</span><span class="sxs-lookup"><span data-stu-id="18b92-142">These two reflections are then combined to form an operator that enacts a single step of amplitude amplification, $Q = -P_0 P_1$, where the overall minus sign is only important to consider in controlled applications.</span></span>
<span data-ttu-id="18b92-143">幅度放大之後，會採取初始狀態 $ \ket{\psi} $ （在初始子空間中），然後執行 $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $ 來繼續進行。</span><span class="sxs-lookup"><span data-stu-id="18b92-143">Amplitude amplification then proceeds by taking an initial state, $\ket{\psi}$ that is in the initial subspace and then performs $\ket{\psi} \mapsto Q^m \ket{\psi}$.</span></span>
<span data-ttu-id="18b92-144">執行這類反復專案可保證如果一開始的初始狀態與已標記的空格重迭了 $ \sin ^ 2 ( \theta) $，則在 $m $ 反復專案之後，此重迭會變成 $ \sin ^ 2 ( [2m + 1] \theta) $。</span><span class="sxs-lookup"><span data-stu-id="18b92-144">Performing such an iteration guarantees that if one starts with an initial state that has overlap $\sin^2(\theta)$ with the marked space then after $m$ iterations this overlap becomes $\sin^2([2m + 1] \theta)$.</span></span>
<span data-ttu-id="18b92-145">因此，我們通常會想要選擇 $m $ 成為免費參數，例如 $ [2m + 1] \theta = \ pi/2 $;不過，這種固定選項對某些形式的波幅放大（例如固定點振幅放大）並不重要。</span><span class="sxs-lookup"><span data-stu-id="18b92-145">We therefore typically wish to choose $m$ to be a free parameter such that $[2m+1]\theta = \pi/2$; however, such rigid choices are not as important for some forms of amplitude amplification such as fixed point amplitude amplification.</span></span>
<span data-ttu-id="18b92-146">此程式可讓我們在標記的子空間中，使用 quadratically 較少的查詢來準備標示的函式，並使用狀態準備函式，而不是在嚴格傳統的裝置上。</span><span class="sxs-lookup"><span data-stu-id="18b92-146">This process allows us to prepare a state in the marked subspace using quadratically fewer queries to the marking function and the state preparation function than would be possible on a strictly classical device.</span></span>
<span data-ttu-id="18b92-147">這就是為什麼振幅放大對於許多量子運算應用程式來說是很重要的建立區塊。</span><span class="sxs-lookup"><span data-stu-id="18b92-147">This is why amplitude amplification is a significant building block for many applications of quantum computing.</span></span>

<span data-ttu-id="18b92-148">為了瞭解如何使用演算法，提供可提供 oracle 結構的範例會很有説明。</span><span class="sxs-lookup"><span data-stu-id="18b92-148">In order to understand how to use the algorithm, it is useful to provide an example that gives a construction of the oracles.</span></span>  <span data-ttu-id="18b92-149">請考慮在此設定中執行資料庫搜尋的格羅弗演算法。</span><span class="sxs-lookup"><span data-stu-id="18b92-149">Consider performing Grover's algorithm for database searches in this setting.</span></span>
<span data-ttu-id="18b92-150">在格羅弗的搜尋中，目標是將狀態 $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket {0} $ 轉換成其中一種 (可能) 許多標示的狀態。</span><span class="sxs-lookup"><span data-stu-id="18b92-150">In Grover's search the goal is to transform the state $\ket{+}^{\otimes n} = H^{\otimes n} \ket{0}$ into one of (potentially) many marked states.</span></span>
<span data-ttu-id="18b92-151">為了進一步簡化，讓我們看看唯一標示的狀態是 $ \ket $ 的情況 {0} 。</span><span class="sxs-lookup"><span data-stu-id="18b92-151">To further simplify, let's just look at the case where the only marked state is $\ket{0}$.</span></span>
<span data-ttu-id="18b92-152">接著，我們設計了兩個 oracle：一個只會以減號標示初始狀態 $ \ket{+} ^ {\otimes n} $，另一個則將標示的狀態 $ \ket {0} $ 標示為減號。</span><span class="sxs-lookup"><span data-stu-id="18b92-152">Then we have design two oracles: one that only marks the initial state $\ket{+}^{\otimes n}$ with a minus sign and another that marks the marked state $\ket{0}$ with a minus sign.</span></span>
<span data-ttu-id="18b92-153">您可以使用 canon 中的控制流程作業，使用下列處理作業來實作為後者的閘道：</span><span class="sxs-lookup"><span data-stu-id="18b92-153">The latter gate can be implemented using the following process operation, by using the control flow operations in the canon:</span></span>

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

<span data-ttu-id="18b92-154">此 oracle 接著是一種特殊的作業案例，可讓您透過 <xref:Microsoft.Quantum.Canon.RAll1> 任意階段來旋轉，而不是反映案例 $ \phi = \pi $。</span><span class="sxs-lookup"><span data-stu-id="18b92-154">This oracle is then a special case of the <xref:Microsoft.Quantum.Canon.RAll1> operation, which allows for rotating by an arbitrary phase instead of the reflection case $\phi = \pi$.</span></span>
<span data-ttu-id="18b92-155">在此情況下， `RAll1` 類似于 <xref:Microsoft.Quantum.Intrinsic.R1> 序言作業，因為它會旋轉 $ \ket{11\cdots1} $，而不是單一量子位狀態 $ \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="18b92-155">In this case, `RAll1` is similar to the <xref:Microsoft.Quantum.Intrinsic.R1> prelude operation, in that it rotates about $\ket{11\cdots1}$ instead of the single-qubit state $\ket{1}$.</span></span>

<span data-ttu-id="18b92-156">標示初始子空間的 oracle 可以類似的方式來建立。</span><span class="sxs-lookup"><span data-stu-id="18b92-156">The oracle that marks the initial subspace can be constructed similarly.</span></span>
<span data-ttu-id="18b92-157">在虛擬虛擬中：</span><span class="sxs-lookup"><span data-stu-id="18b92-157">In pseudocode:</span></span>

1. <span data-ttu-id="18b92-158">將 $H $ 閘道套用至每個量子位。</span><span class="sxs-lookup"><span data-stu-id="18b92-158">Apply $H$ gates to every qubit.</span></span>
2. <span data-ttu-id="18b92-159">將 $X $ 閘道套用至每個量子位。</span><span class="sxs-lookup"><span data-stu-id="18b92-159">Apply $X$ gates to every qubit.</span></span>
3. <span data-ttu-id="18b92-160">將 $n $1 控制 $Z $-閘道套用至 $n ^ {\text{th}} $ 量子位。</span><span class="sxs-lookup"><span data-stu-id="18b92-160">Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.</span></span>
4. <span data-ttu-id="18b92-161">將 $X $ 閘道套用至每個量子位。</span><span class="sxs-lookup"><span data-stu-id="18b92-161">Apply $X$ gates to every qubit.</span></span>
5. <span data-ttu-id="18b92-162">將 $H $ 閘道套用至每個量子位。</span><span class="sxs-lookup"><span data-stu-id="18b92-162">Apply $H$ gates to every qubit.</span></span>

<span data-ttu-id="18b92-163">這次，我們也會示範如何 <xref:Microsoft.Quantum.Canon.ApplyWith> 搭配 <xref:Microsoft.Quantum.Canon.RAll1> 上述操作來使用：</span><span class="sxs-lookup"><span data-stu-id="18b92-163">This time, we also demonstrate using <xref:Microsoft.Quantum.Canon.ApplyWith> together with the <xref:Microsoft.Quantum.Canon.RAll1> operation discussed above:</span></span>

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

<span data-ttu-id="18b92-164">接著，我們可以將這兩個 oracle 結合在一起，以在兩個狀態之間旋轉，並使用多個與 $ Hadamard ^ n} $ 的 \Sqrt{2 閘道進行決定性的轉換 $ \ket{+} ^ {\otimes n} $ 到 $ \ket {0} $ (ie $m \propto \sqrt{2 ^ n} $) 相對於大約 $ 2 ^ n $ 層，在 {0} 觀察到結果 $0 $ 之前，您必須準備和測量初始狀態，才能以非決定性的方式準備 $ \ket $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="18b92-164">We can then combine these two oracles together to rotate between the two states and deterministically transform $\ket{+}^{\otimes n}$ to $\ket{0}$ using a number of layers of Hadamard gates that is proportional to $\sqrt{2^n}$ (ie $m\propto \sqrt{2^n}$) versus the roughly $2^n$ layers that would be needed to non-deterministically prepare the $\ket{0}$ state by preparing and measuring the initial state until the outcome $0$ is observed.</span></span>

### <a name="phase-estimation-oracles"></a><span data-ttu-id="18b92-165">階段估計 Oracle</span><span class="sxs-lookup"><span data-stu-id="18b92-165">Phase Estimation Oracles</span></span> ###

<span data-ttu-id="18b92-166">針對階段估計，oracle 會比較自然。</span><span class="sxs-lookup"><span data-stu-id="18b92-166">For phase estimation the oracles are somewhat more natural.</span></span>
<span data-ttu-id="18b92-167">階段估計的目標是設計一個可從單一矩陣的特徵值取樣的副程式。</span><span class="sxs-lookup"><span data-stu-id="18b92-167">The aim in phase estimation is to design a subroutine that is capable of sampling from the eigenvalues of a unitary matrix.</span></span>
<span data-ttu-id="18b92-168">這種方法在量子模擬中是不可或缺的，因為化學和材質科學中有許多實體問題，這些特徵值提供了量子系統的接地氫化，可提供有關分子的材質和反應動態之階段圖表的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="18b92-168">This method is indispensable in quantum simulation because for many physical problems in chemistry and material science these eigenvalues give the ground-state energies of quantum systems which provides us valuable information about the phase diagrams of materials and reaction dynamics for molecules.</span></span>
<span data-ttu-id="18b92-169">階段估計的每個類別都需要輸入單一。</span><span class="sxs-lookup"><span data-stu-id="18b92-169">Every flavor of phase estimation needs an input unitary.</span></span>
<span data-ttu-id="18b92-170">這個單一的 oracle 通常是由兩種類型的其中一種來描述。</span><span class="sxs-lookup"><span data-stu-id="18b92-170">This unitary is customarily described by one of two types of oracles.</span></span>

> [!TIP]
> <span data-ttu-id="18b92-171">範例中涵蓋了以下所述的兩種 oracle 類型。</span><span class="sxs-lookup"><span data-stu-id="18b92-171">Both of the oracle types described below are covered in the samples.</span></span>
> <span data-ttu-id="18b92-172">若要深入瞭解連續查詢 oracle，請參閱 [ **PhaseEstimation** 範例](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation)。</span><span class="sxs-lookup"><span data-stu-id="18b92-172">To learn more about continuous query oracles, please see the [**PhaseEstimation** sample](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation).</span></span>
> <span data-ttu-id="18b92-173">若要深入瞭解離散查詢 oracle，請參閱 [ **IsingPhaseEstimation** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。</span><span class="sxs-lookup"><span data-stu-id="18b92-173">To learn more about discrete query oracles, please see the [**IsingPhaseEstimation** sample](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).</span></span>

<span data-ttu-id="18b92-174">Oracle 的第一種類型是，我們會呼叫不同的查詢 oracle，並以使用者定義型別表示 <xref:Microsoft.Quantum.Oracles.DiscreteOracle> ，只涉及單一矩陣。</span><span class="sxs-lookup"><span data-stu-id="18b92-174">The first type of oracle, which we call a discrete query oracle and represent with the user-defined type <xref:Microsoft.Quantum.Oracles.DiscreteOracle>, simply involves a unitary matrix.</span></span>
<span data-ttu-id="18b92-175">如果 $U $ 是要預估其特徵值的單一元件，則 $U $ 的 oracle 只是實作為 $U $ 的副程式的一種。</span><span class="sxs-lookup"><span data-stu-id="18b92-175">If $U$ is the unitary whose eigenvalues we wish to estimate then the oracle for $U$ is simply a stand-in for a subroutine that implements $U$.</span></span>
<span data-ttu-id="18b92-176">例如，您可以將 $U $ 視為上方所定義的 oracle $Q $ 以進行振幅估計。</span><span class="sxs-lookup"><span data-stu-id="18b92-176">For example, one could take $U$ to be the oracle $Q$ defined above for amplitude estimation.</span></span>
<span data-ttu-id="18b92-177">此矩陣的特徵值可用來估計初始和目標狀態（$ \sin ^ 2 ( \theta) $）之間的重迭，使用 quadratically 的樣本數比另一種需要的少。</span><span class="sxs-lookup"><span data-stu-id="18b92-177">The eigenvalues of this matrix can be used to estimate the overlap between the initial and target states, $\sin^2(\theta)$, using quadratically fewer samples than one would need otherwise.</span></span>
<span data-ttu-id="18b92-178">這獲得使用格羅弗 oracle $Q $ 做為輸入振幅估計的標記來進行階段估計的應用。</span><span class="sxs-lookup"><span data-stu-id="18b92-178">This earns the application of phase estimation using the Grover oracle $Q$ as input the moniker of amplitude estimation.</span></span>
<span data-ttu-id="18b92-179">在量子測量中廣泛使用的另一個常見的應用程式，則牽涉到估計一個小的旋轉角度。</span><span class="sxs-lookup"><span data-stu-id="18b92-179">Another common application, widely used in quantum metrology, involves estimating a small rotation angle.</span></span>
<span data-ttu-id="18b92-180">換句話說，我們想要為表單 $R _z ( \theta) $ 的未知旋轉閘道預估 $ \theta $。</span><span class="sxs-lookup"><span data-stu-id="18b92-180">In other words, we wish to estimate $\theta$ for an unknown rotation gate of the form $R_z(\theta)$.</span></span>
<span data-ttu-id="18b92-181">在這種情況下，我們會與您互動的副程式，以瞭解此閘道的 $ \theta $ 固定值為 $ $ \begin{align} U & = R_z ( \theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ theta/2} \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="18b92-181">In such cases, the subroutine that we would interact with in order to learn this fixed value of $\theta$ for the gate is $$ \begin{align} U & = R_z(\theta) \\\\ & = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i\theta/2} \end{bmatrix}.</span></span>
<span data-ttu-id="18b92-182">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="18b92-182">\end{align} $$</span></span>

<span data-ttu-id="18b92-183">階段估計中使用的第二種 oracle 類型是連續查詢 oracle，以類型表示 <xref:Microsoft.Quantum.Oracles.ContinuousOracle> 。</span><span class="sxs-lookup"><span data-stu-id="18b92-183">The second type of oracle used in phase estimation is the continuous query oracle, represented by the <xref:Microsoft.Quantum.Oracles.ContinuousOracle> type.</span></span>
<span data-ttu-id="18b92-184">針對階段估計的連續查詢 oracle 採用 $U (t) $ 的形式，其中 $t $ 是傳統方式的已知實數。</span><span class="sxs-lookup"><span data-stu-id="18b92-184">A continuous query oracle for phase estimation takes the form $U(t)$ where $t$ is a classically known real number.</span></span>
<span data-ttu-id="18b92-185">如果我們讓 $U $ 成為固定的單一查詢，則連續查詢 oracle 會採用 $U (t) = U ^ t $ 的表單。</span><span class="sxs-lookup"><span data-stu-id="18b92-185">If we let $U$ be a fixed unitary then the continuous query oracle takes the form $U(t) = U^t$.</span></span>
<span data-ttu-id="18b92-186">這可讓我們查詢 $ \sqrt{U} $ 之類的矩陣，無法直接在離散查詢模型中執行。</span><span class="sxs-lookup"><span data-stu-id="18b92-186">This allows us to query matrices such as $\sqrt{U}$, which could not be implemented directly in the discrete query model.</span></span>

<span data-ttu-id="18b92-187">這種類型的 oracle 在您沒有探查特定的單一的情況下很有用，而是想要學習單一的產生器的屬性。</span><span class="sxs-lookup"><span data-stu-id="18b92-187">This type of oracle is valuable when you're not probing a particular unitary, but rather wish to learn the properties of the generator of the unitary.</span></span>
<span data-ttu-id="18b92-188">例如，在 dynamical 量子模擬中，目標是要設計與 Hermitian 矩陣 $H $ 和演進時間 $t $ $U (t) = e ^ {-i H t} $ 緊密相近的量子電路。</span><span class="sxs-lookup"><span data-stu-id="18b92-188">For example, in dynamical quantum simulation the goal is to devise quantum circuits that closely approximate $U(t)=e^{-i H t}$ for a Hermitian matrix $H$ and evolution time $t$.</span></span>
<span data-ttu-id="18b92-189">$U (t) $ 的特徵值與 $H $ 的特徵值直接相關。</span><span class="sxs-lookup"><span data-stu-id="18b92-189">The eigenvalues of $U(t)$ are directly related to the eigenvalues of $H$.</span></span>
<span data-ttu-id="18b92-190">若要查看這一點，請考慮 $H $： $H \ket{E} = E\ket {E} $ 的 eigenvector，然後很容易就能看到矩陣指數的電源系列定義，$U (t) \ket{E} = e ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $。</span><span class="sxs-lookup"><span data-stu-id="18b92-190">To see this, consider an eigenvector of $H$: $H \ket{E} = E\ket{E}$ then it is easy to see from the power-series definition of the matrix exponential that $U(t) \ket{E} = e^{i\phi}\ket{E}= e^{-iEt}\ket{E}$.</span></span>
<span data-ttu-id="18b92-191">因此，估計 $U (t) $ 的 eigenphase 會提供 eigenvalue $E $ 假設 eigenvector $ \ket{E} $ 是進入階段估計演算法。</span><span class="sxs-lookup"><span data-stu-id="18b92-191">Thus estimating the eigenphase of $U(t)$ gives the eigenvalue $E$ assuming the eigenvector $\ket{E}$ is input into the phase estimation algorithm.</span></span>
<span data-ttu-id="18b92-192">不過，在此情況下，可以選擇使用者的值 $t $，因為 $t $ eigenvalue $E $ 的任何足夠小值，可以透過 $E =-\ phi/t $ 唯一反轉。</span><span class="sxs-lookup"><span data-stu-id="18b92-192">However, in this case the value $t$ can be chosen at the user's discretion since for any sufficiently small value of $t$ the eigenvalue $E$ can be uniquely inverted through $E=-\phi/t$.</span></span>
<span data-ttu-id="18b92-193">由於量子模擬方法提供了執行小數演進的能力，這會授與階段估計演算法在查詢單一時的額外自由，特別是當離散查詢模型只允許 $U ^ j $ 的表單 ^ j $ 以套用至整數 $j $ [連續查詢 oracle 可讓我們將 $U ^ t $ 的格式近似 ^ t $ 的任何實值 $t $。</span><span class="sxs-lookup"><span data-stu-id="18b92-193">Since quantum simulation methods provide the ability to perform a fractional evolution, this grants phase estimation algorithms an additional freedom when querying the unitary, specifically while the discrete query model allows only unitaries of the form $U^j$ to applied for integer $j$ the continuous query oracle allows us to approximate unitaries of the form $U^t$ for any real valued $t$.</span></span>
<span data-ttu-id="18b92-194">這一點很重要，因為它可讓我們選擇精確的實驗，以提供有關 $E $; 的最新資訊。而以離散查詢為基礎的方法，則必須在演算法中選擇最適合的整數查詢數目來進行危害。</span><span class="sxs-lookup"><span data-stu-id="18b92-194">This is important to squeeze every last ounce of efficiency out of phase estimation algorithms because it allows us to choose precisely the experiment that would provide the most information about $E$; whereas methods based on discrete queries must make do with compromising by choosing the best integer number of queries in the algorithm.</span></span>

<span data-ttu-id="18b92-195">以具體的例子來說，請考慮評估不是閘道旋轉角度的問題，而是旋轉量子系統的 procession 頻率。</span><span class="sxs-lookup"><span data-stu-id="18b92-195">As a concrete example of this, consider the problem of estimating not the rotation angle of a gate but the procession frequency of a rotating quantum system.</span></span>
<span data-ttu-id="18b92-196">描述這類量子 dynamics 的單一 $U (t) = R_z (2 \ omega t) $ 表示演進時間 $t $ 和 unknown frequency $ \omega $。</span><span class="sxs-lookup"><span data-stu-id="18b92-196">The unitary that describes such quantum dynamics is $U(t)=R_z(2\omega t)$ for evolution time $t$ and unknown frequency $\omega$.</span></span>
<span data-ttu-id="18b92-197">在此內容中，我們可以使用單一 $R _z $ 閘道來模擬任何 $t $ 的 $U (t) $，因為這種情況不需要將自己限制為只對單一的查詢進行個別的查詢。</span><span class="sxs-lookup"><span data-stu-id="18b92-197">In this context, we can simulate $U(t)$ for any $t$ using a single $R_z$ gate and as such do not need to restrict ourselves to only discrete queries to the unitary.</span></span>
<span data-ttu-id="18b92-198">這類連續模型也有一個屬性，而該屬性的頻率大於 $ 2 \ pi $，可從使用連續查詢的階段估計程式中學習，因為對數函式的分支切割所產生的階段資訊，可能會顯示在 $t $ 的非接近值上執行的實驗結果。</span><span class="sxs-lookup"><span data-stu-id="18b92-198">Such a continuous model also has the property that frequencies greater than $2\pi$ can be learned from phase estimation processes that use continuous queries because phase information that would otherwise be masked by the branch-cuts of the logarithm function can be revealed from the results of experiments performed on non-commensurate values of $t$.</span></span>
<span data-ttu-id="18b92-199">因此，針對階段估計 oracle 的這類連續查詢模型，不只適用于這些問題，而且也優於離散查詢模型。</span><span class="sxs-lookup"><span data-stu-id="18b92-199">Thus for problems such as this continuous query models for the phase estimation oracle are not only appropriate but are also preferable to the discrete query model.</span></span>
<span data-ttu-id="18b92-200">基於這個理由，這 Q# 兩種形式的查詢都有其功能，並讓使用者能夠根據其需求和可用的 oracle 類型來決定階段估計演算法。</span><span class="sxs-lookup"><span data-stu-id="18b92-200">For this reason Q# has functionality for both forms of queries and leave it to the user to decide upon a phase estimation algorithm to fit their needs and the type of oracle that is available.</span></span>

## <a name="dynamical-generator-modeling"></a><span data-ttu-id="18b92-201">Dynamical 產生器模型化</span><span class="sxs-lookup"><span data-stu-id="18b92-201">Dynamical Generator Modeling</span></span> ##

<span data-ttu-id="18b92-202">時間演進的產生器描述狀態如何隨著時間而演進。</span><span class="sxs-lookup"><span data-stu-id="18b92-202">Generators of time-evolution describe how states evolve through time.</span></span> <span data-ttu-id="18b92-203">比方說，量子狀態 $ \ket{\psi} $ 的 dynamics 是由薛丁格方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = H \ket{\psi (t) }，\end{align} $ $ （Hermitian 矩陣 $H $，也稱為 Hamiltonian）作為動作產生器。</span><span class="sxs-lookup"><span data-stu-id="18b92-203">For instance, the dynamics of a quantum state $\ket{\psi}$ is governed by the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = H \ket{\psi(t)}, \end{align} $$ with a Hermitian matrix $H$, known as the Hamiltonian, as the generator of motion.</span></span> <span data-ttu-id="18b92-204">指定初始狀態 $ \ket{\psi (0) } $ at time $t = $0，在時間 $t $ 的正式解決方案，在主體中可能是寫入 $ $ \begin{align} \ket{\psi (t) } = U (t) \ket{\psi (0) }，\end{align} $ $，其中矩陣指數 $U (t) = e ^ {-i H t} $ 稱為單一時間演進運算子。</span><span class="sxs-lookup"><span data-stu-id="18b92-204">Given an initial state $\ket{\psi(0)}$ at time $t=0$, the formal solution to this equation at time $t$ may be, in principle, written $$ \begin{align} \ket{\psi(t)} = U(t)\ket{\psi(0)}, \end{align} $$ where the matrix exponential $U(t)=e^{-i H t}$ is known as the unitary time-evolution operator.</span></span> <span data-ttu-id="18b92-205">雖然我們將焦點放在下列的表單產生器，但我們強調此概念的廣泛套用，例如模擬開放式量子系統或更抽象的差異方程式。</span><span class="sxs-lookup"><span data-stu-id="18b92-205">Though we focus on generators of this form in the following, we emphasize that the concept applies more broadly, such as to the simulation of open quantum systems, or to more abstract differential equations.</span></span>

<span data-ttu-id="18b92-206">Dynamical 模擬的主要目標是在量子電腦量子位中編碼的某些量子狀態上執行時間演進操作員。</span><span class="sxs-lookup"><span data-stu-id="18b92-206">A primary goal of dynamical simulation is to implement the time-evolution operator on some quantum state encoded in qubits of a quantum computer.</span></span>  <span data-ttu-id="18b92-207">在許多情況下，Hamiltonian 可能會細分成部分 $d $ 簡易詞彙的總和</span><span class="sxs-lookup"><span data-stu-id="18b92-207">In many cases, the Hamiltonian may be broken into a sum of some $d$ simpler terms</span></span>

<span data-ttu-id="18b92-208">$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="18b92-208">$$ \begin{align} H & = \sum^{d-1}_{j=0} H_j, \end{align} $$</span></span>

<span data-ttu-id="18b92-209">在量子電腦上執行每個詞彙的時間演進是很容易的。</span><span class="sxs-lookup"><span data-stu-id="18b92-209">where time-evolution by each term alone is easy to implement on a quantum computer.</span></span> <span data-ttu-id="18b92-210">比方說，如果 $H _j $ 是在量子位暫存器第1個和第二個元素上執行的 Pauli $X _1X_2 $ 運算子 `qubits` ，則任何時間的時間演進 $t $ 可透過呼叫作業（具有簽章）來實作為 `Exp([PauliX,PauliX], t, qubits[1..2])` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="18b92-210">For instance, if $H_j$ is a Pauli $X_1X_2$ operator acting on the 1st and 2nd elements of the qubit register `qubits`, time-evolution by it for any time $t$ may be implemented simply by calling the operation `Exp([PauliX,PauliX], t, qubits[1..2])`, which has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="18b92-211">如同 Hamiltonian 模擬稍後所述，其中一個解決方案是以更簡單的作業來 $H $ 進行大約的時間演進</span><span class="sxs-lookup"><span data-stu-id="18b92-211">As discussed later in Hamiltonian Simulation, one solution then is to approximate time-evolution by $H$ with a sequence of simpler operations</span></span>

<span data-ttu-id="18b92-212">$ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/r} e ^ {-iH \_ 1 t/r} \cdots e ^ {-iH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r) ，\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="18b92-212">$$ \begin{align} U(t) & = \left( e^{-iH\_0 t / r} e^{-iH\_1 t / r} \cdots e^{-iH\_{d-1} t / r} \right)^{r} + \mathcal{O}(d^2 \max_j \\|H\_j\\|^2 t^2/r), \end{align} $$</span></span>

<span data-ttu-id="18b92-213">其中 > $0 的整數 $r 會控制近似值誤差。</span><span class="sxs-lookup"><span data-stu-id="18b92-213">where the integer $r > 0$ controls the approximation error.</span></span>

<span data-ttu-id="18b92-214">Dynamical 產生器模型化程式庫提供了一個架構，可根據更簡單的產生器，以有系統的方式編碼複雜的</span><span class="sxs-lookup"><span data-stu-id="18b92-214">The dynamical generator modeling library provides a framework for systematically encoding complicated generators in terms of simpler generators.</span></span> <span data-ttu-id="18b92-215">如此一來，就可以將這類描述傳遞給模擬程式庫，以根據選擇的模擬演算法來執行時間演進，並自動處理許多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="18b92-215">Such a description may then be passed to, say, the simulation library to implement time-evolution by a simulation algorithm of choice, with many details automatically taken care of.</span></span>

> [!TIP]
> <span data-ttu-id="18b92-216">範例中涵蓋了下面所述的 dynamical 產生器程式庫。</span><span class="sxs-lookup"><span data-stu-id="18b92-216">The dynamical generator library described below is covered in the samples.</span></span> <span data-ttu-id="18b92-217">如需以 Ising 模型為基礎的範例，請參閱 [ **IsingGenerators** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators)。</span><span class="sxs-lookup"><span data-stu-id="18b92-217">For an example based on the Ising model, please see the [**IsingGenerators** sample](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators).</span></span>
> <span data-ttu-id="18b92-218">如需以分子 Hydrogen 為基礎的範例，請參閱 [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) 和 [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) 範例。</span><span class="sxs-lookup"><span data-stu-id="18b92-218">For an example based on molecular Hydrogen, please see the [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) and [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) samples.</span></span>

### <a name="complete-description-of-a-generator"></a><span data-ttu-id="18b92-219">產生器的完整描述</span><span class="sxs-lookup"><span data-stu-id="18b92-219">Complete Description of a Generator</span></span> ###

<span data-ttu-id="18b92-220">在最上層，Hamiltonian 的完整描述包含在 `EvolutionGenerator` 具有兩個元件的使用者定義型別中：</span><span class="sxs-lookup"><span data-stu-id="18b92-220">At the top level, a complete description of a Hamiltonian is contained in the `EvolutionGenerator` user-defined type which has two components.:</span></span>

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

<span data-ttu-id="18b92-221">`GeneratorSystem`使用者定義型別是 Hamiltonian 的傳統描述。</span><span class="sxs-lookup"><span data-stu-id="18b92-221">The `GeneratorSystem` user-defined type is a classical description of the Hamiltonian.</span></span>

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

<span data-ttu-id="18b92-222">元組的第一個元素 `Int` 會將 $d $ 的詞彙數目儲存在 Hamiltonian 中，而第二個專案 `(Int -> GeneratorIndex)` 則是將 $ 0 的整數索引 \{ （1,..., d-1 $）對應 \} 至 `GeneratorIndex` 使用者定義類型的函式，可唯一識別 Hamiltonian 中的每個基本詞彙。</span><span class="sxs-lookup"><span data-stu-id="18b92-222">The first element `Int` of the tuple stores the number of terms $d$ in the Hamiltonian, and the second element `(Int -> GeneratorIndex)` is a function that maps an integer index in $\{0,1,...,d-1\}$ to a `GeneratorIndex` user-defined type which uniquely identifies each primitive term in the Hamiltonian.</span></span> <span data-ttu-id="18b92-223">請注意，藉由在 Hamiltonian 中將詞彙集合表示為函式，而不是陣列 `GeneratorIndex[]` ，這可以讓的即時計算， `GeneratorIndex` 這在描述具有大量詞彙的 hamiltonian 時特別有用。</span><span class="sxs-lookup"><span data-stu-id="18b92-223">Note that by expressing the collection of terms in the Hamiltonian as a function rather than as an array `GeneratorIndex[]`, this allows for on-the-fly computation of the `GeneratorIndex` which is especially useful when describing Hamiltonians with a large number of terms.</span></span>

<span data-ttu-id="18b92-224">十分，我們不會對所識別的基本詞彙強加慣例，因為這 `GeneratorIndex` 是容易模擬的。</span><span class="sxs-lookup"><span data-stu-id="18b92-224">Crucially, we do not impose a convention on what primitive terms identified by the `GeneratorIndex` are easy-to-simulate.</span></span> <span data-ttu-id="18b92-225">比方說，基本詞彙可以是上述的 Pauli 運算子，但它們也可以是 Fermionic 的 annihilation 和建立運算子，這些運算子通常用於量子化學模擬。</span><span class="sxs-lookup"><span data-stu-id="18b92-225">For instance, primitive terms could be Pauli operators as discussed above, but they could also be Fermionic annihilation and creation operators commonly used in quantum chemistry simulation.</span></span> <span data-ttu-id="18b92-226">它本身不會有 `GeneratorIndex` 意義，因為它不會描述其指向之詞彙的時間演進，可能會實作為量子電路。</span><span class="sxs-lookup"><span data-stu-id="18b92-226">By itself, a `GeneratorIndex` is meaningless as it does not describe how time-evolution by the term it points to may be implemented as a quantum circuit.</span></span>

<span data-ttu-id="18b92-227">解決方法是指定 `EvolutionSet` 使用者定義型別，將任何 `GeneratorIndex` 取自某個標準集合的設定，對應至單一運算子（ `EvolutionUnitary` 以量子電路表示）。</span><span class="sxs-lookup"><span data-stu-id="18b92-227">This is resolved by specifying an `EvolutionSet` user-defined type that maps any `GeneratorIndex`, drawn from some canonical set, to a unitary operator, the `EvolutionUnitary`, expressed as a quantum circuit.</span></span> <span data-ttu-id="18b92-228">`EvolutionSet`會定義結構的慣例 `GeneratorIndex` ，也會定義一組可能的 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="18b92-228">The `EvolutionSet` defines the convention of how a `GeneratorIndex` is structured, and also defines the set of possible `GeneratorIndex`.</span></span>

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a><span data-ttu-id="18b92-229">Pauli 運算子產生器</span><span class="sxs-lookup"><span data-stu-id="18b92-229">Pauli Operator Generators</span></span> ###

<span data-ttu-id="18b92-230">明確且有用的產生器範例是 Hamiltonian，這是 Pauli 運算子的總和，每個都可能有不同的係數。</span><span class="sxs-lookup"><span data-stu-id="18b92-230">A concrete and useful example of generators are Hamiltonians that are a sum of Pauli operators, each possibly with a different coefficient.</span></span>
<span data-ttu-id="18b92-231">$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j，\end{align} $ $，其中每個 $ \hat H_j $ 現在都從 Pauli 群組中繪製。</span><span class="sxs-lookup"><span data-stu-id="18b92-231">$$ \begin{align} H & = \sum^{d-1}_{j=0} a_j H_j, \end{align} $$ where each $\hat H_j$ is now drawn from the Pauli group.</span></span> <span data-ttu-id="18b92-232">針對這類系統，我們會提供類型的，以 `PauliEvolutionSet()` `EvolutionSet` 定義 Pauli 群組的元素和係數的識別方式 `GeneratorIndex` （具有下列簽章）。</span><span class="sxs-lookup"><span data-stu-id="18b92-232">For such systems, we provide the `PauliEvolutionSet()` of type `EvolutionSet` that defines a convention for how an element of the Pauli group and a coefficient may be identified by a `GeneratorIndex`, which has the following signature.</span></span>

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

<span data-ttu-id="18b92-233">在編碼中，第一個參數會 `Int[]` 指定 Pauli 字串，其中 $ \Hat I\rightarrow $0、$ \Hat X\rightarrow $1、$ \Hat Y\rightarrow $2 和 $ \Hat Z\rightarrow $3。</span><span class="sxs-lookup"><span data-stu-id="18b92-233">In our encoding, the first parameter `Int[]` specifies a Pauli string, where $\hat I\rightarrow 0$, $\hat X\rightarrow 1$, $\hat Y\rightarrow 2$, and $\hat Z\rightarrow 3$.</span></span> <span data-ttu-id="18b92-234">第二個參數會將 `Double[]` Pauli 字串的係數儲存在 Hamiltonian 中。</span><span class="sxs-lookup"><span data-stu-id="18b92-234">The second parameter `Double[]` stores the coefficient of the Pauli string in the Hamiltonian.</span></span> <span data-ttu-id="18b92-235">請注意，只會使用這個陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="18b92-235">Note that only the first element of this array is used.</span></span> <span data-ttu-id="18b92-236">第三個參數 `Int[]` 會索引此 Pauli 字串所作用的量子位，而且不能有重複的元素。</span><span class="sxs-lookup"><span data-stu-id="18b92-236">The third parameter `Int[]` indexes the qubits that this Pauli string acts on, and must have no duplicate elements.</span></span> <span data-ttu-id="18b92-237">因此，Hamiltonian 詞彙 $0.4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ 可能會表示為</span><span class="sxs-lookup"><span data-stu-id="18b92-237">Thus the Hamiltonian term $0.4 \hat X_0 \hat Y_8\hat I_2\hat Z_1$ may be represented as</span></span>

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

<span data-ttu-id="18b92-238">`PauliEvolutionSet()`是一種函式，它會將 `GeneratorIndex` 此表單的任何一個對應至具有下列簽章的 `EvolutionUnitary` 。</span><span class="sxs-lookup"><span data-stu-id="18b92-238">The `PauliEvolutionSet()` is a function that maps any `GeneratorIndex` of this form to an `EvolutionUnitary` with the following signature.</span></span>

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

<span data-ttu-id="18b92-239">第一個參數代表時間持續時間，會乘以 `GeneratorIndex` 單一演進的係數。</span><span class="sxs-lookup"><span data-stu-id="18b92-239">The first parameter represents a time-duration, that will be multiplied by the coefficient in the `GeneratorIndex`, of unitary evolution.</span></span> <span data-ttu-id="18b92-240">第二個參數是單一動作的量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="18b92-240">The second parameter is the qubit register the unitary acts on.</span></span> 

### <a name="time-dependent-generators"></a><span data-ttu-id="18b92-241">Time-Dependent 產生器</span><span class="sxs-lookup"><span data-stu-id="18b92-241">Time-Dependent Generators</span></span> ###

<span data-ttu-id="18b92-242">在許多情況下，我們也想要模型化時間相依的產生器，可能發生在薛丁格方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = \hat H (t) \ket{\psi (t) }、\end{align} $ $，而產生器 $ \hat H (t) $ 現在是與時間相依。</span><span class="sxs-lookup"><span data-stu-id="18b92-242">In many cases, we are also interested in modelling time-dependent generators, as might occur in the Schrödinger equation $$ \begin{align} i\frac{d \ket{\psi(t)}}{d t} & = \hat H(t) \ket{\psi(t)}, \end{align} $$ where the generator $\hat H(t)$ is now time-dependent.</span></span> <span data-ttu-id="18b92-243">從上述時間獨立的產生器到此情況的延伸模組很簡單。</span><span class="sxs-lookup"><span data-stu-id="18b92-243">The extension from the time-independent generators above to this case is straightforward.</span></span> <span data-ttu-id="18b92-244">`GeneratorSystem`我們會改為使用使用者定義型別，而不是針對所有時間 $t $ 來修正 Hamiltonian 的問題 `GeneratorSystemTimeDependent` 。</span><span class="sxs-lookup"><span data-stu-id="18b92-244">Rather than having a fixed `GeneratorSystem` describing the Hamiltonian for all times $t$, we instead have the `GeneratorSystemTimeDependent` user-defined type.</span></span>

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

<span data-ttu-id="18b92-245">第一個參數是連續的排程參數 $s \in [0，1] $，而這種類型的函式會傳回 `GeneratorSystem` 該排程的。</span><span class="sxs-lookup"><span data-stu-id="18b92-245">The first parameter is a continuous schedule parameter $s\in [0,1]$, and functions of this type return a `GeneratorSystem` for that schedule.</span></span> <span data-ttu-id="18b92-246">請注意，schedule 參數可能會與實體時間參數（例如 $s = t/T $）呈線性關聯，以供模擬 $T $ 的時間總計。</span><span class="sxs-lookup"><span data-stu-id="18b92-246">Note that the schedule parameter may be linearly related to the physical time parameter e.g. $s = t / T$, for some total time of simulation $T$.</span></span> <span data-ttu-id="18b92-247">但一般而言，這種情況並不需要。</span><span class="sxs-lookup"><span data-stu-id="18b92-247">In general however, this need not be the case.</span></span>

<span data-ttu-id="18b92-248">同樣地，此產生器的完整描述需要 `EvolutionSet` ，因此我們會定義 `EvolutionSchedule` 使用者定義型別。</span><span class="sxs-lookup"><span data-stu-id="18b92-248">Similarly, a complete description of this generator requires an `EvolutionSet`, and so we define an `EvolutionSchedule` user-defined type.</span></span>

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
