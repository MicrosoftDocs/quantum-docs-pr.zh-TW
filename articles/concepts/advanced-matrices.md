---
title: 進階矩陣概念
description: 深入瞭解特徵向量、特徵值和 matrix 指數，這是用來描述和模擬量子演算法的基本工具。
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630141"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="3f88c-103">Advanced Matrix 概念</span><span class="sxs-lookup"><span data-stu-id="3f88c-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="3f88c-104">我們現在將矩陣的操作延伸到[*特徵值、特徵向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)和[*指數*](https://en.wikipedia.org/wiki/Matrix_exponential)，這會形成一組我們所需的基本工具，以描述和執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="3f88c-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="3f88c-105">特徵值和特徵向量</span><span class="sxs-lookup"><span data-stu-id="3f88c-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="3f88c-106">讓 $M $ 成為正方形矩陣，$v 是 $ 不是全部零向量的向量（亦即，所有專案都等於 $0 的向量 $ ）。</span><span class="sxs-lookup"><span data-stu-id="3f88c-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="3f88c-107">$ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ 如果 $Mv = cv $ $c 的某個數位，則會假設 $v 是 $M 的 eigenvector $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="3f88c-108">我們說 $c $ 是對應至 eigenvector $v 的[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="3f88c-109">在一般情況 $ 下，矩陣 $M 可以將向量轉換成任何其他向量，但 eigenvector 是特殊的，因為它會保留不變，除非乘以數位。</span><span class="sxs-lookup"><span data-stu-id="3f88c-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="3f88c-110">請注意，如果 $v $ 是 eigenvalue $c 的 eigenvector $ ，則 $av $ 也是具有相同 eigenvalue 的 eigenvector （適用于任何非零的 $a $ ）。</span><span class="sxs-lookup"><span data-stu-id="3f88c-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="3f88c-111">例如，對於識別矩陣，每個向量 $v $ 都是 eigenvalue $1 的 eigenvector $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="3f88c-112">另舉一個例子，請考慮一個[*對角線矩陣*](https://en.wikipedia.org/wiki/Diagonal_matrix)$D 在 $ 對角線上只有非零的專案：</span><span class="sxs-lookup"><span data-stu-id="3f88c-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="3f88c-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3f88c-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="3f88c-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ & 0 & d_3 \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="3f88c-115">向量</span><span class="sxs-lookup"><span data-stu-id="3f88c-115">The vectors</span></span>

<span data-ttu-id="3f88c-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } ，\begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } and \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="3f88c-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="3f88c-117">這是此矩陣的特徵向量，分別具有特徵值 $d _1 $ 、$d _2 $ 和 $d _3 $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="3f88c-118">如果 $d _1 $ 、$d _2 $ 和 $d _3 $ 是相異數位，則這些向量（及其倍數）是矩陣 $D 的唯一特徵向量 $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="3f88c-119">一般而言，如果是對角矩陣，就很容易閱讀特徵值和特徵向量。</span><span class="sxs-lookup"><span data-stu-id="3f88c-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="3f88c-120">特徵值是顯示在對角線上的所有數位，其各自的特徵向量是一個專案等於 $1 的單位向量 $ ，而其餘專案則等於 $0 $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="3f88c-121">請注意，在上述範例中，$D 的特徵向量會 $ 形成 $3 $ 維度向量的基礎。</span><span class="sxs-lookup"><span data-stu-id="3f88c-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="3f88c-122">「基礎」是一組向量，可讓任何向量以線性組合的方式寫入。</span><span class="sxs-lookup"><span data-stu-id="3f88c-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="3f88c-123">更明確地來說，$v _1 $ ，$v _2 $ ，而且 $ 如果可以將任何向量 $v $ 寫成 $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ _1 $ 、$a _2 $ 和 $a _3 $ ，則 $v _3 形成基礎。</span><span class="sxs-lookup"><span data-stu-id="3f88c-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="3f88c-124">回想一下，Hermitian 矩陣（也稱為自我 adjoint）是一個複雜的方形矩陣，它等於它自己的複數共軛，而單一矩陣則是一個複雜的正方形矩陣，其反向等於複數共軛。</span><span class="sxs-lookup"><span data-stu-id="3f88c-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="3f88c-125">對於 Hermitian 和單一矩陣（基本上是在量子運算中唯一遇到的矩陣），有一個稱為[*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)的一般結果，它會判斷提示下列事項：針對任何 Hermitian 或單一矩陣 $M $ ，有一個單一 $U， $ 因此 $M = U ^ \dagger D U $ $D $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="3f88c-126">此外，$D 的對角線專案 $ 會是 $M 的特徵值 $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="3f88c-127">我們已經知道如何計算對角矩陣 $D 的特徵值和特徵向量 $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="3f88c-128">使用此定理時，我們知道如果 $v $ 是具有 eigenvalue $c $D 的 eigenvector，也就是 $ $ $Dv = cv $ ，則 $U ^ \dagger v $ 將是 eigenvector $M $c 的 eigenvalue $ $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="3f88c-129">這是因為</span><span class="sxs-lookup"><span data-stu-id="3f88c-129">This is because</span></span>

<span data-ttu-id="3f88c-130">$ $M （U ^ \dagger v） = U ^ \dagger D U （U ^ \dagger v） = U ^ \dagger D （U U ^ \dagger） v = U ^ \dagger D v = c U ^ \dagger v $ $</span><span class="sxs-lookup"><span data-stu-id="3f88c-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="3f88c-131">矩陣指數</span><span class="sxs-lookup"><span data-stu-id="3f88c-131">Matrix Exponentials</span></span>
<span data-ttu-id="3f88c-132">[*矩陣指數*](https://en.wikipedia.org/wiki/Matrix_exponential)也可以定義為與指數函數完全相似。</span><span class="sxs-lookup"><span data-stu-id="3f88c-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="3f88c-133">矩陣 $A 的矩陣指數 $ 可以表示為</span><span class="sxs-lookup"><span data-stu-id="3f88c-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="3f88c-134">$ $ e ^ A = \boldone + A + \frac{A ^ 2 } {2！}+ \frac{A ^ 3 } {3！}+ \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="3f88c-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="3f88c-135">這一點很重要，因為配量機械時間演進是由 $e ^ {iB } $ For Hermitian matrix $B 形式的單一矩陣所描述 $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="3f88c-136">基於這個理由，執行矩陣指數是量子運算的基本部分，因此問 # 會提供內建常式來描述這些作業。</span><span class="sxs-lookup"><span data-stu-id="3f88c-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="3f88c-137">有許多方法可以在傳統電腦上計算矩陣指數，而在一般的數值將逼近中，這種指數是使用危險太。</span><span class="sxs-lookup"><span data-stu-id="3f88c-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="3f88c-138">請參閱[*Cleve Moler 和 Charles Van 貸款。「用來計算矩陣指數的十九可疑方法」。SIAM 計算期刊評論20.4 （1978）： 801-836*](https://doi.org/10.1137/S00361445024180) ，取得涉及挑戰的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3f88c-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="3f88c-139">若要瞭解如何計算矩陣的指數，最簡單的方式是透過該矩陣的特徵值和特徵向量。</span><span class="sxs-lookup"><span data-stu-id="3f88c-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="3f88c-140">具體而言，上述的 spectral 定理指出，針對每個 Hermitian 或單一矩陣 $A $ 存在一個單一矩陣 $U $ 和一個對角線矩陣 $D， $ $A = U ^ \dagger D U $ 。 由於 unitarity 的屬性，我們有 $A ^ 2 = U ^ \dagger D ^ 2 U $ ，同樣適用于任何 power $p $ $A ^ p = u ^ \dagger D ^ p u $ 。 如果我們將此取代為運算子指數的運算子定義，我們會取得：</span><span class="sxs-lookup"><span data-stu-id="3f88c-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="3f88c-141">$ $ e ^ A = U ^ \dagger \left （\boldone + D + \frac{D ^ 2 } {2！}+ \cdots \right） U = u ^ \dagger \begin{ bmatrix } \exp （D_ {11 } ） & 0 & \cdots &0 \\\\ 0 & \exp （D_ {22 } ） & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp （D_ {NN } ） \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="3f88c-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="3f88c-142">換句話說，如果您轉換成矩陣的 eigenbasis $A $ 則計算矩陣的指數就相當於計算矩陣特徵值的一般指數。</span><span class="sxs-lookup"><span data-stu-id="3f88c-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="3f88c-143">由於配量計算中的許多作業都牽涉到執行矩陣指數，所以轉換成矩陣 eigenbasis 以簡化執行運算子指數的這項技巧，會經常出現，而且是在許多量子演算法背後的基礎，例如本指南稍後討論的 Trotter – Plat'home co. 樣式的量子模擬方法。</span><span class="sxs-lookup"><span data-stu-id="3f88c-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="3f88c-144">另一個有用的屬性是，如果 $B $ 同時為 Hermitian，亦即 $B = b ^ {-1 } = b ^ \dagger， $ 則 $B ^ 2 = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="3f88c-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="3f88c-145">藉由將此規則套用至矩陣指數的上方展開，以及將 $ \boldone $ 和 $B 詞彙群組在 $ 一起，就可以看到任何實際值 $x 身分 $ 識別</span><span class="sxs-lookup"><span data-stu-id="3f88c-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="3f88c-146">$ $e ^ {iBx } = \boldone \cos （x） + iB\sin （x） $ $</span><span class="sxs-lookup"><span data-stu-id="3f88c-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="3f88c-147">手.</span><span class="sxs-lookup"><span data-stu-id="3f88c-147">holds.</span></span> <span data-ttu-id="3f88c-148">這項技巧特別有用，因為它可讓您瞭解動作矩陣指數所擁有的原因，即使 $B 的維度是以指數方式呈現，但 $ $B $ 同時為單一和 Hermitian。</span><span class="sxs-lookup"><span data-stu-id="3f88c-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
