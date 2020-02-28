---
title: Q 中的量子演算法#
description: 瞭解基本的量子計算演算法，包括振幅放大、傅立葉轉換、Draper 和 Beauregard adders，以及階段估計。
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: aaa9ddf47e5ea35e7e57b9828db082889d0e6adf
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907234"
---
# <a name="quantum-algorithms"></a>量子演算法 #

## <a name="amplitude-amplification"></a>幅度放大 ##

*振幅放大*是量子運算的基本工具之一。 這是基礎 Grover 搜尋、振幅估計和許多量子機器學習演算法的基本概念。  有許多變化，而在 Q # 中，我們提供了以部分反射為基礎的遺忘式振幅放大的一般版本，以允許應用程式的最廣泛區域。

在振幅放大背後的主要概念，是藉由執行一系列反射來擴展所需結果的機率。  這些反射會將初始狀態旋轉到想要的目標狀態，通常稱為標示的狀態。  具體而言，如果測量初始狀態的機率是 $ \sin ^ 2 （\theta） $，然後在套用振幅放大 $m $ 倍，成功的機率就會變成 $ \sin ^ 2 （（2m + 1） \theta） $。  這表示如果 $ \theta = \ pi/[2 （2n + 1）] $ 適用于某些 $n $ 的值，則振幅放大能夠在 $n $ 反覆運算幅度放大之後，提高成功到 $100\\% $ 的機率。  由於 $ \theta = \sin ^{-1}（\sqrt{\Pr （success）}） $ 這表示取得成功所需的反復專案數目，會 quadratically 低於使用隨機取樣來以非決定性的方式尋找標示的狀態所需的數目。

振幅放大的每次反覆運算都需要指定兩個反映運算子。 具體而言，如果 $Q $ 是「幅度放大」會逐一查看並 $P _0 $ 是在初始子空間上的投影機運算子，而 $P _1 $ 是投影機放在標示的子空間上，然後 $Q =-（\boldone-2P_0）（\boldone-2P_1） $。  回想一下，投影機是具有特徵值 $ + $1 和 $0 $ 的 Hermitian 運算子，因此 $ （\boldone-2P_0） $ 是單一的，因為它有一個屬於 unity 根的特徵值（在此案例中為 $ \pm $1）。 例如，假設 Grover 的搜尋案例中的初始狀態 $H ^ {\otimes n} \ket{0}$ 並標示 state $ \ket{m} $、$P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ 和 $P _1 = \ket{m}\bra{m} $。  在大部分的振幅放大應用程式中 $P _0 $ 將會成為初始狀態的投影機，這表示 $P _0 = \boldone-2 \ ket {\ psi} \ bra {\ psi} $ 適用于某些向量 $ \ket{\psi} $;不過，對於遺忘式的振幅 amplication $P _0 $ 通常會投射到許多配量狀態（也就是 $ + $1 eigenvalue 的多重性，$P _0 $ 大於 $1 $）。

在振幅放大後的邏輯會直接從 $Q $ 的特徵分解。  具體而言，$Q $ 的特徵向量 $ （初始狀態具有非零的支援）可以顯示為 $ + $1 特徵向量的線性組合，$P _0 $ 和 $P _1 $。  具體而言，幅度放大的初始狀態（假設它是 $P _0 $ 的 $ + $1 eigenvector）可以寫成 $ $ \ket{\psi} = \frac{-i}{\sqrt{2}} \left （e ^ {i\theta} \ ket {\ psi_ +} + e ^ {-i\theta} \ ket {\ psi_-} \right）、$ $，其中 $ \ket{\ psi_ \pm} $ 特徵向量 $Q $ with 特徵值 $e ^ {\pm 2i \ theta} $，而且只支援 $P 特徵向量 $ 和 $P _1 $ 的 $ + $1 _0。  特徵值是 $e ^ {\pm i \theta} $ 的事實，意味著運算子 $Q $ 會在兩個投影機所指定的二維子空間中執行旋轉，以及旋轉角度為 $ 2 \ theta $ 的初始狀態。  這就是為什麼在 $m $ 反復 $Q $ 的成功機率為 $ \sin ^ 2 （[2m + 1] \theta） $ 之後。

另一個很實用的屬性，就是 eigenvalue $ \theta $ 與初始狀態標示的機率直接相關（在此情況下，$P 的 _0 $ 只會放在初始狀態）。  由於 $Q $ 的 eigenphases 是 $ 2 \ theta = 2 \ sin ^{-1}（\sqrt{\Pr （success）}） $，因此，如果我們將階段估計套用到 $Q $，我們就可以瞭解單一量副程式成功的機率。  這項功能很有用，因為它需要 quadratically 較少的量副程式應用程式，以瞭解比其他方式需要的成功機率。

