---
標題：配量計算的向量和矩陣描述：瞭解如何使用向量和矩陣的基本概念。
author： QuantumWriter uid： microsoft 量子.. m. i m. nawiebe@microsoft.com 日期：12/11/2017 毫秒。主題：文章不存在：
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

# <a name="vectors-and-matrices"></a>向量和矩陣

若要瞭解配量運算，必須熟悉向量和矩陣。 我們會提供下面簡要介紹，並建議讀者閱讀線性代數的標準參考，例如*Strang、G. (1993) 。 (Vol 的線性代數簡介。 3) 。Wellesley、MA： Wellesley-康橋按下*或線上參考（例如[線性代數](http://joshua.smcvt.edu/linearalgebra/)）。

資料行向量 (或單純的[*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ 的維度 (或大小) $ n $ 是 n 複數的集合， $ $ $ (v_1，v_2，\ldots，v_n) $ 排列為資料行：

$$&=\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n\end{bmatrix}$$

向量 v 的標準 $ $ 定義為 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ 。 向量稱為「單位」（ (），或者，如果它的「標準」是1，則稱為「[*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。 向量 v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 是 $ 以 v ^ 表示 \dagger $ ，且定義為下列資料列向量 $ \* $ ，其中代表共軛複數。

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

將兩個向量相乘的最常見方式是透過[*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)，也稱為「點積」。  內部產品會將一個向量投射到另一個向量，而且對於描述如何以其他更簡單的向量的總和來表達一個向量非常有價值。  U 和 v 之間的內部產品 $ $ $ $ （表示 $ \left \langle u、v） \right \rangle $ 定義為

$$
\langleu、v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。
$$

此標記法也允許將向量 v 的 $ 標準 $ 寫成 $ \sqrt { \langle v，v \rangle } $ 。

我們可以將向量與數位 c 相乘 $ $ ，以形成新的向量，其專案會乘以 $ c $ 。 我們也可以加入兩個向量 $ u $ 和 $ v $ 來形成新的向量，其專案為 $ u $ 和 v 專案的總和 $ $ 。 這些作業如下所示：

$$\mathrm{若為 } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { 和}~
&=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} ， ~ \mathrm { 然後}~
au + bv=\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} 。
$$

大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))為 $ m n 的 \times 矩陣 $ 是 $ $ 以 m 個數據列和 n 個數據行排列之 mn 複數的集合，如下 $ $ $ $ 所示：

$$分鐘= 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
\ddots\\\\
M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\
\end{bmatrix}.$$

請注意，維度 n 的 $ 向量 $ 只是大小為 $ n 1 的 \times 矩陣 $ 。 如同向量，我們可以將矩陣與數位 $ c 相乘 $ 以取得新的矩陣，其中每個專案都會乘以 $ c $ ，而我們可以加入相同大小的兩個矩陣，以產生新的矩陣，其專案為兩個矩陣之個別專案的總和。 

## <a name="matrix-multiplication-and-tensor-products"></a>矩陣乘法和張量產品

我們也可以 $ 將維度 m n 的兩個矩陣 m $ $ \times $ 和 $ n $ 個維度 $ n p 相乘， \times $ 以取得 $ $ 維度 m p 的新矩陣 p $ ，如下所示 \times $ ：

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
    M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
    \ddots\\\\
    M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1 p}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\
\ddots\\\\
N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1 p}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\
\ddots\\\\
P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}
\end{bmatrix}
\end{align}

其中 P 的專案 $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。 例如， $ P_ 11 的專案 { } $ 是 M 的第一個資料列的內部乘積 $ ， $ 其中第一個資料行是 $ N $ 。請注意，由於向量只是一個特殊的矩陣案例，因此此定義會延伸至矩陣向量乘法。 

我們考慮的所有矩陣都是方形矩陣，其中資料列和資料行的數目相等，或只對應于1個數據行的向量 $ $ 。 一個特殊的正方形矩陣是[*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ ，其所有的對角線元素都等於 $ 1 $ ，其餘元素則等於 $ 0 $ ：

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$

若為正方形矩陣 $ a $ ，我們假設矩陣 $ B $ 是其[*反向*](https://en.wikipedia.org/wiki/Invertible_matrix)的（如果 $ AB BA） = = \boldone $ 。 矩陣的反向不需要存在，但當它存在時，它是唯一的，而我們表示它是 $ ^ { -1 } $ 。 

對於任何矩陣 $ m $ 而言，m 的 adjoint 或共軛 $ 轉 $ 類型是一個矩陣 $ N， $ 因此 $ N_ { ij } = M_ { ji } ^ \* $ 。 M 的 adjoint $ $ 通常是以 $ m ^ 表示 \dagger $ 。 我們說 $ $ ，如果有[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ UU ^ \dagger = u ^ \dagger u 或對等的 = \boldone $ $ u ^ { -1 } = U ^ \dagger $ ，矩陣 U 就是單一。  單一矩陣的最重要屬性可能是它們保留向量的標準。  發生這種情況的原因是 

$$\langlev，v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v 2，u v \rangle 。$$  

$ $ 如果[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ m = m ^ \dagger $ ，則矩陣 M 稱為 Hermitian。

最後，[*張量產品*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker 產品) ， $ 大小為 m n 的兩個矩陣 m， $ $ \times $ 而大小為 $ $ $ p q， \times $ 則是較大的矩陣 $ p = M \otimes n $ 大小的 $ mp \times nq $ ，並從 $ M $ 和 n 取得， $ $ 如下所示：

\begin{align}
    M \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\
        \ddots\\\\
        M_ { m1 } ~~ \cdots ~~ M_ { mn  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\
        \ddots\\\\
        N_ { p1 } ~~ \cdots ~~ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

這會更清楚地示範一些範例：

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        a \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ 是\end{bmatrix}
$$

和

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h\end{bmatrix}
     =
    \begin{bmatrix}
    為\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    位元組\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    d\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    ae \ af \ bf\\\\
    ag \ ah \ bg \ bh\\\\
    ce \ cf \ de \ df\\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。
$$

張量產品的最後一個有用的標記慣例是，對於任何向量 $ v $ 或矩陣 $ M 而言， $ $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 是針對 $ n $ 折重複張量產品的短期。  例如︰

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1- \\\\ 1 \\\\ -1 \\\\ 1 \end{bmatrix} ，\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ， \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & \end{bmatrix} 。
\end{align}
