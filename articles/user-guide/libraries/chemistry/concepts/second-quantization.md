---
title: 第二個量化
description: 瞭解在量副程式設計中為電子結構建立模型的第二個量化方法。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835803"
---
# <a name="second-quantization"></a><span data-ttu-id="21d61-103">第二個量化</span><span class="sxs-lookup"><span data-stu-id="21d61-103">Second Quantization</span></span>

<span data-ttu-id="21d61-104">第二個量化會透過不同的鏡頭來查看電子結構的問題。</span><span class="sxs-lookup"><span data-stu-id="21d61-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="21d61-105">第二個量化不會將每個 $N _e $ 電子指派給特定狀態 (或 orbital) ，而是會追蹤每個 orbital，並儲存每個並儲存是否有 electron，同時也會自動確保對應 wave 函數的對稱屬性。</span><span class="sxs-lookup"><span data-stu-id="21d61-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="21d61-106">這點很重要，因為它可讓您指定量子化學模型，而不需要擔心 symmetrizing 輸入狀態 (如 fermions) 所需，也因為第二個量化允許使用小型量子電腦來模擬這類模型。</span><span class="sxs-lookup"><span data-stu-id="21d61-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="21d61-107">作為第二個量化的範例，讓我們假設 $ \ psi_0 \cdots \ psi_ {N-1} $ 是一組 orthonormal 的空間 orbitals。</span><span class="sxs-lookup"><span data-stu-id="21d61-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="21d61-108">這些 orbitals 會選擇在考慮的有限基礎集中精確地表示系統。</span><span class="sxs-lookup"><span data-stu-id="21d61-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="21d61-109">這類 orbitals 的常見範例為不可部分完成的 orbitals，其形成 hydrogen atom 的 eigenbasis。</span><span class="sxs-lookup"><span data-stu-id="21d61-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="21d61-110">因為電子有兩個旋轉狀態，所以可以將兩個電子 crammed 到每個這類的空間 orbital 中。</span><span class="sxs-lookup"><span data-stu-id="21d61-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="21d61-111">也就是說，有效的基礎狀態的格式為 $ \ psi_ {0，\uparrow}，\ldots，\ psi_ {N-1，\uparrow}，\ psi_ {0，\downarrow}，\ldots，\ psi_ {N-1，\downarrow} $，其中 $ \uparrow $ 和 $ \downarrow $ 是指定微調自由度的兩個 eigenstates 的標籤。</span><span class="sxs-lookup"><span data-stu-id="21d61-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="21d61-112">$ (j，\sigma) $ for $ \sigma \in \{ \uparrow，\downarrow $ 的這個結合索引 \} 稱為旋轉 orbital，因為它會儲存空間以及微調的自由度。</span><span class="sxs-lookup"><span data-stu-id="21d61-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="21d61-113">在化學程式庫中，orbitals 會儲存在 `SpinOrbital` 資料結構中，並依照下列方式建立。</span><span class="sxs-lookup"><span data-stu-id="21d61-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

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

<span data-ttu-id="21d61-114">這表示我們可以將 wave 函式的旋轉和空間部分的基礎，視為 $ \ psi_ {0} \cdots \ psi_ {2n-1} $，其中每個索引現在都是 $ (j，\sigma) $ 的列舉。</span><span class="sxs-lookup"><span data-stu-id="21d61-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="21d61-115">其中一個可能的列舉是 $g (j、\sigma) = j + N\sigma ' $。</span><span class="sxs-lookup"><span data-stu-id="21d61-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="21d61-116">另一個可能的列舉是 $h (j、\sigma) = 2 \* j + \sigma $。</span><span class="sxs-lookup"><span data-stu-id="21d61-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="21d61-117">量子化學程式庫可以使用這些慣例，而這類編碼中的旋轉 orbitals 可具現化，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21d61-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

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

