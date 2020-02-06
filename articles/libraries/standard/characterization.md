---
title: '問 # 標準程式庫-特性 |Microsoft Docs'
description: '問 # 標準程式庫-特性'
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0c347113339a77e9eaf63dc0967c320f8b063a0e
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036248"
---
# <a name="quantum-characterization-and-statistics"></a>量子特性和統計資料 #

務必要能夠描述作業的效果，以便開發有用的配量演算法。
這是一項挑戰，因為每個配量系統的測量最多隻會產生一位資訊。
若要瞭解 eigenvalue，請單獨讓一個配量狀態，許多度量的結果都必須拼接在一起，讓使用者能夠搜集所需的許多資訊來表示這些概念。
配量狀態特別令人傷腦筋，因為[沒有任何](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)複製的定理指出無法從單一狀態複本學習任意的量子狀態，因為這樣做可讓您建立狀態的複本。
這會反映使用者的量子狀態混淆，這是因為問 # 並未公開或甚至定義量副程式*的狀態。*
因此，我們藉由將作業和狀態視為全黑箱，來處理量子的特性;這種方法與量子特性、驗證和驗證（QCVV）的實驗性做法共同共通。

特性與先前討論的許多其他程式庫不同。
這裡的目標是要瞭解有關系統的傳統資訊，而不是在狀態向量上執行單一轉換。
因此，這些程式庫必須混合傳統和量子資訊的處理。


## <a name="iterative-phase-estimation"></a>反復階段估計 ##

根據量子特性來查看配量程式設計，會建議對量子階段估計有用的替代方法。
也就是說，我們可以將階段估計視為*傳統*代理程式透過測量來學習量子系統屬性的過程，而不是準備 $n $ qubit 暫存器包含階段的二進位標記法。
我們會在量子案例中繼續進行，方法是使用階段 kickback，將黑色方塊作業的應用程式轉換成未知的角度旋轉，但會測量在旋轉後緊接在每個步驟中旋轉的 ancilla qubit。
這有個優點，我們只需要一個額外的 qubit 來執行量子案例中所述的階段 kickback，因為我們接著會以反復的方式從每個步驟的測量結果中學習階段。  
下面所提議的每一種方法，都使用不同的策略來設計實驗和不同的資料處理方法，以瞭解階段。  它們各有獨特的優勢，範圍從具有嚴格的錯誤界限，到納入先前資訊的能力、容許錯誤或在記憶體 limitted 的傳統電腦上執行。

在討論反復的階段估計時，我們會考慮將單一 $U $ 指定為黑箱作業。
如[資料結構](xref:microsoft.quantum.libraries.data-structures)中的 oracles 一節所述，Q # canon 會依 <xref:microsoft.quantum.oracles.discreteoracle> 使用者定義型別（由元組類型所定義） `((Int, Qubit[]) => Unit : Adjoint, Controlled)`來進行作業。
具體而言，如果 `U : DiscreteOracle`，則 `U(m)` 會為 `m : Int`實 $U ^ m $。

有了這個定義之後，反復階段估計的每個步驟 $U 就會繼續進行 $ \ket{+} $ 狀態的輔助 qubit，以及[我們假設的](xref:microsoft.quantum.concepts.matrix-advanced)初始狀態 $ \ket{\phi} $，亦即 $U （m） \ket{\phi} = e ^ {im\phi} \ ket {\ phi} $。  
接著會使用 `U(m)` 的受控應用程式來準備 state $ \left （R\_1 （m \phi） \ket{+} \right） \ket{\phi} $。
如同在量子案例中，oracle `U(m)` 的受控制應用程式的效果，與在 $ \ket{+} $ 的未知階段套用 $R _1 $ 的效果完全相同，因此我們可以更簡單的方式來描述 $U $ 的效果。
或者，此演算法會藉由套用 $R _1 （-m\theta） $ 來取得 state $ \ket{\psi} = \left （R\_1 （m [\phi-\theta]） \ket{+} \right） \ket{\phi} $ $，以旋轉控制項 qubit。
然後，用來做為 `U(m)` 之控制項的輔助 qubit 會以 $X $ 為單位測量，以取得單一傳統 `Result`。

