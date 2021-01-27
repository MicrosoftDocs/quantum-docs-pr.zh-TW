---
標題： Advanced matrix 概念描述：瞭解特徵向量、特徵值和矩陣指數，這是用來描述和模擬量子演算法的基本工具。
作者： QuantumWriter uid： benbra-advanced ms. author： v-ms. date： 12/11/2017 ms. 主題：概念非 loc：
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Advanced Matrix 概念 #

我們現在將矩陣的操作延伸至 [*特徵值、特徵向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 和 [*指數*](https://en.wikipedia.org/wiki/Matrix_exponential) ，以形成一組我們需要用來描述和實行量子演算法的基本工具。

## <a name="eigenvalues-and-eigenvectors"></a>特徵值和特徵向量 ##

讓 $ M $ 成為正方形矩陣，而 $ v 為 $ 非所有零向量的向量 (例如，將所有專案等於 $ 0) 的向量 $ 。

我們說 $ v $ 是 M 的 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ，  $ 如果有 $ $ = $ 一些數位 c 的 Mv cv $ $ 。 我們說 $ 的 $ 是， [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 對應于 eigenvector $ v $ 。 一般而言 $ ，矩陣 M $ 可能會將向量轉換成任何其他向量，但 eigenvector 是特殊的，因為它會保持不變，但乘以數位。 請注意，如果 $ v $ 是具有 eigenvalue c 的 eigenvector $ $ ，則 $ av $ 也是 eigenvector (，適用于 $ $ 具有相同 eigenvalue 的任何非零) 。

例如，針對身分識別矩陣，每個向量 $ v $ 都是具有 eigenvalue 1 的 eigenvector $ $ 。

另舉一個範例，請考慮使用對角線 [*矩陣*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D， $ 而對角線上只有非零的專案：

$$
\begin{bmatrix}
d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & d_3 \end{bmatrix} 。
$$

向量

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 和 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

是此矩陣的特徵向量  $ ，分別是特徵值 d_1 $ 、 $ d_2 $ 和 $ d_3 $ 。 如果 $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 都是相異數位，則這些向量 (和其倍數) 是矩陣 d 的唯一特徵向量 $ $ 。一般來說，如果是對角線矩陣，就很容易就能閱讀特徵值和特徵向量。 特徵值是出現在對角線上的所有數位，而其個別的特徵向量是一個專案等於 $ 1 $ ，而其餘專案等於0的單位向量 $ $ 。

請注意，在上述範例中，D 的特徵向量會 $ $ 形成 $ 三維向量的基礎 $ 。 「基礎」是一組向量，可將任何向量寫入為它們的線性組合。 更明確地來說， $ v_1 $ 、 $ v_2 $ 和 $ v_3 $ 在任何向量 $ v $ 可以撰寫為 $ v = a_1 v_1 + a_2 v_2 + a_3 v_3 a_1 $ $ $ 、 $ a_2 $ 和 $ a_3 $ 的。

回想一下，Hermitian 矩陣 (也稱為自我 adjoint) ，是相當於它自己的複數互補轉型的複雜正方形矩陣，而單一矩陣是複數的正方形矩陣，其反向等於其 adjoint 或複雜的下轉型。
針對 Hermitian 和單一矩陣（基本上是量子運算中唯一遇到的矩陣），通常會有稱為 [*光譜定理*](https://en.wikipedia.org/wiki/Spectral_theorem)的結果，它會判斷提示如下：對於任何 Hermitian 或單一矩陣 $ M $ ，有一個單一的 $ u， $ 例如， $ = \dagger $ 某些對角矩陣 d 的 m u ^ d $ u $ 。此外，D 的對角線專案 $ $ 將會是 M 的特徵值 $ $ 。

我們已經知道如何計算對角線矩陣 D 的特徵值和特徵向量 $ $ 。使用這個定理時，我們知道如果 $ v $ 是 $ 具有 eigenvalue c 的 D eigenvector （也就 $ $ $ $ 是 Dv = cv $ ），則 $ U ^ \dagger v 將會 $ 是 eigenvector of $ M $ with eigenvalue $ c $ 。 這是因為

$$M (U ^ \dagger v) = U ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger) v = U ^ \dagger D v = c u ^ \dagger v。$$

## <a name="matrix-exponentials"></a>矩陣指數
[*矩陣指數*](https://en.wikipedia.org/wiki/Matrix_exponential)也可以與指數函式完全類似地定義。  矩陣 a 的矩陣指數 $ $ 可表示為

$$
e ^ A = \boldone + a + \frac { a + a ^ 2 } { 2！ } + \frac {^ 3 } { 3！}+\cdots
$$

這點很重要，因為量子機械時間演進是由表單 $ e ^ { IB } $ for Hermitian 矩陣 $ B $ 的單一矩陣所描述。 基於這個理由，執行矩陣指數是量子運算的基本元件，因此 Q# 提供了用來描述這些作業的內部常式。
實務上有許多方式可計算傳統電腦上的矩陣指數，而在一般的數值將逼近中，這類指數是使用危險危險。  請參閱 [*Cleve Moler 和 Charles Van 貸款。「有十九個可疑的方法可計算矩陣的指數」。SIAM 計算期刊評論 20.4 (1978) ： 801-836*](https://doi.org/10.1137/S00361445024180) 以取得相關挑戰的詳細資訊。

若要瞭解如何計算矩陣的指數，最簡單的方式是透過該矩陣的特徵值和特徵向量。  具體來說，上述的光譜定理指出，針對每個 Hermitian 或單一矩陣， $ $ 有一個單一矩陣 $ U $ 和一個對角矩陣 $ d， $ 例如 $ = U ^ \dagger d u $ 。 由於 unitarity 的屬性，我們有 $ ^ 2 = u ^ \dagger d ^ 2 u $ ，也同樣適用于任何 power $ p $ $ A ^ p = u ^ \dagger d ^ p u $ 。 如果我們把它換成運算子的 operator 定義，我們取得的是指數指數：

$$
e ^ A = U ^ \dagger \left (\boldone + d + \frac { d ^ 2 } { 2！ } + \cdots \right) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 }) & 0 & \cdots & 0 \\\\ 0 0 & \exp (D_ { 22 }) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN }) \end{bmatrix} U。$$

換句話說，如果您轉換成矩陣 A 的 eigenbasis， $ $ 則計算矩陣指數就相當於計算矩陣特徵值的一般指數。  在量子運算中有許多作業牽涉到執行矩陣指數，這是轉換成矩陣 eigenbasis 以簡化執行運算子指數的技巧，而這是在本指南稍後討論的許多量子演算法（例如 Trotter – Suzuki 樣式的量子模擬方法）背後的基礎。

另一個有用的屬性是，如果 $ b 同時為 [單一] 和 [Hermitian]，也就是 $ $ b = b ^ { -1 } = B ^ \dagger $ then $ b ^ 2 = \boldone $ 。 藉由將此規則套用至矩陣指數的上方展開，並將 $ \boldone $ 和 $ B 詞彙群組在 $ 一起，就可以看到任何真正的值 x 身分 $ $ 識別

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x) $$


控制. 這項技巧特別有用，因為它可讓您瞭解動作矩陣指數具有的原因，即使 b 的 $ 維度 $ 是以指數方式表示，但在特殊情況下， $ b $ 同時是單一和 Hermitian。