問 # 引進了振幅放大，做為遺忘式振幅放大的特製化。  遺忘式幅度放大會獲得此名字標記，因為投影機到初始 eigenspace 不一定是投影機進入初始狀態。  就這一點而言，通訊協定會遺忘式為初始狀態。  遺忘式振幅放大的主要應用是單一 Hamiltonian 模擬方法的特定*線性組合，其中*初始狀態為未知，但會隨著模擬通訊協定中的 ancilla 暫存器而變成光子。  如果要將此 ancilla 暫存器測量為固定值（例如 $0 $），則這類模擬方法會將所需的單一轉換套用到剩餘的 qubits （稱為系統暫存器）。  不過，所有其他的測量結果都會導致失敗。  遺忘式振幅放大可讓此度量的成功機率提升為 $100\\% $ 使用上述推理。  此外，一般振幅放大會對應到系統暫存器為空白的情況。  這就是為什麼 Q # 會使用遺忘式振幅放大來作為其基礎的幅度放大副程式。

一般常式（`AmpAmpObliviousByReflectionPhases`）有兩個我們稱之為 `ancillaRegister` 和 `systemRegister`的暫存器。 它也會接受兩個 oracles 來進行必要的反射。 `ReflectionOracle` 僅適用于 `ancillaRegister`，而 `ObliviousOracle` 同時在這兩個暫存器上共同運作。 `ancillaRegister` 的輸入必須初始化為第一個反映運算子 $ \boldone-2P_1 $ 的-1 eigenstate。

一般來說，oracle 會以計算基礎 $ \ket{0...0} $ 來準備狀態。 在我們的執行中，會有一個 qubit （`flagQubit`）的 `ancillaRegister` consistes，可控制 `stateOracle` 和所需 ancillas 的其餘部分。 當 `flagQubit` 為 $ \ket{1}$ 時，就會套用 `stateOracle`。

您也可以透過對 `AmpAmpObliviousByOraclePhases`的呼叫，提供 oracles `StateOracle` 和 `ObliviousOracle` 而不是反射。

如前所述，傳統的振幅放大只是這些常式的特殊案例，其中 `ObliviousOracle` 是身分識別運算子，而且沒有系統 qubits （亦即，`systemRegister` 是空的）。 如果您想要取得部分反射的階段（例如，針對 Grover 搜尋），可以使用函數 `AmpAmpPhasesStandard`。 如需 Grover 演算法的範例執行，請參閱 `DatabaseSearch.qs`。