此時，會從透過反復階段估計取得的 `Result` 值來重建階段，這是一種傳統的統計推斷問題。
找出最大化所取得之資訊的 $m $ 值，只是統計資料中的問題。
我們藉由在貝氏參數估計形式中簡要說明理論層級的反復階段估計，然後再繼續描述 Q # canon 中提供的統計演算法來解決此傳統推斷問題，以強調這一點。

### <a name="iterative-phase-estimation-without-eigenstates"></a>不 Eigenstates 的反復階段估計 ###

如果提供的輸入狀態不是 eigenstate，也就是假設如果 $U （m） \ket{\phi\_j} = e ^ {im\phi\_j} $，則階段估計的程式會以非決定性的方式引導到單一能源 eigenstate 的量子狀態。  最後聚合到的 eigenstate 是最有可能產生觀察 `Result`的 eigenstate。

具體而言，PE 的單一步驟會在 state \begin{align} \ sum_j \sqrt{\Pr （\phi\_j）} \ket{\phi\_j} \mapsto \sum\_j\frac {\ sqrt {\ Pr 上執行下列非單一的轉換（\phi\_j）} \sqrt{\Pr （\text{Result} | \phi\_j）} \ket{\phi\_j}} {\sqrt{\Pr （\phi\_j） \sum\_j \Pr （\text{Result} | \phi\_j）}}。
\end{align} 因為此程式會反復執行多個 `Result` 值，所以沒有 $ \ prod_k \Pr （\text{Result}\_k | \phi\_j） $ 的最大值的 eigenstates 將會以指數方式隱藏。
因此，如果已正確選擇實驗，則推斷程式通常會聚合成具有單一 eigenvalue 的狀態。

貝氏機率分類 ' 定理會進一步建議，從階段估計產生的狀態是以 \begin{align} \frac{\sqrt{\Pr （\phi\_j）} \sqrt{\Pr （\text{Result} | \phi\_j）} \ket{\phi\_j}} {\sqrt{\Pr （\phi\_j） \sum\_j \Pr （\text{Result} | \phi\_j）}} = \ sum_j \sqrt{\Pr （\phi\_j | \text{Result}）} \ket{\phi\_j} 的形式寫入。
\end{align} 這裡 $ \Pr （\phi\_j | \text{Result}） $ 可以解釋為每個假設有 ascribe 的機率：

1. 測量之前的量子狀態知識，
2. $U $ 和的 eigenstates 知識
3. $U $ 的特徵值知識。

學習這三件事通常在傳統電腦上會有指數的困難。
第一階段估計的公用程式不是很小的範圍，因為它可以執行這類的量子學習工作，而不需要知道其中任何一項。
此原因的階段估計會出現在提供指數加速的一些量子演算法內。

### <a name="bayesian-phase-estimation"></a>貝氏階段估計 ###

> [!TIP]
> 如需在實務中貝氏階段估計的詳細資訊，請參閱[**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)範例。

貝氏階段估計的概念很簡單。
您可以從階段估計通訊協定收集測量統計資料，然後使用貝氏推斷來處理結果，並提供參數的預估。
這項處理可讓您估計 eigenvalue 以及該估計中的不確定性。
它也可讓您執行自動調整的實驗，並利用先前的資訊。
方法的缺點是，它需要進行計算。