<span data-ttu-id="21d61-118">針對 fermionic 系統，Pauli 排除準則會防止一個以上的 electron 同時存在於任何旋轉 orbital 中。</span><span class="sxs-lookup"><span data-stu-id="21d61-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="21d61-119">這表示我們可以針對 $ \ psi_1 $ 撰寫兩個合法狀態，例如 \begin{equation} \ psi_1 \rightarrow \begin{cases} \ket {0} _1 & \text{if $ \ psi_1 $ 未被佔用，} </span><span class="sxs-lookup"><span data-stu-id="21d61-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="21d61-120">\ket {1} _1 & \text{if $ \ psi_1 $ 已被佔用。}</span><span class="sxs-lookup"><span data-stu-id="21d61-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="21d61-121">\end{cases} \end{equation} 此編碼很適合量子電腦，因為這表示我們可以將電子職業儲存為單一量子位。</span><span class="sxs-lookup"><span data-stu-id="21d61-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="21d61-122">$ 2N $ 微調 orbitals 的職業狀態同樣可以儲存在 $ 2N $ 量子位中。</span><span class="sxs-lookup"><span data-stu-id="21d61-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="21d61-123">例如，如果 $N = $2，則狀態 $ $ \ket {0} \ket {1} \ket {1} \ket {0} ，$ $</span><span class="sxs-lookup"><span data-stu-id="21d61-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="21d61-124">會對應到 orbitals $1 $ 和 $2 $，且其餘部分是空的。</span><span class="sxs-lookup"><span data-stu-id="21d61-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="21d61-125">同樣地，state $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}，$ $</span><span class="sxs-lookup"><span data-stu-id="21d61-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="21d61-126">沒有任何電子，也稱為「清理狀態」。</span><span class="sxs-lookup"><span data-stu-id="21d61-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="21d61-127">第二個量化的一項美觀的副作用是，我們不再需要明確地追蹤量子狀態的反對稱性。</span><span class="sxs-lookup"><span data-stu-id="21d61-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="21d61-128">這是因為如我們所見，狀態的反對稱性本身代表本身，而不是透過建立和終結微調 orbital 之電子職業的運算子的反 commutation 規則。</span><span class="sxs-lookup"><span data-stu-id="21d61-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="21d61-129">Fermionic 運算子</span><span class="sxs-lookup"><span data-stu-id="21d61-129">Fermionic operators</span></span>

<span data-ttu-id="21d61-130">以第二個量化為基礎向量的兩個基本運算子稱為「建立」和「annihilation 運算子」。</span><span class="sxs-lookup"><span data-stu-id="21d61-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="21d61-131">這些運算子會在特定位置插入或終結電子。</span><span class="sxs-lookup"><span data-stu-id="21d61-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="21d61-132">這些分別表示 $a ^ \ dagger_j $ 和 $a _j $。</span><span class="sxs-lookup"><span data-stu-id="21d61-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="21d61-133">例如，\begin{align} ^ \ dagger_1 \ket {0} _1 = \ket {1} _1、\quad ^ \ dagger_1 \ket {1} _1 = 0、\quad a_1 \ket {0} _1 = 0、\quad a_1 \ket {1} _1 = \ket {0} _1。</span><span class="sxs-lookup"><span data-stu-id="21d61-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="21d61-134">\end{align} 請注意，此處 $a ^ \ dagger_1 \ket {1} _1 = 0 $ 和 $a _1 \ket {0} _1 $ yield 零向量 not $ \ket {0} _1 $。</span><span class="sxs-lookup"><span data-stu-id="21d61-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="21d61-135">因此，這類運算子不是 Hermitian 也不是單一。</span><span class="sxs-lookup"><span data-stu-id="21d61-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="21d61-136">我們使用類型來代表一般建立和 annihilation 運算子 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 。</span><span class="sxs-lookup"><span data-stu-id="21d61-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="21d61-137">例如，單一建立運算子會以下面方式表示。</span><span class="sxs-lookup"><span data-stu-id="21d61-137">For instance, a single creation operator is represented as follow.</span></span>

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

<span data-ttu-id="21d61-138">此外，我們也可以使用這類運算子 express $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}。</span><span class="sxs-lookup"><span data-stu-id="21d61-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="21d61-139">$ $ 這一連串的運算子會使用 c # 程式碼在 Hamiltonian 模擬程式庫中建立，類似上述的單一微調 orbital 案例：</span><span class="sxs-lookup"><span data-stu-id="21d61-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
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