我們會將單一 qubit 迴圈階段關聯至反映運算子階段[，如 G.H. Low、Chuang](https://arxiv.org/abs/1707.05391)中所述。 [Yoder、low 和 Chuang](https://arxiv.org/abs/1409.3305)中會詳細說明所使用的固定點階段，以及[低、Yoder 和 Chuang](https://arxiv.org/abs/1603.03996)中的階段。

在背景中，您可以從[標準的振幅放大](https://arxiv.org/abs/quant-ph/0005055)開始，然後移至[遺忘式振幅放大](https://arxiv.org/abs/1312.1414)的簡介，最後會以[低和 Chuang](https://arxiv.org/abs/1610.06546)呈現的一般化。 [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)提供此整個區域（與 Hamiltonian 模擬有關）的絕佳總覽簡報。

## <a name="quantum-fourier-transform"></a>量子傅立葉轉換 ##

傅立葉轉換是傳統分析的基本工具，對量子計算而言也是一樣重要。
此外，配量*傅立葉轉換*（QFT）的效率遠超過傳統電腦上的可能結果，使其成為設計配量演算法時的第一個選擇工具。

做為 QFT 的大致一般化，我們提供了 <xref:microsoft.quantum.canon.approximateqft> 作業，可讓您藉由剪除所需演算法精確度不一定需要的旋轉來進行進一步的優化。
大約的 QFT 需要 dyadic $Z $-輪替作業 <xref:microsoft.quantum.intrinsic.rfrac>，以及 <xref:microsoft.quantum.intrinsic.h> 作業。
假設輸入和輸出是以 big endian 編碼來編碼---也就是說，具有索引 `0` 的 qubit 會以二進位整數表示的最左邊（最高）位編碼。
這會與[ket 標記法](xref:microsoft.quantum.concepts.dirac)對齊，如同 state $ \ket 中的三個 qubits 的暫存器，{100}$ 對應到 $q _0 $ 在 state $ \ket{1}$ 中，而 $q _1 $ 和 $q _2 $ 同時處於 state $ \ket{0}$。
近似值參數 $a $ 決定 $Z $-輪替的剪除層級，也就是 $a \in [0 ... n] $。
在此情況下，所有 $Z $-輪替 $ 2 \ pi/2 ^ k $，其中 $k > $ 會從 QFT 迴圈中移除。
已知 $k \ge \ log_2 （n） + \ log_2 （1/\epsilon） + $3。 一個可以系結 $\\|\operatorname{QFT}-\operatorname{AQFT} \\|< \epsilon $。
這裡 $\\| \cdot\\| $ 是運算子的標準，在此案例中是 $ （\operatorname{QFT}-\operatorname{AQFT}）（\operatorname{QFT}-\operatorname{AQFT}） ^ \dagger $ 最大[eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced)的平方根。

## <a name="arithmetic"></a>算術 ##

就像算術在傳統運算中扮演中央角色一樣，這在量子計算中也是不可或缺的。  演算法（例如快速鍵的分解演算法、量子模擬方法以及許多 oracular 演算法）依賴一致的算數運算。  在量子加入線路上進行算術組建的大部分方法。  最簡單的加入程式會採用傳統輸入 $b $，並將值新增至保留整數 $ \ket{a} $ 的量子狀態。  在數學上，此「對應器」（其代表 $ \operatorname{Add} （b） $ 用於傳統輸入 $b $）的屬性為

$ $ \operatorname{Add} （b） \ket{a} = \ket{a + b}。
$ $ 這個基本的產生程式線路比 incrementer 更多。
您可以透過 $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} 將它轉換成具有兩個配量輸入的加入器，$ $ 使用格式為 \begin{align} \operatorname{Add} \ket{a} \ket{b} adders 的 $n $ 受控制應用程式 & = \Lambda\_{a\_0} \left （\operatorname{Add} （1） \right） \Lambda\_{a\_1} \left （\operatorname{Add} （2） \right） \Lambda\_{a\_2} \left （\operatorname{Add} （4） \right） \cdots \Lambda\_{a\_{n-1}} \left （\運算子名稱 {Add} （{{n-1}}） \right） \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}、\end{align} for $n $ bit integer $a $ and $b $ 和加法模數 $ 2 ^ n $。  回想一下，標記法 $ \Lambda\_x （A） $ 代表任何作業 $A $，到該作業的受控制版本，並以 qubit $x $ 作為控制項。

同樣地，您可以使用類似的一系列受控制新增來執行傳統方式控制乘法（這是快速鍵的分解演算法不可或缺的模組化形式）： \begin{align} \operatorname{Mult} （a） \ket{x}\ket{b} & = \Lambda\_{x\_0} \left （\operatorname{Add} （2 ^ 0 a） \right） \Lambda\_{a\_1} \left （\operatorname{Add} （2 ^ 1a） \right） \Lambda\_{a\_2} \left （\operatorname{Add} （2 ^ 2 a） \right） \cdots \Lambda\_{x\_{n-1}} \left （\operatorname{Add} （{2 ^ {n-1}} a） \right） \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + ax}。
\end{align} 有一個奧妙在配量電腦上有乘法，您可能會注意到上面的 $ \operatorname{Mult} $ 定義。  不同于新增，此線路的量子版本會將輸入的產品儲存在輔助暫存器中，而不是輸入暫存器中。  在此範例中，會使用值 $b $ 初始化暫存器，但通常會開始保留值零。  這在中是必要的，因為一般而言，一般 $a $ 和 $x $ 不會有乘法的反向。  由於所有的量子作業（儲存量測）都是可復原的，因此我們需要保留足夠的資訊來反轉乘法。  基於這個理由，結果會儲存在不同的陣列中。  將無法復原之作業的輸出（例如乘法）儲存在個別的暫存器中，在 Charlie Bennett 之後稱為「Bennett 技巧」，而且是可還原和量子運算的基本工具。

許多配量線路已針對加法提出建議，而且每個電路都會根據 qubits （空間）數目和所需的閘道作業數（時間）來探索不同的取捨。  我們在下方回顧兩個高空間效率的 adders，稱為 Draper 的「進行」和「Beauregard」。

### <a name="draper-adder"></a>Draper 的 ###

