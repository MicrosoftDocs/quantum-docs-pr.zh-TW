---
title: 量子特性和統計資料
description: 瞭解如何使用階段估計的測量統計資料，來估計量副程式設計中的結果值。
author: bradben
uid: microsoft.quantum.libraries.characterization
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51e7b3bcf4402a4d0ba5647643f284e9f10c3bb3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692156"
---
# <a name="quantum-characterization-and-statistics"></a>量子特性和統計資料 #

您必須能夠描述作業的效果，才能開發有用的量子演算法。
這是一項挑戰，因為每次測量量子系統都會產生最多一項資訊。
若要瞭解 eigenvalue，請單獨使用量子狀態，許多度量的結果都必須一起拼接，讓使用者可以搜集所需的許多資訊來代表這些概念。
量子狀態尤其是繁瑣語法，因為 [沒有任何複製定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) 指出沒有任何方法可從單一狀態複本學習任意的量子狀態，因為這樣做可讓您建立狀態的複本。
這種從使用者開始的量子狀態模糊化會反映出來，而不會 Q# 公開或甚至定義狀態對量副程式 *is* 的影響。
因此，我們藉由將作業和狀態視為黑箱來處理量子特性;這種方法與量子特性、驗證和驗證 (QCVV) 的實驗實務很普遍。

特性與先前討論過的其他程式庫不同。
這裡的目的是要瞭解系統的傳統資訊，而不是在狀態向量上執行單一轉換。
因此，這些程式庫必須混合傳統和量子資訊的處理。


## <a name="iterative-phase-estimation"></a>反復階段估計 ##

以量子特性為依據來查看量副程式設計，建議使用量子階段估計的實用替代方法。
也就是說，您可以將階段估計視為 *傳統* 代理程式透過測量來學習量子系統屬性的程式，而不是準備 $n $ 量子位的暫存器來包含該階段的二進位標記法。
我們在量子案例中繼續進行，方法是使用階段 kickback，將黑色方塊作業的應用程式轉換成未知角度的旋轉，但會測量我們在旋轉之後的每個步驟中旋轉的 ancilla 量子位。
這樣做的優點是，我們只需要一個額外的量子位來執行量子案例中所述的階段 kickback，我們就會在每個步驟以反復的方式學習測量結果中的階段。  
以下建議的每個方法都會使用不同的策略來設計實驗，並使用不同的資料處理方法來學習該階段。  它們各有獨特的優點，包括嚴格的錯誤界限、將先前資訊納入的能力、容許錯誤或在記憶體上執行 limitted 傳統電腦。

在討論反復的階段估計時，我們會考慮將單一的 $U $ 指定為黑色方塊的操作。
如同 [資料結構](xref:microsoft.quantum.libraries.data-structures)中的 oracle 一節中所述， Q# canon 會依 <xref:Microsoft.Quantum.Oracles.DiscreteOracle> 使用者定義型別（由元組類型定義）來模型作業 `((Int, Qubit[]) => Unit : Adjoint, Controlled)` 。
具體而言，如果 `U : DiscreteOracle` ，則會 `U(m)` 為執行 $U ^ m $ `m : Int` 。

有了這項定義之後，反復階段估計的每個步驟都會藉由準備 $ \ket{+} $ 狀態的輔助量子位，以及我們 [假設)  ($U 的初始](xref:microsoft.quantum.concepts.matrix-advanced) 狀態 $ \ket{\phi} $ 來進行，亦即 $U (m) \ket{\phi} = e ^ {im\phi} \ ket {\ phi} $。  
接著會使用受控制的應用程式， `U(m)` 以準備狀態 $ \left (R \_ 1 (m \phi) \ket{+} \right) \ket{\phi} $。
如同在量子案例中，受控制的 oracle 應用程式效果與在 `U(m)` $ \ket{+} $ 的未知階段套用 $R _1 $ 的效果完全相同，因此我們可以更簡單的方式描述 $U $ 的效果。
然後，演算法會藉由套用 $R _1 (-m\theta) $ 以取得狀態 $ \ket{\psi} = \left (R \_ 1 (m [\phi-\theta] ) \ket{+} \right) \ket{\phi} $ $，來旋轉控制項量子位。
然後以 $X $ 基礎來測量作為控制項使用的輔助量子位 `U(m)` ，以取得單一傳統 `Result` 。

此時， `Result` 透過反復階段估計所取得的值來重建階段是一個傳統的統計推斷問題。
在指定固定的推斷方法的情況下，尋找最大化所獲得資訊的 $m $ 值只是統計資料中的問題。
我們強調這一點，方法是在貝氏參數估計形式的理論層級簡要描述反復的階段估計，然後再繼續描述 canon 中提供的統計演算法 Q# 來解決這個傳統推斷問題。

