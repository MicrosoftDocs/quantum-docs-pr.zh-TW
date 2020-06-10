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
# <a name="vectors-and-matrices"></a><span data-ttu-id="3685e-103">向量和矩陣</span><span class="sxs-lookup"><span data-stu-id="3685e-103">Vectors and Matrices</span></span>

<span data-ttu-id="3685e-104">若要瞭解配量運算，必須熟悉向量和矩陣。</span><span class="sxs-lookup"><span data-stu-id="3685e-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="3685e-105">我們會提供下面簡要介紹，並建議讀者閱讀線性代數的標準參考，例如*Strang，G. （1993）。線性代數（Vol. 3）簡介。Wellesley、MA： Wellesley-康橋按下*或線上參考（例如[線性代數](http://joshua.smcvt.edu/linearalgebra/)）。</span><span class="sxs-lookup"><span data-stu-id="3685e-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="3685e-106">維度（或大小） $v 的資料行向量（或簡單[*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))） $ $n $ 是 $n $ 複數 $ （v_1，v_2，\ldots，v_n） $ 的集合，以資料行排列：</span><span class="sxs-lookup"><span data-stu-id="3685e-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="3685e-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="3685e-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-108">v_1\\\\</span></span>
<span data-ttu-id="3685e-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-109">v_2\\\\</span></span>
<span data-ttu-id="3685e-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-110">\vdots\\\\</span></span>
<span data-ttu-id="3685e-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="3685e-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="3685e-112">Vector $v 的標準 $ 定義為 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $。</span><span class="sxs-lookup"><span data-stu-id="3685e-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="3685e-113">若向量的標準為 $1，則會將其視為單位標準（或稱為[*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)） $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="3685e-114">向量 $v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ 表示 $v ^ \dagger $ ，且定義為下列資料列向量，其中 $ \* $ 代表共軛複數，</span><span class="sxs-lookup"><span data-stu-id="3685e-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="3685e-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vdots \\ \\ v_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } v_1 ^ \* & \cdots & v_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="3685e-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="3685e-116">將兩個向量相乘的最常見方式是透過[*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)，也稱為「點積」。</span><span class="sxs-lookup"><span data-stu-id="3685e-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="3685e-117">內部產品會將一個向量投射到另一個向量，而且對於描述如何以其他更簡單的向量的總和來表達一個向量非常有價值。</span><span class="sxs-lookup"><span data-stu-id="3685e-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="3685e-118">$U 和 $v 之間的內部產品 $ $ （表示 $ \left \langle u），v \right \rangle $ 定義為</span><span class="sxs-lookup"><span data-stu-id="3685e-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="3685e-119">$ $ \langle u、v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。</span><span class="sxs-lookup"><span data-stu-id="3685e-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="3685e-120">此標記法也允許將 vector $v 的標準 $ 寫成 $ \sqrt { \langle v，v \rangle } $。</span><span class="sxs-lookup"><span data-stu-id="3685e-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="3685e-121">我們可以將向量與數位相乘 $c $ 以形成新的向量，其專案會乘以 $c $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="3685e-122">我們也可以加入兩個向量 $u $ ，$v $ 形成新的向量，其專案是 $u 和 $v 專案的總和 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="3685e-123">這些作業如下所示：</span><span class="sxs-lookup"><span data-stu-id="3685e-123">These operations are depicted below:</span></span>

<span data-ttu-id="3685e-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="3685e-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-125">u_1\\\\</span></span>
<span data-ttu-id="3685e-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-126">u_2\\\\</span></span>
<span data-ttu-id="3685e-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-127">\vdots\\\\</span></span>
<span data-ttu-id="3685e-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-129">v_1\\\\</span></span>
    <span data-ttu-id="3685e-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-130">v_2\\\\</span></span>
    <span data-ttu-id="3685e-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-131">\vdots\\\\</span></span>
    <span data-ttu-id="3685e-132">v_n \end{ bmatrix } 、~ \mathrm{then } ~ au + bv = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="3685e-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="3685e-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="3685e-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-135">\vdots\\\\</span></span>
