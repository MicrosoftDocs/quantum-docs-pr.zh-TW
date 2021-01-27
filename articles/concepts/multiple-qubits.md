---
標題：多個量子位描述：瞭解如何在兩個或多個量子位上執行作業。
作者： bradben uid：量子位 ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：概念非 loc：
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

# <a name="multiple-qubits"></a>多個量子位

雖然單一量子位的閘道具有一些可直覺性的功能，例如在指定時間處於一個以上狀態的能力，但如果在量子電腦中只有一部量子位的閘道，則會有一個裝置具有運算能力，即使計算機只允許一個傳統的超級電腦。
當我們增加量子位數目時，量子運算的真正威力就變得很明顯。
這種電源有一部分，因為量子狀態向量的向量空間維度會以量子位的數目以指數方式成長。
這表示，雖然單一量子位可以完整模型化，但是模擬50量子位的量子計算可能會推送現有超級電腦的限制。
只有一個額外的量子位增加計算的大小會使儲存狀態所需的記憶體 *加倍* ，而且大約會將計算時間 *加倍* 。
這種快速的運算能力，就是為什麼具有相對較少量子位的量子電腦，可能會超越某些計算工作最強大的超級電腦。

為什麼量子狀態向量的指數成長為何？  本節的目標是要探討用來在單一量子位狀態下建立多量子位狀態的規則，以及討論我們必須在閘道集中包含的閘道作業，以形成通用的多量子位量子電腦。
這些工具絕對需要瞭解程式碼中常用的閘道集 Q# ，也可讓您直覺有關量子效果（例如纏結或干擾）呈現量子運算比傳統運算更強大的原因。

## <a name="representing-two-qubits"></a>表示兩個量子位
一種和雙量子位狀態之間的主要差異，在於兩個量子位的狀態是四個維度而不是兩個維度。
這是因為兩個量子位狀態的計算基礎是由一量子位狀態的 tensor 產品所組成。  例如，我們有 \begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} 、 \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} 、\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 0 0 \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ 1 \\\\ 0 \end{bmatrix} 、 \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 0 0 0 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ 1 \end{bmatrix} 。
\end{align}

很容易看出，n 量子位的量子狀態通常是以 $ $ 維度 2 ^ n 的單位向量（ $ $ 使用此結構）來表示。  向量

$$
\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}
$$

表示在兩個量子位上的量子狀態（如果 $ | \alpha _{ 00 } | ^ 2 + | \alpha_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ 2 + | \alpha_ { 11 } | ^ 2 1） = $ 。 如同單一量子位，多個量子位的量子狀態向量會保存描述系統行為所需的所有資訊。

如果我們提供兩個不同的量子位，其中一個處於狀態， $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ 而第二個量子位處於狀態 $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ ，則對應的雙量子位狀態為    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

其中的作業 $ \otimes $ 稱為 tensor product (或 Kronecker product) 的向量。 請注意，雖然我們可以一律讓兩個單一量子位狀態的 tensor 產品形成雙量子位狀態，但並非所有的雙量子位量子狀態都可以撰寫為兩個單一 tensor 狀態的量子位產品。
例如，沒有任何狀態，因此 $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ 其 tensor 產品是狀態     

$$\psi\otimes\phi = \begin{bmatrix}1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} 。$$ 