<span data-ttu-id="21d61-140">針對 $k $ Fermions 的系統，在第二個量化中，建立運算子的動作 $a ^ \ dagger_i $ 是由 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、0_i、\ldots、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ldots、1_i、\ldots、n_k}、$ $ 和 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、1_i、\ldots、n_k} = 0、$ $，其中 $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ 測量單一物件狀態中的 Fermions 總數，而且索引 $j < i $。</span><span class="sxs-lookup"><span data-stu-id="21d61-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="21d61-141">第三個運算子也經常用於第二個量化標記法。</span><span class="sxs-lookup"><span data-stu-id="21d61-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="21d61-142">這個運算子稱為 number 運算子，而且是由 \begin{equation} n_i = a ^ \ dagger_i a_i 所定義。</span><span class="sxs-lookup"><span data-stu-id="21d61-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="21d61-143">\end{equation} 這個運算子會計算給定微調 orbital 的職業，也就是 \begin{align} n_i \ket {0} _i &= 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="21d61-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="21d61-144">n_i \ket {1} _i &= \ket {1} _i。</span><span class="sxs-lookup"><span data-stu-id="21d61-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="21d61-145">\end{align} 與上述範例類似 `FermionTerm` ，這個 number 運算子的結構如下所示。</span><span class="sxs-lookup"><span data-stu-id="21d61-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="21d61-146">雖然在 fermionic 系統中使用建立或 annihilation 運算子時，仍會出現奧妙。</span><span class="sxs-lookup"><span data-stu-id="21d61-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="21d61-147">我們要求任何有效的量子狀態在標籤的交換下都是反對稱的。</span><span class="sxs-lookup"><span data-stu-id="21d61-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="21d61-148">這表示 $ $ a ^ \ dagger_2 ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket {0} 。</span><span class="sxs-lookup"><span data-stu-id="21d61-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="21d61-149">$ $ 這類運算子稱為「反上運算」，而在任何 $i 中，j $ \begin{align} ^ \ dagger_i ^ \ dagger_j =- (1-\ delta_ {i，j} ) ^ \ dagger_j ^ \ dagger_i，\quad ^ \ dagger_i a_j = \ delta_ {i，j}-a_j ^ \ dagger_i。</span><span class="sxs-lookup"><span data-stu-id="21d61-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="21d61-150">\end{align} 因此會將下列兩個 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> 實例視為 inequivalent</span><span class="sxs-lookup"><span data-stu-id="21d61-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
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