若要瞭解此貝氏推斷程式的運作方式，請考慮處理單一 `Zero` 結果的案例。
請注意，$X = \ket{+} \bra{+}-\ket{-}\bra{-}$，因此 $ \ket{+} $ 是對應至 `Zero`之 $X $ 唯一的正 eigenstate。
在給定輸入狀態 $ \ket{\psi}\ket{\phi} $ 的情況中，觀察第一個 qubit 上[`PauliX` 量測](xref:microsoft.quantum.concepts.pauli)`Zero` 的機率，因此 \begin{equation} \Pr （\texttt{Zero} | \psi） = \left |\braket{+ | \psi} \right | ^ 2。
\end{equation} 在反復階段估計的案例中，我們有 $ \ket{\psi} = R_1 （m [\phi-\theta]） \ket{+} $，因此 \begin{align} \Pr （\texttt{Zero} | \phi; m，\theta） & = \left |\braket{+ |R_1 （m [\phi-\theta]） |+} \right | ^ 2 \\\\ & = \left |\frac12 \left （\bra{0} + \bra{1} \right） \left （\ket{0} + e ^ {i m [\phi-\theta]} \ket{1} \right） \right | ^ 2 \\\\ & = \left |\frac{1 + e ^ {i m [\phi-\theta]}}{2} \right | ^ 2 \\\\ & = \cos ^ 2 （m [\phi-\theta]/2） \tag{★} \label{eq：階段-est-可能性}。
\end{align} 也就是，反復的階段估計包含學習 sinusoidal 函式的震盪頻率，並能夠使用該 sinusoid 所指定的偏差來翻轉硬幣。
遵循傳統的傳統術語，我們呼叫 $ \eqref{eq：階段-est-機率} $ 反復階段估計的*可能性函數*。

在觀察到反復階段估計可能性函式中的 `Result` 之後，我們就可以使用貝氏機率分類的規則，規定我們應該認為該階段遵循該觀察。
具體而言、\begin{equation} \Pr （\phi | d） = \frac{\Pr （d | \phi） \Pr （\phi）} {\int \Pr （d | \phi） \Pr （\phi） {\mathrm d} \phi} \Pr （\phi）、\end{equation}，其中 $d \in \\{\texttt{Zero}，\texttt{One}\\} $ 是 `Result`，其中 $ \Pr （\phi） $ 描述我們先前信念的 $ \phi $。
這會使反復階段估計的反復性質明確，因為「事後 posterior 散發 $ \Pr （\phi | d） $ 會立即描述我們在下一個 `Result`觀察之前的信念。

在此程式中的任何時間點，我們可以將傳統控制器所推斷的階段 $ \hat{\phi} $ 報告為 \begin{equation} \hat{\phi} \mathrel{： =} \expect [\phi | \text{data}] = \int \phi \Pr （\phi | \text{data}） {\mathrm d} \phi，\end{equation}，其中 $ \text{data} $ 代表所有取得之 `Result` 值的完整記錄。

實際的貝氏推斷實際上是棘手。
為了查看這種假設，我們想要瞭解 $ $x $ $n $ 位變數。
先前的散發 $ \Pr （x） $ 可支援 $x $ 的 $ 2 ^ n $ 假設值。
這表示，如果我們需要 $x $ 的高精確度估計，則貝氏階段估計可能需要記憶體和處理時間的承受度。
對於某些應用程式（例如量子模擬），所需的 limitted 精確度並不會妨礙其他應用程式（例如快速鍵的演算法）無法在其階段估計步驟中使用精確的貝氏推斷。  基於這個理由，我們也提供大約貝氏方法的實作為，例如[隨機的逐步解說階段估計（RWPE）](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation) ，以及非貝氏的方法，例如[健全的階段估計](xref:microsoft.quantum.characterization.robustphaseestimation)。

### <a name="robust-phase-estimation"></a>健全的階段估計 ###

在最糟的情況下， *posteriori*貝氏從測量結果中重建階段估計的最大值會有指數的困難。 因此，大部分實際的階段估計演算法會犧牲一些重建的品質，而在 exchange 中則是一種傳統的後置處理，它會以所做的測量數目來調整 polynomially。

