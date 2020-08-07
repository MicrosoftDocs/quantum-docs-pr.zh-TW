---
標題： Dirac 標記法描述：瞭解如何使用 Dirac 標記法來表示配量狀態，以及模擬量子作業。
author： QuantumWriter uid： dirac ms-chap。作者： nawiebe@microsoft.com ms. 日期：12/11/2017 毫秒。主題：發行項不存在：
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

雖然資料行向量標記法線上性代數中是普遍的，但在處理多個 qubits 時，通常會難以進行量子計算。  例如，當我們將定義 $ \psi $ 為向量時，不會明確地明確指出 $ \psi $ 是資料列或資料行向量。  因此，如果和是向量，則即使已定義，也會 $ \phi $ $ \psi $ 同樣不清楚， $ \phi \psi $ 因為在 $ \phi $ 內容中，和的形狀 $ \psi $ 可能不清楚。  除了向量形狀的多義性外，使用稍早引進的線性代數標記法來表示偶數的簡單向量也非常繁瑣。 例如，如果我們想要描述 $ $ qubit 狀態，其中每個 qubit 都接受值0， $ $ 則我們會正式地將狀態表示為 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 。 $$  

當然，評估此張量產品並不實用，因為向量位於指數大的空間，因此此標記法實際上是可使用先前的標記法提供之狀態的最佳描述。  

[*Dirac 標記法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)會藉由呈現新的語言，以符合精確的量子機制需求，來解決這些問題。  基於這個理由，我們建議讀者不要查看本節中的範例，做為如何描述配量狀態的一項嚴謹的處方，而是鼓勵讀者將這些內容視為可用於簡化量子概念的建議。

Dirac 標記法中有兩種類型的向量： *bra*向量和*ket*向量，因此名為，因為當放在一起時，它們會形成*braket*或內部產品。  如果 $ \psi $ 是資料行向量，我們可以使用 Dirac 標記法將它寫成 $ \ket { \psi } $ ，其中 $ \ket { \cdot } $ 表示它是單位資料行向量，亦即*ket*向量。  同樣地，資料列向量 $ \psi ^ \dagger $ 也會表示為 $ \bra { \psi } $ 。 換句話說，是藉 $ \psi ^ \dagger $ 由將進入取向的複雜 conjugation 套用至的調換元素來取得 $ \psi $ 。 Bra-ket 標記法直接表示 $ \braket { \psi | \psi } $ 是向量的內部乘積 $ \psi $ 本身，也就是定義 $ 1 $ 。  

更常見的情況是，如果 $ \psi $ 和 $ \phi $ 是配量狀態向量，則其內部產品是 $ \braket { \phi | \psi } $ 指將狀態測量為 $ \ket { \psi } $ $ \ket { \phi } $ $ | \braket { \phi | \psi } | ^ 2 $ 的機率。  

下列慣例是用來描述將零值和一個 (單一 qubit 計算基礎狀態的量子狀態) ：

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ，\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } 。
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>範例：代表具有 Dirac 標記法的 Hadamard 作業

下列標記法通常用來描述將 Hadamard 閘道套用至 $ \ket { 0 } $ 和 $ \ket { 1 } $ (（對應至 $ $ $ $ Bloch) 球體上 + x 和-x 方向的單位向量）所產生的狀態：

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ，\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } 。
$$

您也可以使用 Dirac 標記法，將這些狀態擴充為 $ \ket { 0 } $ 和 $ \ket { 1 } $ 的總和：

$$
\ket{+}= \frac{1 } { \sqrt { 2 } } (\ket { 0 }  +  \ket { 1 }) ， \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } (\ket { 0 }  -  \ket { 1 }) 。
$$

### <a name="computational-basis-vectors"></a>計算基礎向量
這會示範為什麼這些狀態通常稱為「*計算基礎*」：每個配量狀態一律會以計算基礎向量的總和表示，而這類總和則可以使用 Dirac 標記法輕鬆表示。  相反地，這也是狀態， $ \ket { + } $ 而且 $ \ket { - } $ 也會構成量子狀態的基礎。  您可以從下列事實看出

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) ， \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  -  \ket { - }) 。
$$

做為 Dirac 標記法的範例，請考慮使用 braket $ \braket { 0 | 1 } $ ，這是介於 $ 0 $ 和 $ 1 之間的內部產品 $ 。  它可以撰寫成 

$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = 0。$$

這表示 $ \ket { 0 } $ 和 $ \ket { 1 } $ 是正向向量，表示 $ \braket { 0 | 1 } = \braket { 1 | 0 } = 0 $ 。  此外，根據定義 $ \braket { 0 | 0 1 1 1 } = \braket { | } = $ ，這表示兩個計算基礎向量也可以稱為*orthonormal*。
這些 orthonormal 屬性在下列範例中將會很有用。 如果我們有狀態 $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0， } $ 則因為 $ \braket { 1 | 0 } = 0 $ ，測量1的 $ 機率 $ 是  