### <a name="iterative-phase-estimation-without-eigenstates"></a>未 Eigenstates 的反復階段估計 ###

如果提供的輸入狀態不是 eigenstate，也就是說，如果 $U (m) \ket{\phi \_ j} = e ^ {im\phi \_ j} $，則階段估計的進程會以非決定性的方式，將量子狀態引導至單一能源 eigenstate。  最終所要聚合的 eigenstate 是最可能產生觀察到的 eigenstate `Result` 。

具體來說，PE 的單一步驟會在狀態 \begin{align} \ sum_j \sqrt{\Pr ( \phi \_ j) } \ket{\phi \_ j} \mapsto \sum \_ j\frac {\ Sqrt {\ Pr ( \phi j \_) } \sqrt{\Pr ( \text{result} | \phi \_ j) } \Ket{\phi \_ j}} {\sqrt{\Pr ( \phi j) \_ \sum \_ j \Pr ( \text{result} | \phi \_ j) }}。
\end{align}，因為此進程會逐一查看多個值，所以沒有最大 `Result` 值 $ \ prod_k \pr ( \text{result} \_ k | \phi \_ j) $ 的 eigenstates 將會以指數方式隱藏。
如此一來，如果正確選擇實驗，推斷程式就會隨著單一 eigenvalue 而收斂。

貝氏機率分類 ' 定理進一步建議將階段估計所產生的狀態撰寫為 \begin{align} \frac{\sqrt{\Pr ( \phi \_ j) } \sqrt{\Pr ( \text{Result} | \phi \_ j) } \ket{\phi \_ j}} {\sqrt{\Pr ( \phi j \_) \Sum \_ j \Pr ( \text{Result} | \phi \_ j) }} = \ sum_j \sqrt{\Pr ( \phi \_ j | \text{Result} ) } \ket{\phi \_ j}。
\end{align} 這裡 $ \Pr ( \phi \_ j | \text{Result} ) $ 可做為每個假設之歸屬的機率：

1. 測量之前的量子狀態知識
2. $U $ 和的知識 eigenstates
3. $U $ 的特徵值知識。

學習這三件事通常會在傳統電腦上以指數方式呈現。
階段估計的公用程式會產生不太小的範圍，因為它可以執行這類的量子學習工作，而不需要知道任何一項。
此原因的階段估計會出現在提供指數加速的一些量子演算法內。

### <a name="bayesian-phase-estimation"></a>貝氏階段估計 ###

> [!TIP]
> 如需實務貝氏階段估計的詳細資訊，請參閱 [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation) 範例。

貝氏階段估計的概念很簡單。
您可以從階段估計通訊協定收集度量統計資料，然後使用貝氏推斷處理結果並提供參數的估計值。
這項處理可讓您估計 eigenvalue 以及該預估的不確定性。
它也可讓您執行自動調整的實驗，並利用先前的資訊。
方法的缺點是，它需要計算需求。

