---
title: 標準程式庫中的資料結構 Q#
description: 深入瞭解 Microsoft 標準程式庫中的資料結構、oracles 和 dynamical 產生器 Q# 。
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 222fa7d0d33d4ac6c15e9ee9e6e97f380867a145
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868508"
---
# <a name="data-structures-and-modeling"></a>資料結構和模型化 #

## <a name="classical-data-structures"></a>傳統資料結構 ##

除了用來表示量子概念的使用者定義型別之外，canon 也提供作業、函式和型別，來處理用於控制量子系統的傳統資料。
例如，函 <xref:microsoft.quantum.arrays.reversed> 式會採用陣列做為輸入，並以反向順序傳回相同的陣列。
然後，這可用於類型的陣列 `Qubit[]` ，以避免在整數的量子表示之間進行轉換時，必須套用不必要的 $ \operatorname{SWAP} $ 閘道。
同樣地，在上一節中，我們看到表單類型適用 `(Int, Int -> T)` 于代表隨機存取集合，因此函式 <xref:microsoft.quantum.arrays.lookupfunction> 提供了從陣列類型來建立這類類型的便利方式。

### <a name="pairs"></a>形式 ###

Canon 支援配對的功能樣式表示法，藉由解構來補充存取元組：

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>陣列 ###

Canon 提供數個函式來運算元組。
這些函式具有型別參數化，因此可以與任何型別的陣列搭配使用 Q# 。
例如，函式 <xref:microsoft.quantum.arrays.reversed> 會傳回新的陣列，其專案是從其輸入的反向順序。
這可以用來變更呼叫作業時，配量暫存器的表示方式：

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

同樣地， <xref:microsoft.quantum.arrays.subarray> 函數也可以用來重新排列或接受陣列元素的子集：

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

結合流量控制時，陣列操作函式（例如） <xref:microsoft.quantum.arrays.zip> 可提供一種強大的方式來表達量副程式：

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

## <a name="oracles"></a>Oracles ##