$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } 。$$ 

### <a name="tensor-product-notation"></a>張量產品標記法
Dirac 標記法也會在其中包含隱含的張量產品結構。  這一點很重要，因為在量子運算中，兩個不相關的量子暫存器所描述的狀態向量是兩個狀態向量的張量產品。  如果您想要說明配量計算，就很重要的是，描述張量產品結構或缺乏的架構。  張量產品結構意指，我們可以撰寫 $ \psi \otimes \phi $ 任何兩個配量狀態向量 $ \phi $ ，而且 $ \psi $ $ \ket { \psi } \ket { \phi } $ 有時會明確寫入為 $ \ket { \psi } \otimes \ket { \phi } $ ，不過 $ \otimes $ 在向量之間寫入的慣例是不必要的。  例如，具有兩個 qubits 初始化為零狀態的狀態會由指定

$$
\begin{bmatrix}1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } 0 0 0 0 0。
$$

同樣地， $ \ket { integer p 的狀態 p } $ $ $ 代表以二進位標記法編碼的量子狀態，也就是整數 $ p $ 。  例如，如果我們想要 $ 使用不帶正負號的二進位編碼來表示數位5， $ 我們可以同樣地將其表示為

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } 。
$$

在此標記法中 $ \ket { } $ ，0不需要參考單一 qubit 狀態，而是*qubit*暫存器，儲存二進位編碼為 $ 0 $ 。  這兩種標記法之間的差異通常會從內容中清楚明瞭。  此慣例適用于簡化第一個範例，可以透過下列任何方式撰寫：

$$
\begin{bmatrix}1 0 1 0 0 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } 。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>範例：描述具有 Dirac 標記法的重迭
如需如何使用 Dirac 標記法來描述配量狀態的另一個範例，請考慮下列寫入配量狀態的相同方式，這是在每個長度為 n 的可能位字串上相等的重迭 $$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } 。
$$

在這裡，您可能會想知道總和為何會從 $ 0 $ 到 $ 2 ^ { n } -1 $ 的 $ n $ 位。  首先要注意的是，有 $ 2 ^ { n 個 } $ 不同的設定 $ $ 可接受 n 位。  您可以看到，其中一個位可以接受2個 $ $ 值，但兩個位可以接受 $ 4 個值等等 $ 。 一般來說，這表示有 $ 2 ^ n 個不同的 $ 可能位字串，但在其中任何一個中編碼的最大值 $ \cdots 為 1 1 = 2 ^ n-1 $ ，因此是總和的上限。
在此範例中，我們不會將 $ \ket { + } ^ { \otimes n 用於 } = \ket { + } $ 類似 $ \ket { 0 } ^ { \otimes n } = \ket { 0， } $ 因為此標記慣例通常會保留給每個 qubit 初始化為零的計算基礎狀態。  雖然這種慣例在此情況下很合理，但不會在「量子計算」文獻中採用。

### <a name="expressing-linearity-with-dirac-notation"></a>使用 Dirac 標記法來表示線性
Dirac 標記法還有另一項不錯的功能，就是它是線性的事實。  如果我們想要撰寫四個量子狀態向量， 

$$ (\alpha \ket { \psi }  + \beta \ket { \phi }) \otimes (\gamma \ket { \chi }  +  \delta \ket { \omega }) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } 。$$

也就是說，您可以在 Dirac 標記法中散發張量產品標記法，讓州向量之間的張量產品看起來就像一般乘法。

Bra 向量遵循類似的慣例來 ket 向量。  例如，向量等同于 $ \bra { \psi } \bra { \phi } $ $ \psi ^ \dagger \otimes \phi ^ \dagger = \psi \otimes \phi) ^ (\dagger $ 的狀態向量。 如果 ket 向量 $ \ket { \psi } $ 為 $ \alpha \ket { 0 1，則 }  +  \beta \ket { } $ 向量的 bra 向量版本會 $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ * ) $ 。

例如，假設我們想要計算測量狀態 $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 5 0 的機率，方法是使用配量 } { 程式來測量狀態 } \ket { } $ 為 $ \ket { + } $ 或 $ \ket { - } $ 。 然後，裝置會輸出狀態為的機率 $ \ket { - } $ 為 

$$|\braket{- |\psi}|^ 2 = \left | \frac { 1 } { \sqrt { 2 } } (\bra { 0 }  -  \bra { 1 }) # B2 \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 }) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } 。$$

負號出現在機率計算中的事實，是一種量子干擾的表現，這是配量運算透過傳統運算獲得優勢的機制之一。