若要瞭解此貝氏推斷流程的運作方式，請考慮處理單一結果的情況 `Zero` 。
請注意，$X = \ket{+} \bra{+}-\ket {-} \bra {-} $，例如 $ \ket{+} $ 是 $X $ 的唯一正面 eigenstate 對應至 `Zero` 。
在 `Zero` 第一個量子位上觀察到輸入狀態 $ \ket{\psi}\ket{\phi} $ 的[ `PauliX` 測量](xref:microsoft.quantum.concepts.pauli)機率，因此 \begin{equation} \Pr ( \texttt{zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2。
\end{equation} 在反復階段估計的案例中，我們有了 $ \ket{\psi} = R_1 (m [\phi-\theta] ) \ket{+} $，使 \begin{align} \Pr ( \texttt{Zero} |phim，\theta) & = \left |\braket{+ |R_1 (m [\phi-\theta] ) |+} \right | ^ 2 \\ \\ & = \left | \frac12 \left ( \bra {0} + \bra {1} \right) \left ( \ket {0} + e ^ {i m [\phi-\theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{eq：階段-est-可能性}。
\end{align} 也就是，反復階段估計包含學習正弦曲線函式的震盪頻率，並能夠以該 sinusoid 所指定的偏差來翻轉硬幣。
在傳統的傳統術語中，我們稱之為 $ \eqref{eq：階段-est-可能性} $，這是反復階段估計的 *可能性函數* 。

觀察到 `Result` 反復階段估計的可能性函式之後，我們就可以使用貝氏機率分類的規則，以規定應該在該階段之後觀察到的階段。
具體而言、\begin{equation} \Pr ( \phi |d) = \frac{\Pr (d | \phi) \Pr ( \phi) } {\int \Pr (d | \phi) \Pr ( \phi) {\mathrm d} \phi} \Pr ( \phi) 、\end{equation}，其中 $d \in \\ {\texttt{Zero}，\texttt{One} \\ } $ 是 `Result` ，其中 $ \Pr ( \phi) $ 描述之前的信念與 $ \phi $。
如此一來，就可以明確地反復執行反復階段估計的本質，因為「事後 posterior 散發 $ \Pr ( \phi |d) $ 描述我們在下一個的觀察之前的信念 `Result` 。

在此程式中的任何時間點，我們可以將傳統控制器推斷的階段 $ \hat{\phi} $ 報告為 \begin{equation} \hat{\phi} \mathrel{： =} \expect [\phi | \text{data}] = \int \phi \Pr ( \phi |\text{data} ) {\mathrm d} \phi，\end{equation}，其中 $ \text{data} $ 代表所有取得值的完整記錄 `Result` 。

實際的貝氏推斷在實務棘手中。
為了瞭解這一點，我們想要學習 $n $-bit 變數 $x $。
先前的散發 $ \Pr (x) $ 支援 $x $ 的 $ 2 ^ n $ 假設值。
這表示，如果我們需要高度精確的估計值 $x $ then 貝氏階段估計可能需要過高的記憶體和處理時間。
針對某些應用程式（例如量子模擬），所需的 limitted 精確度不會妨礙其他應用程式（例如 Shor 的演算法）在其階段估計步驟內無法使用精確的貝氏推斷。  基於這個理由，我們也提供近似貝氏方法的執行，例如 [隨機的逐步解說階段估計 (RWPE) ](xref:Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation) ，也提供非貝氏的方法，例如 [穩固的階段估計](xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation)。

### <a name="robust-phase-estimation"></a>強大的階段估計 ###

在最糟的情況下，最大 *的 posteriori* 貝氏從測量結果中重建階段預估的重建會以指數方式呈現。 因此，大部分實際的階段估計演算法會犧牲部分重建的品質，在 exchange 中，有一種傳統的後置處理，而改為以所進行的度量數目來調整 polynomially。

使用有效率的傳統後續處理步驟的其中一個範例是 [強大的階段估計演算法](https://arxiv.org/abs/1502.02677)，其簽章和上面所述的輸入。 它假設輸入的單一黑色方塊 $U $ 會封裝為 `DiscreteOracle` 類型，因此只會查詢受控制-$U $ 的整數乘冪。 如果暫存器中的輸入狀態 `Qubit[]` 是 eigenstate $U \ket{\psi} = e ^ {i\phi} \ ket {\ psi} $，健全的階段估計演算法會將 $ \hat{\phi}\in $ 的估計 $ \pi [-\pi，\phi) $ 視為 `Double` 。

強大的階段估計最重要的功能（與其他大部分的有用變異共用）是 $ \hat{\phi} $ 的重建品質在海森堡有限的情況下是有意義的。 這表示，如果 $ \hat{\phi} $ from true 值的偏差為 $ \sigma $，則 $ \sigma $ 會以反比的比例，與 $U $ 的查詢總數 $Q $，亦即 $ \sigma = \mathcal{O} (1/Q) $。 現在，偏差的定義會因不同的估計演算法而有所不同。 在某些情況下，可能表示至少有 $ \mathcal{O} (1) $ 機率，估計錯誤 $ | \hat{\phi}-\phi | \_某些迴圈量值 $ \circ $ 上的 \circ\le \sigma $。 針對穩固的階段估計，偏差會精確地等於 $ \sigma ^ 2 = \mathbb{E} \_ \hat{\phi} [ ( \mod \_ {2 \ pi} ( \hat{\phi}-\phi + \pi) -\pi) ^ 2] $ 如果我們將定期階段解除包裝成單一有限間隔 $ (-\pi，\pi] $。 更精確地說，健全階段估計的標準差滿足到差異 $ $ \begin{align} 2.0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ pi/Q，\end{align} $ $，其中下限是在 asymptotically 大型 $Q $ 的限制內達到，而且即使是小型樣本大小也保證上限。  請注意，輸入所選取的 $n $ `bitsPrecision` ，會以隱含方式定義 $Q $。

其他相關的詳細資料（例如，只有 $1 $ ancilla 量子位的小空間額外負荷）或程式是不可調整的，這表示所需的量子實驗順序與中繼測量結果無關。 在這個範例中，您可以選擇階段估計演算法的重點，其中一個應該參考檔，例如和參考的發行集， @"microsoft.quantum.characterization.robustphaseestimation" 以取得詳細資訊和其執行。

> [!TIP]
> 在許多範例中，會使用強大的階段預估。 如需瞭解各種實體系統的接地狀態能源，請參閱 [ **H2 模擬** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line)、 [ **SimpleIsing** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)和 [ **Hubbard 模型** 範例](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard)。


### <a name="continuous-oracles"></a>連續 Oracle ###

我們也可以從上述使用的 oracle 模型一般化，以允許依 canon 類型模型化的持續時間 oracle <xref:Microsoft.Quantum.Oracles.ContinuousOracle> 。
請考慮使用 $U $ 的單一單一運算子，而不是單一的單一運算子系列 $U (t) $ for $t \in \mathbb{R} $，如此 $U (t) U (s) $ = $U (t + s) $。
這是較弱的語句，因為我們可以藉 <xref:Microsoft.Quantum.Oracles.DiscreteOracle> 由限制 \, 某些固定 $ \delta t $ 的 $t = m \delta t $ 來建立。
藉由 [石頭的定理](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups)，$U (t) = \exp (i H t) $ for a operator $H $，其中 $ \exp $ 是矩陣指數，如 [advanced 矩陣](xref:microsoft.quantum.concepts.matrix-advanced)中所述。
Eigenstate $ \ket{\phi} $ of $H $，如此一來，$H \ket{\phi} = \phi \ket{\phi} $ 接著也是 eigenstate of $U (t) $ for all $t $，\begin{equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}。
\end{equation}

您可以套用針對 [貝氏階段估計](#bayesian-phase-estimation) 所討論的完全相同分析，而且這個更一般 oracle 模型的可能性函式是完全相同的： $ $ \Pr ( \texttt{zero} |phit，\theta) = \cos ^ 2 \ left ( \frac{t [\phi-\theta]} {2} \right) 。
$ $ 再者，如果 $U $ 是模擬 dynamical 產生器，就像 [Hamiltonian 模擬](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)的情況一樣，我們會將 $ \phi $ 解釋為能源。
因此，搭配連續查詢使用階段估計可讓我們瞭解分子、[材質](https://arxiv.org/abs/1510.03859)或[現場理論](https://arxiv.org/abs/1111.3633v2)的模擬[能源](https://arxiv.org/abs/quant-ph/0604193)範圍，而不需要犧牲 $t $ 為整數，而不會危及我們選擇的實驗。

### <a name="random-walk-phase-estimation"></a>隨機的逐步解說階段估計 ###

Q# 提供適用于貝氏階段估計的實用近似值，其設計目的是要透過針對從反復階段估計取得的資料記錄，進行隨機的逐步解說，以接近運作的量子裝置。
這個方法是可調整且完全具決定性的，可讓您在估計階段 $ \hat{\phi} $ 中，以極低的記憶體額外負荷來調整最接近最佳的錯誤。

此通訊協定會使用大約的貝氏推斷方法，假設先前的散發是高斯。
這個高斯假設可讓我們針對實驗流量分析公式，將「事後 posterior 變異數降至最低。
然後，演算法會根據該實驗的結果，將 $ \phi $ 左方或右方的估計值向左或向右移動，並依預先決定的金額來縮減變異數。
這表示和變異數會提供在下一個實驗的 $ \phi $ 之前指定高斯所需的所有資訊。
未預期的測量失敗或真正的結果是在先前的初始連接結尾上，可能會導致此方法失敗。
它會藉由執行實驗來測試目前的平均值和標準差是否適用于系統，從失敗中復原。
如果不是，則演算法會執行逐步解說的反向步驟，並繼續進行處理。
回溯的功能也可讓演算法學習，即使最初的標準差 inapropriately 小也是如此。

## <a name="calling-phase-estimation-algorithms"></a>呼叫階段估計演算法 ##

Canon 所提供的每個階段估計作業都會 Q# 採用一組不同的輸入，將我們所要求的品質參數化為最終估計 $ \hat{\phi} $。
不過，這些不同的輸入全都共用數個輸入，因此在品質參數上的部分應用程式會產生一般簽章。
例如，下一 <xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation> 節中所討論的作業具有下列簽章：

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision`輸入是唯一的 `RobustPhaseEstimation` ，但 `oracle` `eigenstate` 在一般情況下是唯一的。
因此，如 **H2Sample** 中所示，作業可以接受具有表單輸入的反復階段估計演算法， `(DiscreteOracle, Qubit[]) => Unit` 以允許使用者指定任意階段估計演算法：

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

這些無數階段估計演算法已針對不同的屬性和輸入參數優化，您必須瞭解這些演算法，才能針對目標應用程式做出最佳選擇。 比方說，某些階段估計演算法是可調整的，也就是說，未來步驟的測量結果傳統方式會控制未來的步驟。 有些人需要能夠透過任意的實際電源來 exponentiate 其黑箱的單一 oracle，而其他則只需要整數的電源，但只能解析階段預估模數 $ 2 \ pi $。 有些需要許多輔助量子位，有些則只需要一個。

同樣地，使用隨機的逐步解說階段估計，與 canon 提供的其他演算法進行的方式大致相同：

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
