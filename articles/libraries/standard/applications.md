---
title: 'Q # 標準程式庫中的應用程式'
description: 瞭解量子運算中的兩個基本應用程式-Hamiltonian 模擬和快速鍵的搜尋演算法。
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b7c46b634c6d691c067c0dd995301395408c85ca
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907217"
---
# <a name="applications"></a>應用程式 #

## <a name="hamiltonian-simulation"></a>哈密頓模擬 ##

模擬量子系統是最令人興奮的量子計算應用程式之一。
在傳統電腦上，模擬配量機制的困難在於，通常會以其狀態向量表示的維度 $N $ 來調整。
由於這種表示方式會與 $n $ qubits $N = 2 ^ n $ 的數目呈指數成長，因此所謂的特性（也稱為[維度詛咒](xref:microsoft.quantum.concepts.multiple-qubits)）是棘手，而傳統硬體上的量子模擬。

不過，這種情況在量子硬體上可能會有非常不同的情況。 最常見的量子模擬變體稱為與時間無關的 Hamiltonian 模擬問題。 其中會提供系統 Hamiltonian $H $ 的描述，也就是 Hermitian 的矩陣，而某些初始的量子狀態 $ \ket{\psi （0）} $ 是以某種基礎，在量子電腦上 $n $ qubits 進行編碼。 當封閉式系統中的配量狀態在 Schrödinger 方程式 $ $ \begin{align} i\frac {d \ket{\psi （t）}} {d t} & = H \ket{\psi （t）} 下演進時，\end{align} $ $ 的目標是要在某些固定時間執行單一時間進化運算子 $U （t） = e ^ {-iHt} $，$t $，其中 $ \ket{\psi （t）} = U （t） \ket{\psi （0）} $ 會解決 Schrödinger 方程式。
類似，時間相依的 Hamiltonian 模擬問題可解決相同的方程式，但 $H （t） $ 現在是一項功能。

Hamiltonian 模擬是許多其他量子模擬問題的主要元件，而 Hamiltonian 模擬問題的解決方案則是描述一系列基本量子閘道的演算法，以合成將逼近的單一 $ \tilde{U} $，錯誤 $\\| \tilde{U}-U （t）\\|[spectral 標準](xref:microsoft.quantum.concepts.matrix-advanced)中的 \le \epsilon $。 這些演算法的複雜性非常強烈，因為量子電腦可存取相關 Hamiltonian 的描述。 例如，在最糟的情況下，如果要以 $ 2 ^ n \times 2 ^ n $ qubits 的清單來提供 $n $ 的 $H $ 作用，每個矩陣元素都有一個，只要讀取資料，就會需要指數時間。 在最佳的情況下，可以假設有一個 $O \ket{t}\ket{\psi （0）} = \ket{t}U （t） \ket{\psi （0）} $ 完整的黑色方塊，可解決此問題。 這兩種輸入模型都不會特別有趣--前者並不是傳統方法，而後者則是以黑色方塊隱藏其執行的基本閘道複雜度，這可能是 qubits 數目的指數。

### <a name="descriptions-of-hamiltonians"></a>Hamiltonians 的描述 ###

因此需要輸入格式的其他假設。 有足夠描述性的輸入模型與包含有趣的 Hamiltonians （例如實際實體系統或有趣的運算問題，以及嚴格限制的輸入模型）之間必須有精確的平衡以有效率地能實作在量子電腦上。 在此文獻中可找到各種非一般的輸入模型，其範圍從量子到傳統。 

