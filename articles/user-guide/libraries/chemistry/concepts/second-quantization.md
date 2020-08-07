---
title: 第二個量化
description: 瞭解在量副程式設計中模型化電子結構的第二個量化方法。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: ba77c499d6830b1f78bba39e20b15c4ebe9433fc
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869455"
---
# <a name="second-quantization"></a>第二個量化

第二個量化會透過不同的透鏡來查看電子結構的問題。
第二個量化不會將每個 $N _e $ electrons 指派給特定狀態 (或 orbital) ，而是會追蹤每個 orbital 並儲存每個的，並且同時自動確保對應 wave 函數的對稱屬性。
這很重要，因為它允許指定量子化學模型，而不需要擔心 symmetrizing 輸入狀態 (fermions) 所需，同時也因為第二個量化允許使用小型的量子電腦來模擬這類模型。

作為第二個量化的範例，讓我們假設 $ \ psi_0 \cdots \ psi_ {N-1} $ 是一組 orthonormal 的空間 orbitals。
系統會選擇這些 orbitals，盡可能在視為有限的基礎集內正確地表示系統。
這類 orbitals 的常見範例是不可部分完成的 orbitals，它會形成 hydrogen atom 的 eigenbasis。
因為 electrons 有兩個旋轉狀態，所以可以將兩個 electrons crammed 到每個這類的空間 orbital 中。
也就是說，有效的基礎狀態的格式為 $ \ psi_ {0，\uparrow}，\ldots，\ psi_ {N-1，\uparrow}，\ psi_ {0，\downarrow}，\ldots，\ psi_ {N-1，\downarrow} $，其中 $ \uparrow $ 和 $ \downarrow $ 是指定旋轉自由度的兩個 eigenstates 的標籤。
這個結合的 $ (j、\sigma) $ for $ \sigma \in \{ \uparrow、\downarrow $ 的索引 \} 稱為「微調-orbital」，因為它會同時儲存空間和微調的自由度程度。
在化學程式庫中，orbitals 會儲存在 `SpinOrbital` 資料結構中，並依照下列方式建立。

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

這表示我們可以正式地將 wave 函式的微調和空間部分的基礎視為 $ \ psi_ {0} \cdots \ psi_ {2n-1} $，其中每個索引現在是 $ (j，\sigma) $ 的列舉。
其中一個可能的列舉 $g (j，\sigma) = j + N\sigma ' $。
另一個可能的列舉 $h (j，\sigma) = 2 * j + \sigma $。
量子化學程式庫可以使用這些慣例，而這類編碼中的微調 orbitals 可以具現化，如下所示。

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

對於 fermionic 系統，Pauli 排除原則會防止在任何微調 orbital 中同時出現一個以上的 electron。
這表示我們可以將 $ \ psi_1 $ 的兩個法律狀態撰寫為 \begin{equation} \ psi_1 \rightarrow \begin{cases} \ket {0} _1 & \text{if $ \ psi_1 $ 不會被佔用，}\\\
\ket {1} _1 & \text{if $ \ psi_1 $ 已佔用。} \end{cases} \end{equation} 這種編碼方式非常適合用於量子電腦，因為這表示我們可以將電子職業儲存成單一配量位。

$ 2N $ 微調 orbitals 的職業狀態可以同樣地儲存在 $ 2N $ qubits 中。
例如，如果 $N = $2，則 state $ $ \ket {0} \ket {1} \ket {1} \ket {0} ，$ $

會對應到微調 orbitals $1 $ 和 $2 $，並以餘數空白來佔用。
同樣地，state $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}，$ $

沒有 electrons，也稱為「清理狀態」。

第二個量化的美觀副作用是，我們不再需要明確追蹤量子狀態的反對稱性。
這是因為在我們看到的情況下，狀態的反對稱性代表本身，而不是透過建立及摧毀微調 orbital 之電子職業的運算子反 commutation 規則。

## <a name="fermionic-operators"></a>Fermionic 運算子

以第二個量化為基礎的向量的兩個基本運算子稱為「建立」和「annihilation 運算子」。
這些運算子會在特定位置插入或破壞 electrons。
這些會分別表示 $a ^ \ dagger_j $ 和 $a _j $。

