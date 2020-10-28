---
title: 中的量子演算法 Q#
description: 深入瞭解基本的量子運算演算法，包括振幅放大、傅立葉轉換、Draper 和 Beauregard adder，以及階段預估。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 982103876b00718aa3b42c6bc3a07d242cde7594
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692213"
---
# <a name="quantum-algorithms"></a>量子演算法 #

## <a name="amplitude-amplification"></a>幅度放大 ##

*振幅放大* 是量子運算的其中一項基本工具。 它是基礎格羅弗搜尋、振幅估計和許多量子機器學習演算法的基本概念。  其中有許多變化，而在 Q# 我們提供以無警示振幅放大的一般版本（具有部分反映），以允許最廣泛的應用程式區域。

振幅放大的核心概念是藉由執行一系列反射來增強所需結果的機率。  這些反射會將初始狀態旋轉更接近所需的目標狀態，通常稱為標示的狀態。  具體而言，如果測量初始狀態的機率是 $ \sin ^ 2 ( \theta) $ 然後套用振幅放大 $m $ 倍，則成功的機率會變成 $ \sin ^ 2 ( # B3 2m + 1) \theta) $。  這表示，如果 $ \theta = \ pi/[2 (2n + 1) ] $ 表示 $n $ 的某個值，則幅度放大可以 \\ 在幅度放大的 $n $ 反覆運算之後，將成功的機率提升至 $100% $。  由於 $ \theta = \sin ^ {-1} ( \sqrt{\pr (success) } ) $ 這表示取得成功時所需的反覆運算次數會 quadratically 低於使用隨機取樣找出以非決定性方式找出標記狀態所需的次數。

每次的波幅放大反覆運算都需要指定兩個反映運算子。 具體來說，如果 $Q $ 是幅度放大反覆運算器，$P _0 $ 是在初始子空間上的投影機運算子，而且 $P _1 $ 是投影機進入標記的子空間，然後 $Q =- ( \boldone-2P_0) # A2\boldone-2P_1) $。  回想一下，投影機是具有特徵值 $ + $1 和 $0 $ 且結果為 $ ( \boldone 2P_0) $ 的 Hermitian 運算子，因為它的特徵值是 unity 的根目錄 (在本例中是 $ \pm $1) 。 例如，請考慮使用初始狀態 $H ^ {\otimes n} \ket {0} $ 並標示 state $ \ket{m} $、$P _0 = h ^ {\otimes n} \ket {0} \bra {0} H ^ {\otimes n} $ 和 $P _1 = \Ket{m}\bra{m} $ 的格羅弗搜尋案例。  在大部分的波幅放大應用程式中 $P _0 $ 將會是一個投影機進入初始狀態，表示某些向量 $ bra $ 的 $P _0 = \boldone-2 \ ket {\ psi} \ \ket{\psi} {\ psi} $;不過，對於無警示振幅 amplication $P _0 $ 通常會投射到許多量子狀態 (亦即，$P _0 $ 的 $ + $1 eigenvalue 多重性大於 $1 $) 。

振幅放大的邏輯會直接從 $Q $ 的特徵分解。  具體而言，$Q $ 的特徵向量，初始狀態的非零支援可顯示為 $P _0 $ 和 $P _1 $ 的 $ + $1 特徵向量的線性組合。  具體來說，幅度放大的初始狀態 (假設它是 $P _0 $) 的 $ + $1 eigenvector，可寫入 $ $ \ket{\psi} = \frac{-i}{\sqrt {2} } \left (e ^ {i\theta} \ ket {\ psi_ +} + e ^ {-i\theta} \ ket {\ psi_-} \right) ，$ $ where $ \ket{\ psi_ \pm} $ 是特徵向量 of $Q $ with 特徵值 $e ^ {\pm 2i \ theta} $，且僅支援 $P 特徵向量 $ 和 $P _1 $ 的 $ + $1 _0。  特徵值 $e ^ {\pm i \theta} $ 表示運算子 $Q $ 會在兩個投影機指定的二維子空間中執行旋轉，而旋轉角度為 $ 2 \ theta $ 的初始狀態。  這就是為什麼 $m $ 反覆運算 $Q $ 的成功機率是 $ \sin ^ 2 ( [2m + 1] \theta) $。

另一項很有用的屬性是，eigenvalue $ \theta $ 與初始狀態會標示 (的機率直接相關，其中 $P _0 $ 是僅限初始狀態) 的投影機。  由於 $Q $ 的 eigenphases 為 $ 2 \ theta = 2 \ sin ^ {-1} ( \sqrt{\pr (success) } ) $ it 之後，如果我們將階段估計套用至 $Q $，則可以瞭解單一量副程式成功的機率。  這項功能很有用，因為它需要 quadratically 較少的量副程式應用程式來學習成功機率，而不是其他需要的。

Q# 引進了振幅放大作為無警示振幅放大的特製化。  無警示幅度放大獲得這個標記，因為投影機進入初始 eigenspace 時，不一定會有投影機進入初始狀態。  在這種情況下，通訊協定會無警示為初始狀態。  無警示幅度放大的主要應用是單一 Hamiltonian 模擬方法的特定 *線性組合，其中* 初始狀態是未知的，但會與模擬通訊協定中的 ancilla 暫存器進行纏結。  如果要將此 ancilla 註冊測量為固定值（例如 $0 $），則這類模擬方法會將所需的單一轉換套用至剩餘的量子位 (稱為系統註冊) 。  但是，所有其他測量結果都會導致失敗。  無警示幅度放大可利用上述的原因，讓此度量的成功機率提升至 $100 \\ % $。  此外，一般的幅度放大會對應到系統註冊是空的案例。  這就是為什麼 Q# 使用無警示幅度放大作為其基礎振幅放大副程式的原因。

一般常式 (`AmpAmpObliviousByReflectionPhases`) 有兩個稱為和的緩存 `ancillaRegister` 器 `systemRegister` 。 它也接受兩個 oracle 來進行必要的反射。 `ReflectionOracle`只會在 `ancillaRegister` `ObliviousOracle` 這兩個暫存器上共同運作。 的輸入 `ancillaRegister` 必須初始化為第一個反映運算子 $ \boldone-2P_1 $ 的-1 eigenstate。

一般來說，oracle 會以計算基礎來準備狀態 $ \ket{0...0} $。 在我們的實 consistes 中， `ancillaRegister` 有一個量子位 (`flagQubit`) ，可控制所 `stateOracle` 需 ancillas 的和其餘部分。 `stateOracle`當 `flagQubit` 為 $ \ket $ 時，就會套用 {1} 。

您也可以透過 `StateOracle` 呼叫來提供 oracle， `ObliviousOracle` 而不是反射 `AmpAmpObliviousByOraclePhases` 。

如前所述，傳統的波幅放大只是這些常式的特殊案例，其中 `ObliviousOracle` 是身分識別運算子，而且沒有系統量子位 (亦即， `systemRegister` 是空的) 。 如果您想要取得部分反射的階段 (例如，對於格羅弗搜尋) ，則 `AmpAmpPhasesStandard` 可以使用此函數。 `DatabaseSearch.qs`如需格羅弗演算法的範例執行，請參閱。

我們會將單一量子位的旋轉階段與反映運算子階段建立關聯，如 [G.H. Low、Chuang](https://arxiv.org/abs/1707.05391)。 使用的固定點階段詳細說明于 [Yoder、low 和 Chuang](https://arxiv.org/abs/1409.3305) ，以及 [低、Yoder 和 Chuang](https://arxiv.org/abs/1603.03996)中的階段。

在背景中，您可以從 [標準振幅放大](https://arxiv.org/abs/quant-ph/0005055) 開始，移至 [無警示振幅放大](https://arxiv.org/abs/1312.1414) 的簡介，最後再以 [低度和 Chuang](https://arxiv.org/abs/1610.06546)呈現泛用。 這整個領域 (的理想總覽展示，與 Hamiltonian 模擬) 是由 [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)提供。

## <a name="quantum-fourier-transform"></a>量子傅立葉轉換 ##

傅立葉轉換是一種傳統分析的基本工具，與量子計算一樣重要。
此外， *量子傅立葉轉換* (QFT) 遠超過傳統電腦上可能會有的功能，這是設計量子演算法時所選擇的第一個工具。

作為 QFT 的近似值，我們提供的作業可 <xref:Microsoft.Quantum.Canon.ApproximateQft> 讓您針對所需的演算法精確度，剪除不是絕對必要的旋轉，藉以進行進一步的優化。
大約的 QFT 需要 dyadic $Z $-輪替作業以及作業 <xref:Microsoft.Quantum.Intrinsic.RFrac> <xref:Microsoft.Quantum.Intrinsic.H> 。
輸入和輸出會假設以位元組由大到小的編碼方式進行編碼---也就是說，具有索引的量子位 `0` 會在二進位整數表示的最左邊 (最高) 位中進行編碼。
這會與 [ket 標記法](xref:microsoft.quantum.concepts.dirac)一致，因為在 state $ \ket $ 中的三個量子位暫存器 {100} 會對應至處於狀態 $ \ket $ 的 $q _0 $ {1} ，而 $q _1 $ 和 $q _2 $ 同時處於狀態 $ \ket {0} $。
近似值參數 $a $ 會決定 $Z $ 旋轉的剪除層級，亦即 $a \in [0 ... n] $。
在此情況下，所有 $Z $-旋轉 $ 2 \ pi/2 ^ k $，其中 $k > $ 會從 QFT 電路中移除。
已知 $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3。 其中一個可以系結 $ \\ | \operatorname{QFT}-\operatorname{AQFT} \\ | < \epsilon $。
這裡 \\ 的 $ | \cdot \\ | $ 是運算子的標準，在此案例中是 $ ( \Operatorname{qft}-\operatorname{AQFT} ) # A2\OPERATORNAME {QFT}-\operatorname{AQFT} ) ^ \dagger $ 的最大 [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) 的平方根。

## <a name="arithmetic"></a>算術 ##

就像算術在傳統運算中扮演中央角色一樣，在量子運算中也是不可或缺的。  演算法（例如 Shor 的分解演算法、量子模擬方法以及許多 oracular 演算法）都依賴一致的算數運算。  在量子加入電路上進行算術組建的大部分方法。  最簡單的加入程式會 $b $ 取得傳統的輸入，並將值新增至保留整數 $ \ket{a} $ 的量子狀態。   (從數學角度來說，\operatorname{Add} (b) $ 用於傳統輸入 $b $) 具有屬性，

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}。
$ $ 這個基本的「產生器」電路比 incrementer。
您可以透過 $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} 將它轉換成具有兩個量子輸入的整合程式，$ $ 使用 adder 的 $n $ 受控應用程式格式 \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda \_ {a \_ 0} \Left ( \operatorname{Add} (1) \Right) \Lambda \_ {a \_ 1} \left ( \operatorname{Add} (2) \right) \Lambda \_ {a \_ 2} \left ( \operatorname{Add} (4) \right) \cdots \Lambda \_ {a \_ {n-1}} \left ( \operatorname{Add} ( {{n-1-1}} ) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a} $n $ bit 整數的 \end{align} $a $ 和 $b $ 和加法模數 $ 2 ^ n $。  回想一下，表示 $ \Lambda \_ x (A) $ 指的是 $A $ 的任何作業，對該作業的受控制版本進行量子位 $x $ as 控制項。

同樣地，傳統方式控管的乘法 (模組化形式，這對 Shor 的分解演算法而言是不可或缺的，) 可以使用類似的一系列受控制的新增專案來執行： \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda \_ {x \_ 0} \Left ( \operatorname{add} (2 ^ 0 a) \Right) \Lambda \_ {a \_ 1} \left ( \operatorname{add} (2 ^ 1a) \right) \Lambda \_ {a \_ 2} \left ( \operatorname{add} (2 ^ 2 a) \right) \cdots \Lambda \_ {x \_ {n-1}} \left ( \operatorname{add} ( {2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + ax}。
\end{align} 在量子電腦上有一個奧妙，您可能會注意到上述 $ \operatorname{Mult} $ 的定義。  與加法不同的是，此電路的量子版本會將輸入的產品儲存在輔助暫存器中，而不是在輸入暫存器中。  在此範例中，會使用 $b $ 的值來初始化暫存器，但通常會開始將值保留為零。  這在中是必要的，因為一般 $a $ 和 $x $ 沒有乘法反向。  由於所有的量子作業（儲存測量）都是可還原的，因此我們必須保留足夠的資訊，以反轉乘法。  基於這個理由，結果會儲存在不同的陣列中。  在不同的暫存器中儲存無法復原作業的輸出（例如乘法），在 Charlie Bennett 之後稱為「Bennett 技巧」，而且是可復原和量子運算的基本工具。

許多量子線路都已建議新增，而且每個配量會根據量子位 (空間) 和閘道作業數目 (時間) 需要來探索不同的取捨。  我們將在下列兩個具有空間效益的 adder，稱為 Draper 的和 Beauregard 的。

### <a name="draper-adder"></a>Draper ###

Draper 的加入程式是最簡潔的量子 adder 之一，因為它會直接叫用量子屬性來執行加法。  Draper 轉譯器背後的深入解析是，可以使用傅立葉轉換來將階段轉換轉換成位移。  接著，它會套用傅立葉轉換、套用適當的階段移位，然後復原傅立葉轉換，讓您可以執行對應項。  不同于其他許多已建議的 adder，Draper 的完成程式會明確地使用透過量子傅立葉轉換所引進的量子效果。  它沒有自然的傳統對應。  Draper 進行程式的特定步驟如下所示。

假設您有兩個 $n $-bit 量子位暫存器將整數 $a $ 和 $b $，然後所有 $a $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (aj) /2 ^ n} \ket{j}。
$ $ 如果我們定義 $ $ \ket{\phi \_ k (a) } = \frac {1} {\sqrt {2} } \left ( \ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \right) ，$ $ 則在某些代數之後，您可以看到 $ $ \operatorname{QFT}\ket{a} = \ket{\phi \_ 1 () } \otimes \cdots \otimes \ket{\phi \_ n () }。
$ $ 執行完成程式的路徑，在觀察到輸入的總和可以寫成 $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\phi \_ 1 (a + b) } \otimes \cdots \otimes \ket{\phi \_ n (a + b) } 之後，就會變得很清楚。
$ $ $B $ 和 $a $ 的整數，可以藉由使用 $b $ 的位作為控制項，在分解中的每個量子位上執行控制階段旋轉來加入。

您可以藉由記下任何整數 $j $ 和實數 $x $，$e ^ {i2\pi (x + j) } = e ^ {i2\pi x} $ 來進一步簡化此擴充。  這是因為如果您在圓形中旋轉 $ 360 ^ {\circ} $ 度數 ($ 2 \ pi $ 弧度) ，那麼您就會精確地結束您的開始位置。  $X $ for $e ^ {i2\pi x} $ 的唯一重要部分，因此是 $x $ 的小數部分。  具體而言，如果我們有 $x = y +0 格式的二進位擴充。 x \_ 0x \_ 2 \ ldots x \_ n $ then $e ^ {i2\pi x} = e ^ {i2\pi (0. x \_ 0x \_ 2 \ ldots x \_ {n-1} ) } $，因此 $ $ \ket{\phi \_ k (a + b) } = \frac {1} {\sqrt {2} } \left ( \ket {0} + e ^ {i2\pi [a/2 ^ k +0。 b \_ K\ldots b \_ 1]} \ket {1} \right) . $ $ 這表示如果我們藉由在 $ \ket{a} $ 的傅立葉轉換展開時遞增每個 tensor 因數來執行加法，則會縮小 $k $ 減少時的旋轉量。  這可大幅減少在增加項中所需的量子閘道數目。  我們以 $ \operatorname{QFT} ^ {-1} \left ( \Phi \\ \! \operatorname{ADD}\right) \operatorname{QFT} $ 表示以傅立葉轉換、階段加法以及反向傅立葉轉換步驟組成 Draper 的加入程式。 使用這種簡化來執行整個程式的量子電路，如下所示。

![顯示為電路圖的 Draper 顯示](~/media/draper.svg)

線路中的每個受控制 $e ^ {i2 \ pi/k} $ 閘道都是指受控制階段的閘道。  這類閘道的屬性是在其作用的量子位對上，$ \ket {00} \mapsto \ket {00} $，$ \ket {11} \mapsto e ^ {i2 \ pi/k} \ ket {11} $。  這種線路可讓我們使用除了儲存輸入和輸出所需的其他量子位之外，執行加法。

### <a name="beauregard-adder"></a>Beauregard ###

Beauregard 的加入器是一種量子模組化的寫入器，它會使用 Draper 的加入器來執行加法模數 $N $ 表示 $N $ 的任意值正整數。  量子模組化 adder （例如 Beauregard 的加入器）的重要性，與 Shor 演算法內的模組化乘冪步驟中的使用範圍很大，以進行分解。  量子模組化的加入程式具有下列適用于量子輸入 $ \ket{b} $ 和傳統輸入 $a $，其中 $a $ 和 $b $ 會承諾為整數 mod $N $，這表示它們是在間隔 $ [0，\ldots，N-1] $ 中。

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{cases} \ket{b + a}、& b + a < N \\ \\ \ket{b + a-N}、& (b + a) \ge N \end{cases}。
$$

Beauregard 的新增項會使用 Draper 的新增項，或更明確的 $ \phi \\ \! \operatorname{ADD} $，在階段中新增 $a $ 和 $b $。  然後，它會使用相同的作業來識別 $a + b <N $，方法是在 $a + b-N<$0 時減去 $N $ 和測試。  電路會將這項資訊儲存在附屬量子位中，然後在 $a + b<N $ 時新增 $N $ back。  然後 uncomputing 此附屬位來結束 (此步驟是為了確保 ancilla 可以在呼叫加入器) 之後解除配置。  Beauregard 進行程式對應程式的線路如下所示。

![顯示為電路圖的 Beauregard 顯示](~/media/beau.svg)

在這裡，閘道 $ \Phi \\ \! \operatorname{ADD} $ 採用與 $ \Phi \operatorname{ADD} $ 相同的形式 \\ \! ，但在此內容中，輸入是傳統的，而不是量子。  如此一來，就可以將 $ \Phi \Operatorname{ADD} $ 中的受控制階段 \\ \! 取代為階段閘道，然後再編譯成較少的作業，以減少加入程式所需的量子位和閘道數目。

如需詳細資訊，請參閱 [Roetteler、Beth](http://doi.org/10.1007/s00200-008-0072-2 ) 和 [d. Coppersmith](https://arxiv.org/abs/quant-ph/0201067)。

### <a name="quantum-phase-estimation"></a>量子相位估算法 ###

量子傅立葉轉換的一個特別重要的應用，是瞭解單一運算子的特徵值，這是一個稱為 *階段估計* 的問題。
請考慮使用單一 $U $ 和 state $ \ket{\phi} $，讓 $ \ket{\phi} $ 是 $U $ 的 eigenstate，其中包含未知 eigenvalue $ \phi $、\begin{equation} U\ket {\ phi} = \phi\ket{\phi}。
\end{equation}，如果我們只能存取 $U $ 做為 oracle，則可以藉由使用套用至受控制作業目標的 $Z $ 旋轉，來學習階段 $ \phi $，並將其傳播回到控制項上。

假設 $V $ 是 $U $ 的受控應用程式，例如 \begin{align} V ( \ket {0} \otimes \ket{\phi} ) & = \ket \otimes \ket{\phi} {0} \\ \\ \textrm{and} V ( \ket {1} \otimes \ket{\phi} ) & = e ^ {i \phi} \ket {1} \otimes \ket{\phi}。
然後，\end{align} 由線性 \begin{align} V ( \ket{+} \otimes \ket{\phi} ) & = \frac{ ( \ket {0} \otimes \ket{\phi} ) + e ^ {i \phi} ( \ket {1} \otimes \ket{\phi} ) } {\sqrt {2} }。
\end{align} 我們可以收集詞彙，以找出 \begin{align} V ( \ket{+} \otimes \ket{\phi} ) & = \frac{\ket {0} + e ^ {i \phi} \ket {1} } {\sqrt {2} } \otimes \ket{\phi} \\ \\ & = (R_1 ( \phi) \ket{+} ) \otimes \ket{\phi}，\end{align}，其中 $R _1 $ 是作業所套用的單一 <xref:Microsoft.Quantum.Intrinsic.R1> 。
以不同的方式放置，套用 $V $ 的效果與套用具有未知角度的 $R _1 $ 相同，即使我們只能存取 $V $ 做為 oracle。
因此，在本討論的其餘部分，我們將討論以 $R _1 ( \phi) $ （我們使用所謂的 *階段 kickback* 來實行）進行的階段估計。

因為控制和目標暫存器會在此程式之後繼續 untangled，所以我們可以重複使用 $ \ket{\phi} $ 做為受控制應用程式的 $U ^ $2 的目標，以準備第二個控制項量子位處於狀態 $R _1 (2 \phi) \ket{+} $。
以這種方式繼續進行，我們可以取得表單 \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left ( \ket {0} + \exp (i 2 ^ {j} \phi) \ket {1} \right) \\ \\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1-1} \exp (i \phi k) \ket{k} \end{align}，其中 $n $ 是我們需要的精確度位數，而且，我們使用 $ {} \propto {} $ 表示我們已抑制 $1/\sqrt{2 ^ n} $ 的正規化係數。

如果我們假設整數 $p $ 的 $ \phi = 2 \pi p/2 ^ k $，則會將此視為 $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots .. p_n} $，其中 $p _j $ 是 $j ^ {\textrm{th}} $ bit $2 \pi \phi $。
套用量子傅立葉轉換的 adjoint 之後，我們就會取得編碼為量子狀態之階段的二進位標記法。

在中 Q# ，這是由作業所執行，此作業會 <xref:Microsoft.Quantum.Characterization.QuantumPhaseEstimation> 採用 <xref:Microsoft.Quantum.Oracles.DiscreteOracle> $U ^ m $ 的實作為 $m $ 的正整數函數來執行應用程式。