具有有效率的傳統後置處理步驟的其中一個範例是[健全的階段估計演算法](https://arxiv.org/abs/1502.02677)，其簽章和輸入都是上面所述。 它假設輸入單一的黑色方塊 $U $ 已封裝為 `DiscreteOracle` 類型，因此只會查詢受控制 $U $ 的整數乘冪。 如果 `Qubit[]` 暫存器中的輸入狀態是 eigenstate $U \ket{\psi} = e ^ {i\phi} \ ket {\ psi} $，則健全的階段估計演算法會以 `Double`的形式傳回 $ \hat{\phi}\in $ 的預估 $ \pi [-\pi，\phi） $。

健全的階段估計最重要的功能是與其他大部分有用的變體共用，是 $ \hat{\phi} $ 的重建品質在某種程度上是海森堡有限的。 這表示如果 $ \hat{\phi} $ 與 true 值的偏差是 $ \sigma $，則 $ \sigma $ 會以反比星號調整至 $U $ 所控制的查詢總數 $Q $，亦即 $ \sigma = \mathcal{O} （1/Q） $。 現在，偏差的定義會因不同的估計演算法而有所不同。 在某些情況下，它可能表示至少有 $ \mathcal{O} （1） $ 機率，估計錯誤 $ | \hat{\phi}-\phi |\_\circ\le \sigma $ on a 迴圈量值 $ \circ $。 針對健全的階段估計，如果我們將定期階段解除包裝成單一的有限間隔 $ （-\hat{\phi}-\phi，\pi] $，則偏差就會精確地指向 $ \sigma ^ 2 = \mathbb{E}\_\hat{\phi} [（\mod\_{2 \ pi} （\pi + \pi）-\pi） ^ 2] $。 更精確地說，健全狀況估計中的標準差符合到差異 $ $ \begin{align} 2.0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ pi/Q，\end{align} $ $，其中下限達到 asymptotically 大型 $Q $ 的限制，而上限則是針對小型樣本大小所保證。  請注意，由 `bitsPrecision` 輸入所選取的 $n $ 會隱含定義 $Q $。

其他相關的詳細資料包括只有 $1 $ ancilla qubit 的小空間額外負荷，或程式是非彈性的，這表示所需的量子實驗順序與中繼測量結果無關。 在此和即將推出的範例中，階段估計演算法的選擇很重要，其中一個應該參考檔，例如 @"microsoft.quantum.characterization.robustphaseestimation" 和參考的發行集，以取得詳細資訊和其執行方式。

> [!TIP]
> 有許多範例會使用健全的階段估計。 如需瞭解各種實體系統之接地能源的階段估計，請參閱[ **H2 模擬**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)、 [ **SimpleIsing**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)和[ **Hubbard 模型**範例](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)。


### <a name="continuous-oracles"></a>連續 Oracles ###

我們也可以從上面使用的 oracle 模型一般化，以允許持續時間的 oracles （依 canon 類型 <xref:microsoft.quantum.oracles.continuousoracle>模型化）。
請考慮，而不是單一的單一運算子 $U $，我們有一系列的單一運算子 $U （t） $ for $t \in \mathbb{R} $，使 $U （t） U （s） $ = $U （t + s） $。
這是比離散案例更弱的語句，因為我們可以藉由限制某些 fixed $ \delta t $ 的 $t = m\,\delta t $ 來建立 <xref:microsoft.quantum.oracles.discreteoracle>。
根據[石頭的定理](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups)，$U （t） = \exp （i H t） $ for a operator $H $，其中 $ \exp $ 是矩陣指數，如 advanced matrix （高階[矩陣](xref:microsoft.quantum.concepts.matrix-advanced)）中所述。
$H $ 的 eigenstate $ \ket{\phi} $，讓 $H \ket{\phi} = \phi \ket{\phi} $ 也是 $U （t） $ 適用于所有 $t $、eigenstate U （t） \begin{equation} = e ^ {i \ket{\phi} t} \phi 的 \ket{\phi}。
\end{equation}