在[階段估計](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm)和[振幅放大](https://en.wikipedia.org/wiki/Amplitude_amplification)文獻中，oracle 的概念通常會出現。
這裡的 oracle 一詞指的是黑箱量子副程式，它會在一組 qubits 上運作，並以階段傳回答案。
您通常可以將此副程式視為接受 oracle 的量子演算法輸入，除了其他一些參數之外，也會套用一系列的量子作業，並將此量子副程式的呼叫視為基本閘道。
很明顯地，若要實際執行較大的演算法，必須提供 oracle 的實體分解，但不需要這樣的分解，就能瞭解呼叫 oracle 的演算法。
在中 Q# ，此抽象概念是藉由使用該作業為第一個類別的值來表示，因此作業可以用黑箱的方式傳遞至配量演算法的執行。
此外，使用者定義的型別也用來以型別安全的方式標記不同的 oracle 標記法，因此很容易不小心人們不同種類的黑箱作業。

這類 oracles 會出現在許多不同的內容中，包括著名的範例，例如[Grover 的搜尋](https://en.wikipedia.org/wiki/Grover%27s_algorithm)和量子模擬演算法。
在這裡，我們只著重在兩個應用程式所需的 oracles：振幅放大和階段估計。
我們會先討論振幅放大 oracles，再繼續進行階段估計。

### <a name="amplitude-amplification-oracles"></a>振幅放大 Oracles ###

「波幅放大」演算法的目標，是要藉由套用一系列的狀態反射來執行初始狀態與最終狀態之間的旋轉。
為了讓演算法運作，它需要這兩種狀態的規格。
這些規格是由兩個 oracles 所提供。
這些 oracles 的工作方式是將輸入分成兩個空格：「目標」子空間和「初始」子空間。
Oracles 會識別這類 subspaces，類似于 Pauli 運算子如何藉由將 $ \pm $1 階段套用至這些空格，來識別兩個空格。
主要的差別在於，這些空間在此應用程式中不需要是半個空格。
另請注意，這兩個 subspaces 通常不是互斥的，因為有兩個空間成員的向量。
如果不是 true，則幅度放大會沒有作用，因此我們需要初始子空間與目標子空間的非零重迭。

我們會代表我們需要的第一個 oracle，讓振幅放大成為 $P \_ $0，並定義為具有下列動作。  對於 "子空間 $P 中的所有州 $ \ket{x} $， \_ $P 0 \ket{x} =-\ket{x} $，而對於所有狀態 $ \ket{y} $ （不在此子空間中），我們都 \_ 0 \ket{y} = \ket{y} $。
標示目標子空間（$P _1 $）的 oracle 會採用完全相同的格式。
針對目標子空間中的所有狀態 $ \ket{x} $ (亦即，針對您想要演算法輸出的所有狀態) ，$P _1 \ ket {x} =-\ket{x} $。
同樣地，針對不在目標子空間中的所有州 $ \ket{y} $ $P _1 \ ket {y} = \ket{y} $。
然後再結合這兩個反射來形成一個運算子，以制定振幅放大的單一步驟，$Q =-P_0 P_1 $，其中整體減號只在受控制的應用程式中考慮。
振幅放大接著會採用初始子空間中的初始狀態 $ \ket{\psi} $，然後執行 $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $ 來繼續進行。
執行這類反復專案可確保如果一個開始的初始狀態與已標記的空格重迭，則會在 $m $ 反復專案之後，將此重迭變成 $ \sin ^ 2 ( [2m + 1] \theta) $，如果其中一項開頭為已標示為 $ \sin ^ 2 ( \theta) $。
因此，我們通常會想要選擇 $m $ 成為免費的參數，例如 $ [2m + 1] \theta = \ pi/2 $;不過，這類嚴格的選擇對於某些形式的振幅放大（例如，固定點波幅放大）而言並不重要。
此程式可讓我們在標示的子空間中準備狀態，方法是使用對標記函式 quadratically 較少的查詢，以及在嚴格的傳統裝置上進行狀態準備功能。
這就是為什麼振幅放大是許多量子運算應用程式的重要建立區塊。

為了瞭解如何使用演算法，提供可提供 oracles 結構的範例會很有用。  請考慮在此設定中執行 Grover 的資料庫搜尋演算法。
在 Grover 的搜尋中，目標是要將 state $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket {0} $ 轉換成其中一個 (可能) 許多標記的狀態。
為了進一步簡化，讓我們來看看唯一標示的狀態是 $ \ket $ 的情況 {0} 。
接著，我們設計了兩個 oracles：一個只會將初始狀態 $ \ket{+} ^ {\otimes n} $ 標示為減號，另一個標記標記為狀態 $ \ket {0} $ 且正負號為。
第二個閘道可以使用下列進程作業來執行，方法是使用 canon 中的控制流程作業：

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

此 oracle 是作業的特殊案例，可 <xref:microsoft.quantum.canon.rall1> 讓您透過任意階段旋轉，而不是反映案例 $ \phi = \pi $。
在此情況下， `RAll1` 類似于 <xref:microsoft.quantum.intrinsic.r1> 序言作業，因為它會旋轉大約 $ \ket{11\cdots1} $，而不是單一 qubit 狀態 $ \ket {1} $。

標記初始子空間的 oracle 會以類似的方式進行結構化。
在 [虛擬代碼：

1. 將 $H $ 閘道套用到每個 qubit。
2. 將 $X $ 閘道套用到每個 qubit。
3. 將 $n-$1 控制的 $Z $-閘道套用至 $n ^ {\text{th}} $ qubit。
4. 將 $X $ 閘道套用到每個 qubit。
5. 將 $H $ 閘道套用到每個 qubit。

這次，我們也會示範如何 <xref:microsoft.quantum.canon.applywith> 搭配上述作業一起使用 <xref:microsoft.quantum.canon.rall1> ：

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

然後，我們可以將這兩個 oracles 合併在一起，以便在兩個狀態之間旋轉，並使用與 $ Hadamard ^ n} $ 成正比的幾個 \Sqrt{2 閘道，以決定性的方式將 $ \ket{+} ^ {\otimes n} $ 轉換成 $ \ket {0} $ (ie $m \propto \sqrt{2 ^ n} $) 與大約 $ 2 ^ n $ 層，在 {0} 觀察到結果 $0 $ 之前，必須先準備並測量初始狀態，以非決定性的方式準備 $ \ket $ 狀態。

### <a name="phase-estimation-oracles"></a>階段估計 Oracles ###

針對階段估計，oracles 會更自然。
階段估計的目標是設計一個副程式，它能夠從單一矩陣的特徵值進行取樣。
這種方法在量子模擬中是不可或缺的，因為在化學和材質科學方面，這些特徵值會提供 energies 的量子系統，為我們提供有關材質的階段圖表以及分子驅使分子的反應 dynamics 的重要資訊。
階段估計的每個類別都需要輸入單一。
這個單一的程式通常是由兩種 oracles 類型的其中一種來描述。

> [!TIP]
> 以下所述的兩個 oracle 類型都涵蓋在範例中。
> 若要深入瞭解連續查詢 oracles，請參閱[ **PhaseEstimation**範例](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)。
> 若要深入瞭解離散查詢 oracles，請參閱[ **IsingPhaseEstimation**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)。

第一種類型的 oracle，我們稱之為獨立查詢 oracle，並以使用者定義型別表示 <xref:microsoft.quantum.oracles.discreteoracle> ，只牽涉到單一的矩陣。
如果 $U $ 是我們想要預估其特徵值的單一，則適用于 $U $ 的 oracle 只是執行 $U $ 之副程式的一個獨立元件。
例如，您可以使用 $U $，將上面定義的 oracle $Q $ 視為用於振幅估計。
此矩陣的特徵值可用來估計初始和目標狀態之間的重迭，$ \sin ^ 2 ( \theta) $，使用 quadratically 較少的樣本，而不是其他所需。
這會獲得使用 Grover oracle $Q $ 做為輸入，以作為幅度估計的標記，來進行階段估計的應用。
在量子測量中廣泛使用的另一個常見應用程式包含估計較小的旋轉角度。
換句話說，我們想要估計 $ \theta $ 的格式未知的旋轉閘道 $R _z ( \theta) $。
在這種情況下，我們要與之互動的副程式，是為了瞭解適用于此閘道之 $ \theta $ 的固定值為 $ $ \begin{align} U & = R_z ( \theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ theta/2} \end{bmatrix}。
\end{align} $ $

第二種類型的 oracle 在階段估計中使用的是連續查詢 oracle，以 <xref:microsoft.quantum.oracles.continuousoracle> 類型表示。
針對階段估計的連續查詢 oracle 會採用 $U (t) $ 的形式，其中 $t $ 是傳統方式已知的實數。
如果我們讓 $U $ 是固定的，則持續查詢 oracle 會採用 $U (t) = U ^ t $ 的格式。
這可讓我們查詢矩陣（例如 $ \sqrt{U} $），而無法直接在離散查詢模型中執行。

當您不探查特定的單一，而想要瞭解單一的產生器屬性時，這種類型的 oracle 就很有價值。
例如，在 dynamical 量子模擬中，目標是要設計 (t) = e ^ {-i H t} $ for a Hermitian 矩陣 $H $ 和進化時間 $t $ 的 $U 的配量線路。
$U (t) $ 的特徵值與 $H $ 的特徵值直接相關。
若要瞭解這一點，請考慮 $H $： $H \ket{E} = E\ket {E} $ 的 eigenvector，然後很容易就能從矩陣指數的電源序列定義中看出 $U (t) \ket{E} = e ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $。
因此，估計 $U (t) $ 的 eigenphase 會提供 eigenvalue $E $，假設 eigenvector $ \ket{E} $ 已輸入至階段估計演算法。
不過，在此情況下，您可以選擇使用者的值 $t $，因為 $t $ 的任何夠小的值，eigenvalue $E $ 可以透過 $E =-\ phi/t $ 來唯一反轉。
由於配量模擬方法提供執行小數進化的能力，因此在查詢單一時，這會授與階段估計演算法額外的自由度，特別是在離散查詢模型只允許 unitaries 為整數 $j $ 的 $U ^ j $ 的格式時，oracle 可讓我們針對任何實際的值 $t $ 來估計 $U ^ t $ 格式的 unitaries。
這一點很重要，因為它可讓我們選擇精確的實驗，以提供最多有關 $E $;而以離散查詢為基礎的方法，則必須在演算法中選擇最適合的整數查詢，以做出危害。

做為具體的範例，請考慮估計不是閘道旋轉角度的問題，而是旋轉量子系統的 procession 頻率。
描述這類配量 dynamics 的單一是 $U (t) = R_z (2 \ omega t) $ 用於進化時間 $t $ 和 unknown frequency $ \omega $。
在此內容中，我們可以使用單一 $R _z $ 閘道，針對任何 $t $ 模擬 $U (t) $，因此不需要將自己限制為僅針對單一的個別查詢。
這類連續模型也具有大於 $ 2 \ pi $ 的屬性，可以從使用連續查詢的階段估計程式中學習，因為會以其他方式在接近 $ 的非 $t 值上執行的實驗結果，顯示對數函式的分支-剪下所要遮罩的階段資訊。
因此，對於這類問題而言，oracle 估計的持續查詢模型不只適合，而是針對離散查詢模型。
基於這個理由 Q# ，這兩種形式的查詢都有功能，讓使用者可以根據自己的需求和可用的 oracle 類型來決定階段估計演算法。

## <a name="dynamical-generator-modeling"></a>Dynamical 產生器模型 ##

時間進化的產生器會描述狀態如何隨著時間進化。 例如，配量狀態 $ \ket{\psi} $ 的 dynamics 是由 Schrödinger 方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = H \ket{\psi (t) }，\end{align} $ $ 加上 Hermitian 矩陣 $H $ （稱為 Hamiltonian）做為動作的產生器所控制。 指定初始狀態 $ \ket{\psi (0) } $ （時間 $t = $0）時，此方程式在時間 $t $ 的正式解決方案，在主體中，寫入 $ $ \begin{align} \ket{\psi (t) } = U (t) \ket{\psi (0) }，\end{align} $ $，其中矩陣指數 $U (t) = e ^ {-i H t} $ 稱為「單一時間進化」運算子。 雖然我們將焦點放在下列表單的產生器，但我們強調此概念更廣泛地套用，例如模擬開放的量子系統，或更多抽象的差異方程式。

Dynamical 模擬的主要目標是針對在量子電腦的 qubits 中編碼的某些配量狀態，執行時間進化運算子。  在許多情況下，Hamiltonian 可能會細分為一些 $d $ 簡單的詞彙的總和

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j，\end{align} $ $

而每個詞彙的時間進化只是在量子電腦上輕鬆執行。 例如，如果 $H _j $ 是 Pauli $X _1X_2 $ 運算子會在 qubit 暫存器的第1個和第2個元素上 `qubits` 執行，則在任何時間內，只要呼叫具有簽章的作業，就可以只實作用 $t $ 的時間進化 `Exp([PauliX,PauliX], t, qubits[1..2])` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。 如稍後在 Hamiltonian 模擬中所討論，其中一個解決方案就是以較簡單的作業順序 $H $ 來預估時間演進

$ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/r} e ^ {-iH \_ 1 t/r} \cdots e ^ {-iH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r) ，\end{align} $ $

其中 $r 的整數 > $0 控制近似值錯誤。

Dynamical 產生器模型程式庫提供一個架構，可根據簡單的產生器，有系統地編碼複雜的產生器。 如此一來，您就可以將這類描述傳遞給模擬程式庫，以透過選擇的模擬演算法來執行時間演進，並自動處理許多細節。

> [!TIP]
> 以下所述的 dynamical 產生器程式庫已涵蓋在範例中。 如需以 Ising 模型為基礎的範例，請參閱[ **IsingGenerators**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators)。
> 如需以分子 Hydrogen 為基礎的範例，請參閱[**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)和[**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui)範例。

### <a name="complete-description-of-a-generator"></a>產生器的完整描述 ###

在最上層，Hamiltonian 的完整描述包含在包含 `EvolutionGenerator` 兩個元件的使用者自訂類型中：

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem`使用者定義型別是 Hamiltonian 的傳統描述。

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

元組的第一個專案會將 Hamiltonian 中的 `Int` 詞彙數目儲存 $d $，而第二個元素 `(Int -> GeneratorIndex)` 是將 $ \{ 0、1,..., d-1 $ 中的整數索引對應 \} 至 `GeneratorIndex` 使用者定義類型的函式，以唯一識別 Hamiltonian 中的每個基本詞彙。 請注意，藉由將 Hamiltonian 中的詞彙集合表示為函式，而不是陣列 `GeneratorIndex[]` ，這可讓您在 `GeneratorIndex` 以大量詞彙描述 Hamiltonians 時特別有用。

十分，我們不會對所識別的基本詞彙提供慣例，而 `GeneratorIndex` 是容易模擬。 比方說，基本詞彙可以是 Pauli 運算子，如上所述，但它們也可以 Fermionic 在量子化學模擬中常用的 annihilation 和建立運算子。 本身本身並沒有 `GeneratorIndex` 意義，因為它不會描述它所指向之詞彙的時間演進如何實作為配量線路。

其解決方式是指定 `EvolutionSet` 使用者定義型別，將 `GeneratorIndex` 從某個標準集所繪製的任何對應到單一運算子，也就是以配量 `EvolutionUnitary` 線路表示。 `EvolutionSet`定義結構化方式的慣例 `GeneratorIndex` ，也會定義一組可能的 `GeneratorIndex` 。

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Pauli 運算子產生器 ###

產生器的具體和有用範例是 Hamiltonians，這是 Pauli 運算子的總和，每一個都可能有不同的係數。
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j、\end{align} $ $，其中每個 $ \hat H_j $ 現在都是從 Pauli 群組繪製而來。 針對這類系統，我們提供了類型的，以 `PauliEvolutionSet()` `EvolutionSet` 定義 Pauli 群組的元素和係數如何識別的慣例 `GeneratorIndex` ，其具有下列簽章。

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

在編碼中，第一個參數會 `Int[]` 指定 Pauli 字串，其中 $ \Hat I\rightarrow $0、$ \Hat X\rightarrow $1、$ \Hat Y\rightarrow $2 和 $ \Hat Z\rightarrow $3。 第二個參數會將 `Double[]` Pauli 字串的係數儲存在 Hamiltonian 中。 請注意，只會使用這個陣列的第一個元素。 第三個參數 `Int[]` 會為這個 Pauli 字串作用所在的 qubits 編制索引，而且不能有重複的元素。 因此，Hamiltonian 詞彙 $0.4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ 可能會以

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`是一個函式，會將 `GeneratorIndex` 此表單的任何一個對應至具有下列簽章的 `EvolutionUnitary` 。

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

第一個參數代表持續時間，會乘以單一進化的中的係數 `GeneratorIndex` 。 第二個參數是單一作用所在的 qubit 註冊。 

### <a name="time-dependent-generators"></a>時間相依的產生器 ###

在許多情況下，我們也會想要將時間相依的產生器模型化，如同 Schrödinger 方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = \hat H (t) \ket{\psi (t) }，\end{align} $ $，其中產生器 $ \hat H (t) $ 現在是與時間相依。 從上述與時間無關的產生器到此案例的延伸模組相當簡單。 `GeneratorSystem`我們會改為使用使用者定義型別，而不是針對所有時間 $t $ 描述 Hamiltonian 的修正 `GeneratorSystemTimeDependent` 。

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

第一個參數是連續的排程參數 $s \in [0，1] $，而此類型的函式會傳回 `GeneratorSystem` 該排程的。 請注意，[排程] 參數可能會與實體時間參數（例如 $s = t/T $）呈線性相關，$T $ 的總模擬時間。 不過，一般情況下，這不需要這麼做。

同樣地，此產生器的完整描述需要 `EvolutionSet` ，因此我們會定義 `EvolutionSchedule` 使用者定義型別。

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
