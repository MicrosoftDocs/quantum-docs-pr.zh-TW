---
標題：量子 oracle 描述：瞭解如何使用和定義量子 oracle、用來作為另一個演算法輸入的黑色 box 作業。
作者： cgranade uid： oracle ms. 作者： chgranad ms. 日期： 07/11/2018 ms. 主題：不含 loc 的文章：
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
# <a name="quantum-oracles"></a>量子 Oracle

Oracle $ O $ 是「黑箱」作業，可作為另一個演算法的輸入。
通常，這類作業是使用傳統函 $ 式（f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m）來定義，此函式 \\ } $ 會採用 $ n $ 位二進位輸入並產生 $ m $ 位二進位輸出。
若要這樣做，請考慮特定的二進位輸入 $ x = (x_ { 0 } 、x_ { 1 } 、\dots .. x_ { n-1 }) $ 。
我們可以將量子位狀態標記為 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。

我們可能會先嘗試定義 $ o， $ 讓 $ o \ket { x } = \ket { f (x) } $ ，但這有幾個問題。
首先， $ f $ 可能會有不同的輸入和輸出大小 ($ n \ne m $) ，因此套用 $ O $ 會變更暫存器中的量子位數目。
其次，即使 $ n = m，函式 $ 也可能無法反轉：如果 $ f (x) = f (y) $ 用於某些 $ x \ne y $ ，則為 $ o \ket { x o y， } = \ket { } $ 但 $ o ^ \dagger o \ket { x o x o } \ne \dagger \ket { y } $ 。
這表示我們無法建立 adjoint 作業 $ O ^ \dagger $ ，oracle 必須為它們定義 adjoint。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>依據計算基礎狀態的影響來定義 oracle
我們可以藉由引進第二個 $ m 量子位註冊來保存我們的答案，來處理這兩個問題 $ 。
接著，我們會定義 oracle 在所有計算基礎狀態的效果：所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0、1 \\ } ^ m $ 、

$$
\begin{align}
    O (\ket { x } \otimes \ket { y }) = \ket { x } \otimes \ket { y \oplus f (x) } 。
\end{align}
$$

現在 $ o = o o o \dagger $ x 的結構，因此我們解決了這兩個先前的問題。

> [!TIP]
>若要查看該 $ o = o ^ { \dagger } $ ，請注意 $ o ^ 2， = \boldone $ 因為 $ \oplus b \oplus b = a $ for all $ a，b \in \: ：： no loc ( {) ：：：0，1 \: ：： no loc (} ) ： $ ：：。
>因此， $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) x } = \ket { } \ket { y } $ 。

重要的是，以這種方式為每個計算基礎狀態定義 oracle， $ \ket { x } \ket { y } $ 也會定義 $ O $ 對任何其他狀態的運作方式。
這 $ $ 項作業會立即從像是所有量子作業這樣的事實，在其作用的狀態中是線性的。
請考慮 Hadamard 作業，例如，由 $ h \ket { 0 } = \ket { + } $ 和 $ h \ket { 1 定義 } = \ket { - } $ 。
如果我們想要知道 $ h h 如何 $ 運作 $ \ket { + } $ ，我們可以使用該 $ h $ 為線性，

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h (\ket { 0 }  +  \ket { 1 }) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 }) \\\\
           &= \frac{1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) = \frac 12 (\ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 }) = \ket { 0 } 。
\end{align}
$$

在定義 oracle O 的情況下 $ $ ，我們可以同樣地使用 $ \ket { \psi } $ n + m 量子位上的任何狀態都 $ $ 可以撰寫為

$$
\begin{align}
\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}
\end{align}
$$

其中 $ \alpha ： \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C } $ 代表狀態的係數 $ \ket { \psi } $ 。 因此，

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x、y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y \oplus f (x) } 。
\end{align}
$$

## <a name="phase-oracles"></a>階段 oracle
另外，我們也可以 $ $ $ $ 根據輸入至 O 來套用_階段_，將 f 編碼為 oracle O $ $ 。比方說，我們可能會定義 $ O $$$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } 。
\end{align}
$$
如果 oracle 階段一開始是以計算基礎狀態 x 作為基礎 $ \ket { } $ ，則這個階段是全域階段，因此無法觀察。
但是如果套用至迭加或做為受控制的作業，則這類 oracle 可能是非常強大的資源。
例如，假設有一個階段 oracle $ O_f $ 量子位函式 $ f $ 。
然後 $$
\begin{align}
    O_f \ket{+}
        &=O_f (\ket {0 }  +  \ket { 1 }) / \sqrt { 2 }\\\\
        &= ( # A1-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 }) / \sqrt { 2 }\\\\
        &= (-1) ^ { f (0) } (\ket { 0 } + (-1) ^ { f (1) -f (0) } \ket { 1 }) / \sqrt { 2 }\\\\
        &= (-1) ^ { f (0) } Z ^ { f (0) -f (1) } \ket { + } 。
\end{align}
$$

更常見的是，oracle 的這兩個觀點都可以放寬了來代表傳回實數的傳統函式，而不是只有一個位。

選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用這種 oracle。
例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) 依賴以第一種方式執行的 oracle，而 [格羅弗的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm) 則依賴以第二種方式實作為的 oracle。


如需更多詳細資料，我們建議[您*et al*Gilyén](https://arxiv.org/abs/1711.00465)中的討論，例如1711.00465。