例如，\begin{align} ^ \ dagger_1 \ket {0} _1 = \ket {1} _1，\quad a ^ \ dagger_1 \ket {1} _1 = 0，\quad a_1 \ket {0} _1 = 0，\quad a_1 \ket {1} _1 = \ket {0} _1。
\end{align} 請注意，這裡 $a ^ \ dagger_1 \ket {1} _1 = 0 $，而 $a _1 \ket {0} _1 $ yield 零向量 not $ \ket {0} _1 $。
因此，這類運算子不是 Hermitian，也不是單一。
我們使用類型來代表一般建立和 annihilation 運算子 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 。
例如，單一建立運算子會以下列方式表示。

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

此外，我們也可以使用這類運算子來表達 $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} ^ {\otimes 4}。
$ $ 這一系列的運算子會使用 c # 程式碼，在 Hamiltonian 模擬程式庫內建立，類似上述的單一微調 orbital 案例：
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

對於 $k $ Fermions 的系統，在第二個量化中，建立運算子 $a ^ \ dagger_i $ 的動作是由 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、0_i、\ldots、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ldots、1_i、\ldots、n_k}、$ $ 和 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、1_i、\ldots、n_k} = 0、$ $ where $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ 測量單一物件狀態中的 Fermions 總數，且索引 $j < i $。

第三個運算子也經常用於第二個量化標記法。
這個運算子稱為「數位」運算子，是由 \begin{equation} n_i = a ^ \ dagger_i a_i 所定義。
\end{equation} 這個運算子會計算特定微調 orbital 的職業，也就是說 \begin{align} n_i \ket {0} _i &= 0 \ nonumber\\\
n_i \ket {1} _i &= \ket {1} _i。
\end{align} 類似于上述 `FermionTerm` 範例，此數位運算子的結構如下所示。
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

不過，在 fermionic 系統中使用建立或 annihilation 運算子時，會發生奧妙。
我們需要所有有效的配量狀態在標籤的交換下都是反對稱的。
這表示 $ $ a ^ \ dagger_2 ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket {0} 。
$ $ 這類運算子稱為「反運算」，一般而言，在任何 $i 中，j $ 我們 \begin{align} 了 ^ \ dagger_i ^ \ dagger_j =- (1-\ delta_ {i，j} ) ^ \ dagger_j ^ \ dagger_i，\quad a ^ \ dagger_i a_j = \ delta_ {i，j}-a_j ^ \ dagger_i。
\end{align}，因此會將下列兩個 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> 實例視為 inequivalent
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

每個建立運算子的需求都表示，使用第二個量化標記法，會排除反對稱性 Fermions 所面臨的挑戰。
相反地，挑戰會在我們的建立運算子定義中重新浮現。 

使用反 commutation 規則時，某些 `LadderSequence` 實例實際上會對應到相同的 fermionic 運算子序列，有時最多為負號。
例如，請考慮 Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $。
這應採用我們定義每個的標準順序 `FermionTerm` 。
[任何] 會 `FermionTerm` 自動依下列方式進入標準順序。
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

## <a name="second-quantized-fermionic-hamiltonian"></a>第二-量化 Fermionic Hamiltonian

這可能會 unsurprising[電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels)中的 Hamiltonian，可以根據建立和 annihilation 運算子來撰寫。
特別是，如果 $ \psi \_ j $ 是構成基礎的微調 orbitals，則

\begin{equation} \hat{H} = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ Ra \_ s + H \_ {\textrm nuc}，\label{eq： totalHam} \end{equation}，其中 $h \_ {\textrm nuc} $ 是 (的近似值) 的一種常數，

\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x 1 \_) \mathrm{d} ^ 3 倍 \_ 1，\end{align}

其中 $V (x) $ 是 mean 欄位的潛能，而