Draper 的新增項可說是其中一個最簡潔的量子 adders，因為它會直接叫用配量屬性來執行加法。  Draper 加入程式背後的深入解析，是可以使用傅立葉轉換來將階段轉移轉譯成位移位。  接著，藉由套用傅立葉轉換、套用適當的階段移位，然後復原傅立葉轉換，您就可以執行合併器。  不同于其他許多已提議的 adders，Draper 的加入程式會明確地使用透過配量傅立葉轉換所引進的量子效果。  它沒有自然的傳統對應。  以下提供 Draper 相應的特定步驟。

假設您有兩個 $n $ bit qubit 暫存器儲存 $a $ 和 $b $ 的整數，然後適用于所有 $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi （aj）/2 ^ n} \ket{j}。
$ $ 如果我們定義 $ $ \ket{\phi\_k （a）} = \frac{1}{\sqrt{2}} \left （\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right），$ $，然後在某些代數之後，您可以看到 $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 （a）} \otimes \cdots \otimes \ket{\phi\_n （a）}。
$ $ 執行轉換程式的路徑會在觀察到輸入的總和可以寫成 $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\phi\_1 （a + b）} \otimes \cdots \otimes \ket{\phi\_n （a + b）} 之後變得清楚。
$ $ $B $ 和 $a $ 的整數可以藉由使用 $b $ 作為控制項的位，在分解中的每個 qubits 上執行控制階段旋轉來新增。