<span data-ttu-id="21d61-151">每個建立運算子的每個建立運算子都需要使用第二個量化標記法來排除 Fermions 的反對稱性所面臨的挑戰。</span><span class="sxs-lookup"><span data-stu-id="21d61-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="21d61-152">而是在我們的建立運算子定義中重新出現挑戰。</span><span class="sxs-lookup"><span data-stu-id="21d61-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="21d61-153">使用反 commutation 規則時，某些 `LadderSequence` 實例實際上會對應到相同的 fermionic 運算子序列，有時最多可達負號。</span><span class="sxs-lookup"><span data-stu-id="21d61-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="21d61-154">例如，請考慮 Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $。</span><span class="sxs-lookup"><span data-stu-id="21d61-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="21d61-155">這應採用我們為每個定義一個標準順序 `FermionTerm` 。</span><span class="sxs-lookup"><span data-stu-id="21d61-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="21d61-156">任何 `FermionTerm` 會自動放入標準順序，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21d61-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
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

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="21d61-157">第二-量化 Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="21d61-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="21d61-158">也許金錢，在 [電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels) 中，Hamiltonian 可以用建立和 annihilation 運算子來撰寫。</span><span class="sxs-lookup"><span data-stu-id="21d61-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="21d61-159">尤其是，如果 $ \psi \_ j $ 是形成基礎的微調 orbitals，</span><span class="sxs-lookup"><span data-stu-id="21d61-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="21d61-160">\begin{equation} \hat{H} = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ Ra \_ s + H \_ {\textrm nuc}，\label{eq： totalHam} \end{equation} 其中 $h \_ {\textrm nuc} $ (是近似值) 的常數，以及</span><span class="sxs-lookup"><span data-stu-id="21d61-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="21d61-161">\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3 層 \_ 1，\end{align}</span><span class="sxs-lookup"><span data-stu-id="21d61-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="21d61-162">其中 $V (x) $ 是 mean 現場潛力，而</span><span class="sxs-lookup"><span data-stu-id="21d61-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="21d61-163">\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left ( \frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3 倍 x \_ \_ label {eq：積分} mathrm</span><span class="sxs-lookup"><span data-stu-id="21d61-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="21d61-164">$H \_ {pq} $ 的詞彙稱為一 electron 的積分，因為所有這類詞彙只牽涉到單一電子，同樣 $h \_ {pqrs} $ 是雙 electron 的積分。</span><span class="sxs-lookup"><span data-stu-id="21d61-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="21d61-165">它們稱為整數，因為計算這些係數的值需要整數。</span><span class="sxs-lookup"><span data-stu-id="21d61-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="21d61-166">其中一個 electron 詞彙描述個別電子的動態能源，以及其與 nuclei 的電力欄位之間的互動。</span><span class="sxs-lookup"><span data-stu-id="21d61-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="21d61-167">另一方面，這兩個 electron 的積分描述電子之間的互動。</span><span class="sxs-lookup"><span data-stu-id="21d61-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="21d61-168">這些詞彙所代表之意義的直覺可以從建立和組成每一個的 annihilation 運算子以往累積。</span><span class="sxs-lookup"><span data-stu-id="21d61-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="21d61-169">例如，$h _ {pq} a ^ \ dagger_p a_q $ 說明從微調 orbital $q $ 到旋轉 orbital $p $ 的 electron 跳動。</span><span class="sxs-lookup"><span data-stu-id="21d61-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="21d61-170">同樣地，$h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (針對相異的 $p、q、r、s $) 描述兩個微調 orbitals 中的電子 $r $ 和 $s $ 散佈，最後在旋轉 orbitals $p $ 和 $q $。</span><span class="sxs-lookup"><span data-stu-id="21d61-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="21d61-171">如果 $r = q $ 和 $p = s $，$h _ {prrp} a ^ \ dagger_p ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ 可讓與彼此接近的兩個電子相關聯的能源損失，但不會描述 dynamical 流程。</span><span class="sxs-lookup"><span data-stu-id="21d61-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="21d61-172">我們可能會使用類別來代表這類 Hamiltonian `FermionHamiltonian` ，這基本上是包含所有所需 `FermionTerm` 實例的清單。</span><span class="sxs-lookup"><span data-stu-id="21d61-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="21d61-173">因為 Hamiltonian 是依定義 Hermitian，所以我們會使用更特殊化的型別來編制詞彙的索引， `HermitianFermionTerm` 而在檢查詞彙是否相等時也會使用 Hermitian 的對稱型別。</span><span class="sxs-lookup"><span data-stu-id="21d61-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="21d61-174">讓我們來建立一些說明範例。</span><span class="sxs-lookup"><span data-stu-id="21d61-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="21d61-175">請考慮 Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $。</span><span class="sxs-lookup"><span data-stu-id="21d61-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
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
<span data-ttu-id="21d61-176">我們可能會使用 Hamiltonian 運算子為 Hermitian 運算子的事實來簡化此結構。</span><span class="sxs-lookup"><span data-stu-id="21d61-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="21d61-177">使用將詞彙新增至 Hamiltonian 時 `Add` ，任何非 Hermitian 的詞彙（例如） `fermionTerm0` 都會假設成對其 Hermitian 共軛。</span><span class="sxs-lookup"><span data-stu-id="21d61-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="21d61-178">因此，下列程式碼片段也代表相同的 Hamiltonian：</span><span class="sxs-lookup"><span data-stu-id="21d61-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="21d61-179">使用反 commutation 規則時， `FermionTerm` Hamiltonian 中的某些實例實際上會對應到相同的 fermionic 運算子序列，有時最多可達負號。</span><span class="sxs-lookup"><span data-stu-id="21d61-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="21d61-180">例如，請考慮 Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $，這是上述所述詞彙的總和。</span><span class="sxs-lookup"><span data-stu-id="21d61-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="21d61-181">對使用者而言，這些都是對等的詞彙可能不會很清楚，因此可以個別新增至 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="21d61-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="21d61-182">或者，您可能會想要在 Hamiltonian 中修改已經存在的詞彙。</span><span class="sxs-lookup"><span data-stu-id="21d61-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="21d61-183">在這些情況下，我們可能會結合對等詞彙，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21d61-183">In these cases, we may combine equivalent terms as follows.</span></span>
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
<span data-ttu-id="21d61-184">藉由合併對等詞彙的係數，我們會減少 Hamiltonian 中的總詞彙數。</span><span class="sxs-lookup"><span data-stu-id="21d61-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="21d61-185">之後，這會減少模擬 Hamiltonian 所需的量子閘道數目。</span><span class="sxs-lookup"><span data-stu-id="21d61-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="21d61-186">內部標記法</span><span class="sxs-lookup"><span data-stu-id="21d61-186">Internal Representation</span></span>

<span data-ttu-id="21d61-187">具有一和兩個主體互動的 fermionic Hamiltonian 會以第二個量化標記法表示</span><span class="sxs-lookup"><span data-stu-id="21d61-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="21d61-188">$ $ \begin{align} H = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s}。</span><span class="sxs-lookup"><span data-stu-id="21d61-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="21d61-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="21d61-189">\end{align} $$</span></span>

<span data-ttu-id="21d61-190">在此標記法中，最多會有 $N ^ 2 + N ^ 4 $ 係數。</span><span class="sxs-lookup"><span data-stu-id="21d61-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="21d61-191">不過，這些係數當中有許多可能會在對應至相同運算子的情況下收集。</span><span class="sxs-lookup"><span data-stu-id="21d61-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="21d61-192">例如，在 $p、q、r、s $ 是相異的索引，我們可以使用反 commutation 規則來顯示： $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {s} a \_ {r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ s} a \_ {r}。</span><span class="sxs-lookup"><span data-stu-id="21d61-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="21d61-193">此外，當 $H $ 為 Hermitian 時，每個非 Hermitian fermionic 運算子（例如 $h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $）都有 Hermitian 共軛，也可以在 $H $ 中找到。</span><span class="sxs-lookup"><span data-stu-id="21d61-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="21d61-194">為了根據這些 symmetries 來唯一編制詞彙的索引，我們會針對索引 $ (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) $，定義任何 $n + m $ fermionic 運算子序列的標準順序 $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as 如下所示：</span><span class="sxs-lookup"><span data-stu-id="21d61-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="21d61-195">所有建立運算子 $a ^ \dagger \_ {i \_ \cdot} $ 都會放置在所有 annihilation 運算子 $a \_ {j \_ \cdot} $ 之前。</span><span class="sxs-lookup"><span data-stu-id="21d61-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="21d61-196">所有建立運算子索引都會以遞增順序排序，也就是 $i \_ 1< i \_ 2< \cdots < i \_ n $。</span><span class="sxs-lookup"><span data-stu-id="21d61-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="21d61-197">所有的 annihilation 運算子索引會以遞減順序排序，也就是 $j \_ 1> j \_ 2 \cdots > j \_ m $。</span><span class="sxs-lookup"><span data-stu-id="21d61-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="21d61-198">最左邊的索引小於或等於最右邊的索引，也就是 $i \_ 1 \ le j \_ m $。</span><span class="sxs-lookup"><span data-stu-id="21d61-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="21d61-199">讓我們將這組標準方式排序索引識別為 $ $ \begin{align} (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) \in S \_ {n，m}。</span><span class="sxs-lookup"><span data-stu-id="21d61-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="21d61-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="21d61-200">\end{align} $$</span></span>

<span data-ttu-id="21d61-201">使用這個標準順序，fermionic Hamiltonian 可能會以 $ $ \begin{align} H = \sum \_ { (p，q) \In S \_ {1,1} } H ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger { \_ q} a \_ {p}} {2} + \sum \_ { (p，q，r，s) \in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} ，\end{align} $ $，分別適當地調整一次和雙 electron 的積分 $h ' \_ {pq} $ 和 $h ' \_ {pqrs} $。</span><span class="sxs-lookup"><span data-stu-id="21d61-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