## <a name="ketbra-or-outer-product"></a>ketbra 或外部產品
在 Dirac 標記法中，值得討論的最後一個專案是*ketbra*或外部產品。  外部產品在 Dirac 標記法中是以形式呈現 $ \ket { \psi } \bra { \phi } $ ，有時也稱為 ketbras，因為 bras 和 kets 發生的順序與 brakets 相反。  外部產品是透過矩陣乘法定義，做 $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ 為量子狀態向量 $ \psi $ 和 $ \phi $ 。  最簡單且可說是此標記法的最常見範例，就是

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\\\ 0 & 0 \end{bmatrix} \qquad \ket { 1 } \bra { 1 } = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \begin{bmatrix} 0 & 1 \end{bmatrix} = \begin{bmatrix} 0 & \\\\ & \end{bmatrix} 0 0 1。
$$

Ketbras 通常稱為投影機，因為它們會將配量狀態投射到固定值上。  因為這些作業不是單一 (，甚至不會保留向量) 的標準，所以量子電腦無法以決定性的方式套用投影機。  不過，投影機會執行一項美觀的作業來描述測量在配量狀態上的動作。  例如，如果我們將某個狀態測量 $ \ket { \psi } $ 為0，則 $ 產生的轉換會 $ 因為測量而導致狀態體驗為

  $$\ket{\psi}\right \frac 箭 { 號 (\ket { 0 } \bra { 0 }) \ket { \psi } } { | \braket { 0 0 | \psi } | } = \ket { } ，$$

如果您要測量狀態，並將其尋找為0，則會預期為一 $ \ket { } $ 。  再次重申，這類投影機無法以決定性的方式套用到量子電腦上的狀態。  相反地，它們最適合用來隨機套用，結果 $ \ket { 0 會 } $ 出現一些固定機率。  這類測量的機率可能會以狀態中的「量子投影機」預期值來寫入

$$
\bra{\psi} (\ket { 0 } \bra { 0 }) \ket { \psi } = | \braket { \psi | 0 } | ^ 2，$$

其中說明投影機只是提供一種新的方式來表達測量流程。

如果改為考慮將多 qubit 狀態的第一個 qubit 測量為1， $ $ 則我們也可以使用投影機和 Dirac 標記法來方便地描述此程式：

$$
P (\text { 第一個 qubit = 1 }) = \bra { \psi } \left (\ket { 1 } \bra { } \otimes \boldone ^ { \otimes 個 n-1 個 } \right) \ket { \psi } 。
$$

在這裡，您可以用 Dirac 標記法輕鬆地將身分識別矩陣寫成

$$
\boldone= \ket{0 } \bra { 0 1 1 1 } + \ket { } \bra { } = \begin{bmatrix} & 0 \\\\ 0 & 1 \end{bmatrix} 。
$$

在有兩個 qubits 的情況下，投影機可以擴充為 

$$
\ket{1 1 1 } \bra { } \otimes \id = \ket { } \bra { 1 } \otimes (\ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 }) = \ket { 10 } \bra { 10 }  +  \ket { 11 11 } \bra { } 。
$$

然後，我們可以看到這與使用資料行向量標記法之 multiqubit 狀態的度量 likelihoods 討論一致：

$$
P (\text { first qubit = 1 }) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e 11 \_ { } ^ \dagger) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2，$$

其中符合多 qubit 的測量討論。  不過，此結果對多 qubit 案例的一般化，使用 Dirac 標記法比資料行向量標記法更直接表達，而且完全等同于先前的處理。

## <a name="density-operators"></a>密度運算子

另一個使用 Dirac 標記法來表示的有用運算子是*密度運算子*，有時也稱為「*狀態運算子*」。
量子狀態向量的密度運算子採用 $ \rho 格式 = \ket { \psi } \bra { \psi } $ 。
將狀態表示為矩陣（而不是向量）的這個概念通常很方便，因為它提供便利的方式來表示機率計算，也允許一個描述統計不確定性以及相同形式內的量子不確定性。
一般的量子狀態運算子（而不是向量）在量子運算的某些區域中很普遍，但不一定要瞭解此欄位的基本概念。
對於感興趣的讀者，建議您閱讀中所提供的其中一個參考書籍，[以取得詳細資訊](xref:microsoft.quantum.more-information)。

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q#閘道序列相當於量子狀態
關於量子標記法和程式設計語言的最後一點 Q# ：我們在本檔的萌芽中提到，配量狀態是量子運算中資訊的基本物件。  這可能會令人驚訝，因為沒有配 Q# 量狀態的概念。  相反地，所有狀態只會由用來準備它們的作業來描述。  先前的範例是這個的絕佳說明。  我們可以將結果表示為 $ H ^ { \otimes n } \ket { 0 } $ ，而不是在暫存器中的每個配量位字串上表示統一的重迭。  這種狀態的指數較短描述不僅具有我們可以傳統方式其相關原因的優點，還會簡明扼要地定義透過軟體堆疊傳播以執行演算法所需的作業。  基於這個理由，的 Q# 設計是用來發出閘道序列，而不是配量狀態; 不過，理論層級的兩個觀點是相等的。
