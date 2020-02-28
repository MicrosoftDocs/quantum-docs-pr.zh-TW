---
title: 進階矩陣概念
description: 深入瞭解特徵向量、特徵值和 matrix 指數，這是用來描述和模擬量子演算法的基本工具。
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: a83911e01ad758bbcb7f701000fd58b4f1c91cd2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907574"
---
# <a name="advanced-matrix-concepts"></a>Advanced Matrix 概念 #

我們現在將矩陣的操作延伸到[*特徵值、特徵向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)和[*指數*](https://en.wikipedia.org/wiki/Matrix_exponential)，這會形成一組我們所需的基本工具，以描述和執行量子演算法。

## <a name="eigenvalues-and-eigenvectors"></a>特徵值和特徵向量 ##

讓 $M $ 成為正方形矩陣，$v $ 是不是全部零向量的向量（亦即，所有專案都等於 $0 $ 的向量）。

我們說 $v $ 是 $M $ 的[*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ，如果 $Mv = cv $ 代表某個數位 $c $。 我們說 $c $ 是對應至 eigenvector $v $ 的[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 。 在一般情況下，矩陣 $M $ 可以將向量轉換成任何其他向量，但 eigenvector 是特殊的，因為它會保留不變，除非乘以數位。 請注意，如果 $v $ 是 eigenvalue $c $ 的 eigenvector，則 $av $ 也是具有相同 eigenvalue 的 eigenvector （適用于任何非零 $a $）。

例如，對於識別矩陣，每個向量 $v $ 都是 eigenvalue $1 $ 的 eigenvector。

另舉一個例子，請考慮使用[*對角線矩陣*](https://en.wikipedia.org/wiki/Diagonal_matrix)$D $，在對角線上只有非零的專案：

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}。
$$

向量

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}、\begin{bmatrix}0 \\\\ 1 \\\\ 0 \ end {bmatrix} 和 \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ end {bmatrix} $ $

這是此矩陣的特徵向量，分別具有特徵值 $d _1 $、$d _2 $ 和 $d _3 $。 如果 $d _1 $、$d _2 $ 和 $d _3 $ 是相異數位，則這些向量（及其倍數）是矩陣 $D $ 的唯一特徵向量。 一般而言，如果是對角矩陣，就很容易閱讀特徵值和特徵向量。 特徵值是顯示在對角線上的所有數位，其各自的特徵向量就是一個專案等於 $1 $ 且剩餘的專案等於 $0 $ 的單位向量。

請注意，在上述範例中，$D $ 的特徵向量會形成 $ 3 $ 維向量的基礎。 「基礎」是一組向量，可讓任何向量以線性組合的方式寫入。 更明確地來說，$v _1 $，$v _2 $，以及 $v _3 $ form，如果任何向量 $v $ 可以撰寫成 $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $，$a _2 $ 和 $a _3 $。

回想一下，Hermitian 矩陣（也稱為自我 adjoint）是一個複雜的方形矩陣，它等於它自己的複數共軛，而單一矩陣則是一個複雜的正方形矩陣，其反向等於複數共軛。
對於 Hermitian 和單一矩陣，這基本上是在量子運算中唯一遇到的矩陣，有一個稱為[*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)的一般結果，它會判斷提示下列事項：對於任何 Hermitian 或單一矩陣 $M $，都有一個 $U $，因此 $M = U ^ \Dagger D U $ 的某個對角線矩陣 $D $。 此外，$D $ 的對角線專案會是 $M $ 的特徵值。

我們已經知道如何計算對角矩陣 $D $ 的特徵值和特徵向量。 使用此定理時，我們知道如果 $v $ 是 eigenvector $D $ with eigenvalue $c $，亦即 $Dv = cv $，則 $U ^ \dagger v $ 將是 $M $ with eigenvector $c $ 的 eigenvalue。 這是因為

$ $M （U ^ \dagger v） = U ^ \dagger D U （U ^ \dagger v） = U ^ \dagger D （U U ^ \dagger） v = U ^ \dagger D v = c U ^ \dagger v $ $

## <a name="matrix-exponentials"></a>矩陣指數
[*矩陣指數*](https://en.wikipedia.org/wiki/Matrix_exponential)也可以定義為與指數函數完全相似。  矩陣的矩陣指數 $A $ 可以表示為

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2！}+ \frac{A ^ 3} {3！}+ \cdots $ $

這一點很重要，因為配量機械時間演進是由 $e ^ {iB} $ for Hermitian matrix $B $ 的表單的單一矩陣所描述。  基於這個理由，執行矩陣指數是量子運算的基本部分，因此問 # 會提供內建常式來描述這些作業。
有許多方法可以在傳統電腦上計算矩陣指數，而在一般的數值將逼近中，這種指數是使用危險太。  請參閱[*Cleve Moler 和 Charles Van 貸款。「用來計算矩陣指數的十九可疑方法」。SIAM 計算期刊評論20.4 （1978）： 801-836*](https://doi.org/10.1137/S00361445024180) ，取得涉及挑戰的詳細資訊。

若要瞭解如何計算矩陣的指數，最簡單的方式是透過該矩陣的特徵值和特徵向量。  具體而言，上述的 spectral 定理指出每個 Hermitian 或單一矩陣 $A $ 都有一個單一矩陣 $U $ 和對角線矩陣 $D $，因此 $A = U ^ \dagger D U $。  由於 unitarity 的屬性，我們有 $A ^ 2 = U ^ \dagger D ^ 2 U $，同樣適用于任何 power $p $ $A ^ p = U ^ \dagger D ^ p U $。  如果我們將此取代為運算子指數的運算子定義，我們會取得：

$ $ e ^ A = U ^ \dagger \left （\boldone + D + \frac{D ^ 2} {2！}+ \cdots \right） U = U ^ \dagger \begin{bmatrix}\exp （D_{11}） & 0 & \cdots & 0\\\\ 0 & \exp （D_{22}） & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp （D_ {NN}） \end{bmatrix} U. $ $

換句話說，如果您轉換成矩陣的 eigenbasis $A $，那麼計算矩陣的指數就相當於計算矩陣特徵值的一般指數。  隨著量子運算中的許多作業都牽涉到執行矩陣指數，轉換成矩陣 eigenbasis 以簡化執行運算子指數的這個技巧，會經常出現，而且是許多量子演算法背後的基礎，例如Trotter –本指南稍後所討論的 Plat'home co. 樣式量子模擬方法。

另一個有用的屬性是，如果 $B $ 同時為單一和 Hermitian，也就是 $B = B ^{-1}= B ^ \dagger $，然後 $B ^ 2 = \boldone $。 藉由將此規則套用至矩陣指數的上方展開，以及將 $ \boldone $ 和 $B $ 詞彙群組在一起，可以看到任何實際值 $x $ 身分識別

$ $e ^ {iBx} = \boldone \cos （x） + iB\sin （x） $ $


手. 這項技巧特別有用，因為它可讓您瞭解動作矩陣指數所擁有的原因，即使 $B $ 的維度是以指數方式表示，當 $B $ 同時為單一和 Hermitian 時，特殊情況也是如此。
