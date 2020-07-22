---
標題：配量 oracles 描述：瞭解如何使用並定義量子 oracles，這是用來做為其他演算法輸入的黑色箱作業。
author： cgranade uid： oracles ms-chap。作者： Christopher.Granade@microsoft.com ms. 日期：07/11/2018 毫秒。主題：發行項不存在：
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
# <a name="quantum-oracles"></a>量子 Oracles

Oracle $ O $ 是「黑箱」作業，用來做為另一個演算法的輸入。
通常，這類作業會使用傳統函式 $ f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m 來定義， \\ } $ 這會接受 $ n 位的 $ 二進位輸入，並產生 $ m $ 位二進位輸出。
若要這麼做，請考慮特定的二進位輸入 $ x = （x_ { 0 } ，x_ { 1 } ，\dots ..，x_ { n-1 } ） $ 。
我們可以將 qubit 狀態標示為 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。

我們可能會先嘗試定義 $ o， $ 使 $ o \ket { x } = \ket { f （x） } $ ，但這有幾個問題。
首先， $ f $ 可能會有不同的輸入和輸出大小（ $ n \ne m $ ），因此套用 $ O $ 會變更暫存器中的 qubits 數目。
第二，即使 $ n = m $ ，函式也可能無法反轉：如果 $ f （x） = f （y） $ 用於某個 $ x \ne y $ ，則為 $ o \ket { x } = o \ket { y， } $ 但 $ o ^ \dagger o x o \ket { } \ne \dagger \ket { y } $ 。
這表示我們無法建立 adjoint 作業 $ O ^ \dagger $ ，oracles 必須為其定義 adjoint。

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>依其對計算基礎狀態的影響來定義 oracle
我們可以藉由引進 m qubits 的第二個暫存器來處理這兩個問題， $ $ 以保存我們的解答。
然後，我們將定義 oracle 在所有計算基礎狀態的效果：對於所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0，1 \\ } ^ m $ ，

$$
\begin{align}
    O （ \ket { x } \otimes \ket { y } ） = \ket { x } \otimes \ket { y \oplus f （x） } 。
\end{align}
$$

現在 $ = ，我們已透過結構化 o o ^ \dagger $ ，因此我們解決了這兩個先前的問題。

> [!TIP]
>若要查看 $ o = o ^ { \dagger } $ ，請注意 $ o ^ 2 = \boldone $ 自 $ \oplus b \oplus b = a $ 對所有 $ a、b \in \[ ！OP.NO-LOC （{）] 0，1 \[ ！OP.無-LOC （}）] $ 。
>因此， $ O \ket { x } \ket { y \oplus f （x） } = \ket { x } \ket { y \oplus f （x） \oplus f （x） } = \ket { x } \ket { y } $ 。

重要的是，以這種方式為每個計算基礎狀態 x y 定義 oracle， $ \ket { } \ket { } $ 也會定義 $ O $ 對任何其他狀態的行為。
這會立即遵循 $ $ ，如同所有的配量作業，其作用所在的狀態都是線性的。
請考慮 Hadamard 作業，例如，它是由 $ h \ket { 0 } = \ket { + } $ 和 $ H \ket { 1 } = \ket { - } $ 所定義。
如果我們想要知道 $ h 的 $ 作用如何 $ \ket { + } $ ，我們可以使用這個 $ h $ 是線性的。

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H （ \ket { 0 }  +  \ket { 1 } ） = \frac { 1 } { \sqrt { 2 } } （h \ket { 0 } + H \ket { 1 } ）\\\\
           &= \frac{1 } { \sqrt { 2 } } （ \ket { + }  +  \ket { - } ） = \frac 12 （ \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ） = \ket { 0 } 。
\end{align}
$$

在定義 oracle O 的情況下 $ $ ，我們可以同樣地使用 $ \ket { \psi } $ n + m qubits 上的任何狀態都 $ $ 可以撰寫為

$$
\begin{align}
\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha （x，y） \ket { x } \ket { y}
\end{align}
$$

其中 $ \alpha ： \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C } $ 代表狀態的係數 $ \ket { \psi } $ 。 因此，

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha （x，y） \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m （x，y） O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha （x，y） \ket { x } \ket { y \oplus f （x） } 。
\end{align}
$$

## <a name="phase-oracles"></a>階段 oracles
或者，我們可以根據對 $ O 的輸入套用階段，將 f 編碼 $ 成 oracle $ O $ _phase_ $ $ 。比方說，我們可能會定義 $ O $$$
\begin{align}
    O \ket { x } = （-1） ^ { f （x） } \ket { x } 。
\end{align}
$$
如果某個階段在一開始是以計算基礎狀態 x 進行暫存器 $ \ket { } $ ，則此階段為全域階段，因此無法觀察。
但是，如果套用至重迭或做為受控制的作業，這類 oracle 可能是非常強大的資源。
例如，假設有一個階段的 oracle $ O_f $ 適用于單一 qubit 函數 $ f $ 。
請$$
\begin{align}
    O_f\ket{+}
        &=O_f （ \ket { 0 }  +  \ket { 1 } ）/ \sqrt { 2 }\\\\
        &=（（-1） ^ { f （0） } \ket { 0 } + （-1） ^ { f （1） } \ket { 1 } ）/ \sqrt { 2 }\\\\
        &=（-1） ^ { f （0） } （ \ket { 0 } + （-1） ^ { f （1）-f （0） } \ket { 1 } ）/ \sqrt { 2 }\\\\
        &=（-1） ^ { f （0） } Z ^ { f （0）-f （1） } \ket { + } 。
\end{align}
$$

更常見的情況是，可以放寬了 oracles 的兩個觀點來代表傳回實數的傳統函式，而不只是單一位。

選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用此 oracle。
例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依賴以第一種方式實作為的 oracle，而[Grover 的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依賴以第二種方式實施的 oracle。


如需更多詳細資訊，建議您在[Gilyén *et al*1711.00465](https://arxiv.org/abs/1711.00465)中進行討論。
