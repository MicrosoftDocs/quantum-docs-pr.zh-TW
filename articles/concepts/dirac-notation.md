---
標題： Dirac 標記法描述：瞭解如何使用 Dirac 標記法來表示量子狀態，以及模擬量子作業。
作者： QuantumWriter uid： dirac ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：非 loc 文章：
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="dirac-notation"></a>Dirac 標記法

雖然資料行向量標記法線上性代數中是普遍的，但在處理多個量子位時，量子運算通常很繁瑣。  例如，當我們定義 $ \psi $ 為向量時，不會明確地明確指出 $ \psi $ 是資料列或資料行向量。  因此 $ \phi $ ，如果和 $ \psi $ 是向量，則即使定義時，也會不清楚， $ \phi \psi $ 因為在 $ \phi $ 內容中的圖案 $ \psi $ 可能不清楚。  除了向量圖形的混淆之外，使用先前引進的線性代數標記法來表示簡單的向量也相當繁瑣。 例如，如果我們想要描述 $ n $ 個量子位狀態，其中每個量子位都採用0值， $ $ 則我們會正式將狀態表示為 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 。 $$  

當然，評估這個 tensor 產品並不實用，因為向量位於以指數方式表示的大型空間中，因此這個標記法實際上是可使用先前的標記法來指定之狀態的最佳描述。  

[*Dirac 標記法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) 藉由呈現新的語言，以符合量子機制的精確需求來解決這些問題。  基於這個理由，我們建議讀者不要將本節中的範例視為如何描述量子狀態的固定處方，而是建議讀者將這些範例視為可以用來精確表達量子概念的建議。

Dirac 標記法中有兩種類型的向量： *bra* 向量和 *ket* 向量，因此命名方式是將它們組成 *braket* 或內部產品。  如果 $ \psi $ 是資料行向量，則可以使用 Dirac 標記法來撰寫它 $ \ket { \psi } $ ，其中 $ \ket { \cdot } $ 表示它是單位資料行向量，亦即*ket*向量。  同樣地，資料列向量 $ \psi ^ \dagger $ 會表示為 $ \bra { \psi } $ 。 換句話說，是藉 $ \psi ^ \dagger $ 由將進入層級複雜結合套用至的 [重設] 的元素來取得 $ \psi $ 。 Bra-ket 標記法直接表示 $ \braket { \psi | \psi } $ 是向量的內部乘積，也 $ \psi $ 就是定義 $ 1 $ 。  

一般來說，如果 $ \psi $ 和 $ \phi $ 是量子狀態向量，其內部產品即 $ \braket { \phi | \psi } $ 表示測量狀態的機率 $ \ket { \psi } $ $ \ket { \phi } $ 為 $ | \braket { \phi | \psi } | ^ 2 $ 。  

下列慣例可用來描述將零值和一個 (單一量子位計算基礎狀態) 編碼的量子狀態：

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } 、\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } 。
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>範例：使用 Dirac 標記法來表示 Hadamard 作業

下列標記法通常用來描述將 Hadamard 閘道套用至 $ \ket { 0 } $ 和 1 (的狀態， $ \ket { } $ 而這會對應至 $ $ $ $ 布洛赫球體) 上 + x 和 x 方向的單位向量：

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ，\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } 。
$$

您也可以使用 Dirac 標記法將這些狀態擴充為 $ \ket { 0 } $ 和 $ \ket { 1 } $ 的總和：

$$
\ket{+}= \frac{1 } { \sqrt { 2 } } (\ket { 0 }  +  \ket { 1 }) ， \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } (\ket { 0 }  -  \ket { 1 }) 。
$$

### <a name="computational-basis-vectors"></a>計算基礎向量
這會示範為何這些狀態通常稱為 *計算基礎*：每個量子狀態一律會表示為計算基礎向量的總和，而這類總和可使用 Dirac 標記法輕鬆表示。  相反地，狀態也會 $ \ket { + } $ $ \ket { - } $ 形成量子狀態的基礎。  您可以從下列事實看出：

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) ， \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  -  \ket { - }) 。
$$

作為 Dirac 標記法的範例，請考慮使用 braket $ \braket { 0 | 1 } $ ，這是介於 $ 0 $ 和1之間的內部乘積 $ $ 。  它可以撰寫為 

$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 0 \end{bmatrix} \begin{bmatrix} \\\\ 1 \end{bmatrix} = 0。$$

這表示 $ \ket { 0 } $ 和 $ \ket { 1 } $ 是直角向量，表示 $ \braket { 0 | 1 } = \braket { 1 | 0 } = 0 $ 。  此外，根據定義 $ \braket { 0 | 0 1 1 1 } = \braket { | } = $ ，這表示這兩個計算基礎向量也可以稱為*orthonormal*。
這些 orthonormal 屬性在下列範例中將會很有用。 如果我們有狀態 $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0， } $ 則因為 $ \braket { 1 | 0 } = 0 $ ，測量 $ 1 $ 的機率為  

