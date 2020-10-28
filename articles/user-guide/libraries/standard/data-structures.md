---
title: 標準程式庫中的資料結構 Q#
description: 深入瞭解 Microsoft 標準程式庫中的資料結構、oracle 和 dynamical 產生器 Q# 。
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3ce5d531618c269d15be3e4eb58ecbb597a022c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692233"
---
# <a name="data-structures-and-modeling"></a>資料結構與模型化 #

## <a name="classical-data-structures"></a>傳統資料結構 ##

除了用來表示量子概念的使用者定義型別之外，canon 還提供作業、函式和型別，以使用用於量子系統控制中的傳統資料。
例如，函 <xref:Microsoft.Quantum.Arrays.Reversed> 式會採用陣列做為輸入，並以反向順序傳回相同的陣列。
然後可以在型別的陣列上使用 `Qubit[]` ，以避免在整數的量子表示之間轉換時，必須套用不必要的 $ \operatorname{SWAP} $ 管制。
同樣地，在上一節中，我們在上一節中看到，表單的類型 `(Int, Int -> T)` 可以用來表示隨機存取集合，因此函式會 <xref:Microsoft.Quantum.Arrays.LookupFunction> 提供便利的方式來從陣列類型中建立這類類型。

### <a name="pairs"></a>對 ###

Canon 支援對成對的函式樣式表示法，並藉由解構來補充存取元組：

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>陣列 ###

Canon 提供數個函式來處理陣列。
這些函式是以類型參數化，因此可以與任何類型的陣列一起使用 Q# 。
例如，函式 <xref:Microsoft.Quantum.Arrays.Reversed> 會傳回新的陣列，其專案是從其輸入的反向順序。
這可以用來變更在呼叫作業時如何表示量子暫存器：

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

同樣地，函 <xref:Microsoft.Quantum.Arrays.Subarray> 式可以用來重新排列或取得陣列元素的子集：

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

結合 flow 控制項時，陣列操作函式（例如） <xref:Microsoft.Quantum.Arrays.Zipped> 可以提供強大的方式來表達量副程式：

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

## <a name="oracles"></a>神 諭 ##

