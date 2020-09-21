---
title: 標準程式庫中的應用程式 Q#
description: 瞭解量子運算中的兩個基本應用程式-Hamiltonian 模擬和 Shor 的搜尋演算法。
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: a3380627aa196a749dd9487ad603aad29f34ae29
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759923"
---
# <a name="applications"></a>應用程式 #

## <a name="hamiltonian-simulation"></a>哈密頓模擬 ##

模擬量子系統是最令人興奮的量子計算應用程式之一。
在傳統電腦上，模擬量子機制的困難之處在于，通常會以其狀態向量表示的維度 $N $ 來進行調整。
當此表示以指數方式成長時，$n $ 量子位 $N = 2 ^ n $ 的特性，也就是 [已知的特性，也](xref:microsoft.quantum.concepts.multiple-qubits)就是在傳統硬體上進行量子模擬的棘手。

不過，在量子硬體上的情況可能會非常不同。 量子模擬最常見的變化，就是所謂與時間無關的 Hamiltonian 模擬問題。 其中會提供系統 Hamiltonian 的描述，$H $ （即 Hermitian 矩陣），以及一些在量子電腦上 $n $ 量子位編碼的初始量子狀態 $ \ket{\psi (0) } $。 當封閉式系統中的量子狀態演進時，薛丁格方程式 $ $ \begin{align} i\frac {d \ket{\psi (t) }} {d t} & = H \ket{\psi (t) } \end{align} $ $ 的目標是要在一段固定時間執行單一的時間演進運算子 $U (t) = e ^ {-iHt} $，其中 $ \ket{\psi (t) } = U (t) \ket{\psi (0) } $t $ 可解決薛丁格方程式。
類似，時間相依的 Hamiltonian 模擬問題可解決相同的方程式，但 $H (t) $ 現在是時間的函式。

Hamiltonian 模擬是許多其他量子模擬問題的主要元件，而 Hamiltonian 模擬問題的解決方案則是描述一系列基本量子閘道的演算法，可合成將逼近單一 $ \tilde{U} $，並 \\ 在 \tilde{U} 的標準中使用 error $ | \le-U (t) \\ | \epsilon 光譜 $。 [spectral norm](xref:microsoft.quantum.concepts.matrix-advanced) 這些演算法的複雜性非常強烈，因為量子電腦可以存取感興趣的 Hamiltonian 描述。 例如，在最糟的情況下，如果要將 $n $ 量子位上的 $H $ 做為 $ 2 ^ n \times 2 ^ n $ 數位的清單，每個矩陣專案都有一個清單，只要讀取資料已需要指數時間即可。 在最佳情況下，您可以假設存取 $O \ket{t}\ket{\psi (0) } = \ket{t}U (t) \ket{\psi (0) } $ 完整解決問題的黑箱單一。 這兩種輸入模型都不太有趣，前者是因為它不如傳統的方法好用，而後者則是以黑色方塊隱藏其實作為基本閘道的複雜度，這可能是量子位數目的指數。

### <a name="descriptions-of-hamiltonians"></a>Hamiltonian 的描述 ###

因此需要輸入格式的其他假設。 在可充分描述的輸入模型之間必須有足夠的平衡，以包含有趣的 Hamiltonian，例如實際的實體系統或有趣的計算問題，以及足以在量子電腦上有效率地而且實作的輸入模型。 在文獻中可以找到各種非一般的輸入模型，其範圍從量子到傳統。 