<span data-ttu-id="3685e-136">au_n + bv_n \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="3685e-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="3685e-137">大小 $m \times n 的[*矩陣*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $ 是 $ 以 $m 資料列和 $n 資料行排列之 $mn 複數的集合，如下 $ $ 所示：</span><span class="sxs-lookup"><span data-stu-id="3685e-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="3685e-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="3685e-139">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="3685e-140">M_ {m1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="3685e-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="3685e-141">請注意，維度 $n 的向量 $ 只是大小 $n \times 1 的矩陣 $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="3685e-142">如同向量，我們可以將矩陣與數位相乘 $c $ 以取得新的矩陣，其中每個專案都會乘以 $c $ ，而我們可以加入相同大小的兩個矩陣，以產生新的矩陣，其專案為兩個矩陣之個別專案的總和。</span><span class="sxs-lookup"><span data-stu-id="3685e-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="3685e-143">矩陣乘法和張量產品</span><span class="sxs-lookup"><span data-stu-id="3685e-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="3685e-144">我們也可以將維度 $m n 的兩個 $M 矩陣 $ \times $ 和 $N $ 的維度 $n \times p 相乘， $ 以取得 $ 維度 $P \times p 的新矩陣 $m，如下所示 $ ：</span><span class="sxs-lookup"><span data-stu-id="3685e-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="3685e-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="3685e-145">\begin{align}</span></span>
<span data-ttu-id="3685e-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-147">M_ {11 } ~ ~ M_ {12 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ M_ {21 } ~ ~ M_ {22 } ~ ~ \cdots ~ ~ M_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="3685e-148">M_ {m1 } ~ ~ M_ {m2 } ~ ~ \cdots ~ ~ M_ {mn}</span><span class="sxs-lookup"><span data-stu-id="3685e-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="3685e-149">成品bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-149">\end{bmatrix}</span></span>
<span data-ttu-id="3685e-150">起點bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-150">\begin{bmatrix}</span></span>
<span data-ttu-id="3685e-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cdots ~ ~ N_ {1 p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cdots ~ ~ N_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="3685e-152">N_ {n1 } ~ ~ N_ {n2 } ~ ~ \cdots ~ ~ N_ {np}</span><span class="sxs-lookup"><span data-stu-id="3685e-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="3685e-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="3685e-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1 p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="3685e-155">P_ {m1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {mp}</span><span class="sxs-lookup"><span data-stu-id="3685e-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="3685e-156">成品bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-156">\end{bmatrix}</span></span>
<span data-ttu-id="3685e-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3685e-157">\end{align}</span></span>

<span data-ttu-id="3685e-158">其中 $P 的專案 $ $P _ {ik } = \ sum_j M_ {ij} N_ {jk } $。</span><span class="sxs-lookup"><span data-stu-id="3685e-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="3685e-159">例如，專案 $P _ {11 } $ 是 $M 第一個資料列的內部乘積， $ 其中第一個資料行是 $N $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="3685e-160">請注意，由於向量只是一個特殊的矩陣案例，因此此定義會延伸至矩陣向量乘法。</span><span class="sxs-lookup"><span data-stu-id="3685e-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="3685e-161">我們所考慮的所有矩陣都是方形矩陣，其中資料列和資料行的數目相等，或僅對應于 $1 資料行的向量 $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="3685e-162">一個特殊的正方形矩陣是[*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ ，其所有的對角線元素都等於 $1 $ ，而其餘元素等於 $0 $ ：</span><span class="sxs-lookup"><span data-stu-id="3685e-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="3685e-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="3685e-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="3685e-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="3685e-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="3685e-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="3685e-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="3685e-168">若為方形矩陣 $A $ ，我們說， $ 如果 $AB = BA = \boldone，則 $B 為[*反向*](https://en.wikipedia.org/wiki/Invertible_matrix)矩陣 $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="3685e-169">矩陣的反向不需要存在，但當它存在時，它是唯一的，而我們會將它表示 $A ^ {-1 } $。</span><span class="sxs-lookup"><span data-stu-id="3685e-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="3685e-170">針對任何矩陣 $M $ ，$M 的 adjoint 或共軛轉置 $ 是一個矩陣 $N $ 讓 $N _ {ij } = M_ {ji } ^ \* $。</span><span class="sxs-lookup"><span data-stu-id="3685e-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="3685e-171">$M 的 adjoint $ 通常表示 $M ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="3685e-172">$如果 $UU ^ \dagger = u [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) ^ \dagger U = \boldone $ 或等位，$U ^ {-1 } = U ^ \dagger，就會假設矩陣 $U 是單一的 $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="3685e-173">單一矩陣的最重要屬性可能是它們保留向量的標準。</span><span class="sxs-lookup"><span data-stu-id="3685e-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="3685e-174">發生這種情況的原因是</span><span class="sxs-lookup"><span data-stu-id="3685e-174">This happens because</span></span> 

<span data-ttu-id="3685e-175">$ $ \langle v、v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } U v = v ^ \Dagger u ^ \Dagger u v = \Langle U v，u v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="3685e-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="3685e-176">$如果 $M = M ^ \dagger，則矩陣 $M 稱為[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ 。</span><span class="sxs-lookup"><span data-stu-id="3685e-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="3685e-177">最後，$M 大小 $m n 和 $N 大小的兩個矩陣的[*張量產品*](https://en.wikipedia.org/wiki/Tensor_product)（或 Kronecker 產品） $ \times $ $ $p \times q $ 是較大的矩陣 $P = \otimes $ \times nq 大小的 M n $ ，而是從 $mp $ 和 $M 取得， $ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="3685e-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="3685e-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="3685e-178">\begin{align}</span></span>
    <span data-ttu-id="3685e-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-180">M_ {11 } ~ ~ \cdots ~ ~ M_ {1n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="3685e-181">M_ {m1 } ~ ~ \cdots ~ ~ M_ {mn}</span><span class="sxs-lookup"><span data-stu-id="3685e-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="3685e-182">成品bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-182">\end{bmatrix}</span></span>
    <span data-ttu-id="3685e-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-184">N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="3685e-185">N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq}</span><span class="sxs-lookup"><span data-stu-id="3685e-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="3685e-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {1n } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="3685e-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="3685e-188">M_ {m1 } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{ bmatrix } ~ ~ \cdots ~ ~ M_ {mn } \begin{ bmatrix } N_ {11 } ~ ~ \cdots ~ ~ N_ {1q } \\ \\ \ddots \\\\ N_ {p1 } ~ ~ \cdots ~ ~ N_ {pq } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="3685e-189">\end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="3685e-189">\end{bmatrix}.</span></span>
<span data-ttu-id="3685e-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3685e-190">\end{align}</span></span>

<span data-ttu-id="3685e-191">這會更清楚地示範一些範例：</span><span class="sxs-lookup"><span data-stu-id="3685e-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="3685e-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="3685e-195">\\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="3685e-196">成品bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-196">\end{bmatrix}</span></span>
    <span data-ttu-id="3685e-197">= \begin{ bmatrix } a c a \\ \\ d \\ \\ a e \\ \\ b c \\ \\ b d \\ \\ 是 \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="3685e-198">及</span><span class="sxs-lookup"><span data-stu-id="3685e-198">and</span></span>

<span data-ttu-id="3685e-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="3685e-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="3685e-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="3685e-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-204">a \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3685e-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3685e-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3685e-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="3685e-212">成品bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-212">\end{bmatrix}</span></span>
    <span data-ttu-id="3685e-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="3685e-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="3685e-214">ae \ af \ 是 \ bf \\ \\ ag \ ah \ bg \ bh \\ \\ ce \ cf \ df： \\ \\ cg \ ch \ dg \ dh \end{ bmatrix } 。</span><span class="sxs-lookup"><span data-stu-id="3685e-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="3685e-215">圍繞張量產品的最後一個有用的標記慣例是，針對任何向量 $v $ 或矩陣 $M $ ，$v ^ {\otimes n } $ 或 $M ^ {\otimes n } $ 就是 $n 折迭 $ 張量產品的短期。</span><span class="sxs-lookup"><span data-stu-id="3685e-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="3685e-216">例如：</span><span class="sxs-lookup"><span data-stu-id="3685e-216">For example:</span></span>

<span data-ttu-id="3685e-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="3685e-217">\begin{align}</span></span>
<span data-ttu-id="3685e-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } ， \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ，\qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 \\ \\ 0 \\ \\ \\\\ \end bmatrix } &0&1&0 0 &0&0&0 {。</span><span class="sxs-lookup"><span data-stu-id="3685e-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="3685e-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="3685e-219">\end{align}</span></span>
