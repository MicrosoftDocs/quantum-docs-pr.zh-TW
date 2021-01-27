---
title: 第二個量化
description: 瞭解在量副程式設計中為電子結構建立模型的第二個量化方法。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: a08e20d5b53aa97cb12ead0dc3a36069d0ec5df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858841"
---
# <a name="second-quantization"></a>第二個量化

第二個量化會透過不同的鏡頭來查看電子結構的問題。
第二個量化不會將每個 $N _e $ 電子指派給特定狀態 (或 orbital) ，而是會追蹤每個 orbital，並儲存每個並儲存是否有 electron，同時也會自動確保對應 wave 函數的對稱屬性。
這點很重要，因為它可讓您指定量子化學模型，而不需要擔心 symmetrizing 輸入狀態 (如 fermions) 所需，也因為第二個量化允許使用小型量子電腦來模擬這類模型。

作為第二個量化的範例，讓我們假設 $ \ psi_0 \cdots \ psi_ {N-1} $ 是一組 orthonormal 的空間 orbitals。
這些 orbitals 會選擇在考慮的有限基礎集中精確地表示系統。
這類 orbitals 的常見範例為不可部分完成的 orbitals，其形成 hydrogen atom 的 eigenbasis。
因為電子有兩個旋轉狀態，所以可以將兩個電子 crammed 到每個這類的空間 orbital 中。
也就是說，有效的基礎狀態的格式為 $ \ psi_ {0，\uparrow}，\ldots，\ psi_ {N-1，\uparrow}，\ psi_ {0，\downarrow}，\ldots，\ psi_ {N-1，\downarrow} $，其中 $ \uparrow $ 和 $ \downarrow $ 是指定微調自由度的兩個 eigenstates 的標籤。
$ (j，\sigma) $ for $ \sigma \in \{ \uparrow，\downarrow $ 的這個結合索引 \} 稱為旋轉 orbital，因為它會儲存空間以及微調的自由度。
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

這表示我們可以將 wave 函式的旋轉和空間部分的基礎，視為 $ \ psi_ {0} \cdots \ psi_ {2n-1} $，其中每個索引現在都是 $ (j，\sigma) $ 的列舉。
其中一個可能的列舉是 $g (j、\sigma) = j + N\sigma ' $。
另一個可能的列舉是 $h (j、\sigma) = 2 * j + \sigma $。
量子化學程式庫可以使用這些慣例，而這類編碼中的旋轉 orbitals 可具現化，如下所示。

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

針對 fermionic 系統，Pauli 排除準則會防止一個以上的 electron 同時存在於任何旋轉 orbital 中。
這表示我們可以針對 $ \ psi_1 $ 撰寫兩個合法狀態，例如 \begin{equation} \ psi_1 \rightarrow \begin{cases} \ket {0} _1 & \text{if $ \ psi_1 $ 未被佔用，} \\\
\ket {1} _1 & \text{if $ \ psi_1 $ 已被佔用。} \end{cases} \end{equation} 此編碼很適合量子電腦，因為這表示我們可以將電子職業儲存為單一量子位。

$ 2N $ 微調 orbitals 的職業狀態同樣可以儲存在 $ 2N $ 量子位中。
例如，如果 $N = $2，則狀態 $ $ \ket {0} \ket {1} \ket {1} \ket {0} ，$ $

會對應到 orbitals $1 $ 和 $2 $，且其餘部分是空的。
同樣地，state $ $ \ket {0} \equiv \ket {0} _{0} \cdots \ket {0}_{N-1}，$ $

沒有任何電子，也稱為「清理狀態」。

第二個量化的一項美觀的副作用是，我們不再需要明確地追蹤量子狀態的反對稱性。
這是因為如我們所見，狀態的反對稱性本身代表本身，而不是透過建立和終結微調 orbital 之電子職業的運算子的反 commutation 規則。

## <a name="fermionic-operators"></a>Fermionic 運算子

以第二個量化為基礎向量的兩個基本運算子稱為「建立」和「annihilation 運算子」。
這些運算子會在特定位置插入或終結電子。
這些分別表示 $a ^ \ dagger_j $ 和 $a _j $。

