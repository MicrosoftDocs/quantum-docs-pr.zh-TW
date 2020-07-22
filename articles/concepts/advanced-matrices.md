---
標題： Advanced matrix 概念描述：瞭解特徵向量、特徵值和 matrix 指數，這是用來描述和模擬量子演算法的基本工具。
author： QuantumWriter uid： microsoft 量子. matrix-advanced ms. author： nawiebe@microsoft.com ms. date： 12/11/2017 ms。主題：不含 loc 的文章：
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

我們現在將矩陣的操作延伸到[*特徵值、特徵向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)和[*指數*](https://en.wikipedia.org/wiki/Matrix_exponential)，這會形成一組我們所需的基本工具，以描述和執行量子演算法。

## <a name="eigenvalues-and-eigenvectors"></a>特徵值和特徵向量 ##

假設 $ M $ 是正方形矩陣，而 $ v $ 則是不是全部零向量的向量（亦即，所有專案都等於0的向量 $ $ ）。

我們假設 $ v $ 是 M 的[*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ， $ 如果是 $ $ = 數位 c 的 Mv cv $ $ $ 。 我們說 $ c $ 是對應[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)至 eigenvector v 的 eigenvalue $ $ 。 在一般情況 $ $ 下，矩陣 M 可以將向量轉換成任何其他向量，但 eigenvector 是特殊的，因為它會保留不變，但會乘以數位。 請注意，如果 $ v $ 是具有 eigenvalue c 的 eigenvector $ $ ，則 $ av $ 也是 $ $ 具有相同 eigenvalue 的 eigenvector （適用于任何非零 a）。

例如，針對身分識別矩陣，每個向量 $ v $ 都是 eigenvalue 1 的 $ eigenvector $ 。

另舉一個例子，請考慮一個[*對角線矩陣*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D， $ 其對角線上只有非零的專案：

$$
\begin{bmatrix}
d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & & d_3 \end{bmatrix} 。
$$

向量

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 和 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

這是此矩陣的特徵向量， $ 分別具有特徵值 d_1 $ 、 $ d_2 $ 和 $ d_3 $ 。 如果 $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 是相異數位，則這些向量（及其倍數）是矩陣 d 的唯一特徵向量 $ $ 。一般而言，如果是對角矩陣，就很容易閱讀特徵值和特徵向量。 特徵值是顯示在對角線上的所有數位，而其各自的特徵向量是單位向量，其中一個專案等於 $ 1 $ ，而其餘專案則等於 $ 0 $ 。

請注意，在上述範例中，D 的特徵向量會 $ $ 形成 $ 三維向量的基礎 $ 。 「基礎」是一組向量，可讓任何向量以線性組合的方式寫入。 更明確、 $ v_1 $ 、 $ v_2 $ 和 $ v_3 $ 組成基礎，如果 $ 可以將任何向量 v $ 撰寫為 $ v a_1 v_1 + a_2 v_2 + a_3 v_3，a_1 = $ $ $ 、 $ a_2 $ 和 $ a_3 $ 的數位。

回想一下，Hermitian 矩陣（也稱為自我 adjoint）是一個複雜的方形矩陣，它等於它自己的複雜共軛轉型，而單一矩陣則是一個複雜的正方形矩陣，其反向等於其 adjoint 或複雜的共軛轉型。
對於 Hermitian 和單一矩陣，這基本上是在配量運算中唯一遇到的矩陣，有一個稱為[*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)的一般結果，它會判斷提示下列事項：對於任何 Hermitian 或單一矩陣 $ M $ ，都有一個單一 $ U， $ 例如 $ M = u ^ \dagger d U $ 適用于某個對角線矩陣 $ D $ 。此外，D 的對角線專案 $ $ 會是 M 的特徵值 $ $ 。

我們已經知道如何計算對角線矩陣 D 的特徵值和特徵向量 $ $ 。使用此定理時，我們知道如果 $ v $ 是 $ 具有 eigenvalue c 的 D eigenvector （也就是 $ $ $ $ Dv = cv $ ），則 $ U ^ \dagger v $ 會是 eigenvector，而 $ $ eigenvalue c 則是 M $ $ 。 這是因為

$$M （U ^ \dagger v） = u ^ \dagger d U （u ^ \dagger v） = U ^ \dagger d （u u ^ \dagger ） v = u ^ \dagger d v = c U ^ \dagger v。$$

## <a name="matrix-exponentials"></a>矩陣指數
[*矩陣指數*](https://en.wikipedia.org/wiki/Matrix_exponential)也可以定義為與指數函數完全相似。  矩陣 a 的矩陣指數， $ $ 可以表示為

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2！ } + \frac {答 ^ 3 } { 3！}+\cdots
$$

這一點很重要，因為配量機械時間演進是由 $ e ^ { IB } $ for Hermitian matrix $ B $ 形式的單一矩陣所描述。 基於這個理由，執行矩陣指數是量子運算的基本部分，因此問 # 會提供內建常式來描述這些作業。
有許多方法可以在傳統電腦上計算矩陣指數，而在一般的數值將逼近中，這種指數是使用危險太。  請參閱[*Cleve Moler 和 Charles Van 貸款。「用來計算矩陣指數的十九可疑方法」。SIAM 計算期刊評論20.4 （1978）： 801-836*](https://doi.org/10.1137/S00361445024180) ，取得涉及挑戰的詳細資訊。

若要瞭解如何計算矩陣的指數，最簡單的方式是透過該矩陣的特徵值和特徵向量。  具體來說，上述的 spectral 定理指出，針對每個 Hermitian 或單一矩陣， $ $ 有一個單一矩陣 $ U $ 和一個對角線矩陣 $ D $ ，例如 $ = U ^ \dagger d u $ 。 由於 unitarity 的屬性，我們擁有 $ ^ 2 = u ^ \dagger D ^ 2 u $ ，同樣地，任何 power $ p $ $ A ^ p = u ^ \dagger d ^ p u $ 。 如果我們將此取代為運算子指數的運算子定義，我們會取得：

$$
e ^ A = U ^ \dagger \left （ \boldone + d + \frac { d ^ 2 } { 2！ } + \cdots \right ）U = u ^ \dagger \begin{bmatrix} \exp （D_ { 11 } ） & 0 & \cdots & 0 \\\\ 0 & \exp （D_ { 22 } ） & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp （D_ { NN } ） \end{bmatrix} U。$$

換句話說，如果您轉換成矩陣的 eigenbasis， $ $ 則計算矩陣的指數就相當於計算矩陣特徵值的一般指數。  由於配量計算中的許多作業都牽涉到執行矩陣指數，所以轉換成矩陣 eigenbasis 以簡化執行運算子指數的這項技巧，會經常出現，而且是在許多量子演算法背後的基礎，例如本指南稍後討論的 Trotter – Plat'home co. 樣式的量子模擬方法。

另一個有用的屬性是，如果 $ b $ 同時是單一和 Hermitian，即 $ b = b ^ { -1 } = B ^ \dagger $ then $ b ^ 2 = \boldone $ 。 藉由將此規則套用至矩陣指數的上方展開，以及將 $ \boldone $ 和 $ B 詞彙群組在 $ 一起，就可以看到任何實際值 $ x 身分 $ 識別

$$e ^ { iBx } = \boldone \cos （x） + iB\sin （x）$$


手. 這項技巧特別有用，因為它可讓您瞭解動作矩陣指數所擁有的原因，即使 b 的維度以指數方式表示， $ $ 當 $ b $ 同時為單一和 Hermitian 時，特殊情況也是如此。
