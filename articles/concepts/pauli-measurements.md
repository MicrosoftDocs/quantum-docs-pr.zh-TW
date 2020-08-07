---
標題： Pauli 測量描述：瞭解如何使用單一和多 qubit 的 Pauli 測量作業。
author： QuantumWriter uid： pauli ms-chap。作者： nawiebe@microsoft.com ms. 日期：12/11/2017 毫秒。主題：發行項不存在：
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

在先前的討論中，我們著重于計算基礎測量。
事實上，從標記的角度來看，在計量運算中所發生的其他常見測量，在計算基礎測量方面很方便表達。
當您使用時 Q# ，最常見的測量類型可能是*Pauli 測量*，這會將計算基礎測量一般化以包含其他基底的度量，以及不同 qubits 之間的同位檢查。
在這種情況下，通常會討論測量 Pauli 運算子，通常是如 $ x、Y、z $ 或 $ z \otimes z、x \otimes x、x \otimes Y $ 等等的運算子。

> [!TIP]
>在中 Q# ，多 qubit 的 Pauli 運算子通常會由類型的陣列表示 `Pauli[]` 。
>例如，若要表示 $ X \otimes Z \otimes Y $ ，您可以使用陣列 `[PauliX, PauliZ, PauliY]` 。

討論 Pauli 運算子方面的測量，特別是在量子錯誤更正的子欄位中。
在中 Q# ，我們會遵循類似的慣例，我們現在會說明這種替代的度量觀點。

在探究到如何思考 Pauli 測量的詳細資料之前，請考慮測量量子電腦內的單一 qubit 對量子狀態的作用。
假設我們有一個 qubit 的配量 $ $ 狀態，然後測量一個 qubit 立即的規則 $ $ ，這是狀態可能出現在 2 ^ n 個可能性的一半。
換句話說，測量會將量子狀態投射到兩個半形的其中一個。
我們可以將我們認為測量的方式一般化，以反映此直覺。

為了簡潔地識別這些 subspaces，我們需要用來描述它們的語言。
描述兩個 subspaces 的其中一種方式，就是透過僅具有兩個唯一特徵值的矩陣來指定它們，慣例是 $ \pm 1 $ 。
如需以這種方式描述 subspaces 的簡單範例，請考慮使用 $ Z $ ：

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。
\end{align}
$$

藉由讀取 Pauli-Z 矩陣的對角線 $ 元素 $ ，我們可以看到 $ Z $ 有兩個特徵向量（ $ \ket { 0 } $ 和 $ \ket { 1 } $ ），以及對應的特徵值 $ \pm 1 $ 。
因此，如果我們測量 qubit，並取得 `Zero` 對應至狀態 $ \ket { 0) 的 (} $ ，我們就知道 qubit 的狀態是 $ Z 運算子的 + 1 $ eigenstate $ $ 。
同樣地，如果我們取得 `One` ，我們知道我們的 qubit 狀態是 z 的 $ -1 $ eigenstate $ $ 。此程式稱為「測量 Pauli Z」的 Pauli 度量語言， $ $ 完全等同于執行計算基礎測量。

任何 $ \times $ 屬於 Z 的單一轉換的 2 2 矩陣 $ $ 也都符合此準則。
也就是說，我們也可以使用一個 $ = u ^ \dagger Z u 的矩陣 $ ，其中 $ u $ 是任何其他的單一矩陣，以提供一個矩陣，在其 $ \pm 1 特徵向量中定義度量的兩個結果 $ 。
Pauli 量值的標記法會藉由 $ 將 X、Y、Z 量值識別為對等的測量值，來參考這個單一等價項， $ 以取得來自 qubit 的資訊。
為了方便起見，以下提供這些測量。


|Pauli 測量 | 單一轉換|
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X |$H               $                    |
|$ $ Y |$HS ^               {\dagger}$         |

也就是說，使用這種語言，「測量 $ Y」等同于套用 $ $ HS ^， \dagger $ 然後以計算為基礎，其中是內建 [`S`](xref:microsoft.quantum.intrinsic.s) 的量子作業，有時稱為「階段閘道」，而且可以由單一矩陣模擬

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} 。
\end{align}
$$

這也相當於將 $ HS ^ 套用 \dagger $ 到量子狀態向量，然後測量 $ Z $ ，讓下列作業相當於 `Measure([PauliY], [q])` ：

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

藉由轉換回計算基礎來尋找正確的狀態，這是將 $ SH 套用 $ 到量子狀態向量的數量; 在上述程式碼片段中，轉換回計算基礎的動作會透過使用區塊來自動處理 `within … apply` 。