例如，\begin{align} ^ \ dagger_1 \ket {0} _1 = \ket {1} _1、\quad ^ \ dagger_1 \ket {1} _1 = 0、\quad a_1 \ket {0} _1 = 0、\quad a_1 \ket {1} _1 = \ket {0} _1。
\end{align} 請注意，此處 $a ^ \ dagger_1 \ket {1} _1 = 0 $ 和 $a _1 \ket {0} _1 $ yield 零向量 not $ \ket {0} _1 $。
因此，這類運算子不是 Hermitian 也不是單一。
我們使用類型來代表一般建立和 annihilation 運算子 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> 。
例如，單一建立運算子會以下面方式表示。

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

此外，我們也可以使用這類運算子 express $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}。
$ $ 這一連串的運算子會使用 c # 程式碼在 Hamiltonian 模擬程式庫中建立，類似上述的單一微調 orbital 案例：
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

針對 $k $ Fermions 的系統，在第二個量化中，建立運算子的動作 $a ^ \ dagger_i $ 是由 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、0_i、\ldots、n_k} = (-1) ^ {S_i} \ket{n_1、n_2、\ldots、1_i、\ldots、n_k}、$ $ 和 $ $ a ^ \ dagger_i \ket{n_1、n_2、\ldots、1_i、\ldots、n_k} = 0、$ $，其中 $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ 測量單一物件狀態中的 Fermions 總數，而且索引 $j < i $。

第三個運算子也經常用於第二個量化標記法。
這個運算子稱為 number 運算子，而且是由 \begin{equation} n_i = a ^ \ dagger_i a_i 所定義。
\end{equation} 這個運算子會計算給定微調 orbital 的職業，也就是 \begin{align} n_i \ket {0} _i &= 0 \ nonumber\\\
n_i \ket {1} _i &= \ket {1} _i。
\end{align} 與上述範例類似 `FermionTerm` ，這個 number 運算子的結構如下所示。
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

雖然在 fermionic 系統中使用建立或 annihilation 運算子時，仍會出現奧妙。
我們要求任何有效的量子狀態在標籤的交換下都是反對稱的。
這表示 $ $ a ^ \ dagger_2 ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket {0} 。
$ $ 這類運算子稱為「反上運算」，而在任何 $i 中，j $ \begin{align} ^ \ dagger_i ^ \ dagger_j =- (1-\ delta_ {i，j} ) ^ \ dagger_j ^ \ dagger_i，\quad ^ \ dagger_i a_j = \ delta_ {i，j}-a_j ^ \ dagger_i。
\end{align} 因此會將下列兩個 <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> 實例視為 inequivalent
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

每個建立運算子的每個建立運算子都需要使用第二個量化標記法來排除 Fermions 的反對稱性所面臨的挑戰。
而是在我們的建立運算子定義中重新出現挑戰。 

使用反 commutation 規則時，某些 `LadderSequence` 實例實際上會對應到相同的 fermionic 運算子序列，有時最多可達負號。
例如，請考慮 Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $。
這應採用我們為每個定義一個標準順序 `FermionTerm` 。
任何 `FermionTerm` 會自動放入標準順序，如下所示。
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Second-Quantized Fermionic Hamiltonian

也許金錢，在 [電子系統的量子模型](xref:microsoft.quantum.chemistry.concepts.quantummodels) 中，Hamiltonian 可以用建立和 annihilation 運算子來撰寫。
尤其是，如果 $ \psi \_ j $ 是形成基礎的微調 orbitals，

\begin{equation} \hat{H} = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ Ra \_ s + H \_ {\textrm nuc}，\label{eq： totalHam} \end{equation} 其中 $h \_ {\textrm nuc} $ 是近似值 (的 Born-Oppenheimer 近似值) 和

\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3 層 \_ 1，\end{align}

其中 $V (x) $ 是 mean 現場潛力，而