做為配量輸入模型的範例，以[範例為基礎的 Hamiltonian 模擬](http://www.nature.com/articles/s41534-017-0013-7)會假設產生密度矩陣 $ \rho $ 之複製的量子作業的黑箱存取，而這會被視為 Hamiltonian $H $。 在[單一存取模型](https://arxiv.org/abs/1202.5822)中，一個 supposes Hamiltonian 改為會 decompose 為 unitaries $ $ \Begin{align} & H 的總和\_{j = 0} a\_j \sum\_j，\hat{U} $ $，其中 $a\_j > 0 $ 為係數，而 $ \end{align}\_j $ 是 \hat{U}。 然後假設有一個人可以用黑色方塊來存取單一 oracle $V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $ 來選取所需的 $ \hat{U}\_j $，和 oracle $A \ket{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ sum ^ {d-1}\_{k = 0} \Alpha\_j} \ket{j} $ 來建立量子狀態編碼這些係數。 在[Sparse Hamiltonian 模擬](https://arxiv.org/abs/quant-ph/0301023)的案例中，一個假設 Hamiltonian 是一個疏鬆陣列，其中每個資料列只包含 $d = \mathcal{O} （\Text{polylog} （N）） $ 非零的元素。 此外，其中一個會假設有有效率的配量電路，輸出這些非零元素的位置，以及它們的值。 [Hamiltonian 模擬演算法](xref:microsoft.quantum.more-information)的複雜性是根據這些黑箱的查詢數來進行評估，而基本閘道的複雜性則會非常依賴執行這些黑色方塊的困難程度。

> [!NOTE]
> Big O 標記法通常用來描述演算法的複雜性調整。 假設有兩個真正的函式 $f，g $，expression $g （x） = \mathcal{O} （f （x）） $ 表示存在絕對的正常數 $x\_0，c > 0 $，讓 $g （x） \le c f （x） $ 適用于所有 $x \ge x\_$0。 

在最實際的應用程式中，若要在量子電腦上執行，這些黑箱必須有效率地能實作，也就是 $ \mathcal{O} （\text{polylog} （N）） $ 基本型量子閘道。 更強、有效率的 simulable Hamiltonians 必須有足夠的稀疏傳統描述。 在其中一個這類的形式中，假設 Hamiltonian 會 decompose 為 Hermitian part $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j 的總和。
\end{align} $ $ 也會假設每個元件（Hamiltonian $H\_j $）很容易模擬。 這表示任何時間 $t $ 的單一 $e ^ {-iH\_j t} $ 可以完全使用 $ \mathcal{O} （1） $ 基本型量子閘道來執行。 比方說，在特殊情況下，每個 $H\_j $ 都是本機 Pauli 運算子，這表示它們是張量產品的 $ \mathcal{O} （1） $ 非身分識別 Pauli 運算子，其作用於空間關閉的 qubits。 此模型特別適用于具有系結和本機互動的實體系統，因為詞彙數目是 $d = \mathcal{O} （\text{polylog} （N）） $，而且可能會清楚地寫下，亦即傳統方式所述的多項式時間。

> [!TIP]
> 分解成元件總和的 Hamiltonians 可能會使用 Dynamical 產生器表示程式庫來描述。 如需詳細資訊，請參閱[資料結構](xref:microsoft.quantum.libraries.data-structures)中的 Dynamical 產生器表示一節。

### <a name="simulation-algorithms"></a>模擬演算法 ###

量子模擬演算法會將指定的 Hamiltonian 描述轉換成一系列基本的配量閘道，這是一個整體的 Hamiltonian，大約是時間進化。

在 Hamiltonian 會 decompose 為 Hermitian 部分總和的特殊情況下，Trotter-Plat'home co. 分解是特別簡單且直覺化的演算法，可模擬 Hamiltonians，以分解成 Hermitian 元件的總和。 例如，此系列的第一位整合者約 $ $ \begin{align} U （t） & = \left （e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right） ^ {r} + \mathcal{O} （d ^ 2 \ max_j\\|H\_j\\| ^ 2 t/r），使用 $r d $ 詞彙的乘積 \end{align} $ $。 

> [!TIP]
> 範例中涵蓋 Trotter Plat'home co. 模擬演算法的應用程式。
> 針對僅使用每部目的電腦所提供之內建作業的 Ising 模型，請參閱[ **SimpleIsing**範例](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple)。
> 如需使用 Trotter-Plat'home co. 程式庫控制項結構的 Ising 模型，請參閱[ **IsingTrotter**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution)。
> 如需使用 Trotter Plat'home co. 程式庫控制結構的分子 Hydrogen，請參閱[ **H2 模擬**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)。

在許多情況下，我們想要執行模擬演算法，但對其執行的細節並不感興趣。 例如，第二個訂單的整合者近似 $ $ \begin{align} U （t） & = \left （e ^ {-iH\_0 t/2r} e ^ {-iH\_1 t/2r} \cdots e ^ {-iH\_{d-1} t/2r} e ^ {-iH\_{d-1} t/2r} \cdots e ^ {-iH\_1 t/2r} e ^ {-iH\_0 t/2r} \right） ^ {r} + \mathcal{O} （d ^ 3 \ max_j\\|H\_j\\| ^ 3 t ^ 3/r ^ 2），使用 $ 2rd $ 詞彙的產品 \end{align} $ $。 較大的訂單也牽涉到更多詞彙，而優化變體可能需要指數上的高度非一般排序。 其他先進的演算法也可能牽涉到在中繼步驟中使用 ancilla qubits。 因此，我們會在 canon 中將模擬演算法封裝為使用者定義型別

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

第一個參數 `Double` 是模擬的時間，而第二個參數 `EvolutionGenerator`（在[資料結構](xref:microsoft.quantum.libraries.data-structures)的 Dynamical 產生器表示區段中涵蓋）是與時間無關 Hamiltonian 的傳統描述，其中包含有關 Hamiltonian 中每個詞彙如何由量子線路模擬的指示。 此形式的類型大約是第三個參數 `Qubit[]`上的單一作業 $e ^ {-iHt} $，這是儲存模擬系統之量子狀態的暫存器。 類似于時間相依的情況，我們會改為定義具有 `EvolutionSchedule` 類型的使用者定義型別，這是時間相依 Hamiltonian 的傳統描述。

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

例如，您可以使用下列 canon 函式來呼叫 Trotter-Plat'home co. 分解，其中參數 `trotterStepSize` 修改每個指數中模擬的持續時間，並 `trotterOrder` 所需的整合器順序。

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
> 範例中涵蓋模擬程式庫的應用程式。 如需使用 `SimulationAlgorithm`Ising 模型中的階段估計，請參閱[ **IsingPhaseEstimation**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)。
> 如需使用 `TimeDependentSimulationAlgorithm`Ising 模型中的 adiabatic 狀態準備，請參閱[ **AdiabaticIsing**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic)。


### <a name="adiabatic-state-preparation--phase-estimation"></a>Adiabatic 狀態準備 & 階段估計 ###

Hamiltonian 模擬的一個常見應用就是 adiabatic 狀態準備。 這裡提供兩個 Hamiltonians $H\_{\text{start}} $ 和 $H\_{\text{end}} $）和量子 state $ \ket{\psi （0）} $，這是開始 Hamiltonian $H\_{\text{start}} $ 的基礎狀態。 通常會選擇 $H\_{\text{start}} $，讓 $ \ket{\psi （0）} $ 很容易從計算基礎狀態 $ \ket{0\cdots 0} $ 準備。 藉由在具有時間相依模擬問題的 Hamiltonians 之間插上足夠的速度，最後可能會有很高的機率，也就是\_{\text{end}} $ 的最終 Hamiltonian $H 的基礎狀態。 雖然準備好的 Hamiltonian 基礎狀態，可以藉由呼叫以時間為基礎的 Hamiltonian 模擬演算法做為副程式來繼續進行，而其他概念不同的方法，例如 variational 量子eigensolver 是可行的。

但是在量子化學中的另一個應用程式，是估計 Hamiltonians 的基礎狀態能源，代表化學反應的中繼步驟。 例如，這種配置可能會依賴 adiabatic 狀態準備來建立地面狀態，然後將與時間無關的 Hamiltonian 模擬納入階段估計特性中，以使用一些有限的錯誤來將此能源解壓縮，並成功的機率。 

將模擬演算法抽象化為使用者定義的型別 `SimulationAlgorithm` 和 `TimeDependentSimulationAlgorithm` 可讓我們輕鬆地將其功能納入更複雜的量子演算法。 這應採用我們對這些常用的副程式執行相同的動作。

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

這會傳回單一作業，此作業會執行 adiabatic 狀態準備的所有步驟。 第一個參數 `interpolatedTime` 定義在第二個 `evolutionGeneratorStart` 參數所描述的開始 Hamiltonian 和第三個參數 `evolutionGeneratorEnd`所描述的結束 Hamiltonian 之間，線性插補的時間。 第四個參數 `timeDependentSimulationAlgorithm` 是其中一個可選擇模擬演算法的位置。 請注意，如果 `interpolatedTime` 夠長，初始的狀態會在時間相依模擬的整個持續時間內維持 Hamiltonian 的瞬間接地狀態，因此會在結束 Hamiltonian 的基礎狀態結束。

我們也定義了一個有用的作業，可自動執行典型「量子化學」實驗的所有步驟。 比方說，我們有下列各項，它會傳回 adiabatic 狀態準備所產生之狀態的能源預估：

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

`nQubits` 是用來編碼初始量子狀態的 qubits 數目。 `statePrepUnitary` 從計算基礎 $ \ket{0\cdots 0} $ 準備開始狀態。 `adiabaticUnitary` 是執行 adiabatic 狀態準備的單一作業，例如由 `InterpolatedEvolution` 函數所產生。 `qpeUnitary` 是用來對產生的量子狀態執行階段估計的單一作業。 `phaseEstAlgorithm` 是我們選擇的階段估計演算法。

> [!TIP]
> 範例中會涵蓋 adiabatic 狀態準備的應用程式。 針對使用手動執行 adiabatic 狀態準備與使用 `AdiabaticEvolution` 函數的 Ising 模型，請參閱[ **AdiabaticIsing**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic)。
> 如需 Ising 模型中的階段估計和 adiabatic 狀態準備，請參閱[ **IsingPhaseEstimation**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)。

> [!TIP]
> [模擬分子 Hydrogen](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)是一個有趣又簡單的範例。 [O'Malley et. al](https://arxiv.org/abs/1512.06860)中回報的模型和實驗性結果。 只需要 Pauli 矩陣，並採用 $ \hat H = g\_格式 {0}I\_0 I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $。 這是有效的 Hamiltonian，只需要2個 qubits，其中 $g $ 的常數是從兩個 Hydrogen 原子之間的距離 $R $ 計算而來。 使用 canon 函數，Paulis 會轉換成 unitaries，然後使用 Trotter-Plat'home co. 分解，在短時間內演變。 在不使用 adiabatic 狀態準備的情況下，您可以建立 $H _2 $ 地面狀態的良好近似值，因此可以利用來自 canon 的階段估計，直接找到基礎狀態的能源。

## <a name="shors-algorithm"></a>秀爾演算法 ##
快速鍵的演算法仍然是配量計算的其中一個最重要的發展，因為它顯示配量電腦可用來解決重要、目前傳統方式的棘手問題。
快速鍵的演算法提供了一種快速的方法，讓您使用量子電腦來將大量數位納入考慮，此問題稱為「*分解*」。
許多當日 cryptosystems 的安全性是根據假設沒有任何快速演算法可進行分解。
因此，快速鍵的演算法對於我們在後量子世界中的安全性考慮有深遠的影響。

快速鍵的演算法可以視為混合式演算法。
量子電腦是用來執行所謂的運算硬性工作，稱為「期間尋找」。
然後會傳統方式處理期間尋找的結果來估計因素。
我們會在下列兩個步驟中進行檢查。

### <a name="period-finding"></a>期間尋找 ###

瞭解配量傅立葉轉換和階段估計的工作（請參閱[量子演算法](xref:microsoft.quantum.libraries.standard.algorithms)），我們可以使用這些工具來解決傳統方式的硬運算問題，稱為*期間尋找*。  在下一節中，我們將瞭解如何套用期間尋找以進行分解。

假設有兩個整數 $a $ 和 $N $，其中 $a < N $，期間尋找的目標（也稱為「訂單尋找」）是尋找 $r $ 模數 $a $ 的_順序_$N $，其中 $r $ 已定義為最小正整數，例如 $a ^ r \equiv 1 \text{Mod} N $。  

若要使用量子電腦來尋找訂單，我們可以使用套用至下列單一運算子的階段估計演算法 $U _a $： $ $ U_a \ket{x} \equiv \ket{（ax） \text{mod} N}。 $ $ 特徵向量 of $U _a $ 適用于 integer $s $ 和 $ 0 \ leq s \leq r-$1，$ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i sk} {r}} \ket{a ^ k\text {mod} N}，$ $ 是 $U _a $ _eigenstates_ 。
$U _a $ 的特徵值是 $ $ U\_\ket{x\_s} = e ^ {2 \ pi i s/r} \ket{x\_s}。 $$