$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } 。$$ 

### <a name="tensor-product-notation"></a>Tensor 產品標記法
Dirac 標記法也包含其中的隱含 tensor product 結構。  這點很重要，因為在量子運算中，兩個不相關的量子暫存器所描述的狀態向量就是兩個狀態向量的 tensor 產品。  如果您想要說明量子計算，很重要的一點是，很重要的是，tensor 產品結構或缺乏。  Tensor 產品結構暗示我們可以撰寫 $ \psi \otimes \phi $ 任何兩個量子狀態向量，也可以 $ \phi $ $ \psi $ 像 $ \ket { \psi } \ket { \phi } $ 明確撰寫一樣， $ \ket { \psi } \otimes \ket { \phi } $ 但 $ \otimes $ 不需要在向量之間撰寫的慣例。  例如，兩個量子位初始化為零狀態的狀態是由

$$
\begin{bmatrix}1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } 0 0 0 0 0。
$$

同樣地， $ \ket { 整數 p 的狀態 p } $ $ $ 表示以二進位標記法來編碼整數 p 的量子 $ 狀態 $ 。  例如，如果我們想要 $ $ 使用不帶正負號的二進位編碼來表示數位5，我們可以同樣地將它表示為

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } 。
$$

在這個標記法中 $ \ket { } $ ，0不需要參考單一量子位狀態，而是*qubit register*儲存二進位編碼為0的量子位 $ $ 暫存器。  這兩種標記法之間的差異通常會從內容中清楚明瞭。  這個慣例有助於簡化第一個可利用下列方式撰寫的範例：

$$
\begin{bmatrix}1 0 1 0 0 0 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } 。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>範例：使用 Dirac 標記法描述迭加
如需如何使用 Dirac 標記法來描述量子狀態的另一個範例，請考慮使用下列對等方式來寫入量子狀態，此狀態是對每個長度為 n 的可能位字串的相等迭加 $$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1-1 } \ket { j } = \ket { + } ^ { \otimes n } 。
$$

在這裡，您可能會想知道為什麼 n 位的總和是從 $ 0 $ 到 $ 2 ^ { n-1 } $ $ $ 。  首先要注意的是，有 $ 2 ^ { n 個 } $ 不同的設定， $ n $ 位可以採用。  您可以看到其中一個位可以採用 $ 2 $ 個值，但兩個位可能需要 $ 4 個 $ 值，依此類推。 一般情況下，這表示有 $ 2 ^ n 個 $ 不同的可能位字串，但最大的值是以 $ 1 \cdots 1 = 2 ^ n-1 的其中任何一種， $ 因此它是總和的上限。
請注意，在此範例中，我們不會使用 $ \ket { + } ^ { \otimes n } = \ket { + } $ 來表示為 $ \ket { 0 } ^ { \otimes n } = \ket { 0， } $ 因為此標記慣例通常會保留給計算基礎狀態，且每個量子位都會初始化為零。  雖然這種慣例在這種情況下是合理的，但它並不是在量子運算文獻中採用。

### <a name="expressing-linearity-with-dirac-notation"></a>使用 Dirac 標記法來表示線性
Dirac 標記法的另一項不錯的功能，就是它是線性的。  如果我們想要撰寫任何四個量子狀態向量， 

$$ (\alpha \ket { \psi }  + \beta \ket { \phi }) \otimes (\gamma \ket { \chi }  +  \delta \ket { \omega }) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } 。$$

也就是說，您可以在 Dirac 標記法中散發 tensor 產品標記法，讓州向量之間的 tensor 產品最後看似一般的乘法。

Bra 向量遵循類似的慣例來 ket 向量。  例如，向量 $ \bra { \psi } \bra { \phi } $ 等同于狀態向量 $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ 。 如果 ket 向量 $ \ket { \psi } $ 為 $ \alpha \ket { 0 1，則 }  +  \beta \ket { } $ 向量的 bra 向量版本是 $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ * ) $ 。

例如，假設我們想要使用量副程式來計算測量狀態 $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 5 0 的機率， } { } \ket { } $ 以將狀態測量為 $ \ket { + } $ 或 $ \ket { - } $ 。 然後，裝置會輸出狀態的機率 $ \ket { - } $ 為 

$$|\braket{- |\psi}|^ 2 = \left | \frac { 1 } { \sqrt { 2 } } (\bra { 0 }  -  \bra { 1 }) # B2 \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 }) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } 。$$

這種情況下，負號會出現在機率的計算中，是量子干擾的結果，這是量子運算獲得優於傳統運算之優勢的機制之一。