您可以套用針對[貝氏階段估計](#bayesian-phase-estimation)所討論的相同分析，而此機率函式與此較一般的 oracle 模型完全相同： $ $ \Pr （\texttt{Zero} | \phi; t，\theta） = \cos ^ 2 \ left （\frac{t [\phi-\theta]}{2}\right）。
$ $ 此外，如果 $U $ 是 dynamical 產生器的模擬（ [Hamiltonian 模擬](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)的情況），我們會將 $ \phi $ 解讀為能源。
因此，使用階段估計搭配連續查詢，可讓我們瞭解分子驅使分子、[材質](https://arxiv.org/abs/1510.03859)或[現場理論](https://arxiv.org/abs/1111.3633v2)的模擬[能源](https://arxiv.org/abs/quant-ph/0604193)範圍，而不需犧牲所選的實驗，方法是要求 $t $ 必須是整數。

### <a name="random-walk-phase-estimation"></a>隨機逐步解說階段估計 ###

問 # 提供貝氏階段估計的有用近似值，其設計目的是要使用接近的配量裝置，其操作方式是針對從反復階段估計取得的資料記錄，進行隨機的引導。
這個方法既可調適型且完全具決定性，允許在估計階段 $ \hat{\phi} $ 中，以極低的記憶體額外負荷來進行接近優化的錯誤調整。

通訊協定會使用近似的貝氏推斷方法，假設先前的散發為高斯。
此高斯假設可讓我們針對實驗流量分析公式，以最小化「事後 posterior 變異數。
然後，此演算法會根據該實驗的結果，將 $ \phi $ left 或 right 的估計值向左或向右移動預先決定的數量，並根據預先決定的數量來縮小變異數。
這個平均值和變異數會提供在 $ \phi $ 之前指定高斯以進行下一個實驗所需的所有資訊。
未預期的測量失敗，或 true 結果在先前的連接結尾上，可能會導致這個方法失敗。
它會藉由執行實驗來測試目前的平均值和標準差是否適用于系統，以從失敗中復原。
如果不是，則演算法會執行本逐步解說的反向步驟，而且進程會繼續進行。
回溯的能力也可以讓演算法學習，即使最初的標準差是 inapropriately 小的也一樣。

## <a name="calling-phase-estimation-algorithms"></a>呼叫階段估計演算法 ##

Q # canon 所提供的每個階段估計作業，會採用一組不同的輸入，將我們所需的品質參數化為最終估計 $ \hat{\phi} $。
不過，這些不同的輸入全都共用數個常見的輸入，因此部分應用程式在品質參數上會產生共同的簽章。
例如，下一節所討論的 <xref:microsoft.quantum.characterization.robustphaseestimation> 作業具有下列簽章：

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

`bitsPrecision` 輸入對 `RobustPhaseEstimation`而言是唯一的，而 `oracle` 和 `eigenstate` 是常見的。
因此，在**H2Sample**中，作業可以接受具有格式輸入 `(DiscreteOracle, Qubit[]) => Unit` 的反復階段估計演算法，以允許使用者指定任意階段估計演算法：

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

這些各式各樣的階段估計演算法會針對不同的屬性和輸入參數進行優化，必須加以瞭解才能為目標應用程式做出最佳選擇。 比方說，某些階段估計演算法是可調整的，這表示未來的步驟是由先前步驟的測量結果來傳統方式控制。 有些人需要能夠以任意實際的方式 exponentiate 其黑箱的單一 oracle，而有些則只需要整數乘冪，但只能解析階段估計的模數 $ 2 \ pi $。 有些需要多個輔助 qubits，而其他則只需要一個。

同樣地，使用隨機的逐步解說階段估計，會以與 canon 所提供的其他演算法大致相同的方式進行：

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
