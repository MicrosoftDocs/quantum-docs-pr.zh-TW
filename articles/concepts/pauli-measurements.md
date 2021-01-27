---
標題： Pauli 度量描述：瞭解如何使用單一和多重量子位的 Pauli 度量運算。
作者： bradben uid： pauli ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：概念無 loc：
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

# <a name="pauli-measurements"></a>Pauli 測量

在先前的討論中，我們著重于計算基礎度量。
事實上，量子運算中有其他常見的測量，從標記的角度來看，這在計算基礎測量方面很方便。
當您使用時 Q# ，最常見的測量類型可能會是 *Pauli 測量*，這會將計算基礎度量一般化以包含其他基底的度量，以及不同量子位之間的同位檢查。
在這種情況下，通常會討論測量 Pauli 運算子，通常是 $ x、Y、z $ 或 $ z \otimes z、x \otimes x、x \otimes Y $ 等運算子。 

> [!TIP]
> 在中 Q# ，多量子位的 Pauli 運算子通常是以類型的陣列表示 `Pauli[]` 。
> 例如，若要表示 $ X \otimes Z \otimes Y $ ，您可以使用陣列 `[PauliX, PauliZ, PauliY]` 。

討論 Pauli 運算子的度量在量子錯誤修正的子欄位中特別常見。
在中 Q# ，我們會遵循類似的慣例，我們現在會說明這種替代的度量觀點。

在探究有關如何思考 Pauli 測量的詳細資訊之前，請先思考測量量子電腦內的單一量子位對量子狀態的作用。
想像一下，我們有 $ 一個 $ 量子位的量子狀態，然後測量一個量子位，立即將該州的 $ 2 ^ n 個可能性的一半 $ 視為一半。
換句話說，量測會將量子狀態投射到兩個半空格的其中一個。
我們可以將我們認為測量的方式一般化，以反映此直覺。

為了簡潔地識別這些 subspaces，我們需要用來描述這些的語言。
描述這兩個 subspaces 的其中一種方式，是透過只有兩個唯一特徵值的矩陣來指定它們，慣例會採用 $ \pm 1 $ 。
如需以這種方式描述 subspaces 的簡單範例，請考慮使用 $ Z $ ：

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。
\end{align}
$$

藉由讀取 Pauli-Z 矩陣的對角線 $ 元素 $ ，我們可以看到 $ Z $ 有兩個特徵向量（ $ \ket { 0 } $ 和 $ \ket { 1），以及 } $ 對應的特徵值 $ \pm 1 $ 。
因此，如果我們測量量子位並取得與 `Zero` 狀態 0) 對應的 ($ \ket { } $ ，我們知道量子位的狀態是 $ Z 運算子的 + 1 $ eigenstate $ $ 。
同樣地，如果我們得到 `One` ，我們知道量子位的狀態是 $ z 的-1 $ eigenstate $ $ 。此程式稱為「測量 Pauli Z」的 Pauli 度量語言， $ $ 完全等同于執行計算基礎度量。

任何 $ 2 \times 2 $ 矩陣（即單一轉換 Z） $ $ 也會滿足此準則。
也就是說，我們也可以使用矩陣 $ a = U ^ \dagger Z u $ ，其中 $ u $ 是任何其他的單一矩陣，以提供矩陣來定義測量結果在其 $ \pm 1 特徵向量中的兩個結果 $ 。
Pauli 量值的標記法會藉由識別 $ X、Y、Z 量測作為對等量值來參考這項單一等價 $ ，以從量子位中得到資訊。
為了方便起見，以下提供這些度量。


|Pauli 測量  | 單一轉換  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X |$H               $                    |
|$ $ Y |$HS ^               {\dagger}$         |

也就是說，使用這種語言時，「measure Y」相當於套用 $ $ $ HS ^， \dagger $ 然後以計算為基礎來測量，其中是內建的 [`S`](xref:Microsoft.Quantum.Intrinsic.S) 量子作業有時稱為「階段閘道」，且可由單一矩陣模擬

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} 。
\end{align}
$$

它也相當於將 $ HS ^ 套用 \dagger $ 至量子狀態向量，然後測量 $ Z $ ，讓下列作業相當於 `Measure([PauliY], [q])` ：