這種量子位狀態（無法撰寫為單一量子位狀態的 tensor 產品）稱為「纏結狀態」;這兩個量子位稱為「 [*纏結*](https://en.wikipedia.org/wiki/Quantum_entanglement)」。  鬆散說，因為量子狀態無法被視為單一量子位狀態的 tensor 產品，所以狀態保留的資訊並不會個別局限于量子位的其中一個。  相反地，此資訊會以非本機方式儲存在這兩個狀態之間的相互關聯中。  這種非區域資訊是在傳統運算上的量子運算的主要區別功能之一，也是許多量子通訊協定（包括 [量子遙傳](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) 和 [量子錯誤修正](xref:microsoft.quantum.libraries.error-correction)）不可或缺的功能。

## <a name="measuring-two-qubit-states"></a>測量 Two-Qubit 狀態 ##
測量兩個量子位的狀態非常類似于單一量子位測量。 測量狀態

$$
    \begin{bmatrix}
        \alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\ 
        \alpha_{ 10 } 11 \\\\ \alpha_ {}
    \end{bmatrix}
$$

會 $ 產生 $ 具有機率 $ | \alpha _{ 00 } | ^ 2 $ 、 $ $ 01 $ 、 | 機率 \alpha_ 為 { 01 } | ^ 2、10（機率 $ $ $ 為 $ | \alpha _{ 10 ^ 2） } | $ 和 $ 11 $ （機率 $ 為 | 11 \alpha_ { } | ^ 2 $ ）的00。 已刻意將變數 $ \alpha _{ 00 } 、 \alpha_ { 01 } 、 \alpha _{ 10 } $ 和 $ 11 \alpha_ { } $ 命名為清除此連接。 在測量之後，如果結果為00，則 $ $ 雙量子位系統的量子狀態已折迭，而且現在是

$$
    演講 \equiv
    \begin{bmatrix}
        1 \\\\ 
        0 \\\\ 
        0 \\\\ 
        0 \end{bmatrix} 。
$$

您也可以只測量一個雙量子位量子狀態的量子位。 如果您只測量其中一個量子位，測量的影響會稍微不同，因為整個狀態不會折迭為計算基礎狀態，而是只會折迭為一個子系統。  換句話說，在這種情況下，只會測量一個量子位，而不是全部的子系統。  

若要瞭解這一點，請考慮測量下列狀態的第一個量子位，其形成方式是 $ $ 在兩個量子位上套用 Hadamard 轉換 H （最初設定為 "0" 狀態）： $$
H ^ 2 ( 1 0 1 0) 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1-1-1 1 0 0 0 1 2 1 1 1 1 1 1 2 1 2 1 2 1 1 1 1 1 1 1 { \otimes } \left \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \right = \frac { } { } \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} = \frac { } { } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { } = & \frac { } { \sqrt { 2 } } \begin{bmatrix} 1 2 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} \\\\ \text { 結果 } = 1 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 0 \\\\ \\\\ 1 \\\\ 1 \end{bmatrix} \\\\ \end{cases} 。  
$$
這兩個結果有50% 的機率發生。  這兩個結果的結果為50% 的機率，這是因為 $ $ $ $ 第一個量子位上的初始量子狀態向量在交換0和1的情況下是不變的。

測量第一個或第二個量子位的數學規則很簡單。  如果我們讓 $ e_k $ 成為 $ { 計算基礎向量的 k ^ \Rm } $ ，並讓 $ S $ 成為所有 e_k 的集合，讓有 $ 問題的 $ 量子位採用值1做 $ $ 為 k 的值 $ $ 。  例如，如果我們想要測量第一個量子位，則 $ $ 會包含 $ e_1 \equiv 10 $ 和 $ e_3 \equiv 11 $ 。  同樣地，如果我們對第二個量子位有興趣，則 $ $ 會包含 $ e_2 \equiv 01 $ 和 $ e_3 \equiv 11 $ 。  然後，測量所選量子位為1的機率 $ $ 是針對狀態向量 $\psi$

$$
P (\text { 結果 } = 1) = \sum _ { e_k \text { 的 } } \psi ^ \dagger e_k e_k ^ \dagger \psi 。
$$

> [!NOTE]
> 在這份檔中，我們使用位元組由小到小的格式來標記計算基礎。 以位元組由小到大的格式來說，最不重要的位會最先出現。 例如，以位元組由大到小的格式來表示四個數字，以位001的字串表示。

因為每個量子位量值只能產生 $ 0 $ 或 $ 1，所以 $ 測量0的機率 $ $ 只是 $ 1-P (\text { 結果 } = 1) $ 。  這就是為什麼我們只針對測量1的機率明確提供公式 $ $ 。

