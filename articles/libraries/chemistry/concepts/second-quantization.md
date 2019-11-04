---
title: 第二個量化 |Microsoft Docs
description: 第二個量化概念檔
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: b3cc7eb8139d2df6e02de371ccf7a423e58ea76d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210401"
---
# <a name="second-quantization"></a><span data-ttu-id="44cdb-103">第二個量化</span><span class="sxs-lookup"><span data-stu-id="44cdb-103">Second Quantization</span></span>

<span data-ttu-id="44cdb-104">第二個量化會透過不同的透鏡來查看電子結構的問題。</span><span class="sxs-lookup"><span data-stu-id="44cdb-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="44cdb-105">第二個量化不會將每個 $N _e $ electrons 指派給特定狀態（或 orbital），而是會追蹤每個 orbital 並儲存每個的，並且同時自動確保的對稱屬性。對應的 wave 函數。</span><span class="sxs-lookup"><span data-stu-id="44cdb-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="44cdb-106">這很重要，因為它允許指定量子化學模型，而不需要擔心 symmetrizing 輸入狀態（如 fermions 所需），同時也因為第二個量化允許使用小型配量來模擬這類模型電腦.</span><span class="sxs-lookup"><span data-stu-id="44cdb-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="44cdb-107">作為第二個量化的範例，讓我們假設 $ \ psi_0 \cdots \ psi_ {N-1} $ 是一組 orthonormal 的空間 orbitals。</span><span class="sxs-lookup"><span data-stu-id="44cdb-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="44cdb-108">系統會選擇這些 orbitals，盡可能在視為有限的基礎集內正確地表示系統。</span><span class="sxs-lookup"><span data-stu-id="44cdb-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="44cdb-109">這類 orbitals 的常見範例是不可部分完成的 orbitals，它會形成 hydrogen atom 的 eigenbasis。</span><span class="sxs-lookup"><span data-stu-id="44cdb-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="44cdb-110">因為 electrons 有兩個旋轉狀態，所以可以將兩個 electrons crammed 到每個這類的空間 orbital 中。</span><span class="sxs-lookup"><span data-stu-id="44cdb-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="44cdb-111">也就是說，有效的基礎狀態的格式為 $ \ psi_ {0，\uparrow}，\ldots，\ psi_ {N-1，\uparrow}，\ psi_ {0，\downarrow}，\ldots，\ psi_ {N-1，\downarrow} $，其中 $ \uparrow $ 和 $ \downarrow $ 是指定微調程度之兩個 eigenstates 的標籤靈活性.</span><span class="sxs-lookup"><span data-stu-id="44cdb-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="44cdb-112">$ （J，\sigma） $ for $ \sigma \in \{\uparrow，\downarrow\}$ 的這個結合索引稱為「微調-orbital」，因為它會同時儲存空間和微調的自由度程度。</span><span class="sxs-lookup"><span data-stu-id="44cdb-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="44cdb-113">在化學程式庫中，微調 orbitals 會儲存在 `SpinOrbital` 的資料結構中，並依照下列方式建立。</span><span class="sxs-lookup"><span data-stu-id="44cdb-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="44cdb-114">這表示我們可以正式地將 wave 函式的微調和空間部分的基礎視為 $ \ psi_{0} \cdots \ psi_ {2N-1} $，其中每個索引現在都是 $ （j，\sigma） $ 的列舉。</span><span class="sxs-lookup"><span data-stu-id="44cdb-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="44cdb-115">其中一個可能的列舉是 $g （j，\sigma） = j + N\sigma ' $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="44cdb-116">另一個可能的列舉是 $h （j，\sigma） = 2 \* j + \sigma $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="44cdb-117">量子化學程式庫可以使用這些慣例，而這類編碼中的微調 orbitals 可以具現化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="44cdb-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="44cdb-118">對於 fermionic 系統，Pauli 排除原則會防止在任何微調 orbital 中同時出現一個以上的 electron。</span><span class="sxs-lookup"><span data-stu-id="44cdb-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="44cdb-119">這表示我們可以將 $ \ psi_1 $ 的兩個法律狀態撰寫為 \begin{equation} \ psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $ \ psi_1 $ 不會被佔用，} </span><span class="sxs-lookup"><span data-stu-id="44cdb-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="44cdb-120">\ket{1}_1 & \text{if $ \ psi_1 $ 已佔用。}</span><span class="sxs-lookup"><span data-stu-id="44cdb-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="44cdb-121">\end{cases} \end{equation} 這種編碼方式非常適合用於量子電腦，因為這表示我們可以將電子職業儲存成單一配量位。</span><span class="sxs-lookup"><span data-stu-id="44cdb-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="44cdb-122">$ 2N $ 微調 orbitals 的職業狀態可以同樣地儲存在 $ 2N $ qubits 中。</span><span class="sxs-lookup"><span data-stu-id="44cdb-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="44cdb-123">例如，如果 $N = $2，則 state $ $ \ket{0} \ket{1} \ket{1} \ket{0}，$ $</span><span class="sxs-lookup"><span data-stu-id="44cdb-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="44cdb-124">會對應到微調 orbitals $1 $ 和 $2 $，並以餘數空白來佔用。</span><span class="sxs-lookup"><span data-stu-id="44cdb-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="44cdb-125">同樣地，state $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}，$ $</span><span class="sxs-lookup"><span data-stu-id="44cdb-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="44cdb-126">沒有 electrons，也稱為「清理狀態」。</span><span class="sxs-lookup"><span data-stu-id="44cdb-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="44cdb-127">第二個量化的美觀副作用是，我們不再需要明確追蹤量子狀態的反對稱性。</span><span class="sxs-lookup"><span data-stu-id="44cdb-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="44cdb-128">這是因為在我們看到的情況下，狀態的反對稱性代表本身，而不是透過建立及摧毀微調 orbital 之電子職業的運算子反 commutation 規則。</span><span class="sxs-lookup"><span data-stu-id="44cdb-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="44cdb-129">Fermionic 運算子</span><span class="sxs-lookup"><span data-stu-id="44cdb-129">Fermionic operators</span></span>