第一階段估計會輸出特徵值 $e ^ {2 \ pi i s/r} $，其中 $r $ 可以使用 $s/r $ 的[接續分數](https://en.wikipedia.org/wiki/Continued_fraction)有效率地學習。

配量期間的線路圖表如下：

![尋找配量期間的線路圖](./../../media/QPE.svg)

這裡 $ 2n $ qubits 會初始化為 $ \ket{0}$，$n $ qubits 會初始化為 $ \ket{1}$。
讀者可能會想知道，eigenstates 的量子暫存器為何會初始化為 $ \ket{1}$。
因為一個人事先不知道訂單 $r $，所以我們無法直接準備 $ \ket{x_s} $ 狀態。
幸運的是，$ 1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$。
我們不需要實際準備 $ \ket{x} $！
我們可以只在 state $ \ket{1}$ 中準備 $n $ qubits 的量子暫存器。 

線路包含 QFT 和數個受控制的閘道。
[先前](xref:microsoft.quantum.libraries.standard.algorithms)已說明過 QFT 閘道。
如果控制項 qubit 是 $ \ket{1}$，受控制的 $U _a $ 閘道會將 $ \ket{x} $ 對應至 $ \ket{（ax） \text{mod} N} $，否則會將 $ \ket{x} $ 對應至 $ \ket{x} $。

若要達到 $ （a ^ nx） \text{mod} N $，我們可以直接套用受控制的 $U _ {a ^ n} $，其中我們會計算 $a ^ N \text{mod} N $ 傳統方式以插入量子線路。  
如需達成這類別模組化算術的線路，請參閱[量子算術檔](./algorithms.md#arithmetic)，特別是我們需要模組化乘冪來執行受控制的 $U\_{a ^ i} $ 作業。

雖然上述線路對應至配量[階段估計](xref:microsoft.quantum.characterization.quantumphaseestimation)，並明確啟用訂單尋找，但我們可以減少所需的 qubits 數目。 我們可以依照[arXiv： quant-ph/0205095v3 的第8頁](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)中所述的順序尋找 Beauregard 的方法，或使用 Microsoft 所提供的其中一個階段估計常式。 例如，[健全的階段估計](xref:microsoft.quantum.characterization.robustphaseestimation)也會使用一個額外的 qubit。
 
### <a name="factoring"></a>出來 ###
「分解」的目標是要判斷兩個整數 $N $ 的主要因素，其中 $N $ 是 $n $ 位數位。  
「分解」包含如下所述的步驟。 這些步驟分成三個部分：傳統前置處理常式（1-4）;用來尋找 $a \text{mod} N $ （5）順序的量子計算常式;和傳統的後處理常式，以衍生訂單的主要因數（6-9）。

傳統前置處理常式包含下列步驟：
1. 如果 $N $ 為偶數，則傳回質數因數 $2 $。
2. 如果 $N = p ^ q $ for $p \geq1 $，$q \geq2 $，則傳回 $p $ 的主要因數。  此步驟執行傳統方式。
3. 選擇 $a $ 的亂數字，讓 $1 < < N-$1。
4. 如果 $ \text{gcd} （a，N） > 1 $，則傳回主要因數 $ \text{gcd} （a，N） $。 此步驟是使用 Euclid 的演算法來計算。
如果未傳回任何主要因素，我們會繼續進行量副程式：
5. 呼叫配量期間尋找演算法，以計算 $a \text{mod} N $ 的 order $r $。 在傳統的後處理常式中使用 $r $ 來判斷主要因素：
6. 如果 $r $ 是奇數，請回到前置處理步驟（3）。
7. 如果 $r $ 是偶數，$a ^ {r/2} =-1 \ 文字 {mod} N $，請回到前置處理步驟（3）。
8. 如果 $ \text{gcd} （^ {r/2} + 1，N） $ 是 $N $ 的非一般因素，則會傳回 $ \text{gcd} （a ^ {r/2} + 1，N） $。
9. 如果 $ \text{gcd} （^ {r/2}-1，N） $ 是 $N $ 的非一般因素，則會傳回 $ \text{gcd} （a ^ {r/2}-1，N） $。


「分解演算法」（概率）：可顯示的機率至少為一一半，$r $ 會是偶數，$a ^ {r/2} \neq-1 \text{mod} N $，因而產生一個主要因素。  （如需詳細[資訊](xref:microsoft.quantum.more-information)，請參閱[快速鍵的原始](https://doi.org/10.1109/SFCS.1994.365700)檔，或中的其中一個*基本量子計算*文字）。
如果未傳回主要因素，我們只需重複步驟（1）中的演算法。  $N $ 嘗試之後，每次嘗試失敗的機率最多為 $ 2 ^ {-n} $。
因此，在重複演算法之後，幾乎都能確保成功的次數。