這類測量對狀態的動作可以數學表示

$$
\psi\mapsto \frac{\sum_ { e_k \text { 的 } } e_k e_k ^ \dagger \psi } { \sqrt { P (\text { 結果 } = 1) } } 。
$$

謹慎的讀者可能會擔心測量的機率為零時，會發生什麼事。  雖然在這種情況下，結果狀態在技術上是未定義的，但我們永遠不需要擔心這類 eventualities，因為機率為零！


如果我們採用 $ \psi $ 上面所提供的統一狀態向量，並且想要測量第一個量子位， 

$$
P (\text { 測量第一個量子位 } = 1) = (\psi ^ \dagger e_1) # B4 e_1 ^ \dagger \psi) + (\psi ^ \dagger e_3) # B8 e_3 ^ \dagger \psi) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2。
$$

請注意，這只是測量結果10和11所預期的兩個機率的總和 $ ， $ $ 全都是 $ 要測量的量子位。
在我們的範例中，這會評估為

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 & 0 1 1 1 \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ 1 \end{bmatrix} \right | ^ 2 + 1 4 0 0 0 1 1 1 1 \frac { } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } 。
$$

這完全符合我們直覺告訴我們機率的結果。  同樣地，狀態也可以撰寫為

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

同樣地，根據我們的直覺。

## <a name="two-qubit-operations"></a>Two-Qubit 作業
如同在單一量子位案例中，任何單一轉換都是量子位上的有效作業。 一般情況下，n 量子位的單一轉換 $ $ 是大小為 $ $ $ 2 ^ n \times 2 ^ n (的矩陣 U， $ 因此它會在大小為 $ 2 ^ n) 的向量上運作 $ ，例如 $ U ^ { -1 } = U ^ \dagger $ 。
例如，CNOT (控制-不) 閘道是常用的雙量子位閘道，並以下列的單一矩陣表示：

$$
\operatorname{CNOT } = \begin{bmatrix} 1 \ 0 \ 0 \ 0  \\\\  0 \ 1 \ 0 \ 0 \\\\  0 0 \ 0 \ 0 \ 1 \\\\  0 \ 0 \ 1 \ 0 \end{bmatrix}
$$

我們也可以在這兩個量子位上套用單一量子位閘道，形成雙量子位的閘道。 例如，如果我們套用閘道 

$$
\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

及

$$\begin{bmatrix}
e \ f \\\\ g h h \end{bmatrix}
$$

第一個和第二個量子位，這相當於套用 tensor 產品所指定的兩個量子位的單一專案： $$\begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g h h \end{bmatrix}=
    \begin{bmatrix}
    ae \ af \ bf \\\\
    ag \ ah \ bg \ bh \\\\
    ce \ cf \ de \ df \\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。$$
因此，我們可以採用一些已知單一量子位閘道的 tensor 產品，形成雙量子位的閘道。 雙量子位管制的一些範例包括 $ h \otimes h $ 、 $ x \otimes \boldone $ 和 $ x \otimes Z $ 。

請注意，雖然任何兩個單一量子位的閘道都是藉由取得 tensor 產品來定義雙量子位的閘道，但反向的情況並不成立。 並非所有的雙量子位閘道都可以撰寫成單一量子位閘道的 tensor 產品。  這類閘道稱為 *entangling* 閘道。 Entangling 閘道的其中一個範例是 CNOT 閘道。

受控制-非閘道後方的直覺可一般化至任意的閘道。  一般而言，受控制的閘道是做為身分識別 (ie 除非特定量子位為1，否則不會有任何動作) $ $ 。  在此案例中，我們會針對標示為 x 的量子位來代表受控制的單一控制項， $ $ 其中 $ \Lambda \_ x (U) $ 。  例如 $ \Lambda _0 (U) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ 和 $ \Lambda \_ 0 (U) e \_ { 0 } \otimes { \psi } = e \_ { 0 } \otimes { \psi } $ ，其中 $ e \_ 0 $ 和 $ e \_ 1 $ 是對應至值 $ 0 $ 和1之單一量子位的計算基礎向量 $ $ 。  例如，請考慮下列受控制的 $ z 網 $ 關，我們可以將其表示為 $$
\Lambda\_0 (Z) 1 0 0 0 0 1 0 0 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & 1 0 0 0 0 & \\\\ & & & -1 \end{bmatrix} = (\boldone \otimes H) \operatorname { CNOT } (\boldone \otimes H) 。
$$

