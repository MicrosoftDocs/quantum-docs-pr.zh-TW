---
標題：量子運算描述中的向量和矩陣：瞭解如何使用向量和矩陣的基本概念。
author： QuantumWriter uid： benbra ms. ms. date： 12/11/2017 ms. 主題：概念非 loc：
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

# <a name="vectors-and-matrices"></a>向量和矩陣

對向量和矩陣的熟悉程度，是瞭解量子運算的關鍵。 我們提供以下的簡短簡介，並且有興趣的讀者建議您閱讀線性代數的標準參考，例如 *Strang、g. (1993) 。線性代數的簡介 (Vol. 3) 。Wellesley，MA： Wellesley-Cambridge 按下* 或線上參考，例如 [線性代數](http://joshua.smcvt.edu/linearalgebra/)。

資料行向量 (或單純是 [*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ 的維度 (或大小) $ n $ 是 n 複數的集合 $ $ $ ， (v_1、v_2、\ldots、v_n) $ 排列成資料行：

$$v =\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

向量 v 的標準 $ $ 定義為 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ 。 向量稱為「單位」（ (），或者，如果其標準為1，則會被稱為 [*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。 向量 v 的 [*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 會 $ 以 v ^ 表示， \dagger $ 並定義為下列資料列向量 $ \* $ ，其中表示共軛複數。

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

將兩個向量相乘的最常見方法是透過 [*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)（也稱為「點」產品）。  內部產品可將一個向量投射到另一個向量，而且很有説明，可描述如何以其他更簡單的向量的總和來表達一個向量。  U 和 v 之間的內部產品 $ $ $ $ （表示 $ \left \langle u、v） \right \rangle $ 定義為

$$
\langleu，v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。
$$

此標記法也可讓向量 v 的 $ 標準 $ 撰寫為 $ \sqrt { \langle v，v \rangle } $ 。

我們可以將向量乘以數位 $ c $ 來形成新的向量，其專案會乘以 $ c $ 。 我們也可以新增兩個向量 $ u $ 和 $ v $ 來形成新的向量，其專案為 $ u $ 和 v 專案的總和 $ $ 。 這些作業如下所示：

$$\mathrm{If } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { 和}~
V =\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} ， ~ \mathrm { 則}~
au + bv =\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} 。
$$

大小[](https://en.wikipedia.org/wiki/Matrix_(mathematics))為 $ m n 的 \times 矩陣 $ 是 $ mn 複數的集合 $ ，以 m 個 $ 資料 $ 列和 n 個數據行排列， $ $ 如下所示：

$$M = 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
\ddots\\\\
M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\
\end{bmatrix}.$$

請注意，維度 n 的 $ 向量 $ 只是大小為 $ n 1 的 \times 矩陣 $ 。 如同向量，我們可以將矩陣與數位 c 相乘， $ $ 以取得新的矩陣，其中每個專案都與 $ c 相乘 $ ，而且我們可以加入兩個相同大小的矩陣，以產生新的矩陣，其專案是兩個矩陣之個別專案的總和。 

## <a name="matrix-multiplication-and-tensor-products"></a>矩陣乘法和 Tensor 產品

我們也可以將維度 $ m n 和 n 的兩個矩陣 m 乘以維度 $ $ \times $ $ $ $ n \times p， $ 以取得 $ $ 維度 $ m p 的 \times $ 新矩陣 p，如下所示：

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

其中 P 的專案 $ $ 是 $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。 例如， $ P_ 11 的專案 { } $ 是 M 的第一個資料列的內部乘積 $ $ ，第一個資料行是 $ N $ 。請注意，因為向量只是矩陣的特殊案例，所以這個定義會延伸至矩陣向量乘法。 

我們所考慮的所有矩陣都是正方形矩陣，其中資料列和資料行的數目相等，或僅對應至1個數據行的向量 $ $ 。 一個特殊的正方形矩陣是 [*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ 其所有對角線元素等於 $ 1 $ ，其餘元素等於 $ 0 $ ：

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$

如果是正方形矩陣 $ a $ ，則 $ $ 如果 AB BA，則會將矩陣 B 作為 [*反向*](https://en.wikipedia.org/wiki/Invertible_matrix) $ = = \boldone $ 。 矩陣的反向需要不存在，但當其存在時，就表示它是唯一的，而且我們會將它表示 $ 為 ^ { -1 } $ 。 

對於任何矩陣 $ m $ ，M 的 adjoint 或共軛變換 $ $ 是矩陣 N， $ $ 因此 $ N_ { ij } = M_ { ji } ^ \* $ 。 M 的 adjoint $ $ 通常是以 $ m ^ 表示 \dagger $ 。 假設矩陣 $ u $ 是 [*單一*](https://en.wikipedia.org/wiki/Unitary_matrix)的，如果是 $ UU ^ \dagger = u ^ \dagger u = \boldone $ 或等同的 $ u ^ { -1 } = u ^ \dagger $ 。  單一矩陣的最重要屬性可能是它們保留向量的標準。  發生這種情況的原因是 

$$\langlev，v v \rangle = ^ \dagger v = v ^ \dagger u ^ { -1 } U v v = ^ \dagger u ^ \dagger u v = \langle u v. u v \rangle 。$$  

$ $ [](https://en.wikipedia.org/wiki/Hermitian_matrix)如果 $ m m ^，則會將矩陣 m 視為 Hermitian = \dagger $ 。

最後， [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker product) 兩個大小為 $ $ m n 的 $ 矩陣 \times $ ，而 $ n $ 的大小 $ p \times q $ 則是大型 $ mp nq 大小的矩陣 p = M \otimes n $ $ \times $ ，而且是從 $ M $ 和 $ n $ 取得，如下所示：

\begin{align}
    M \otimes N &=
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

以下是更好的示範範例：

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}
        \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}
$$

及

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d \end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g h h \end{bmatrix}
     =
    \begin{bmatrix}
    的\begin{bmatrix}
    e \ f \\\\ g h h \end{bmatrix}
    B\begin{bmatrix}
    e \ f \\\\ g h h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g h h \end{bmatrix}
    D\begin{bmatrix}
    e \ f \\\\ g h h \end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    ae \ af \ bf \\\\
    ag \ ah \ bg \ bh \\\\
    ce \ cf \ de \ df \\\\
    cg \ ch \ dg \ dh \end{bmatrix} 。
$$

關於 tensor 產品的最後一個實用標記慣例，就是，針對任何向量 $ v $ 或矩陣 $ M $ ， $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 都是對 $ n $ 折迭重複 tensor 產品的簡短。  例如：

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} 、\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 0 0 0 } = \begin{bmatrix} & & & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & \\\\ & & & \end{bmatrix} 0 1 0 0 0 0。
\end{align}
