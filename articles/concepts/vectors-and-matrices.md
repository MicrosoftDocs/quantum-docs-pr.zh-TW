---
title: 量子運算中的向量和矩陣
description: 瞭解如何使用向量和矩陣的基本概念。
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630195"
---
# <a name="vectors-and-matrices"></a>向量和矩陣

若要瞭解配量運算，必須熟悉向量和矩陣。 我們會提供下面簡要介紹，並建議讀者閱讀線性代數的標準參考，例如*Strang，G. （1993）。線性代數（Vol. 3）簡介。Wellesley、MA： Wellesley-康橋按下*或線上參考（例如[線性代數](http://joshua.smcvt.edu/linearalgebra/)）。

維度（或大小） $v 的資料行向量（或簡單[*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))） $ $n $ 是 $n $ 複數 $ （v_1，v_2，\ldots，v_n） $ 的集合，以資料行排列：

$ $v = \begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

Vector $v 的標準 $ 定義為 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $。 若向量的標準為 $1，則會將其視為單位標準（或稱為[*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)） $ 。 向量 $v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ 表示 $v ^ \dagger $ ，且定義為下列資料列向量，其中 $ \* $ 代表共軛複數，

$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ * & \cdots & v_n ^ * \end{bmatrix}$$

將兩個向量相乘的最常見方式是透過[*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)，也稱為「點積」。  內部產品會將一個向量投射到另一個向量，而且對於描述如何以其他更簡單的向量的總和來表達一個向量非常有價值。  $U 和 $v 之間的內部產品 $ $ （表示 $ \left \langle u），v \right \rangle $ 定義為

$ $ \langle u、v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。
$$

此標記法也允許將 vector $v 的標準 $ 寫成 $ \sqrt { \langle v，v \rangle } $。

我們可以將向量與數位相乘 $c $ 以形成新的向量，其專案會乘以 $c $ 。 我們也可以加入兩個向量 $u $ ，$v $ 形成新的向量，其專案是 $u 和 $v 專案的總和 $ $ 。 這些作業如下所示：

$ $ \mathrm{If } ~ u = \begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{ bmatrix } 、~ \mathrm{then } ~ au + bv = \begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{ bmatrix } 。
$$

大小 $m \times n 的[*矩陣*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $ 是 $ 以 $m 資料列和 $n 資料行排列之 $mn 複數的集合，如下 $ $ 所示：

$ $M = \begin{bmatrix}
M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\
M_ {m1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn } \\ \\ \end{ bmatrix } . $ $

請注意，維度 $n 的向量 $ 只是大小 $n \times 1 的矩陣 $ 。 如同向量，我們可以將矩陣與數位相乘 $c $ 以取得新的矩陣，其中每個專案都會乘以 $c $ ，而我們可以加入相同大小的兩個矩陣，以產生新的矩陣，其專案為兩個矩陣之個別專案的總和。 

## <a name="matrix-multiplication-and-tensor-products"></a>矩陣乘法和張量產品

我們也可以將維度 $m n 的兩個 $M 矩陣 $ \times $ 和 $N $ 的維度 $n \times p 相乘， $ 以取得 $ 維度 $P \times p 的新矩陣 $m，如下所示 $ ：

\begin{align}
& \begin{bmatrix}
    M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\
    M_ {m1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn}
成品bmatrix}
起點bmatrix}
N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1 p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\ \ddots\\\\
N_ {n1 } ~ ~ N_ {n2 } ~ ~ \cdots ~ ~ N_ {np}
\end{ bmatrix } = \begin{bmatrix}
P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1 p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\
P_ {m1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {mp}
成品bmatrix}
\end{align}

其中 $P 的專案 $ $P _ {ik } = \ sum_j M_ {ij} N_ {jk } $。 例如，專案 $P _ {11 } $ 是 $M 第一個資料列的內部乘積， $ 其中第一個資料行是 $N $ 。 請注意，由於向量只是一個特殊的矩陣案例，因此此定義會延伸至矩陣向量乘法。 

我們所考慮的所有矩陣都是方形矩陣，其中資料列和資料行的數目相等，或僅對應于 $1 資料行的向量 $ 。 一個特殊的正方形矩陣是[*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ ，其所有的對角線元素都等於 $1 $ ，而其餘元素等於 $0 $ ：

$ $ \boldone = \begin{bmatrix}
1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\
0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\
~ ~ \ddots\\\\
0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $

若為方形矩陣 $A $ ，我們說， $ 如果 $AB = BA = \boldone，則 $B 為[*反向*](https://en.wikipedia.org/wiki/Invertible_matrix)矩陣 $ 。 矩陣的反向不需要存在，但當它存在時，它是唯一的，而我們會將它表示 $A ^ {-1 } $。 

針對任何矩陣 $M $ ，$M 的 adjoint 或共軛轉置 $ 是一個矩陣 $N $ 讓 $N _ {ij } = M_ {ji } ^ \* $。 $M 的 adjoint $ 通常表示 $M ^ \dagger $ 。 $如果 $UU ^ \dagger = u [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) ^ \dagger U = \boldone $ 或等位，$U ^ {-1 } = U ^ \dagger，就會假設矩陣 $U 是單一的 $ 。  單一矩陣的最重要屬性可能是它們保留向量的標準。  發生這種情況的原因是 

$ $ \langle v、v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle U v，u v \rangle . $ $  

$如果 $M = M ^ \dagger，則矩陣 $M 稱為[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ 。

最後，$M 大小 $m n 和 $N 大小的兩個矩陣的[*張量產品*](https://en.wikipedia.org/wiki/Tensor_product)（或 Kronecker 產品） $ \times $ $ $p \times q $ 是較大的矩陣 $P = \otimes $ \times nq 大小的 M n $ ，而是從 $mp $ 和 $M 取得， $ 如下所示：

\begin{align}
    M \otimes N &= \begin{bmatrix}
        M_ {11 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ \ddots\\\\
        M_ {m1 } ~ ~ \cdots ~ ~ M_ {mn}
    成品bmatrix}
    \otimes \begin{bmatrix}
        N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots\\\\
        N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq}
    \end{ bmatrix } \\ \\ &= \begin{bmatrix}
        M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1n } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\
        M_ {m1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {mn } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{bmatrix}
    \end{ bmatrix } 。
\end{align}

這會更清楚地示範一些範例：

$ $ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}
        \begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}
        \\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}
    成品bmatrix}
    = \begin{ bmatrix } a c a \\ \\ d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\ 是 \end {bmatrix}
$$

及

$ $ \begin{bmatrix}
        a \ b \\ \\ c \ d \end{bmatrix}
    \otimes \begin{bmatrix}
        e \ f \\ \\ g \ h \end{bmatrix}
     = \begin{bmatrix}
    a \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    b \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    d \begin {bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    成品bmatrix}
    = \begin{bmatrix}
    ae \ af \ 是 \ bf \\ \\ ag \ ah \ bg \ bh \\ \\ ce \ cf \ df： \\ \\ cg \ ch \ dg \ dh \end{ bmatrix } 。
$$

圍繞張量產品的最後一個有用的標記慣例是，針對任何向量 $v $ 或矩陣 $M $ ，$v ^ {\otimes n } $ 或 $M ^ {\otimes n } $ 就是 $n 折迭 $ 張量產品的短期。  例如：

\begin{align}
& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } ， \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 \\ \\ \\\\ \end bmatrix } &0&1&0 0 &0&0&0 {。
\end{align}