請注意，對於任何整數 $j $ 和 real $x $、$e ^ {i2\pi （x + j）} = e ^ {i2\pi x} $，都可以進一步簡化這項擴充。  這是因為如果您在圓圈中旋轉 $ 360 ^ {\circ} $ 度數（$ 2 \ pi $ radians），就會精確地結束您的開始位置。  $E ^ {i2\pi x} $ 的 $x $ 唯一重要的部分，就是 $x $ 的小數部分。  具體而言，如果我們有格式的二進位擴充 $x = y +0. x\_0x\_2 \ ldots x\_n $ then $e ^ {i2\pi x} = e ^ {i2\pi （0）。 x\_0x\_2 \ ldots x\_{n-1}）} $，因此 $ $ \ket{\phi\_k （a + b）} = \frac{1}{\sqrt{2}} \left （\ket{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ket{1} \right）。 $ $ 這表示如果我們藉由遞增每個張量 $ \ket{a} $ 的傅立葉轉換時的因素，然後隨著 $k $ 減少，旋轉數目會縮小。  這會大幅減少在「增加項」中所需的量子閘道數目。  我們代表以 $ \operatorname{QFT} ^{-1} \left （\phi\\\!\operatorname{ADD}\right） \operatorname{QFT} $ 形式組成 Draper 加入程式的傅立葉轉換、階段新增和反向傅立葉轉換步驟。 以下是使用這種簡化來執行整個程式的量子線路。

![顯示為「電路圖」的 Draper](~/media/draper.png)

線路中的每個受控制 $e ^ {i2 \ pi/k} $ 閘道指的是受控制階段的閘道。  這類閘道的屬性會在其作用的 qubits 上，$ \ket{00}\mapsto \ket{00}$ 但 $ \ket{11}\mapsto e ^ {i2 \ pi/k} \ ket{11}$。  此線路可讓我們使用除了儲存輸入和輸出所需的其他 qubits 來執行加法。

### <a name="beauregard-adder"></a>Beauregard 的 ###

Beauregard 的加入程式是一種配量模組化的「配量」，它會使用 Draper 加入程式來對任意值 $N $ 的正整數執行加法模數 $N $。  量子模組化 adders （例如 Beauregard 的加入器）的重要性，會從其在快速鍵的演算法中用於分解的模組乘冪步驟中，被視為很大的範圍。  配量模組化的加入器對於配量輸入 $ \ket{b} $ 和傳統輸入 $a $ 具有下列動作，其中 $a $ 和 $b $ 會承諾為整數 mod $N $，表示它們是在間隔 $ [0，\ldots，N-1] $ 中。

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{cases} \ket{b + a}、& b + a < N\\\\ \ket{b + a-N}、& （b + a） \ge N \end{cases}。
$$

Beauregard 的加入載入項會使用 Draper 的加入或更具體的 $ \phi\\\!\operatorname{ADD} $），在階段中新增 $a $ 和 $b $。  然後，它會使用相同的作業來識別是否 $a + b < N $，方法是減去 $N $，並在 $a + b-N < 0 $ 時進行測試。  線路會將這項資訊儲存在輔助 qubit 中，然後在 $a + b < N $ 時，將 $N $ 返回註冊。  然後藉由 uncomputing 此輔助單位來結束（必須執行此步驟，才能確保在呼叫加入器之後可以解除配置 ancilla）。  以下提供 Beauregard 對應程式的線路。

![顯示為「電路圖」的 Beauregard](~/media/beau.png)

這裡的閘道 $ \Phi\\\!\operatorname{ADD} $ 採用與 $ \Phi\\\!\operatorname{ADD} $ 相同的格式，但在此內容中，輸入是傳統而不是配量。  這可讓 $ \Phi\\\!\operatorname{ADD} $ 中受控制的階段取代為階段閘道，然後將其編譯成較少的作業，以減少 qubits 數目和加入程式所需的閘道數目。

如需詳細資訊，請參閱[Roetteler、Beth](http://doi.org/10.1007/s00200-008-0072-2 )和[Coppersmith](https://arxiv.org/abs/quant-ph/0201067)。

### <a name="quantum-phase-estimation"></a>量子相位估算法 ###

配量傅立葉轉換的一個特別重要應用，是瞭解單一運算子的特徵值，這是一個稱為「*階段估計*」的問題。
請考慮使用單一 $U $ 和 state $ \ket{\phi} $，讓 $ \ket{\phi} $ 是 $U $ 的 eigenstate，其中包含未知的 eigenvalue $ \phi $、\begin{equation} U\ket {\ phi} = \phi\ket{\phi}。
\end{equation} 如果我們只有 $U $ 做為 oracle 的存取權，我們就可以藉由使用對受控制作業的目標所套用的 $Z $ 旋轉，來學習階段 $ \phi $，將其傳播回控制項上。

假設 $V $ 是受控制的 $U $ 應用程式，因此 \begin{align} V （\ket{0} \otimes \ket{\phi}） & = \ket{0} \otimes \ket{\phi} \\\\ \textrm{和} V （\ket{1} \otimes \ket{\phi}） & = e ^ {i \phi} \ket{1} \otimes \ket{\phi}。
\end{align} Then，by 線性，\begin{align} V （\ket{+} \otimes \ket{\phi}） & = \frac{（\ket{0} \otimes \ket{\phi}） + e ^ {i \phi} （\ket{1} \otimes \ket{\phi}）} {\sqrt{2}}。
\end{align} 我們可以收集詞彙以尋找 \begin{align} V （\ket{+} \otimes \ket{\phi}） & = \frac{\ket{0} + e ^ {i \phi} \ket{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = （R_1 （\phi） \ket{+}） \otimes \ket{\phi}，\end{align}，其中 $R _1 $ 是 <xref:microsoft.quantum.intrinsic.r1> 作業所套用的單一。
以不同的方式放置，套用 $V $ 的效果與將 $R _1 $ 與未知的角度一起套用，即使我們只有以 oracle 的方式存取 $V $ 也一樣。
因此，在本討論的其餘部分，我們將根據 $R _1 （\phi） $ 來討論階段估計，我們使用所謂的*階段 kickback*來實現。

由於控制項和目標暫存器在此程式之後仍然 untangled，因此我們可以重複使用 $ \ket{\phi} $ 做為受控制應用程式的目標，$U ^ $2 來準備第二個控制項 qubit 的狀態 $R _1 （2 \phi） \ket{+} $。
以這種方式繼續進行，我們可以取得表單 \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 （2 ^ j \phi） \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left （\ket{0} + \exp （i 2 ^ {j} \phi） \ket{1}\right） \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp （i \phi k） \ket{k} \end{align}，其中 $n $ 是我們需要的精確度位數，我們使用 ${} \propto {}$ 來表示我們已抑制 $ 的正規化因數1/\sqrt{2 ^ n} $。

如果我們假設 $ \phi = 2 \pi p/2 ^ k $ 適用于 integer $p $，則我們會將它辨識為 $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots . p_n} $，其中 $p _j $ 是 $2 \textrm{th}} \pi $ 的 $j ^ {\phi $ bit。
套用配量傅立葉轉換的 adjoint 時，我們會取得編碼為配量狀態之階段的二進位標記法。

在 Q # 中，這是由 <xref:microsoft.quantum.characterization.quantumphaseestimation> 作業所執行，此作業會採用 <xref:microsoft.quantum.oracles.discreteoracle> 將 $U ^ m $ 的應用程式實作為正整數 $m $ 的函式。