```qsharp
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

然後，您可以藉由轉換回計算基礎來找到正確的狀態，將 SH 套用 $ $ 至量子狀態向量; 在上述程式碼片段中，轉換回計算基礎是使用區塊自動處理 `within … apply` 。

在中 Q# ，我們假設結果---也就是，從與---狀態互動所解壓縮的傳統資訊是由 `Result` 值 j 零所提供 $ \in \\ { \texttt { } ， \texttt { 一個 } \\ } $ 表示結果是否在 $ $ 所測量 Pauli 運算子的 (-1) ^ j eigenspace 中。


## <a name="multiple-qubit-measurements"></a>多量子位度量

多量子位 Pauli 運算子的度量定義類似，如下所示：

$$
Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & & \\\\ & -1 & 0 0 0 0 & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 0 1。
$$

因此，兩個 Pauli z 運算子的 tensor 產品 $ $ 形成由兩個空格組成的矩陣 $ ，由 + 1 $ 和 $ -1 $ 特徵值組成。
就像單一量子位案例一樣，兩者都構成一半的空間，這表示一半的可存取向量空間屬於 $ + 1 $ eigenspace，而剩餘一半到 $ -1 $ eigenspace。
一般來說，從 tensor 產品的定義中，任何 Pauli-Z 運算子的 tensor 產品 $ $ 和身分識別也會遵守這一點，都很容易看出。
例如，

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 &  0 &  0 &  0 \\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & -1 &  0 \\\\
        0 &  0 &  0 & -1 \end{bmatrix} 。
\end{align}
$$

同樣地，這類矩陣的任何單一轉換也會描述 \pm 1 特徵值所標記的兩個半空格 $ $ 。
例如， $ x \otimes x = h \otimes h (z \otimes z) H h， \otimes $  從 z HXH 的身分識別 $ = $ 。
類似于量子位案例，所有的雙量子位 Pauli 度量都可以撰寫為 $ u ^ \dagger (Z \otimes \id) u， $ 適用于 $ 4 \times 4 個 $ 單一矩陣 $ u $ 。我們列舉下表中的轉換。

> [!NOTE]
>在下表中，我們使用 $ \operatorname { SWAP } $ 來指出矩陣 >$$
> \begin{align}
>     \operatorname{交換 } &=
>     \left (\begin { 矩陣}
>         1 & 0 & 0 & 0 \\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & 0 & 1 > \end { 矩陣 } \right) >     \end{align}
> $$
> 用來模擬內建函式 [`SWAP`](xref:Microsoft.Quantum.Intrinsic) 。

|Pauli 測量     | 單一轉換  |
|----------------------|------------------------|
|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|
|$ \otimes \boldone X $| $\otimes \boldone H $|
|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|
|$\boldone \otimesZ $ | $ \operatorname { 交換 } $|
|$\boldone \otimesX $ | $ (H \otimes \boldone) \operatorname { 交換 } $|
|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone) \operatorname { 交換 } $|
|$Z \otimesZ $ | $ \operatorname { CNOT } \_ { 10 } $|
|$X \otimesZ $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone) $|
|$Y \otimesZ $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone) $|
|$Z \otimesX $ | $ \operatorname { CNOT } \_ { 10 } (\boldone \otimes H) $|
|$X \otimesX $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|
|$Y \otimesX $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimesY $ | $ \operatorname { CNOT } \_ { 10 } (\boldone \otimes HS ^ \dagger) $|
|$X \otimesY $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger) $|
|$Y \otimesY $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes hs ^ \dagger) $|

在此， [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) 會因為下列原因而出現作業。
每個不含矩陣的 Pauli 量值 $ \boldone $ 都等同于上述推理的單一至 $ z \otimes z $ 。
$Z z 的特徵值 \otimes $ 只取決於構成每個計算基礎向量之量子位的同位，且受控制的作業不會用來計算這個同位，並將其儲存在第一個位。
然後，在測量第一個位之後，我們可以復原產生之半形的身分識別，這相當於測量 Pauli 運算子。

另一個注意事項：雖然假設測量 $ z \otimes z 與 $ 依序測量 $ z \otimes \mathbb { 1 和 1 Z 的方式相同，但 } $ 這項 $ \mathbb { 假設會 } \otimes $ 是 false。
原因是測量 $ Z z 會 \otimes $ 將量子狀態投射到 $ 這些運算子的 + 1 $ 或 $ -1 $ eigenstate 中。
測量 $ z \otimes \mathbb { 1 } $ ，然後 $ \mathbb { } \otimes 按 1 z， $ 將量子狀態向量先投射到 Z 1 的一半空間 $ \otimes \mathbb { } $ ，然後再到 $ \mathbb { 1 } \otimes z $ 的半個空格。由於有四個計算基礎向量，執行這兩個測量可將狀態減少到四分之一空間，因此會將其縮減為單一計算基礎向量。

## <a name="correlations-between-qubits"></a>量子位元之間的關聯性
另一種查看 Pauli 矩陣（例如 $ x x 或 z z） tensor 產品的方式 \otimes $ $ \otimes $ ，就是這些測量資料可讓您查看儲存在兩個量子位之間相互關聯的資訊。
測量 $ X \otimes \id $ 可讓您查看在第一個量子位中儲存在本機的資訊。
雖然這兩種類型的度量在量子運算中同樣有價值，但前者也會導致量子運算的威力。
它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一量子位中，而是會一次儲存在所有量子位中，因此只會透過聯合 (度量來查看它（例如 $ Z \otimes z $) 會將這項資訊變成資訊清單）。

例如，在錯誤修正中，我們通常會想要瞭解在學習到我們想要保護的狀態時，發生了什麼錯誤。
[位在程式碼範例](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)中的範例示範如何使用 $ Z \otimes z \otimes \id $ 和 $ \id \otimes z \otimes z $ < 等度量來進行。--TODO：當位翻轉程式碼範例在上線上時，請將此變更為範例瀏覽器的連結。 -->

您也可以測量任意 Pauli 運算子（例如 $ X \otimes Y \otimes Z \otimes \boldone $ ）。
Pauli 運算子的所有這類 tensor 產品只有兩個特徵值 $ \pm 1 $ ，而 eigenspaces 則構成整個向量空間的一半空格。
因此，它們會符合上述的需求。

在中 Q# ， $ $ 如果測量結果產生 eigenspace 的正負號 $ (-1) ^ j 的結果，這類測量結果會傳回 j $ 。
將 Pauli 量測視為中的內建功能 Q# 很有説明，因為測量這類運算子需要較長的控制-非管制和基礎轉換鏈，以描述將作業 $ $ 表示為 Z 和 tensor 產品所需的 diagonalizing U 閘道 $ $ $ \id $ 。
藉由指定您想要執行上述其中一個預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎度量能提供必要的資訊。
Q# 自動為您處理所有必要的基礎轉換。
如需詳細資訊，請參閱 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 和 [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) 作業。

## <a name="the-no-cloning-theorem"></a>No-Cloning 定理

量子資訊的功能強大。
它讓我們能夠以更快的速度，比最知名的傳統演算法更快地進行一些令人驚奇的事，像是更有效率地模擬傳統方式需要指數成本才能精確模擬的相關 electron 系統。
不過，量子運算的威力有一些限制。
這種限制是由 *無複製定理* 所提供。

No-Cloning 的定理會恰如其命名。
它不允許量子電腦複製一般量子狀態。
定理證明很簡單。
雖然沒有複製定理的完整證明在這裡的討論方面有點太技術性，但是在我們的範圍內沒有其他輔助量子位的證明也是如此。

針對這類量子電腦，複製作業必須由單一矩陣描述。
我們不允許進行度量，因為它會損毀我們嘗試複製的量子狀態。
為了模擬複製作業，我們想要使用單一矩陣來取得屬性 $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
適用于任何狀態 $ \ket { \psi } $ 。
矩陣乘法的線性屬性工作表示，在任何第二個量子狀態 $ \ket { \phi } $ 下，

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right ] \ket { 0}
    &= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right \right) ) 。
\end{align}
$$

這會提供 No-Cloning 定理背後的基本直覺：任何複製未知量子狀態的裝置，都必須在其所複製的部分狀態下引發錯誤。
雖然 cloner 在輸入狀態上以線性方式運作的關鍵假設是透過新增和測量輔助量子位，所以這類互動也會透過測量統計資料來洩漏系統的相關資訊，並防止在這類情況下進行完全複製。
如需更完整的 No-Cloning 定理詳細 [資訊](xref:microsoft.quantum.more-information)，請參閱。

No-Cloning 定理對於量子運算很重要，因為如果您可以更經濟的方式複製量子狀態，則會獲得從量子狀態學習的近乎神奇功能。
事實上，您可能違反了海森堡的 vaunted 不確定性原則。
或者，您也可以使用最佳的 cloner，從複雜的量子散發取得單一範例，並從單一範例學習該散發的所有相關資訊。
這就像是您將硬幣和觀察到的結果，然後在告知朋友的結果中，他們會回應「必須使用 $ p = 0.512643 \ ldots $ ！來讓那個硬幣的分佈有利  這類的語句不會 sensical，因為 (列印頭結果的其中一項資訊，) 只是無法提供在沒有大量先前資訊的情況下編碼散發所需的許多資訊。
同樣地，在沒有先前資訊的情況下，我們無法完全複製量子狀態，因為我們無法在不知道 p 的情況下準備集團這類的硬幣 $ $ 。

在量子運算中，資訊不是免費的。
測量的每個量子位都提供一項資訊，而 No-Cloning 定理指出沒有任何後門程式可被入侵，以因應系統與在其上叫用之干擾之間的基本取捨。