作為量子輸入模型的範例，以 [範例為基礎的 Hamiltonian 模擬](http://www.nature.com/articles/s41534-017-0013-7) 會假設以黑色方塊存取產生密度對照表 $ \rho $ 複本的量子作業，這會被視為 Hamiltonian $H $。 在 [單一存取模型](https://arxiv.org/abs/1202.5822) 中，Hamiltonian 會改為分解為 unitaries $ $ \begin{align} H & = \sum ^ {d-1} \_ {j = 0} a \_ j \hat{U} \_ j、\end{align} $ $ （其中 $a \_ j>$0 為係數）和 $ \hat{U} \_ j $ 為 unitaries。 然後，假設一個人可以用黑色方塊存取單一 oracle $V = \sum ^ {d-1} \_ {j = 0} \Ket{j}\bra{j}\otimes \hat{U} \_ j $，以選取所需的 $ \hat{U} \_ j $，和 oracle $A \ket {0} = \sum ^ {d-1} \_ {j = 0} \sqrt{a \_ j/\ sum ^ {d-1} \_ {k = 0} \Alpha \_ j} \ket{j} $，可建立這些係數的量子狀態編碼。 在 [稀疏 Hamiltonian 模擬](https://arxiv.org/abs/quant-ph/0301023)的情況下，會假設 Hamiltonian 是一種疏鬆陣列，而且每個資料列中都只有 $d = \mathcal{O} ( \Text{polylog} (N) # B3 $ 非零的元素。 此外，也假設有一個有效率的量子電路，可輸出這些非零元素的位置，以及它們的值。 [Hamiltonian 模擬演算法](xref:microsoft.quantum.more-information)的複雜度是以這些黑色方塊的查詢數目來評估，而基本閘道的複雜度則很大，因此非常適合用來執行這些黑色方塊的困難之處。

> [!NOTE]
> Big-O 標記法通常用來描述演算法的複雜度調整。 假設有兩個實際函式 $f、g $、運算式 $g (x) = \mathcal{O} (f (x) # B6 $ 表示有絕對的正常數 $x \_ 0，c>$0，因此 $g (x) \le c f (x) $ 表示所有 $x \ge x \_ $0。 

在量子電腦上執行的大部分實際應用程式中，這些黑色方塊必須有效率地而且實作，也就是 $ \mathcal{O} ( \text{polylog} (N) # B3 $ 基本量子閘道。 更強、有效率的 simulable Hamiltonian 必須有充分的稀疏傳統描述。 在這種情況下，假設 Hamiltonian 分解為 Hermitian parts $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j 的總和。
\end{align} $ $ 再者，假設每個部分（Hamiltonian $H \_ j $）很容易模擬。 這表示，任何時間 $t $ 的單一 $e ^ {-iH \_ j t} $，都可以使用 $ \mathcal{O} (1) $ 基本量子閘道進行精確的實作為。 比方說，在特殊情況下，這種情況是成立的，其中每個 $H \_ j $ 都是本機 Pauli 運算子，也就是說，它們屬於 $ \mathcal{O} (1) $ 非身分識別 Pauli 運算子的 tensor 產品，其會在空間關閉量子位時採取行動。 此模型特別適用于具有系結和本機互動的實體系統，因為詞彙數目 $d = \mathcal{O} ( \text{polylog} (N) # B3 $，而且可能會在多項式時間清楚地寫下（即傳統方式所述）。

> [!TIP]
> 您可以使用 Dynamical 產生器表示程式庫，來描述分解為部分的總和的 hamiltonian。 如需詳細資訊，請參閱 [資料結構](xref:microsoft.quantum.libraries.data-structures)中的 Dynamical 產生器標記法一節。

### <a name="simulation-algorithms"></a>模擬演算法 ###

量子模擬演算法會將 Hamiltonian 的指定描述轉換成一系列的基本量子閘道，這是指 Hamiltonian 所說的整體大約時間演進。

在 Hamiltonian 分解為 Hermitian 元件總和的特殊情況下，Trotter-Suzuki 分解是一個特別簡單且直覺的演算法，用來模擬 Hamiltonian，以分解成 Hermitian 元件的總和。 比方說，這個系列的第一個訂單整合者近似 $ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/r} e ^ {-iH \_ 1 t/r} \cdots e ^ {-iH \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r) ，使用 $r d $ 詞彙的產品 \end{align} $ $。 

> [!TIP]
> 範例中涵蓋了 Trotter Suzuki 模擬演算法的應用程式。
> 針對 Ising 模型，只使用每部目的電腦提供的內部作業，請參閱[ **SimpleIsing**範例](https://github.com/microsoft/Quantum/blob/main/samples/simulation/ising/simple)。
> 如需使用 Trotter Suzuki 程式庫控制結構的 Ising 模型，請參閱[ **IsingTrotter**範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/trotter-evolution)。
> 如需使用 Trotter Suzuki 程式庫控制結構的分子 Hydrogen，請參閱[ **H2 模擬**範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line)。

在許多情況下，我們想要執行模擬演算法，但對其執行的細節不感興趣。 例如，第二個訂單的整合者近似 $ $ \begin{align} U (t) & = \left ( e ^ {-iH \_ 0 t/2r} e ^ {-iH \_ 1 t/2r} \cdots e ^ {-iH \_ {d-1} t/2r} e ^ {-iH \_ {d-1} t/2r} \cdots e ^ {-iH \_ 1 t/2r} e ^ {-iH \_ 0 t/2r} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j \\ |H \_ j \\ | ^ 3 t ^ 3/r ^ 2) ，\end{align} $ $ （使用 $ 2rd $ 詞彙的產品）。 較大的訂單會牽涉到更多的詞彙，而優化的變異可能需要指數的高度非一般排序。 其他先進的演算法也可能牽涉到在中繼步驟中使用 ancilla 量子位。 因此，我們會將模擬演算法封裝在 canon 中做為使用者定義型別

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

第一個參數 `Double` 是模擬的時間，第二個參數是 `EvolutionGenerator` 在 [資料結構](xref:microsoft.quantum.libraries.data-structures)的「Dynamical 產生器表示」區段中，是與時間無關 Hamiltonian 封裝的傳統描述，其中包含有關 Hamiltonian 中每個詞彙如何由量子電路模擬的指示。 這種形式的類型近似于單一作業 $e ^ {-iHt} $ on 第三個參數 `Qubit[]` ，也就是儲存模擬系統之量子狀態的註冊。 同樣地，在時間相依的情況下，我們會以類型來定義使用者定義型別 `EvolutionSchedule` ，而這是時間相依 Hamiltonian 的傳統描述。

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

例如，您可以使用下列 canon 函式來呼叫 Trotter Suzuki 分解，並以參數 `trotterStepSize` 修改每個指數中的模擬持續時間，以及所 `trotterOrder` 需的整合程式順序。

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> 範例中涵蓋模擬程式庫的應用程式。 如需使用 Ising 模型中的階段估計 `SimulationAlgorithm` ，請參閱[ **IsingPhaseEstimation**範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。
> 如需使用 Ising 模型中的 adiabatic 狀態準備 `TimeDependentSimulationAlgorithm` ，請參閱[ **AdiabaticIsing**範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic)。


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic 狀態準備 & 階段估計 ###

Hamiltonian 模擬的一個常見應用是 adiabatic 狀態準備。 在這裡，有一個提供兩個 Hamiltonian $H \_ {\text{start}} $ 和 $H \_ {\text{end}} $，而量子 state $ \ket{\psi (0) } $ 是開始 Hamiltonian $H \_ {\text{start}} $ 的基礎狀態。 通常 \_ 會選擇 $H {\text{start}} $，讓 $ \ket{\psi (0) } $ 很容易從計算基礎狀態 $ \ket{0\cdots 0} $ 進行準備。 藉由在與時間相依的模擬問題之間進行插即插 Hamiltonian，可讓您在最終 Hamiltonian $H {\text{end}} $ 的基礎狀態下，得到很高的機率 \_ 。 雖然準備良好的 Hamiltonian 地面狀態，還是可以透過這種方式來進行，方法是在與時間相依的 Hamiltonian 模擬演算法上呼叫做為副程式，其他概念上不同的方法（例如 variational 量子 eigensolver）也是可行的。

但量子化學中的另一個應用程式，是估計 Hamiltonian 的地面狀態能源，代表化學反應的中繼步驟。 例如，這種配置可以依賴 adiabatic 狀態準備來建立地面狀態，然後將時間獨立的 Hamiltonian 模擬納入階段估計的特性，以將這項能源與部分有限的錯誤和成功機率進行解壓縮。 

將模擬演算法抽象化為使用者定義型別 `SimulationAlgorithm` ，並 `TimeDependentSimulationAlgorithm` 讓我們能夠方便地將其功能納入更複雜的量子演算法。 這應採用我們針對這些常用的副程式進行相同的動作。

因此，我們定義了方便的函式

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

這會傳回單一作業，以實行 adiabatic 狀態準備的所有步驟。 第一個參數會定義在這段時間，我們會在 `interpolatedTime` 第二個參數所描述的開始 Hamiltonian `evolutionGeneratorStart` 和第三個參數所描述的 end Hamiltonian 之間，以線性方式插補 `evolutionGeneratorEnd` 。 第四個參數 `timeDependentSimulationAlgorithm` 是可選擇模擬演算法的參數。 請注意，如果 `interpolatedTime` 夠長，則初始的接地狀態會在時間相依模擬的整個持續期間維持 Hamiltonian 的瞬間狀態，因而結束于結束 Hamiltonian 的接地狀態。

我們也會定義一個實用的作業，以自動執行一般量子化學實驗的所有步驟。 比方說，我們有下列各項，這會傳回 adiabatic 狀態準備所產生之狀態的能源預估：

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` 這是用來編碼初始量子狀態的量子位數目。 `statePrepUnitary` 從計算基礎 $ \ket{0\cdots 0} $ 準備開始狀態。 `adiabaticUnitary` 是實 adiabatic 狀態準備的單一作業，例如函數所產生的  `InterpolatedEvolution` 。 `qpeUnitary` 這是用來對產生的量子狀態執行階段估計的單一作業。 `phaseEstAlgorithm` 是我們選擇的階段估計演算法。

> [!TIP]
> 範例中涵蓋 adiabatic 狀態準備的應用程式。 針對使用手動執行 adiabatic 狀態準備和使用函式的 Ising 模型 `AdiabaticEvolution` ，請參閱[ **AdiabaticIsing**範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/adiabatic)。
> 如需 Ising 模型中的階段估計和 adiabatic 狀態準備，請參閱[ **IsingPhaseEstimation**範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation)。

> [!TIP]
> [分子 Hydrogen 的模擬](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line)是有趣且簡短的範例。 [O'Malley](https://arxiv.org/abs/1512.06860)中所報告的模型和實驗性結果。 只需要 Pauli 矩陣，並採用表單 $ \hat H = g \_ {0} I \_ 0I \_ 1 + g \_ 1 {z \_ 0} + g \_ 2 {Z \_ 1} + g \_ 3 {z \_ 0} {z 1} + g \_ \_ 4 {y 0} { \_ Y 1} \_ + g \_ 5 {x \_ 0} {X \_ 1} $。 這是有效的 Hamiltonian，只需要2個量子位，其中 $g $ 的常數會從兩個 Hydrogen 原子之間的距離 $R $ 計算。 使用 canon 函式，Paulis 會轉換成 unitaries，然後使用 Trotter-Suzuki 分解在短時間內演進。 在不使用 adiabatic 狀態準備的情況下，您可以建立 $H _2 $ 地面狀態的良好近似值，因此可以直接藉由利用 canon 的階段估計來找到地面狀態能源。

## <a name="shors-algorithm"></a>秀爾演算法 ##
Shor 的演算法仍是量子運算中最重要的一項發展，因為它展示了量子電腦可用來解決重要的問題，目前傳統方式棘手的問題。
Shor 的演算法提供快速的方式，讓您使用量子電腦來將大型數位納入考慮，這是一種稱為「 *分解*」的問題。
許多當日 cryptosystems 的安全性是根據假設沒有快速演算法可進行分解。
因此，Shor 的演算法對於我們在量子後世界中的安全性考慮有深遠的影響。

Shor 的演算法可視為混合式演算法。
量子電腦是用來執行稱為「期間尋找」的計算困難工作。
然後會傳統方式處理期間尋找的結果，以估計因素。
我們將在下面兩個步驟中複習。

### <a name="period-finding"></a>期間尋找 ###

瞭解量子傅立葉轉換和階段估計的運作方式 (查看 [量子演算法](xref:microsoft.quantum.libraries.standard.algorithms)) ，我們可以使用這些工具來解決傳統方式的硬運算問題，稱為「 *期間尋找*」。  在下一節中，我們將瞭解如何套用期間尋找以進行分解。

假設有兩個整數 $a $ 和 $N $，其中 $a<N $，則期間尋找的目標（也稱為訂單尋找）是尋找 _order_ $r $ of $a $ 模數 $N $，其中 $r $ 會定義為最小的正整數，例如 $a ^ r \equiv 1 \text{Mod} N $。  

若要使用量子電腦來尋找訂單，我們可以使用適用于下列單一運算子的階段估計演算法 $U _a $： $ $ U_a \ket{x} \equiv \ket{ (ax) \text{mod} N}。 $ $ 特徵向量 $U _a $ 適用于 integer $s $ 和 $ 0 \ leq s \leq r-$1，$ $ \ket{x_s} \equiv 1/\sqrt{r} \sum \_ {k = 0} ^ {r-1} e ^ {\frac{-2\pi i sk} {r}} \ket{a ^ k\text {mod} N}，$ $ 是 _eigenstates_ of $U _a $。
$U _a $ 的特徵值為 $ $ U \_ a \ket{x \_ s} = e ^ {2 \ pi i s/r} \ket{x \_ s}。 $$

因此，階段估計會輸出特徵值 $e ^ {2 \ pi i s/r} $，$r $ 可使用 $s/r $ 的 [接續分數](https://en.wikipedia.org/wiki/Continued_fraction) 有效率地學習。

量子期間尋找的電路圖為：

![量子期間尋找的電路圖](~/media/QPE.svg)

這裡 $ 2n $ 量子位會初始化為 $ \ket {0} $，$n $ 量子位會初始化為 $ \ket {1} $。
讀者可能會想知道為何將 eigenstates 的量子暫存器初始化為 $ \ket {1} $。
因為您事先不知道 order $r $，所以我們實際上無法直接準備 $ \ket{x_s} $ 狀態。
幸運的是，$ 1/\ sqrt {r} \sum \_ {s = 0} ^ {r-1} \ket{x \_ s} = \ket {1} $。
我們不需要實際準備 $ \ket{x} $！
我們可以準備在 state $ \ket $ 中 $n $ 量子位的量子暫存器 {1} 。 

線路包含 QFT 和數個控制的閘道。
[先前](xref:microsoft.quantum.libraries.standard.algorithms)已說明過 QFT 閘道。
如果控制項量子位為 $ \ket $，受控制的 $U _a $ 閘道會將 $ \ket{x} $ 對應到 $ \ket{ (ax) \text{mod} N} $ {1} ，否則會將 $ \ket{x} $ 對應到 $ \ket{x} $。

為了達到 $ (a ^ nx) \text{mod} N $，我們可以直接套用受控制的 $U _ {a ^ n} $，我們會在其中計算 $a ^ n \text{mod} N $ 傳統方式，以插入量子電路。  
[量子算術檔](./algorithms.md#arithmetic)中已描述達成這類別模組化算術的線路，尤其我們需要模組乘冪電路來實行受控制的 $U \_ {a ^ i} $ 作業。

雖然上述電路對應至 [量子階段估計](xref:microsoft.quantum.characterization.quantumphaseestimation) ，並明確地啟用訂單尋找，但我們可以減少所需的量子位數目。 我們可以依照 [arXiv： quant 的第8頁](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)所述的順序尋找 Beauregard 的方法，或使用位於 Microsoft 的其中一個階段估計常式。 例如， [健全的階段估計](xref:microsoft.quantum.characterization.robustphaseestimation) 也會使用一個額外的量子位。
 
### <a name="factoring"></a>保 理 ###
分解的目標是要判斷整數 $N $ 的兩個主要因素，其中 $N $ 是 $n $ 位數位。  
分解包含以下所述的步驟。 這些步驟分成三個部分：傳統前置處理常式 (1-4) ;用來找出 $a \text{mod} N $ (5) 的量子運算常式;和傳統的後處理常式，從 order (6-9) 衍生質數。

傳統前置處理常式是由下列步驟所組成：
1. 如果 $N $ 為偶數，則傳回主要因數 $2 $。
2. 如果 $p \geq1 $ $q \geq2 $ $N = p ^ q $，則會傳回 $p $ 的主要因數。  此步驟會傳統方式執行。
3. 選擇 $a $ 的亂數字，$1 以 < < N-$1。
4. 如果 $ \text{gcd} (a、N) # B0 $1，則傳回主要因數 $ \text{gcd} (a，N) $。 此步驟是使用 Euclid 的演算法來計算。
如果未傳回任何主要因素，我們會繼續進行量副程式：
5. 呼叫量子期間尋找演算法來計算 order $r $ of $a \text{mod} N $。 在傳統的後處理常式中使用 $r $ 來判斷主要因素：
6. 如果 $r $ 是奇數，請返回前置處理步驟 (3) 。
7. 如果 $r $ 是偶數，$a ^ {r/2} =-1 \ 文字 {mod} N $，請返回前置處理步驟 (3) 。
8. 如果 $ \text{gcd} (^ {r/2} + 1，N) $ 是 $N $ 的非一般因素，會傳回 $ \text{gcd} (^ {r/2} + 1，N) $。
9. 如果 $ \text{gcd} (^ {r/2}-1，N) $ 是 $N $ 的非一般因素，會傳回 $ \text{gcd} (^ {r/2}-1，N) $。


分解演算法是概率：它可以顯示，機率至少為一半，$r $ 將是偶數，$a ^ {r/2} \neq-1 \text{mod} N $，因此會產生主要因數。   (如需詳細資訊，請參閱[Shor 的原始](https://doi.org/10.1109/SFCS.1994.365700)檔，[如需詳細資訊](xref:microsoft.quantum.more-information)) ，請參閱中的其中一個*基本的量子*運算文字。
如果未傳回主要因素，則只需從步驟 (1) 重複演算法。  $N $ 嘗試之後，每次嘗試失敗的機率最多為 $ 2 ^ {-n} $。
因此，在重複此演算法之後，幾乎可以確保成功的次數很少。