在中 Q# ，我們會將結果---也就是，從與---狀態互動所解壓縮的傳統資訊是由 `Result` 值 $ j \in \\ { \texttt { 零提供 } ， \texttt { 一個 } \\ } $ 表示結果是否在 $ Pauli 運算子的 (-1) ^ j $ eigenspace 中。


## <a name="multiple-qubit-measurements"></a>多 qubit 測量

多 qubit Pauli 運算子的度量定義類似，如下所示：

$$
Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & -1 0 0 0 0 & \\\\ & & & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1。
$$

因此，兩個 Pauli z 運算子的張量產品會 $ $ 形成一個矩陣，其中包含由 $ + 1 $ 和 $ -1 特徵值 $ 組成的兩個空格。
就像單一 qubit 的情況一樣，兩者都構成一半空間，這表示可存取的兩個向量空間一半屬於 $ + 1 $ eigenspace，其餘一半則是 $ -1 $ eigenspace。
一般來說，您可以從張量產品的定義中查看 Pauli-Z 運算子的任何張量產品，以及身分 $ $ 識別也會遵守這項功能。
例如

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 & 0 0 &\\\\
        0 & 1 & 0 & 0\\\\
        0 & 0 & -1 & 0\\\\
        0 & 0 & 0 & -1 \end{bmatrix} 。
\end{align}
$$

如前所述，這類矩陣的任何單一轉換也會描述 \pm 1 特徵值所標示的兩個半形 $ $ 。
例如， $ x \otimes x = h \otimes h (z z， \otimes \otimes $ 從 z HXH 的識別) H $ h = $ 。
類似于一 qubit 的情況，所有的雙 qubit Pauli 量值都可以撰寫為 $ u ^ \dagger (Z \otimes \id) u $ （適用于 $ 4 4 的 \times $ 單一矩陣 $ U） $ 。我們會列舉下表中的轉換。

> [!NOTE]
>在下表中，我們使用 $ \operatorname { SWAP } $ 來表示矩陣 >$$
> \begin{align}
>     \operatorname{交換 } &=
>     \left (\begin { 矩陣}
>1 & 0 & 0 0 &\\\\
>0 & 0 & 1 & 0\\\\
>0 & 1 & 0 & 0\\\\
>0 0 0 & & & 1 > \end { 矩陣 } \right) >     \end{align}
> $$
>用來模擬內部作業 [`SWAP`](xref:microsoft.quantum.intrinsic) 。

|Pauli 測量 | 單一轉換|
|----------------------|------------------------|
|$ \otimes \boldone Z $| $\boldone\otimes \boldone$|
|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|
|$ \otimes \boldone X $| $\otimes \boldone H $|
|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|
|$\boldone \otimesZ $ | $ \operatorname { 交換 } $|
|$\boldone \otimesX $ | $ (H \otimes \boldone) \operatorname { 交換 } $|
|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone) \operatorname { SWAP } $|
|$Z \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } $|
|$X \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes \boldone) $|
|$Y \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes \boldone) $|
|$Z \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes H) $|
|$X \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (h \otimes h) $|
|$Y \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes HS ^ \dagger) $|
|$X \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes HS ^ \dagger) $|
|$Y \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger) $|

在這裡，作業 [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) 會因為下列原因而出現。
不包含矩陣的每個 Pauli 量值， $ \boldone $ 都相當於上述推理的單一到 $ z \otimes $ 。
$Z z 的特徵值 \otimes $ 僅取決於組成每個計算基礎向量的 qubits 同位檢查，而受控制的非作業則是用來計算此同位，並將其儲存在第一位。
然後在測量第一個位之後，我們就可以復原結果半形的識別，這相當於測量 Pauli 運算子。

另一個注意事項：雖然假設測量 $ z \otimes z $ 的方式相當於依序測量 $ z \otimes \mathbb { 1 } $ 和 $ \mathbb { 1 } \otimes z $ ，但此假設為 false。
原因是測量 $ z \otimes z 將配 $ 量狀態投射到 $ 這些運算子的 + 1 $ 或 $ -1 $ eigenstate 中。
測量 $ z \otimes \mathbb { 1 } $ ，然後再 $ \mathbb { } \otimes $ 將配量狀態向量投射到 z 1 的一半空間 $ \otimes \mathbb { } $ ，然後到 $ \mathbb { 1 } \otimes z $ 的一半空間。因為有四個計算基礎的向量，同時執行這兩個度量會將狀態縮減為四分之一空間，因而減少為單一計算基礎向量。

