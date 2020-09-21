---
<span data-ttu-id="208db-101">標題： Advanced matrix 概念描述：瞭解特徵向量、特徵值和矩陣指數，這是用來描述和模擬量子演算法的基本工具。</span><span class="sxs-lookup"><span data-stu-id="208db-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="208db-102">作者： QuantumWriter uid： benbra-advanced ms. author： v-ms. date： 12/11/2017 ms. 主題：非 loc 文章：</span><span class="sxs-lookup"><span data-stu-id="208db-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="208db-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="208db-103">"Q#"</span></span>
- <span data-ttu-id="208db-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="208db-104">"$$v"</span></span>
- <span data-ttu-id="208db-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="208db-105">"$$"</span></span>
- <span data-ttu-id="208db-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="208db-106">"$$"</span></span>
- <span data-ttu-id="208db-107">"$"</span><span class="sxs-lookup"><span data-stu-id="208db-107">"$"</span></span>
- <span data-ttu-id="208db-108">"$"</span><span class="sxs-lookup"><span data-stu-id="208db-108">"$"</span></span>
- <span data-ttu-id="208db-109">"$"</span><span class="sxs-lookup"><span data-stu-id="208db-109">"$"</span></span>
- <span data-ttu-id="208db-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="208db-110">"$$"</span></span>
- <span data-ttu-id="208db-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="208db-111">"$$$"</span></span>
- <span data-ttu-id="208db-112">"$$$"</span><span class="sxs-lookup"><span data-stu-id="208db-112">"$$$"</span></span>
- <span data-ttu-id="208db-113">"$$$"</span><span class="sxs-lookup"><span data-stu-id="208db-113">"$$$"</span></span>
- <span data-ttu-id="208db-114">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="208db-114">"\cdots"</span></span>
- <span data-ttu-id="208db-115">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="208db-115">"bmatrix"</span></span>
- <span data-ttu-id="208db-116">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="208db-116">"\ddots"</span></span>
- <span data-ttu-id="208db-117">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="208db-117">"\equiv"</span></span>
- <span data-ttu-id="208db-118">"\sum"</span><span class="sxs-lookup"><span data-stu-id="208db-118">"\sum"</span></span>
- <span data-ttu-id="208db-119">"\begin"</span><span class="sxs-lookup"><span data-stu-id="208db-119">"\begin"</span></span>
- <span data-ttu-id="208db-120">"\end"</span><span class="sxs-lookup"><span data-stu-id="208db-120">"\end"</span></span>
- <span data-ttu-id="208db-121">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="208db-121">"\sqrt"</span></span>
- <span data-ttu-id="208db-122">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="208db-122">"\otimes"</span></span>
- <span data-ttu-id="208db-123">"{"</span><span class="sxs-lookup"><span data-stu-id="208db-123">"{"</span></span>
- <span data-ttu-id="208db-124">"}"</span><span class="sxs-lookup"><span data-stu-id="208db-124">"}"</span></span>
- <span data-ttu-id="208db-125">"\text"</span><span class="sxs-lookup"><span data-stu-id="208db-125">"\text"</span></span>
- <span data-ttu-id="208db-126">"\phi"</span><span class="sxs-lookup"><span data-stu-id="208db-126">"\phi"</span></span>
- <span data-ttu-id="208db-127">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="208db-127">"\kappa"</span></span>
- <span data-ttu-id="208db-128">"\psi"</span><span class="sxs-lookup"><span data-stu-id="208db-128">"\psi"</span></span>
- <span data-ttu-id="208db-129">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="208db-129">"\alpha"</span></span>
- <span data-ttu-id="208db-130">"\beta"</span><span class="sxs-lookup"><span data-stu-id="208db-130">"\beta"</span></span>
- <span data-ttu-id="208db-131">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="208db-131">"\gamma"</span></span>
- <span data-ttu-id="208db-132">"\delta"</span><span class="sxs-lookup"><span data-stu-id="208db-132">"\delta"</span></span>
- <span data-ttu-id="208db-133">"\omega"</span><span class="sxs-lookup"><span data-stu-id="208db-133">"\omega"</span></span>
- <span data-ttu-id="208db-134">"\bra"</span><span class="sxs-lookup"><span data-stu-id="208db-134">"\bra"</span></span>
- <span data-ttu-id="208db-135">"\ket"</span><span class="sxs-lookup"><span data-stu-id="208db-135">"\ket"</span></span>
- <span data-ttu-id="208db-136">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="208db-136">"\boldone"</span></span>
- <span data-ttu-id="208db-137">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="208db-137">"\\\\"</span></span>
- <span data-ttu-id="208db-138">"\\"</span><span class="sxs-lookup"><span data-stu-id="208db-138">"\\"</span></span>
- <span data-ttu-id="208db-139">"="</span><span class="sxs-lookup"><span data-stu-id="208db-139">"="</span></span>
- <span data-ttu-id="208db-140">"\frac"</span><span class="sxs-lookup"><span data-stu-id="208db-140">"\frac"</span></span>
- <span data-ttu-id="208db-141">"\text"</span><span class="sxs-lookup"><span data-stu-id="208db-141">"\text"</span></span>
- <span data-ttu-id="208db-142">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="208db-142">"\mapsto"</span></span>
- <span data-ttu-id="208db-143">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="208db-143">"\dagger"</span></span>
- <span data-ttu-id="208db-144">"\to"</span><span class="sxs-lookup"><span data-stu-id="208db-144">"\to"</span></span>
- <span data-ttu-id="208db-145">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="208db-145">"\begin{cases}"</span></span>
- <span data-ttu-id="208db-146">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="208db-146">"\end{cases}"</span></span>
- <span data-ttu-id="208db-147">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="208db-147">"\operatorname"</span></span>
- <span data-ttu-id="208db-148">"\braket"</span><span class="sxs-lookup"><span data-stu-id="208db-148">"\braket"</span></span>
- <span data-ttu-id="208db-149">"\id"</span><span class="sxs-lookup"><span data-stu-id="208db-149">"\id"</span></span>
- <span data-ttu-id="208db-150">"\expect"</span><span class="sxs-lookup"><span data-stu-id="208db-150">"\expect"</span></span>
- <span data-ttu-id="208db-151">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="208db-151">"\defeq"</span></span>
- <span data-ttu-id="208db-152">"\variance"</span><span class="sxs-lookup"><span data-stu-id="208db-152">"\variance"</span></span>
- <span data-ttu-id="208db-153">"\dd"</span><span class="sxs-lookup"><span data-stu-id="208db-153">"\dd"</span></span>
- <span data-ttu-id="208db-154">"&"</span><span class="sxs-lookup"><span data-stu-id="208db-154">"&"</span></span>
- <span data-ttu-id="208db-155">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="208db-155">"\begin{align}"</span></span>
- <span data-ttu-id="208db-156">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="208db-156">"\end{align}"</span></span>
- <span data-ttu-id="208db-157">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="208db-157">"\Lambda"</span></span>
- <span data-ttu-id="208db-158">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="208db-158">"\lambda"</span></span>
- <span data-ttu-id="208db-159">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="208db-159">"\Omega"</span></span>
- <span data-ttu-id="208db-160">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="208db-160">"\mathrm"</span></span>
- <span data-ttu-id="208db-161">"\left"</span><span class="sxs-lookup"><span data-stu-id="208db-161">"\left"</span></span>
- <span data-ttu-id="208db-162">"\right"</span><span class="sxs-lookup"><span data-stu-id="208db-162">"\right"</span></span>
- <span data-ttu-id="208db-163">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="208db-163">"\qquad"</span></span>
- <span data-ttu-id="208db-164">"\times"</span><span class="sxs-lookup"><span data-stu-id="208db-164">"\times"</span></span>
- <span data-ttu-id="208db-165">"\big"</span><span class="sxs-lookup"><span data-stu-id="208db-165">"\big"</span></span>
- <span data-ttu-id="208db-166">"\langle"</span><span class="sxs-lookup"><span data-stu-id="208db-166">"\langle"</span></span>
- <span data-ttu-id="208db-167">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="208db-167">"\rangle"</span></span>
- <span data-ttu-id="208db-168">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="208db-168">"\bigg"</span></span>
- <span data-ttu-id="208db-169">"\Big"</span><span class="sxs-lookup"><span data-stu-id="208db-169">"\Big"</span></span>
- <span data-ttu-id="208db-170">"|"</span><span class="sxs-lookup"><span data-stu-id="208db-170">"|"</span></span>
- <span data-ttu-id="208db-171">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="208db-171">"\mathbb"</span></span>
- <span data-ttu-id="208db-172">"\vec"</span><span class="sxs-lookup"><span data-stu-id="208db-172">"\vec"</span></span>
- <span data-ttu-id="208db-173">"\in"</span><span class="sxs-lookup"><span data-stu-id="208db-173">"\in"</span></span>
- <span data-ttu-id="208db-174">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="208db-174">"\texttt"</span></span>
- <span data-ttu-id="208db-175">"\ne"</span><span class="sxs-lookup"><span data-stu-id="208db-175">"\ne"</span></span>
- <span data-ttu-id="208db-176">"<"</span><span class="sxs-lookup"><span data-stu-id="208db-176">"<"</span></span>
- <span data-ttu-id="208db-177">">"</span><span class="sxs-lookup"><span data-stu-id="208db-177">">"</span></span>
- <span data-ttu-id="208db-178">"\leq"</span><span class="sxs-lookup"><span data-stu-id="208db-178">"\leq"</span></span>
- <span data-ttu-id="208db-179">"\geq"</span><span class="sxs-lookup"><span data-stu-id="208db-179">"\geq"</span></span>
- <span data-ttu-id="208db-180">"~~"</span><span class="sxs-lookup"><span data-stu-id="208db-180">"~~"</span></span>
- <span data-ttu-id="208db-181">"~"</span><span class="sxs-lookup"><span data-stu-id="208db-181">"~"</span></span>
- <span data-ttu-id="208db-182">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="208db-182">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="208db-183">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="208db-183">"\end{bmatrix}"</span></span>
- <span data-ttu-id="208db-184">"\_"</span><span class="sxs-lookup"><span data-stu-id="208db-184">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="208db-185">Advanced Matrix 概念</span><span class="sxs-lookup"><span data-stu-id="208db-185">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="208db-186">我們現在將矩陣的操作延伸至 [*特徵值、特徵向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 和 [*指數*](https://en.wikipedia.org/wiki/Matrix_exponential) ，以形成一組我們需要用來描述和實行量子演算法的基本工具。</span><span class="sxs-lookup"><span data-stu-id="208db-186">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="208db-187">特徵值和特徵向量</span><span class="sxs-lookup"><span data-stu-id="208db-187">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="208db-188">讓 $ M $ 成為正方形矩陣，而 $ v 為 $ 非所有零向量的向量 (例如，將所有專案等於 $ 0) 的向量 $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-188">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="208db-189">我們說 $ v $ 是 M 的 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ，  $ 如果有 $ $ = $ 一些數位 c 的 Mv cv $ $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-189">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="208db-190">我們說 $ 的 $ 是， [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 對應于 eigenvector $ v $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-190">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="208db-191">一般而言 $ ，矩陣 M $ 可能會將向量轉換成任何其他向量，但 eigenvector 是特殊的，因為它會保持不變，但乘以數位。</span><span class="sxs-lookup"><span data-stu-id="208db-191">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="208db-192">請注意，如果 $ v $ 是具有 eigenvalue c 的 eigenvector $ $ ，則 $ av $ 也是 eigenvector (，適用于 $ $ 具有相同 eigenvalue 的任何非零) 。</span><span class="sxs-lookup"><span data-stu-id="208db-192">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="208db-193">例如，針對身分識別矩陣，每個向量 $ v $ 都是具有 eigenvalue 1 的 eigenvector $ $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-193">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="208db-194">另舉一個範例，請考慮使用對角線 [*矩陣*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D， $ 而對角線上只有非零的專案：</span><span class="sxs-lookup"><span data-stu-id="208db-194">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="208db-195">d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & d_3 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="208db-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="208db-196">向量</span><span class="sxs-lookup"><span data-stu-id="208db-196">The vectors</span></span>

<span data-ttu-id="208db-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 和 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="208db-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="208db-198">是此矩陣的特徵向量  $ ，分別是特徵值 d_1 $ 、 $ d_2 $ 和 $ d_3 $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-198">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="208db-199">如果 $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 都是相異數位，則這些向量 (和其倍數) 是矩陣 d 的唯一特徵向量 $ $ 。一般來說，如果是對角線矩陣，就很容易就能閱讀特徵值和特徵向量。</span><span class="sxs-lookup"><span data-stu-id="208db-199">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="208db-200">特徵值是出現在對角線上的所有數位，而其個別的特徵向量是一個專案等於 $ 1 $ ，而其餘專案等於0的單位向量 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-200">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="208db-201">請注意，在上述範例中，D 的特徵向量會 $ $ 形成 $ 三維向量的基礎 $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-201">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="208db-202">「基礎」是一組向量，可將任何向量寫入為它們的線性組合。</span><span class="sxs-lookup"><span data-stu-id="208db-202">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="208db-203">更明確地來說， $ v_1 $ 、 $ v_2 $ 和 $ v_3 $ 在任何向量 $ v $ 可以撰寫為 $ v = a_1 v_1 + a_2 v_2 + a_3 v_3 a_1 $ $ $ 、 $ a_2 $ 和 $ a_3 $ 的。</span><span class="sxs-lookup"><span data-stu-id="208db-203">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="208db-204">回想一下，Hermitian 矩陣 (也稱為自我 adjoint) ，是相當於它自己的複數互補轉型的複雜正方形矩陣，而單一矩陣是複數的正方形矩陣，其反向等於其 adjoint 或複雜的下轉型。</span><span class="sxs-lookup"><span data-stu-id="208db-204">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="208db-205">針對 Hermitian 和單一矩陣（基本上是量子運算中唯一遇到的矩陣），通常會有稱為 [*光譜定理*](https://en.wikipedia.org/wiki/Spectral_theorem)的結果，它會判斷提示如下：對於任何 Hermitian 或單一矩陣 $ M $ ，有一個單一的 $ u， $ 例如， $ = \dagger $ 某些對角矩陣 d 的 m u ^ d $ u $ 。此外，D 的對角線專案 $ $ 將會是 M 的特徵值 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-205">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="208db-206">我們已經知道如何計算對角線矩陣 D 的特徵值和特徵向量 $ $ 。使用這個定理時，我們知道如果 $ v $ 是 $ 具有 eigenvalue c 的 D eigenvector （也就 $ $ $ $ 是 Dv = cv $ ），則 $ U ^ \dagger v 將會 $ 是 eigenvector of $ M $ with eigenvalue $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-206">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="208db-207">這是因為</span><span class="sxs-lookup"><span data-stu-id="208db-207">This is because</span></span>

<span data-ttu-id="208db-208">$$M (U ^ \dagger v) = U ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger) v = U ^ \dagger D v = c u ^ \dagger v。$$</span><span class="sxs-lookup"><span data-stu-id="208db-208">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="208db-209">矩陣指數</span><span class="sxs-lookup"><span data-stu-id="208db-209">Matrix Exponentials</span></span>
<span data-ttu-id="208db-210">[*矩陣指數*](https://en.wikipedia.org/wiki/Matrix_exponential)也可以與指數函式完全類似地定義。</span><span class="sxs-lookup"><span data-stu-id="208db-210">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="208db-211">矩陣 a 的矩陣指數 $ $ 可表示為</span><span class="sxs-lookup"><span data-stu-id="208db-211">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="208db-212">e ^ A = \boldone + a + \frac { a + a ^ 2 } { 2！ } + \frac {^ 3 } { 3！}+\cdots</span><span class="sxs-lookup"><span data-stu-id="208db-212">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="208db-213">這點很重要，因為量子機械時間演進是由表單 $ e ^ { IB } $ for Hermitian 矩陣 $ B $ 的單一矩陣所描述。 基於這個理由，執行矩陣指數是量子運算的基本元件，因此 Q# 提供了用來描述這些作業的內部常式。</span><span class="sxs-lookup"><span data-stu-id="208db-213">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="208db-214">實務上有許多方式可計算傳統電腦上的矩陣指數，而在一般的數值將逼近中，這類指數是使用危險危險。</span><span class="sxs-lookup"><span data-stu-id="208db-214">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="208db-215">請參閱 [*Cleve Moler 和 Charles Van 貸款。「有十九個可疑的方法可計算矩陣的指數」。SIAM 計算期刊評論 20.4 (1978) ： 801-836*](https://doi.org/10.1137/S00361445024180) 以取得相關挑戰的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="208db-215">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="208db-216">若要瞭解如何計算矩陣的指數，最簡單的方式是透過該矩陣的特徵值和特徵向量。</span><span class="sxs-lookup"><span data-stu-id="208db-216">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="208db-217">具體來說，上述的光譜定理指出，針對每個 Hermitian 或單一矩陣， $ $ 有一個單一矩陣 $ U $ 和一個對角矩陣 $ d， $ 例如 $ = U ^ \dagger d u $ 。 由於 unitarity 的屬性，我們有 $ ^ 2 = u ^ \dagger d ^ 2 u $ ，也同樣適用于任何 power $ p $ $ A ^ p = u ^ \dagger d ^ p u $ 。 如果我們把它換成運算子的 operator 定義，我們取得的是指數指數：</span><span class="sxs-lookup"><span data-stu-id="208db-217">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="208db-218">e ^ A = U ^ \dagger \left (\boldone + d + \frac { d ^ 2 } { 2！ } + \cdots \right) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 }) & 0 & \cdots & 0 \\\\ 0 0 & \exp (D_ { 22 }) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN }) \end{bmatrix} U。$$</span><span class="sxs-lookup"><span data-stu-id="208db-218">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="208db-219">換句話說，如果您轉換成矩陣 A 的 eigenbasis， $ $ 則計算矩陣指數就相當於計算矩陣特徵值的一般指數。</span><span class="sxs-lookup"><span data-stu-id="208db-219">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="208db-220">在量子運算中有許多作業牽涉到執行矩陣指數，這是轉換成矩陣 eigenbasis 以簡化執行運算子指數的技巧，而這是在本指南稍後討論的許多量子演算法（例如 Trotter – Suzuki 樣式的量子模擬方法）背後的基礎。</span><span class="sxs-lookup"><span data-stu-id="208db-220">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="208db-221">另一個有用的屬性是，如果 $ b 同時為 [單一] 和 [Hermitian]，也就是 $ $ b = b ^ { -1 } = B ^ \dagger $ then $ b ^ 2 = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="208db-221">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="208db-222">藉由將此規則套用至矩陣指數的上方展開，並將 $ \boldone $ 和 $ B 詞彙群組在 $ 一起，就可以看到任何真正的值 x 身分 $ $ 識別</span><span class="sxs-lookup"><span data-stu-id="208db-222">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="208db-223">$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x) $$</span><span class="sxs-lookup"><span data-stu-id="208db-223">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="208db-224">控制.</span><span class="sxs-lookup"><span data-stu-id="208db-224">holds.</span></span> <span data-ttu-id="208db-225">這項技巧特別有用，因為它可讓您瞭解動作矩陣指數具有的原因，即使 b 的 $ 維度 $ 是以指數方式表示，但在特殊情況下， $ b $ 同時是單一和 Hermitian。</span><span class="sxs-lookup"><span data-stu-id="208db-225">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
