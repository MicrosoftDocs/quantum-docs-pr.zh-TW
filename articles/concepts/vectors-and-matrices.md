---
title: 量子運算中的向量和矩陣
description: 瞭解如何使用向量和矩陣的基本概念。
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 076ab6242b7ae31d4936ae8505034f1f13fa4727
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904905"
---
# <a name="vectors-and-matrices"></a>向量和矩陣

若要瞭解配量運算，必須熟悉向量和矩陣。 我們會提供下面簡要介紹，並建議讀者閱讀線性代數的標準參考，例如*Strang，G. （1993）。線性代數（Vol. 3）簡介。Wellesley、MA： Wellesley-康橋按下*或線上參考（例如[線性代數](http://joshua.smcvt.edu/linearalgebra/)）。

資料行向量（或單純的[*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))） $v $ of dimension （或 size） $n $ 是 $n $ complex 數位 $ （v_1，v_2，\ldots，v_n） $ 的集合，並以資料行排列：

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

向量 $v $ 的標準定義為 $ \sqrt{\sum\_i | v\_i | ^ 2} $。 如果向量的「標準」為 $1 $，則表示其為「單位」（或稱為「[*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)」）。 向量 $v $ 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix)表示 $v ^ \dagger $，而且定義為下列資料列向量，其中 $\*$ 代表共軛複數，

$ $ \begin{bmatrix} v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

將兩個向量相乘的最常見方式是透過[*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)，也稱為「點積」。  內部產品會將一個向量投射到另一個向量，而且對於描述如何以其他更簡單的向量的總和來表達一個向量非常有價值。  $U $ 與 $v $ 之間的內部產品（表示 $ \left\langle u，v\right\rangle $）定義為

$ $ \langle u、v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n。
$$

此標記法也允許將 vector $v $ 的標準寫入為 $ \sqrt{\langle v，v\rangle} $。

我們可以將向量與數位 $c $ 來形成新向量，其專案會乘以 $c $。 我們也可以加入兩個向量 $u $ 和 $v $ 來形成新向量，其專案為 $u $ 和 $v $ 專案的總和。 這些作業如下所示：

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix}，~ \mathrm{then} ~ au + bv = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}。
$$

大小 $m \times n $ 的[*矩陣*](https://en.wikipedia.org/wiki/Matrix_(mathematics))是以 $m $ rows 和 $n $ 資料行排列 $mn $ 複數的集合，如下所示：

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1n}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {m1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {mn}\\\\ \end{bmatrix}. $ $

請注意，維度 $n $ 的向量只是大小 $n \times $1 的矩陣。 如同向量，我們可以將矩陣與數位 $c $ 來取得新的矩陣，其中每個專案都會乘以 $c $，而我們可以加入兩個相同大小的矩陣，以產生新的矩陣，其專案為兩個矩陣之個別專案的總和。 

## <a name="matrix-multiplication-and-tensor-products"></a>矩陣乘法和張量產品

我們也可以將維度的兩個矩陣 $M $ $m \times n $ 和 $N $ of dimension $n \times p $ 來取得新的矩陣 $P $ of dimension $m \times p $，如下所示：

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1n}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {m1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {mn} \end{bmatrix} \begin{bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1 p}\\\\ N_{21} ~ ~ N_{22} ~ ~ \cdots ~ ~ N_ {2p}\\\\ \ddots\\\\ N_ {n1} ~ ~ N_ {n2} ~ ~ \cdots ~ ~ N_ {np} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1 p}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2p}\\\\ \ddots\\\\ P_ {m1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {mp} \end{bmatrix} \end{align}

其中 $P $ 的專案 $P _ {ik} = \ sum_j M_ {ij} N_ {jk} $。 例如，專案 $P _{11}$ 是 $M $ 的第一個資料列的內部乘積，其中第一個資料行是 $N $。 請注意，由於向量只是一個特殊的矩陣案例，因此此定義會延伸至矩陣向量乘法。 

我們考慮的所有矩陣都是方形矩陣，其中資料列和資料行的數目相等，或僅對應于 $1 $ column 的向量。 一個特殊的正方形矩陣是[*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $，其所有的對角線元素都等於 $1 $，其餘元素等於 $0 $：

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

對於 $A $ 的正方形矩陣而言，如果 $AB = BA = \boldone $，則 $B $ 是[*反白*](https://en.wikipedia.org/wiki/Invertible_matrix)的矩陣。 矩陣的反向不需要存在，但當它存在時，它是唯一的，而我們會將它表示 $A ^{-1}$。 

針對任何 $M $ 的矩陣，$M $ 的 adjoint 或共軛轉類型是 $N $ 的矩陣，因此 $N _ {ij} = M_ {ji} ^\*$。 $M $ 的 adjoint 通常表示 $M ^ \dagger $。 我們說，如果 $UU ^ \dagger = U ^ \dagger U = \boldone $ 或同等的，$U ^{-1} = U ^ \dagger $，就會有一個矩陣 $U $ 是[*單一*](https://en.wikipedia.org/wiki/Unitary_matrix)的。  單一矩陣的最重要屬性可能是它們保留向量的標準。  發生這種情況的原因是 

$ $ \langle v、v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v，U v\rangle. $ $  

如果 $M = M ^ \dagger $，則 $M $ 的矩陣稱為「 [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) 」。

最後，兩個矩陣的[*張量產品*](https://en.wikipedia.org/wiki/Tensor_product)（或 Kronecker 產品） $M $ 大小 $m \times n $ 和 $N $ of 大小 $p \times q $ 是較大的矩陣 $P = M\otimes n $ of 大小 $mp \times nq $，而是從 $M $ 和 $N $ 取得，如下所示：

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1n} \\\\ \ddots\\\\ M_ {m1} ~ ~ \cdots ~ ~ M_ {mn} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}~ ~ \cdots ~ ~ M_ {1n} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {m1} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {mn} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1q}\\\\ \ddots\\\\ N_ {p1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} \end{bmatrix}.
\end{align}

這會更清楚地示範一些範例：

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} \\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ bc \\\\ b d \\\\ be\end {bmatrix} $ $

和

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ae \ af \ bf \\\\ ag \ ah \ bg \ bh \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \end{bmatrix}。
$$

張量產品的最後一個有用的標記慣例是，針對任何向量 $v $ 或 matrix $M $，$v ^ {\otimes n} $ 或 $M ^ {\otimes n} $ 是 $n $-折迭重複張量產品的一小手勢。  例如：

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}，\qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}，\qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 1 \end{bmatrix}、\\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}，\qquad\begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ & & 1 & 0\\0 \\ 0 \ 結束 {bmatrix}.\\\\\\\\
\end{align}