## <a name="correlations-between-qubits"></a>Qubits 之間的相互關聯
另一個查看 Pauli 矩陣（例如 x x 或 z z）之張量產品的方式， $ \otimes $ $ \otimes $ 是這些測量可讓您查看儲存在兩個 qubits 之間相互關聯中的資訊。
測量 $ X \otimes \id $ 可讓您查看本機儲存在第一個 qubit 中的資訊。
雖然這兩種類型的測量在量子運算中也同樣有價值，但前者也會照亮量子運算的威力。
它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一 qubit 中，而是會一次儲存在所有 qubits 中，因此，只有透過聯合 (測量來查看（例如 $ z \otimes z) ， $ 這項資訊才會變成資訊清單。

例如，在錯誤修正中，我們通常會想要瞭解在學習嘗試保護的狀態時，所發生的錯誤。
「[翻轉」程式碼範例會示範](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)如何使用 $ z \otimes z \otimes \id $ 和 $ \id \otimes z \otimes $ < z 等度量來執行這項操作。--TODO：只要有位翻轉程式碼範例在上線上，就會將此變更為範例瀏覽器的連結。 -->

也可以測量任意的 Pauli 運算子，例如 $ X \otimes Y \otimes Z \otimes \boldone $ 。
Pauli 運算子的所有這類張量產品只有兩個特徵值 $ \pm 1 $ ，而這兩個 eigenspaces 構成整個向量空間的半個空格。
因此，它們會符合上面所述的需求。

在中 Q# ， $ $ 如果測量結果產生 eigenspace 的正負號 $ (-1) ^ j，這類測量就會傳回 j $ 。
將 Pauli 測量當做內建的功能會很 Q# 有説明，因為測量這類運算子需要較長的受控制-NOT 閘道和基礎轉換鏈，以描述將作業 $ $ 表示為 Z 和之張量產品所需的 diagonalizing U 閘道 $ $ $ \id $ 。
藉由指定您想要執行上述其中一項預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎測量提供必要的資訊。
Q#自動為您處理所有必要的基礎轉換。
如需詳細資訊，請參閱 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 和 [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 作業。

## <a name="the-no-cloning-theorem"></a>無複製定理

量子資訊功能強大。
這讓我們能夠執行令人驚奇的事，像是以指數方式比最佳的傳統演算法更快，或有效率地模擬傳統方式需要指數成本才能正確模擬的相互關聯 electron 系統。
不過，配量運算的功能有一些限制。
其中一項限制是由*無複製定理*所提供。

未複製的定理是名為的恰如其。
它不允許由量子電腦複製一般量子狀態。
定理證明十分簡單。
雖然不復制定理的完整證明在這裡的討論方面有點技術性，但在我們的範圍內沒有其他輔助 qubits 的證明是在領域 (輔助 qubits 會 qubits 用於計算期間的臨時空間，而且很容易在中使用和管理 Q# ，請參閱借用的[qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)) 。

對於這類的量子電腦，複製作業必須由單一矩陣描述。
我們不允許測量，因為它會損毀我們嘗試要複製的量子狀態。
為了模擬複製作業，我們想要使用單一矩陣來擁有屬性，$$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
適用于任何狀態 $ \ket { \psi } $ 。
矩陣乘法的線性屬性會指出，針對任何第二個量子狀態 $ \ket { \phi } $ ，

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

這提供了不復制定理背後的基礎直覺：任何複製不明量子狀態的裝置，都必須在其複製的至少部分狀態中引發錯誤。
雖然在輸入狀態上以線性方式執行 cloner 的主要假設是透過新增和測量輔助 qubits 來違反，這類互動也會透過測量統計資料來流失系統的相關資訊，並避免在這種情況下進行完全複製。
如需更完整的無複製定理證明，請參閱[以取得詳細資訊](xref:microsoft.quantum.more-information)。

無複製定理對於區分量子運算而言非常重要，因為如果您可以在較低的情況中複製配量狀態，則會被授與從配量狀態學習的近乎神奇功能。
事實上，您可能違反了海森堡的 vaunted 不確定性原則。
或者，您可以使用最佳的 cloner 從複雜的配量散發取得單一範例，並瞭解您可能會從一個範例中瞭解該散發的所有資訊。
這就像是您翻轉一間的一門硬幣，然後告訴朋友，其回應結果為「啊，該硬幣的分佈必須以 $ p = 0.512643 \ ldots $ ！」  這類語句不會 sensical，因為 (列印頭結果的其中一項資訊) 只是無法提供編碼散發所需的許多資訊，而不需要大量的先前資訊。
同樣地，如果沒有先前的資訊，我們就無法完全複製量子狀態，因為我們無法在不知道 p 的情況下準備集團這類的硬幣 $ $ 。

在量子運算中，資訊不是免費的。
每個 qubit 都有提供一項資訊，而不復制定理顯示沒有任何後門可被利用，來解決系統與在其上叫用之騒之間的基本取捨。