\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left ( \frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3 倍 \_ \_ 。 \ 標籤 {eq：積分} mathrm

$H \_ {pq} $ 的詞彙稱為一 electron 的積分，因為所有這類詞彙都只牽涉到單一 electrons，同樣地 $h \_ {pqrs} $ 是兩個 electron 的積分。
它們稱為「積分」，因為計算這些係數的值需要整數。
其中一個 electron 詞彙描述個別 electrons 的動態能源，以及其與 nuclei 的電動欄位的互動。
另一方面，兩個 electron 的積分描述 electrons 之間的互動。

這些詞彙所代表之意義的直覺，可以從組成每一個的建立和 annihilation 運算子中以往累積所有。
例如，$h _ {pq} a ^ \ dagger_p a_q $ 描述從微調 orbital $q $ 到微調 orbital $p $ 的 electron 跳躍。
同樣地，$h _ {pqrs} 一詞 ^ \ dagger_p ^ \ dagger_q a_r a_s $ (針對相異 $p、q、r、s $) 描述微調 orbitals 中的兩個 electrons $r $ 和 $s $ 散佈彼此之間，最後再結束微調 orbitals $p $ 和 $q $。
如果 $r = q $ and $p = s $，則 $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ 會提供與兩個 electrons 相關聯的能源損失，但不會描述 dynamical 進程。

我們可能會使用 `FermionHamiltonian` 類別來代表這類 Hamiltonians，這基本上是包含所有所需 `FermionTerm` 實例的清單。
由於 Hamiltonians 是由定義所 Hermitian，因此我們會使用更特殊化的類型來編制詞彙的索引， `HermitianFermionTerm` 而在檢查詞彙是否相等時也會使用 Hermitian 對稱。

讓我們來建造一些解說範例。
請考慮 Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $。
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
我們可以使用 Hamiltonian 運算子為 Hermitian 運算子的事實來簡化這種結構。
使用將詞彙新增至 Hamiltonian 時 `Add` ，任何非 Hermitian 的詞彙（例如） `fermionTerm0` 都會假設為與其 Hermitian 共軛配對。
因此，下列程式碼片段也代表相同的 Hamiltonian：
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

使用反 commutation 規則， `FermionTerm` Hamiltonian 中的某些實例實際上會對應到相同的 fermionic 運算子序列，有時最多可達負號。
比方說，請考慮 Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $，這是上面所述之詞彙的總和。
使用者可能不一定清楚這些是對等的詞彙，因此可能會分別新增至 Hamiltonian。
或者，您可能有興趣修改 Hamiltonian 中已存在的詞彙。
在這些情況下，我們可能會結合對等的詞彙，如下所示。
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
藉由結合對等詞彙的係數，我們減少了 Hamiltonian 中的總詞彙數。
稍後，這會減少模擬 Hamiltonian 所需的量子閘道數目。

### <a name="internal-representation"></a>內部標記法

具有一和二個主體互動的 fermionic Hamiltonian 會以第二量化標記法表示為

$ $ \begin{align} H = \sum \_ {pq} h \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s}。
\end{align} $ $

在此標記法中，最多有 $N ^ 2 + N ^ 4 $ 係數。
不過，其中許多係數可能會隨著對應至相同的運算子而收集。
例如，在 $p、q、r、s $ 是相異的索引，我們可以使用反 commutation 規則顯示： $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ s} a { \_ r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {s} a \_ {r}。
$$

此外，當 $H $ Hermitian 時，每個非 Hermitian fermionic 運算子（假設 $h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $）都有 Hermitian 共軛，也可以在 $H $ 中找到。 若要以唯一的方式為這些 symmetries 所特性的詞彙群組編制索引，我們定義了標準的排序方式，針對 $ (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) $ of 任何 $n + m $ fermionic 運算子序列 $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as：
-   所有建立運算子 $a ^ \dagger \_ {i \_ \cdot} $ 都放在所有 annihilation 運算子 $a \_ {j \_ \cdot} $ 之前。
-   所有建立運算子索引都是以遞增順序排序，也就是 $i \_ 1< i \_ 2< \cdots < i \_ n $。
-   所有的 annihilation 運算子索引都是以遞減順序排序，也就是 $j \_ 1> j \_ 2 \cdots > j \_ m $。
-   最左邊的索引小於或等於最右邊的索引，也就是 $i \_ 1 \ le j \_ m $。

讓我們將這組以標準方式排序索引識別為 $ $ \begin{align} (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) \in S \_ {n，m}。
\end{align} $ $

使用此標準順序時，fermionic Hamiltonian 可能會以 $ $ \begin{align} H = \sum \_ { (p、q) \In S \_ {1,1} } H ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger { \_ q} a \_ {p}} {2} + \sum { \_ (p、q、r、s) \in S \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} ，\end{align} $ $ 搭配適當調整的一和雙 electron 積分，分別 $h ' \_ {pq} $ 和 $h ' \_ {pqrs} $。