\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left ( \frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3 倍 x \_ \_ label {eq：積分} mathrm

$H \_ {pq} $ 的詞彙稱為一 electron 的積分，因為所有這類詞彙只牽涉到單一電子，同樣 $h \_ {pqrs} $ 是雙 electron 的積分。
它們稱為整數，因為計算這些係數的值需要整數。
其中一個 electron 詞彙描述個別電子的動態能源，以及其與 nuclei 的電力欄位之間的互動。
另一方面，這兩個 electron 的積分描述電子之間的互動。

這些詞彙所代表之意義的直覺可以從建立和組成每一個的 annihilation 運算子以往累積。
例如，$h _ {pq} a ^ \ dagger_p a_q $ 說明從微調 orbital $q $ 到旋轉 orbital $p $ 的 electron 跳動。
同樣地，$h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (針對相異的 $p、q、r、s $) 描述兩個微調 orbitals 中的電子 $r $ 和 $s $ 散佈，最後在旋轉 orbitals $p $ 和 $q $。
如果 $r = q $ 和 $p = s $，$h _ {prrp} a ^ \ dagger_p ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ 可讓與彼此接近的兩個電子相關聯的能源損失，但不會描述 dynamical 流程。

我們可能會使用類別來代表這類 Hamiltonian `FermionHamiltonian` ，這基本上是包含所有所需 `FermionTerm` 實例的清單。
因為 Hamiltonian 是依定義 Hermitian，所以我們會使用更特殊化的型別來編制詞彙的索引， `HermitianFermionTerm` 而在檢查詞彙是否相等時也會使用 Hermitian 的對稱型別。

讓我們來建立一些說明範例。
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
我們可能會使用 Hamiltonian 運算子為 Hermitian 運算子的事實來簡化此結構。
使用將詞彙新增至 Hamiltonian 時 `Add` ，任何非 Hermitian 的詞彙（例如） `fermionTerm0` 都會假設成對其 Hermitian 共軛。
因此，下列程式碼片段也代表相同的 Hamiltonian：
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

使用反 commutation 規則時， `FermionTerm` Hamiltonian 中的某些實例實際上會對應到相同的 fermionic 運算子序列，有時最多可達負號。
例如，請考慮 Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $，這是上述所述詞彙的總和。
對使用者而言，這些都是對等的詞彙可能不會很清楚，因此可以個別新增至 Hamiltonian。
或者，您可能會想要在 Hamiltonian 中修改已經存在的詞彙。
在這些情況下，我們可能會結合對等詞彙，如下所示。
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
藉由合併對等詞彙的係數，我們會減少 Hamiltonian 中的總詞彙數。
之後，這會減少模擬 Hamiltonian 所需的量子閘道數目。

### <a name="internal-representation"></a>內部標記法

具有一和兩個主體互動的 fermionic Hamiltonian 會以第二個量化標記法表示

$ $ \begin{align} H = \sum \_ {pq} H \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s}。
\end{align} $ $

在此標記法中，最多會有 $N ^ 2 + N ^ 4 $ 係數。
不過，這些係數當中有許多可能會在對應至相同運算子的情況下收集。
例如，在 $p、q、r、s $ 是相異的索引，我們可以使用反 commutation 規則來顯示： $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {s} a \_ {r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ s} a \_ {r}。
$$

此外，當 $H $ 為 Hermitian 時，每個非 Hermitian fermionic 運算子（例如 $h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $）都有 Hermitian 共軛，也可以在 $H $ 中找到。 為了根據這些 symmetries 來唯一編制詞彙的索引，我們會針對索引 $ (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) $，定義任何 $n + m $ fermionic 運算子序列的標準順序 $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $as 如下所示：
-   所有建立運算子 $a ^ \dagger \_ {i \_ \cdot} $ 都會放置在所有 annihilation 運算子 $a \_ {j \_ \cdot} $ 之前。
-   所有建立運算子索引都會以遞增順序排序，也就是 $i \_ 1< i \_ 2< \cdots < i \_ n $。
-   所有的 annihilation 運算子索引會以遞減順序排序，也就是 $j \_ 1> j \_ 2 \cdots > j \_ m $。
-   最左邊的索引小於或等於最右邊的索引，也就是 $i \_ 1 \ le j \_ m $。

讓我們將這組標準方式排序索引識別為 $ $ \begin{align} (i \_ 1、\cdots、i \_ n、j \_ 1、\cdots、j \_ m) \in S \_ {n，m}。
\end{align} $ $

使用這個標準順序，fermionic Hamiltonian 可能會以 $ $ \begin{align} H = \sum \_ { (p，q) \In S \_ {1,1} } H ' \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger { \_ q} a \_ {p}} {2} + \sum \_ { (p，q，r，s) \in s \_ {2,2} } H ' \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {S} + a ^ \dagger \_ {S} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} ，\end{align} $ $，分別適當地調整一次和雙 electron 的積分 $h ' \_ {pq} $ 和 $h ' \_ {pqrs} $。