<span data-ttu-id="44cdb-130">以第二個量化為基礎的向量的兩個基本運算子稱為「建立」和「annihilation 運算子」。</span><span class="sxs-lookup"><span data-stu-id="44cdb-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="44cdb-131">這些運算子會在特定位置插入或破壞 electrons。</span><span class="sxs-lookup"><span data-stu-id="44cdb-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="44cdb-132">這些會分別表示 $a ^ \ dagger_j $ 和 $a _j $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="44cdb-133">例如，\begin{align} ^ \ dagger_1 \ket{0}_1 = \ket{1}_1，\quad a ^ \ dagger_1 \ket{1}_1 = 0，\quad a_1 \ket{0}_1 = 0，\quad a_1 \ket{1}_1 = \ket{0}_1。</span><span class="sxs-lookup"><span data-stu-id="44cdb-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="44cdb-134">\end{align} 請注意，這裡 $a ^ \ dagger_1 \ket{1}_1 = 0 $ 和 $a _1 \ket{0}_1 $ yield 零向量 not $ \ket{0}_1 $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="44cdb-135">因此，這類運算子不是 Hermitian，也不是單一。</span><span class="sxs-lookup"><span data-stu-id="44cdb-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="44cdb-136">我們會使用 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 類型來代表一般建立和 annihilation 運算子。</span><span class="sxs-lookup"><span data-stu-id="44cdb-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="44cdb-137">例如，單一建立運算子會以下列方式表示。</span><span class="sxs-lookup"><span data-stu-id="44cdb-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="44cdb-138">此外，我們也可以使用這類運算子來表達 $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \ dagger_1 ^ \ dagger_2 \ket{0}^ {\otimes 4}。</span><span class="sxs-lookup"><span data-stu-id="44cdb-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="44cdb-139">$ $ 這一系列的運算子會使用C#類似上述的單一微調 orbital 案例的程式碼，在 Hamiltonian 模擬程式庫內進行構建：</span><span class="sxs-lookup"><span data-stu-id="44cdb-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="44cdb-140">對於 $k $ Fermions 的系統，在第二個量化中，建立運算子 $a ^ \ dagger_i $ 的動作是由 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、0_i、\ldots、n_k} = （-1） ^ {S_i} \ket{n_1、n_2、\ldots、1_i、\ldots、n_k}、$ $ 和 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、1_i、\ldots、n_k} = 0、$ $，其中 $S _i = \ sum_ {j < i} a ^ \ dagger_j a_j $ 測量單一物件狀態中的 Fermions 總數，且索引 $j < i $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="44cdb-141">第三個運算子也經常用於第二個量化標記法。</span><span class="sxs-lookup"><span data-stu-id="44cdb-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="44cdb-142">這個運算子稱為「數位」運算子，是由 \begin{equation} n_i = a ^ \ dagger_i a_i 所定義。</span><span class="sxs-lookup"><span data-stu-id="44cdb-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="44cdb-143">\end{equation} 這個運算子會計算特定微調 orbital 的職業，也就是說 \begin{align} n_i \ket{0}_i & = 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="44cdb-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="44cdb-144">n_i \ket{1}_i & = \ket{1}_i。</span><span class="sxs-lookup"><span data-stu-id="44cdb-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="44cdb-145">\end{align} 類似于上述 `FermionTerm` 範例，此數位運算子的結構如下所示。</span><span class="sxs-lookup"><span data-stu-id="44cdb-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have ommitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="44cdb-146">不過，在 fermionic 系統中使用建立或 annihilation 運算子時，會發生奧妙。</span><span class="sxs-lookup"><span data-stu-id="44cdb-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="44cdb-147">我們需要所有有效的配量狀態在標籤的交換下都是反對稱的。</span><span class="sxs-lookup"><span data-stu-id="44cdb-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="44cdb-148">這表示 $ $ a ^ \ dagger_2 ^ \ dagger_1 \ket{0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket{0}。</span><span class="sxs-lookup"><span data-stu-id="44cdb-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="44cdb-149">$ $ 這類運算子稱為「反運算」，一般而言，在任何 $i 中，j $ 我們 \begin{align} 了 ^ \ dagger_i ^ \ dagger_j =-（1-\ delta_ {i，j}） ^ \ dagger_j ^ \ dagger_i，\quad ^ \ dagger_i a_j = \ delta_ {i，j}-a_j ^ \ dagger_i。</span><span class="sxs-lookup"><span data-stu-id="44cdb-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="44cdb-150">因此，\end{align} 會將下列兩個 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> 實例視為 inequivalent</span><span class="sxs-lookup"><span data-stu-id="44cdb-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="44cdb-151">每個建立運算子的需求都表示，使用第二個量化標記法，會排除反對稱性 Fermions 所面臨的挑戰。</span><span class="sxs-lookup"><span data-stu-id="44cdb-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="44cdb-152">相反地，挑戰會在我們的建立運算子定義中重新浮現。</span><span class="sxs-lookup"><span data-stu-id="44cdb-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="44cdb-153">使用反 commutation 規則時，某些 `LadderSequence` 實例實際上會對應到相同的 fermionic 運算子序列，有時最多為負號。</span><span class="sxs-lookup"><span data-stu-id="44cdb-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="44cdb-154">例如，請考慮 Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="44cdb-155">這應採用我們定義每個 `FermionTerm`的標準排序。</span><span class="sxs-lookup"><span data-stu-id="44cdb-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="44cdb-156">任何 `FermionTerm` 都會自動放入標準順序，如下所示。</span><span class="sxs-lookup"><span data-stu-id="44cdb-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="44cdb-157">第二-量化 Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="44cdb-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="44cdb-158">這可能會 unsurprising[電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中的 Hamiltonian，可以根據建立和 annihilation 運算子來撰寫。</span><span class="sxs-lookup"><span data-stu-id="44cdb-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="44cdb-159">特別是，如果 $ \psi\_j $ 是構成基礎的微調 orbitals，則</span><span class="sxs-lookup"><span data-stu-id="44cdb-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="44cdb-160">\begin{equation} \hat{H} = \sum\_{pq} H\_{pq} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_p a ^ \dagger\_q a\_ra\_s + h\_{\textrm nuc}，\label{eq： totalHam} \end{equation}，其中 $h\_{\textrm nuc} $ 是一項的能源（這是在近似值之下的常數），而</span><span class="sxs-lookup"><span data-stu-id="44cdb-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="44cdb-161">\begin{align} h\_{pq} & = \int\_{-\infty} ^ \infty \psi ^\*\_p （x\_1） \left （-\frac{\nabla ^ 2}{2} + V （x\_1） \right） \psi\_q （x\_1） \mathrm{d} ^ 3 倍\_1，\end{align}</span><span class="sxs-lookup"><span data-stu-id="44cdb-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="44cdb-162">其中 $V （x） $ 是 mean 欄位的潛能，而</span><span class="sxs-lookup"><span data-stu-id="44cdb-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="44cdb-163">\begin{align} h\_{pqrs} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*（x\_1） \psi\_q ^\*（x\_2） \left （\frac{1}{| x_1-x_2 |} \right） \psi\_r （x\_2） \psi\_s （x\_1） \mathrm{d} ^ 3 倍\_1 \ mathrm {d} ^ 3 倍\_2. \ 標籤 {eq：積分} \end{align}</span><span class="sxs-lookup"><span data-stu-id="44cdb-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="44cdb-164">\_{pq} $ $h 的詞彙稱為一個 electron 的積分，因為所有這類詞彙都只牽涉到單一 electrons，同樣地 $h\_{pqrs} $ 是兩個 electron 的積分。</span><span class="sxs-lookup"><span data-stu-id="44cdb-164">The terms $h\_{pq}$ are refered to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="44cdb-165">它們稱為「積分」，因為計算這些係數的值需要整數。</span><span class="sxs-lookup"><span data-stu-id="44cdb-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="44cdb-166">其中一個 electron 詞彙描述個別 electrons 的動態能源，以及其與 nuclei 的電動欄位的互動。</span><span class="sxs-lookup"><span data-stu-id="44cdb-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="44cdb-167">另一方面，兩個 electron 的積分描述 electrons 之間的互動。</span><span class="sxs-lookup"><span data-stu-id="44cdb-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="44cdb-168">這些詞彙所代表之意義的直覺，可以從組成每一個的建立和 annihilation 運算子中以往累積所有。</span><span class="sxs-lookup"><span data-stu-id="44cdb-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="44cdb-169">例如，$h _ {pq} a ^ \ dagger_p a_q $ 描述從微調 orbital $q $ 到微調 orbital $p $ 的 electron 跳躍。</span><span class="sxs-lookup"><span data-stu-id="44cdb-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="44cdb-170">同樣地，$h _ {pqrs} a ^ \ dagger_p ^ \ dagger_q a_r a_s $ （適用于相異 $p、q、r、s $）一詞描述了微調 orbitals 中的兩個 electrons $r $，而 $s $ 散佈于彼此之間，最後再以微調 orbitals $p $ 和 $q $ 為結尾。</span><span class="sxs-lookup"><span data-stu-id="44cdb-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="44cdb-171">如果 $r = q $ and $p = s $，則 $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ 會提供與兩個 electrons 相關聯的能源損失，但不會描述 dynamical 進程。</span><span class="sxs-lookup"><span data-stu-id="44cdb-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="44cdb-172">我們可能會使用 `FermionHamiltonian` 類別來代表這類 Hamiltonians，這基本上是包含所有所需 `FermionTerm` 實例的清單。</span><span class="sxs-lookup"><span data-stu-id="44cdb-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="44cdb-173">由於 Hamiltonians 是由定義所 Hermitian，因此我們會使用更特殊化的型別來編制詞彙的索引，`HermitianFermionTerm` 也會在檢查詞彙是否相等時使用 Hermitian 對稱。</span><span class="sxs-lookup"><span data-stu-id="44cdb-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="44cdb-174">讓我們來建造一些解說範例。</span><span class="sxs-lookup"><span data-stu-id="44cdb-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="44cdb-175">請考慮 Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="44cdb-176">我們可以使用 Hamiltonian 運算子為 Hermitian 運算子的事實來簡化這種結構。</span><span class="sxs-lookup"><span data-stu-id="44cdb-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="44cdb-177">使用 `Add`將詞彙新增至 Hamiltonian 時，任何非 Hermitian 的詞彙（例如 `fermionTerm0`）都會假設為與其 Hermitian 共軛配對。</span><span class="sxs-lookup"><span data-stu-id="44cdb-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="44cdb-178">因此，下列程式碼片段也代表相同的 Hamiltonian：</span><span class="sxs-lookup"><span data-stu-id="44cdb-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="44cdb-179">使用反 commutation 規則，Hamiltonian 中的某些 `FermionTerm` 實例實際上會對應到相同的 fermionic 運算子序列，有時最多為負號。</span><span class="sxs-lookup"><span data-stu-id="44cdb-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="44cdb-180">比方說，請考慮 Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $，這是上面所述之詞彙的總和。</span><span class="sxs-lookup"><span data-stu-id="44cdb-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="44cdb-181">使用者可能不一定清楚這些是對等的詞彙，因此可能會分別新增至 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="44cdb-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="44cdb-182">或者，您可能有興趣修改 Hamiltonian 中已存在的詞彙。</span><span class="sxs-lookup"><span data-stu-id="44cdb-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="44cdb-183">在這些情況下，我們可能會結合對等的詞彙，如下所示。</span><span class="sxs-lookup"><span data-stu-id="44cdb-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="44cdb-184">藉由結合對等詞彙的係數，我們減少了 Hamiltonian 中的總詞彙數。</span><span class="sxs-lookup"><span data-stu-id="44cdb-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="44cdb-185">稍後，這會減少模擬 Hamiltonian 所需的量子閘道數目。</span><span class="sxs-lookup"><span data-stu-id="44cdb-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="44cdb-186">內部標記法</span><span class="sxs-lookup"><span data-stu-id="44cdb-186">Internal Representation</span></span>

<span data-ttu-id="44cdb-187">具有一和二個主體互動的 fermionic Hamiltonian 會以第二量化標記法表示為</span><span class="sxs-lookup"><span data-stu-id="44cdb-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="44cdb-188">$ $ \begin{align} H = \sum\_{pq} H\_{pq} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{pqrs} H\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s}。</span><span class="sxs-lookup"><span data-stu-id="44cdb-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="44cdb-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="44cdb-189">\end{align} $$</span></span>

<span data-ttu-id="44cdb-190">在此標記法中，最多有 $N ^ 2 + N ^ 4 $ 係數。</span><span class="sxs-lookup"><span data-stu-id="44cdb-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="44cdb-191">不過，其中許多係數可能會隨著對應至相同的運算子而收集。</span><span class="sxs-lookup"><span data-stu-id="44cdb-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="44cdb-192">例如，如果 $p、q、r、s $ 是相異的索引，我們可以使用反 commutation 規則來顯示： $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r} a\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{s} a\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{r}。</span><span class="sxs-lookup"><span data-stu-id="44cdb-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="44cdb-193">此外，當 $H $ Hermitian 時，每個非 Hermitian 的 fermionic 運算子（假設 $h\_{pqrs} a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $，在 $H $ 中也可以找到 Hermitian 共軛。</span><span class="sxs-lookup"><span data-stu-id="44cdb-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="44cdb-194">為了唯一編制這些 symmetries 所特性的詞彙群組的索引，我們定義了指數 $ （i\_1、\cdots、i\_n、j\_1、\cdots、j\_m） $ （任何 $n + m $ fermionic 運算子 $a ^ \dagger 的順序）\_{i\_1} \cdots ^ \dagger\_{i\_n}\_{j\_1} \cdots a\_{j\_m} $as 遵循：</span><span class="sxs-lookup"><span data-stu-id="44cdb-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="44cdb-195">所有建立運算子 $a ^ \dagger\_{i\_\cdot} $ 都放在所有 annihilation 運算子之前，$a\_{j\_\cdot} $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="44cdb-196">所有建立運算子索引都是以遞增順序排序，也就是 $i\_1 < i\_2 < \cdots < i\_n $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="44cdb-197">所有的 annihilation 運算子索引都是以遞減順序排序，也就是 $j\_1 > j\_2 \cdots > j\_m $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="44cdb-198">最左邊的索引小於或等於最右邊的索引，也就是 $i\_1 \ le j\_m $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="44cdb-199">讓我們將這組以標準方式排序索引識別為 $ $ \begin{align} （i\_1，\cdots，i\_n，j\_1，\cdots，j\_m） \in S\_{n，m}。</span><span class="sxs-lookup"><span data-stu-id="44cdb-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="44cdb-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="44cdb-200">\end{align} $$</span></span>

<span data-ttu-id="44cdb-201">使用此標準順序時，fermionic Hamiltonian 可能會以 $ $ \begin{align} H = \sum\_{（p，q） \in S\_{1,1}} H '\_{pq} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{p}}{2}+ \sum\_{（p，q，r，s） \in S\_{2,2}} h '\_{pqrs} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} + a ^ \dagger\_{s} a ^ \dagger\_{r} a\_{q} a\_{p}}{2}，\end{align} $ $ 搭配適當調整的一對一和雙 electron 積分 $h '\_{pq} $ 和 $h '\_{pqrs} $。</span><span class="sxs-lookup"><span data-stu-id="44cdb-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