以有效率的方式建立控制的 unitaries 是一項重大挑戰。  執行這項作業的最簡單方式，就是形成基礎閘道的控制版本資料庫，並以其控制的對應項取代原始單一作業中的每個基本閘道。  這通常是相當浪費的工作，而且聰明的深入解析通常可以用來將幾個閘道取代為受控制的版本，以達成相同的影響。  基於這個理由，我們在架構中提供的功能，就是在已知優化的手動調整版本時，執行控制或允許使用者定義受控制版本的單一方法。

閘道也可以使用傳統資訊來控制。  例如，傳統方式控制的非閘道只是一般的非閘道，但只有在傳統位是 $ 1 而不是量子位時才適用 $ 。  在這種情況下，傳統方式控制的閘道可視為量副程式代碼中的 if 語句，其中的閘道只會在程式碼的一個分支中套用。


如同在單一量子位案例中，如果有任何 $ 4 \times 個 $ 單一矩陣可將此集合中的閘道乘積設定為任意有效位數，則雙量子位閘道集會設定為通用。
通用閘道集合的其中一個範例是 Hadamard 閘道、T 閘道和 CNOT 閘道。 藉由取得這些閘道的產品，我們可以將兩個量子位上的任何單一矩陣近似。

## <a name="many-qubit-systems"></a>Many-Qubit 系統
我們會遵循在兩個量子位案例中所探索到的相同模式，從較小的系統建立多量子位的量子狀態。  這種狀態的建立方式是形成較小狀態的 tensor 產品。  例如，請考慮 $ $ 在量子電腦中編碼位字串1011001。  我們可以將此編碼為

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} 。
$$

量子閘道的運作方式完全相同。  例如，如果我們想要將 X 網 $ $ 關套用至第一個量子位，然後在第二個和第三個量子位之間執行 CNOT，我們可以將這種轉換表達為

\begin{align}
& (X \otimes \operatorname { CNOT } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 1 0 1 0 0 1\end{bmatrix}\\\\
&\qquad\qquad\equiv 0011001。 \end{align}

在許多量子位系統中，通常需要配置和解除配置作為量子電腦暫存記憶體的量子位。  這類量子位稱為 ancilla。  根據預設，我們假設量子位狀態會在 $ 配置時初始化為 e_0 $ 。  我們會進一步假設在 $ $ 解除配置之前再次傳回 e_0。  這項假設很重要，因為如果 ancilla 量子位在解除配置時，與另一個量子位暫存器變成纏結，解除配置的程式將會損毀 ancilla。  基於這個理由，我們一定會假設這類量子位會在發行前還原為其初始狀態。

最後，雖然需要將新的閘道新增至閘道，以達成兩個量子位量子電腦的通用量子運算，但是在多量子位的情況下，不需要引進任何新的閘道。  閘道 $ H $ 、 $ T $ 和 CNOT 形成許多量子位上的通用閘道，因為任何一般的單一轉換都可分成一系列的兩個量子位旋轉。  接著，我們可以利用針對兩個量子位案例開發的理論，並在有許多量子位的情況下再次使用它。

雖然我們使用到目前為止的線性代數標記法可以用來描述多量子位的狀態，但隨著我們增加狀態的大小，就會變得越來越繁瑣。  例如，針對長度為7位字串所產生的資料行向量為 $ 128 $ 維度，這會使用先前所述的標記法來表示它。  基於這個理由，我們接下來會在量子運算中呈現常見的標記法，讓我們可以簡要地描述這些高維度的向量。