在 [階段估計](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) 和 [振幅放大](https://en.wikipedia.org/wiki/Amplitude_amplification) 的文獻中，oracle 的概念經常出現。
Oracle 這一詞是指一組黑箱量子副程式，可在一組量子位上運作，並以階段傳回答案。
這個副程式通常可以被視為接受 oracle 的量子演算法的輸入，除了其他一些參數之外，還會套用一連串的量子作業，並將呼叫視為基本閘道。
很明顯地，若要實際實施較大型的演算法，必須提供 oracle 到基本閘道的具體分解，但這類分解不需要用來瞭解呼叫 oracle 的演算法。
在中 Q# ，這個抽象是使用該作業為第一級的值來表示，如此一來，就能以黑箱的方式將作業傳遞給量子演算法的執行。
此外，使用者定義型別是用來以型別安全的方式來標記不同的 oracle 標記法，因此很難不慎人們不同種類的黑色方塊作業。

這類 oracle 出現在許多不同的內容中，包括著名的範例，例如 [格羅弗的搜尋](https://en.wikipedia.org/wiki/Grover%27s_algorithm) 和量子模擬演算法。
在這裡，我們將焦點放在兩個應用程式所需的 oracle：振幅放大和階段估計。
我們將先討論振幅放大 oracle，再繼續進行階段估計。

### <a name="amplitude-amplification-oracles"></a>振幅放大 Oracle ###

振幅放大演算法的目標是藉由套用一系列狀態的反射來執行初始狀態與最終狀態之間的旋轉。
為了讓演算法運作，它需要這兩種狀態的規格。
這些規格是由兩個 oracle 所提供。
這些 oracle 的運作方式是將輸入分成兩個空格：「目標」子空間和「初始」子空間。
Oracle 會識別這類 subspaces，類似于 Pauli 運算子如何藉由將 $ \pm $1 階段套用至這些空間來識別兩個空格。
主要的差別在於，這些空間在此應用程式中不需要是半空白。
另請注意，這兩個 subspaces 通常不會互斥：兩個區域的成員都是。
如果不是 true，則幅度放大不會有任何作用，因此我們需要初始子空間與目標子空間有非零的重迭。

我們會將幅度放大所需的第一個 oracle 表示為 $P \_ $0，定義為具有下列動作。  針對 "初始" 子空間中的所有狀態 $ \ket{x} $ $P \_ 0 \ket{x} =-\ket{x} $，而針對所有不在此 \ket{y} 中的狀態 $ 子空間 $，我們有 $P \_ 0 \ket{y} = \ket{y} $。
將目標子空間標示 $P _1 $ 的 oracle 會採用完全相同的格式。
針對目標子空間中的所有狀態 $ \ket{x} $ (亦即，您希望演算法輸出) 的所有狀態，$P _1 \ ket {x} =-\ket{x} $。
同樣地，對於不在目標子空間中的所有州 $ \ket{y} $，$P _1 \ ket {y} = \ket{y} $。
這兩個反射接著會合並來形成一個運算子，該運算子會制定幅度放大的單一步驟，$Q =-P_0 P_1 $，其中整體的負號只需要在受控制的應用程式中考慮。
幅度放大之後，會採取初始狀態 $ \ket{\psi} $ （在初始子空間中），然後執行 $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $ 來繼續進行。
執行這類反復專案可保證如果一開始的初始狀態與已標記的空格重迭了 $ \sin ^ 2 ( \theta) $，則在 $m $ 反復專案之後，此重迭會變成 $ \sin ^ 2 ( [2m + 1] \theta) $。
因此，我們通常會想要選擇 $m $ 成為免費參數，例如 $ [2m + 1] \theta = \ pi/2 $;不過，這種固定選項對某些形式的波幅放大（例如固定點振幅放大）並不重要。
此程式可讓我們在標記的子空間中，使用 quadratically 較少的查詢來準備標示的函式，並使用狀態準備函式，而不是在嚴格傳統的裝置上。
這就是為什麼振幅放大對於許多量子運算應用程式來說是很重要的建立區塊。

為了瞭解如何使用演算法，提供可提供 oracle 結構的範例會很有説明。  請考慮在此設定中執行資料庫搜尋的格羅弗演算法。
在格羅弗的搜尋中，目標是將狀態 $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket {0} $ 轉換成其中一種 (可能) 許多標示的狀態。
為了進一步簡化，讓我們看看唯一標示的狀態是 $ \ket $ 的情況 {0} 。
接著，我們設計了兩個 oracle：一個只會以減號標示初始狀態 $ \ket{+} ^ {\otimes n} $，另一個則將標示的狀態 $ \ket {0} $ 標示為減號。
您可以使用 canon 中的控制流程作業，使用下列處理作業來實作為後者的閘道：

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

此 oracle 接著是一種特殊的作業案例，可讓您透過 <xref:Microsoft.Quantum.Canon.RAll1> 任意階段來旋轉，而不是反映案例 $ \phi = \pi $。
在此情況下， `RAll1` 類似于 <xref:Microsoft.Quantum.Intrinsic.R1> 序言作業，因為它會旋轉 $ \ket{11\cdots1} $，而不是單一量子位狀態 $ \ket {1} $。

標示初始子空間的 oracle 可以類似的方式來建立。
在虛擬虛擬中：

1. 將 $H $ 閘道套用至每個量子位。
2. 將 $X $ 閘道套用至每個量子位。
3. 將 $n $1 控制 $Z $-閘道套用至 $n ^ {\text{th}} $ 量子位。
4. 將 $X $ 閘道套用至每個量子位。
5. 將 $H $ 閘道套用至每個量子位。

這次，我們也會示範如何 <xref:Microsoft.Quantum.Canon.ApplyWith> 搭配 <xref:Microsoft.Quantum.Canon.RAll1> 上述操作來使用：

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

接著，我們可以將這兩個 oracle 結合在一起，以在兩個狀態之間旋轉，並使用多個與 $ Hadamard ^ n} $ 的 \Sqrt{2 閘道進行決定性的轉換 $ \ket{+} ^ {\otimes n} $ 到 $ \ket {0} $ (ie $m \propto \sqrt{2 ^ n} $) 相對於大約 $ 2 ^ n $ 層，在 {0} 觀察到結果 $0 $ 之前，您必須準備和測量初始狀態，才能以非決定性的方式準備 $ \ket $ 狀態。

### <a name="phase-estimation-oracles"></a>階段估計 Oracle ###

針對階段估計，oracle 會比較自然。
階段估計的目標是設計一個可從單一矩陣的特徵值取樣的副程式。
這種方法在量子模擬中是不可或缺的，因為化學和材質科學中有許多實體問題，這些特徵值提供了量子系統的接地氫化，可提供有關分子的材質和反應動態之階段圖表的重要資訊。
階段估計的每個類別都需要輸入單一。
這個單一的 oracle 通常是由兩種類型的其中一種來描述。

> [!TIP]
> 範例中涵蓋了以下所述的兩種 oracle 類型。
> 若要深入瞭解連續查詢 oracle，請參閱 [ **PhaseEstimation** 範例](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation)。
> 若要深入瞭解離散查詢 oracle，請參閱 [ **IsingPhaseEstimation** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。

Oracle 的第一種類型是，我們會呼叫不同的查詢 oracle，並以使用者定義型別表示 <xref:Microsoft.Quantum.Oracles.DiscreteOracle> ，只涉及單一矩陣。
如果 $U $ 是要預估其特徵值的單一元件，則 $U $ 的 oracle 只是實作為 $U $ 的副程式的一種。
例如，您可以將 $U $ 視為上方所定義的 oracle $Q $ 以進行振幅估計。
此矩陣的特徵值可用來估計初始和目標狀態（$ \sin ^ 2 ( \theta) $）之間的重迭，使用 quadratically 的樣本數比另一種需要的少。
這獲得使用格羅弗 oracle $Q $ 做為輸入振幅估計的標記來進行階段估計的應用。
在量子測量中廣泛使用的另一個常見的應用程式，則牽涉到估計一個小的旋轉角度。
換句話說，我們想要為表單 $R _z ( \theta) $ 的未知旋轉閘道預估 $ \theta $。
在這種情況下，我們會與您互動的副程式，以瞭解此閘道的 $ \theta $ 固定值為 $ $ \begin{align} U & = R_z ( \theta) \\ \\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \ theta/2} \end{bmatrix}。
\end{align} $ $

階段估計中使用的第二種 oracle 類型是連續查詢 oracle，以類型表示 <xref:Microsoft.Quantum.Oracles.ContinuousOracle> 。
針對階段估計的連續查詢 oracle 採用 $U (t) $ 的形式，其中 $t $ 是傳統方式的已知實數。
如果我們讓 $U $ 成為固定的單一查詢，則連續查詢 oracle 會採用 $U (t) = U ^ t $ 的表單。
這可讓我們查詢 $ \sqrt{U} $ 之類的矩陣，無法直接在離散查詢模型中執行。

這種類型的 oracle 在您沒有探查特定的單一的情況下很有用，而是想要學習單一的產生器的屬性。
例如，在 dynamical 量子模擬中，目標是要設計與 Hermitian 矩陣 $H $ 和演進時間 $t $ $U (t) = e ^ {-i H t} $ 緊密相近的量子電路。
$U (t) $ 的特徵值與 $H $ 的特徵值直接相關。
若要查看這一點，請考慮 $H $： $H \ket{E} = E\ket {E} $ 的 eigenvector，然後很容易就能看到矩陣指數的電源系列定義，$U (t) \ket{E} = e ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $。
因此，估計 $U (t) $ 的 eigenphase 會提供 eigenvalue $E $ 假設 eigenvector $ \ket{E} $ 是進入階段估計演算法。
不過，在此情況下，可以選擇使用者的值 $t $，因為 $t $ eigenvalue $E $ 的任何足夠小值，可以透過 $E =-\ phi/t $ 唯一反轉。
由於量子模擬方法提供了執行小數演進的能力，這會授與階段估計演算法在查詢單一時的額外自由，特別是當離散查詢模型只允許 $U ^ j $ 的表單 ^ j $ 以套用至整數 $j $ [連續查詢 oracle 可讓我們將 $U ^ t $ 的格式近似 ^ t $ 的任何實值 $t $。
這一點很重要，因為它可讓我們選擇精確的實驗，以提供有關 $E $; 的最新資訊。而以離散查詢為基礎的方法，則必須在演算法中選擇最適合的整數查詢數目來進行危害。

以具體的例子來說，請考慮評估不是閘道旋轉角度的問題，而是旋轉量子系統的 procession 頻率。
描述這類量子 dynamics 的單一 $U (t) = R_z (2 \ omega t) $ 表示演進時間 $t $ 和 unknown frequency $ \omega $。
在此內容中，我們可以使用單一 $R _z $ 閘道來模擬任何 $t $ 的 $U (t) $，因為這種情況不需要將自己限制為只對單一的查詢進行個別的查詢。
這類連續模型也有一個屬性，而該屬性的頻率大於 $ 2 \ pi $，可從使用連續查詢的階段估計程式中學習，因為對數函式的分支切割所產生的階段資訊，可能會顯示在 $t $ 的非接近值上執行的實驗結果。
因此，針對階段估計 oracle 的這類連續查詢模型，不只適用于這些問題，而且也優於離散查詢模型。
基於這個理由，這 Q# 兩種形式的查詢都有其功能，並讓使用者能夠根據其需求和可用的 oracle 類型來決定階段估計演算法。

## <a name="dynamical-generator-modeling"></a>Dynamical 產生器模型化 ##

時間演進的產生器描述狀態如何隨著時間而演進。 比方說，量子狀態 $ \ket{\psi} $ 的 dynamics 是由薛丁格方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = H \ket{\psi (t) }，\end{align} $ $ （Hermitian 矩陣 $H $，也稱為 Hamiltonian）作為動作產生器。 指定初始狀態 $ \ket{\psi (0) } $ at time $t = $0，在時間 $t $ 的正式解決方案，在主體中可能是寫入 $ $ \begin{align} \ket{\psi (t) } = U (t) \ket{\psi (0) }，\end{align} $ $，其中矩陣指數 $U (t) = e ^ {-i H t} $ 稱為單一時間演進運算子。 雖然我們將焦點放在下列的表單產生器，但我們強調此概念的廣泛套用，例如模擬開放式量子系統或更抽象的差異方程式。

Dynamical 模擬的主要目標是在量子電腦量子位中編碼的某些量子狀態上執行時間演進操作員。  在許多情況下，Hamiltonian 可能會細分成部分 $d $ 簡易詞彙的總和

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j，\end{align} $ $

在量子電腦上執行每個詞彙的時間演進是很容易的。 比方說，如果 $H _j $ 是在量子位暫存器第1個和第二個元素上執行的 Pauli $X _1X_2 $ 運算子 `qubits` ，則任何時間的時間演進 $t $ 可透過呼叫作業（具有簽章）來實作為 `Exp([PauliX,PauliX], t, qubits[1..2])` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。 如同 Hamiltonian 模擬稍後所述，其中一個解決方案是以更簡單的作業來 $H $ 進行大約的時間演進

$ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/r} e ^ {-iH \_ 1 t/r} \cdots e ^ {-iH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r) ，\end{align} $ $

其中 > $0 的整數 $r 會控制近似值誤差。

Dynamical 產生器模型化程式庫提供了一個架構，可根據更簡單的產生器，以有系統的方式編碼複雜的 如此一來，就可以將這類描述傳遞給模擬程式庫，以根據選擇的模擬演算法來執行時間演進，並自動處理許多詳細資料。

> [!TIP]
> 範例中涵蓋了下面所述的 dynamical 產生器程式庫。 如需以 Ising 模型為基礎的範例，請參閱 [ **IsingGenerators** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators)。
> 如需以分子 Hydrogen 為基礎的範例，請參閱 [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) 和 [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui) 範例。

### <a name="complete-description-of-a-generator"></a>產生器的完整描述 ###

在最上層，Hamiltonian 的完整描述包含在 `EvolutionGenerator` 具有兩個元件的使用者定義型別中：

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem`使用者定義型別是 Hamiltonian 的傳統描述。

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

元組的第一個元素 `Int` 會將 $d $ 的詞彙數目儲存在 Hamiltonian 中，而第二個專案 `(Int -> GeneratorIndex)` 則是將 $ 0 的整數索引 \{ （1,..., d-1 $）對應 \} 至 `GeneratorIndex` 使用者定義類型的函式，可唯一識別 Hamiltonian 中的每個基本詞彙。 請注意，藉由在 Hamiltonian 中將詞彙集合表示為函式，而不是陣列 `GeneratorIndex[]` ，這可以讓的即時計算， `GeneratorIndex` 這在描述具有大量詞彙的 hamiltonian 時特別有用。

十分，我們不會對所識別的基本詞彙強加慣例，因為這 `GeneratorIndex` 是容易模擬的。 比方說，基本詞彙可以是上述的 Pauli 運算子，但它們也可以是 Fermionic 的 annihilation 和建立運算子，這些運算子通常用於量子化學模擬。 它本身不會有 `GeneratorIndex` 意義，因為它不會描述其指向之詞彙的時間演進，可能會實作為量子電路。

解決方法是指定 `EvolutionSet` 使用者定義型別，將任何 `GeneratorIndex` 取自某個標準集合的設定，對應至單一運算子（ `EvolutionUnitary` 以量子電路表示）。 `EvolutionSet`會定義結構的慣例 `GeneratorIndex` ，也會定義一組可能的 `GeneratorIndex` 。

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Pauli 運算子產生器 ###

明確且有用的產生器範例是 Hamiltonian，這是 Pauli 運算子的總和，每個都可能有不同的係數。
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j，\end{align} $ $，其中每個 $ \hat H_j $ 現在都從 Pauli 群組中繪製。 針對這類系統，我們會提供類型的，以 `PauliEvolutionSet()` `EvolutionSet` 定義 Pauli 群組的元素和係數的識別方式 `GeneratorIndex` （具有下列簽章）。

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

在編碼中，第一個參數會 `Int[]` 指定 Pauli 字串，其中 $ \Hat I\rightarrow $0、$ \Hat X\rightarrow $1、$ \Hat Y\rightarrow $2 和 $ \Hat Z\rightarrow $3。 第二個參數會將 `Double[]` Pauli 字串的係數儲存在 Hamiltonian 中。 請注意，只會使用這個陣列的第一個元素。 第三個參數 `Int[]` 會索引此 Pauli 字串所作用的量子位，而且不能有重複的元素。 因此，Hamiltonian 詞彙 $0.4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ 可能會表示為

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`是一種函式，它會將 `GeneratorIndex` 此表單的任何一個對應至具有下列簽章的 `EvolutionUnitary` 。

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

第一個參數代表時間持續時間，會乘以 `GeneratorIndex` 單一演進的係數。 第二個參數是單一動作的量子位暫存器。 

### <a name="time-dependent-generators"></a>Time-Dependent 產生器 ###

在許多情況下，我們也想要模型化時間相依的產生器，可能發生在薛丁格方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = \hat H (t) \ket{\psi (t) }、\end{align} $ $，而產生器 $ \hat H (t) $ 現在是與時間相依。 從上述時間獨立的產生器到此情況的延伸模組很簡單。 `GeneratorSystem`我們會改為使用使用者定義型別，而不是針對所有時間 $t $ 來修正 Hamiltonian 的問題 `GeneratorSystemTimeDependent` 。

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

第一個參數是連續的排程參數 $s \in [0，1] $，而這種類型的函式會傳回 `GeneratorSystem` 該排程的。 請注意，schedule 參數可能會與實體時間參數（例如 $s = t/T $）呈線性關聯，以供模擬 $T $ 的時間總計。 但一般而言，這種情況並不需要。

同樣地，此產生器的完整描述需要 `EvolutionSet` ，因此我們會定義 `EvolutionSchedule` 使用者定義型別。

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