## <a name="ketbra-or-outer-product"></a>ketbra 或外部產品
Dirac 標記法中的最後一個值得討論的專案是 *ketbra* 或外部產品。  外部產品會在 Dirac 標記法中表示為 $ \ket { \psi } \bra { \phi } $ ，有時也稱為 ketbras，因為 bras 和 kets 會以與 brakets 相反的順序來進行。  外部產品是透過矩陣乘法來定義，做 $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ 為量子狀態向量 $ \psi $ 和 $ \phi $ 。  最簡單且最常見的是此標記法的範例為

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 0 0 \\\\ & \end{bmatrix} \qquad \ket { 1 } \bra { 1 } = \begin{bmatrix} 0 \\\\ 1 0 \end{bmatrix} \begin{bmatrix} & 1 \end{bmatrix} = \begin{bmatrix} 0 & \\\\ & \end{bmatrix} 0 0 0 1。
$$

Ketbras 通常稱為投影機，因為它們會將量子狀態投射到固定值。  因為這些作業並不是單一 (，也不會保留向量) 的標準，所以量子電腦無法以決定性的方式套用投影機也不會驚訝。  不過，投影機會以美觀的工作來描述測量在量子狀態上的動作。  例如，如果我們將狀態測量 $ \ket { \psi } $ 為0， $ 則 $ 產生的轉換會因為測量結果而發生狀態的結果

  $$\ket{\psi}\right \frac 箭 { 號 (\ket { 0 } \bra { 0 }) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } 、$$

因為您需要測量狀態並將其視為 $ \ket { 0 } $ 。  再次重申，這類投影機無法以決定性的方式套用到量子電腦上的狀態。  相反地，它們可以用隨機的方式套用，結果 $ \ket { 0 會 } $ 出現一些固定機率。  這類測量結果的機率可以寫成州量子投影機的預期值

$$
\bra{\psi} (\ket { 0 } \bra { 0 }) \ket { \psi } = | \braket { \psi | 0 } | ^ 2，$$

其中說明投影機只是提供一種新方法來表示測量流程。

相反地，我們會考慮將多量子位狀態的第一個量子位測量為1，如此一來， $ $ 我們也可以使用投影機和 Dirac 標記法方便地描述此程式：

$$
P (\text { 第一個量子位 = 1 }) = \bra { \psi } \left (\ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n 1 } \right) \ket { \psi } 。
$$

在這裡，識別矩陣可以用 Dirac 標記法的形式方便寫入

$$
\boldone= \ket{0 } \bra { 0 } + \ket { 1 1 } \bra { } = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} 。
$$

如果有兩個量子位，則可以將投影機擴充為 

$$
\ket{1 1 1 1 } \bra { } \otimes \id = \ket { } \bra { } \otimes (\ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 }) = \ket { 10 } \bra { 10 }  +  \ket { 11 11 } \bra { 11 } 。
$$

接著，我們可以看到這與使用資料行向量標記法之 multiqubit 狀態的度量 likelihoods 相關討論一致：

$$
P (\text { first 量子位 = 1 }) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2$$

符合多量子位測量的討論。  不過，在多量子位的情況下，此結果的一般化會稍微比使用 Dirac 標記法來表示，而非資料行向量標記法，而且完全等於先前的處理方式。

## <a name="density-operators"></a>密度運算子

另一個用來表示使用 Dirac 標記法的實用運算子是 *密度運算子*，有時也稱為 *州運算子*。
量子狀態向量的密度運算子採用 $ \rho 形式 = \ket { \psi } \bra { \psi } $ 。
以矩陣（而非向量）表示狀態的這個概念通常很方便，因為它提供了一個便利的方式來表示機率計算，同時也可讓您在相同的形式中描述統計的不確定性以及量子不確定性。
一般量子狀態運算子（而不是向量）在量子運算的某些區域中很普遍，但不需要瞭解此欄位的基本概念。
針對感興趣的讀者，建議您閱讀中提供的其中一個參考書， [以取得詳細資訊](xref:microsoft.quantum.more-information)。

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q# 等同于量子狀態的閘道序列
最後值得一提的一點是量子標記法和程式 Q# 設計語言：在本文的驗證中，我們提到量子狀態是量子運算中資訊的基礎物件。  這可能會令人驚訝，因為沒有 Q# 量子狀態的概念。  相反地，所有狀態只會由用來準備這些狀態的作業描述。  先前的範例是這個的絕佳圖解。  我們可以將結果表示為 $ H ^ { \otimes n } \ket { 0 } $ ，而不是對暫存器中的每個量子位字串表示統一迭加。  以指數方式縮短的狀態原因不但能讓我們傳統方式原因，還可以精確地定義透過軟體堆疊傳播以實行演算法所需的作業。  基於這個理由， Q# 設計用來發出閘道順序，而不是量子狀態; 不過，在理論層級上，這兩個觀點是相等的。
