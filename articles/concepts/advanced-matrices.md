---
<span data-ttu-id="6f066-101">標題： Advanced matrix 概念描述：瞭解特徵向量、特徵值和 matrix 指數，這是用來描述和模擬量子演算法的基本工具。</span><span class="sxs-lookup"><span data-stu-id="6f066-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="6f066-102">author： QuantumWriter uid： microsoft 量子. matrix-advanced ms. author： nawiebe@microsoft.com ms. date： 12/11/2017 ms。主題：不含 loc 的文章：</span><span class="sxs-lookup"><span data-stu-id="6f066-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="6f066-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="6f066-103">"$$"</span></span>
- <span data-ttu-id="6f066-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="6f066-104">"$$"</span></span>
- <span data-ttu-id="6f066-105">"$"</span><span class="sxs-lookup"><span data-stu-id="6f066-105">"$"</span></span>
- <span data-ttu-id="6f066-106">"$"</span><span class="sxs-lookup"><span data-stu-id="6f066-106">"$"</span></span>
- <span data-ttu-id="6f066-107">"$"</span><span class="sxs-lookup"><span data-stu-id="6f066-107">"$"</span></span>
- <span data-ttu-id="6f066-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="6f066-108">"$$"</span></span>
- <span data-ttu-id="6f066-109">"$$$"</span><span class="sxs-lookup"><span data-stu-id="6f066-109">"$$$"</span></span>
- <span data-ttu-id="6f066-110">"$$$"</span><span class="sxs-lookup"><span data-stu-id="6f066-110">"$$$"</span></span>
- <span data-ttu-id="6f066-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="6f066-111">"$$$"</span></span>
- <span data-ttu-id="6f066-112">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="6f066-112">"\cdots"</span></span>
- <span data-ttu-id="6f066-113">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="6f066-113">"bmatrix"</span></span>
- <span data-ttu-id="6f066-114">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="6f066-114">"\ddots"</span></span>
- <span data-ttu-id="6f066-115">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="6f066-115">"\equiv"</span></span>
- <span data-ttu-id="6f066-116">"\sum"</span><span class="sxs-lookup"><span data-stu-id="6f066-116">"\sum"</span></span>
- <span data-ttu-id="6f066-117">"\begin"</span><span class="sxs-lookup"><span data-stu-id="6f066-117">"\begin"</span></span>
- <span data-ttu-id="6f066-118">"\end"</span><span class="sxs-lookup"><span data-stu-id="6f066-118">"\end"</span></span>
- <span data-ttu-id="6f066-119">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="6f066-119">"\sqrt"</span></span>
- <span data-ttu-id="6f066-120">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="6f066-120">"\otimes"</span></span>
- <span data-ttu-id="6f066-121">"{"</span><span class="sxs-lookup"><span data-stu-id="6f066-121">"{"</span></span>
- <span data-ttu-id="6f066-122">"}"</span><span class="sxs-lookup"><span data-stu-id="6f066-122">"}"</span></span>
- <span data-ttu-id="6f066-123">"\text"</span><span class="sxs-lookup"><span data-stu-id="6f066-123">"\text"</span></span>
- <span data-ttu-id="6f066-124">"\phi"</span><span class="sxs-lookup"><span data-stu-id="6f066-124">"\phi"</span></span>
- <span data-ttu-id="6f066-125">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="6f066-125">"\kappa"</span></span>
- <span data-ttu-id="6f066-126">"\psi"</span><span class="sxs-lookup"><span data-stu-id="6f066-126">"\psi"</span></span>
- <span data-ttu-id="6f066-127">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="6f066-127">"\alpha"</span></span>
- <span data-ttu-id="6f066-128">"\beta"</span><span class="sxs-lookup"><span data-stu-id="6f066-128">"\beta"</span></span>
- <span data-ttu-id="6f066-129">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="6f066-129">"\gamma"</span></span>
- <span data-ttu-id="6f066-130">"\delta"</span><span class="sxs-lookup"><span data-stu-id="6f066-130">"\delta"</span></span>
- <span data-ttu-id="6f066-131">"\omega"</span><span class="sxs-lookup"><span data-stu-id="6f066-131">"\omega"</span></span>
- <span data-ttu-id="6f066-132">"\bra"</span><span class="sxs-lookup"><span data-stu-id="6f066-132">"\bra"</span></span>
- <span data-ttu-id="6f066-133">"\ket"</span><span class="sxs-lookup"><span data-stu-id="6f066-133">"\ket"</span></span>
- <span data-ttu-id="6f066-134">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="6f066-134">"\boldone"</span></span>
- <span data-ttu-id="6f066-135">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="6f066-135">"\\\\"</span></span>
- <span data-ttu-id="6f066-136">"\\"</span><span class="sxs-lookup"><span data-stu-id="6f066-136">"\\"</span></span>
- <span data-ttu-id="6f066-137">"="</span><span class="sxs-lookup"><span data-stu-id="6f066-137">"="</span></span>
- <span data-ttu-id="6f066-138">"\frac"</span><span class="sxs-lookup"><span data-stu-id="6f066-138">"\frac"</span></span>
- <span data-ttu-id="6f066-139">"\text"</span><span class="sxs-lookup"><span data-stu-id="6f066-139">"\text"</span></span>
- <span data-ttu-id="6f066-140">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="6f066-140">"\mapsto"</span></span>
- <span data-ttu-id="6f066-141">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="6f066-141">"\dagger"</span></span>
- <span data-ttu-id="6f066-142">"\to"</span><span class="sxs-lookup"><span data-stu-id="6f066-142">"\to"</span></span>
- <span data-ttu-id="6f066-143">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="6f066-143">"\begin{cases}"</span></span>
- <span data-ttu-id="6f066-144">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="6f066-144">"\end{cases}"</span></span>
- <span data-ttu-id="6f066-145">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="6f066-145">"\operatorname"</span></span>
- <span data-ttu-id="6f066-146">"\braket"</span><span class="sxs-lookup"><span data-stu-id="6f066-146">"\braket"</span></span>
- <span data-ttu-id="6f066-147">"\id"</span><span class="sxs-lookup"><span data-stu-id="6f066-147">"\id"</span></span>
- <span data-ttu-id="6f066-148">"\expect"</span><span class="sxs-lookup"><span data-stu-id="6f066-148">"\expect"</span></span>
- <span data-ttu-id="6f066-149">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="6f066-149">"\defeq"</span></span>
- <span data-ttu-id="6f066-150">"\variance"</span><span class="sxs-lookup"><span data-stu-id="6f066-150">"\variance"</span></span>
- <span data-ttu-id="6f066-151">"\dd"</span><span class="sxs-lookup"><span data-stu-id="6f066-151">"\dd"</span></span>
- <span data-ttu-id="6f066-152">"&"</span><span class="sxs-lookup"><span data-stu-id="6f066-152">"&"</span></span>
- <span data-ttu-id="6f066-153">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="6f066-153">"\begin{align}"</span></span>
- <span data-ttu-id="6f066-154">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="6f066-154">"\end{align}"</span></span>
- <span data-ttu-id="6f066-155">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="6f066-155">"\Lambda"</span></span>
- <span data-ttu-id="6f066-156">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="6f066-156">"\lambda"</span></span>
- <span data-ttu-id="6f066-157">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="6f066-157">"\Omega"</span></span>
- <span data-ttu-id="6f066-158">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="6f066-158">"\mathrm"</span></span>
- <span data-ttu-id="6f066-159">"\left"</span><span class="sxs-lookup"><span data-stu-id="6f066-159">"\left"</span></span>
- <span data-ttu-id="6f066-160">"\right"</span><span class="sxs-lookup"><span data-stu-id="6f066-160">"\right"</span></span>
- <span data-ttu-id="6f066-161">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="6f066-161">"\qquad"</span></span>
- <span data-ttu-id="6f066-162">"\times"</span><span class="sxs-lookup"><span data-stu-id="6f066-162">"\times"</span></span>
- <span data-ttu-id="6f066-163">"\big"</span><span class="sxs-lookup"><span data-stu-id="6f066-163">"\big"</span></span>
- <span data-ttu-id="6f066-164">"\langle"</span><span class="sxs-lookup"><span data-stu-id="6f066-164">"\langle"</span></span>
- <span data-ttu-id="6f066-165">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="6f066-165">"\rangle"</span></span>
- <span data-ttu-id="6f066-166">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="6f066-166">"\bigg"</span></span>
- <span data-ttu-id="6f066-167">"\Big"</span><span class="sxs-lookup"><span data-stu-id="6f066-167">"\Big"</span></span>
- <span data-ttu-id="6f066-168">"|"</span><span class="sxs-lookup"><span data-stu-id="6f066-168">"|"</span></span>
- <span data-ttu-id="6f066-169">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="6f066-169">"\mathbb"</span></span>
- <span data-ttu-id="6f066-170">"\vec"</span><span class="sxs-lookup"><span data-stu-id="6f066-170">"\vec"</span></span>
- <span data-ttu-id="6f066-171">"\in"</span><span class="sxs-lookup"><span data-stu-id="6f066-171">"\in"</span></span>
- <span data-ttu-id="6f066-172">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="6f066-172">"\texttt"</span></span>
- <span data-ttu-id="6f066-173">"\ne"</span><span class="sxs-lookup"><span data-stu-id="6f066-173">"\ne"</span></span>
- <span data-ttu-id="6f066-174">"<"</span><span class="sxs-lookup"><span data-stu-id="6f066-174">"<"</span></span>
- <span data-ttu-id="6f066-175">">"</span><span class="sxs-lookup"><span data-stu-id="6f066-175">">"</span></span>
- <span data-ttu-id="6f066-176">"\leq"</span><span class="sxs-lookup"><span data-stu-id="6f066-176">"\leq"</span></span>
- <span data-ttu-id="6f066-177">"\geq"</span><span class="sxs-lookup"><span data-stu-id="6f066-177">"\geq"</span></span>
- <span data-ttu-id="6f066-178">"~~"</span><span class="sxs-lookup"><span data-stu-id="6f066-178">"~~"</span></span>
- <span data-ttu-id="6f066-179">"~"</span><span class="sxs-lookup"><span data-stu-id="6f066-179">"~"</span></span>
- <span data-ttu-id="6f066-180">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6f066-180">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="6f066-181">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6f066-181">"\end{bmatrix}"</span></span>
- <span data-ttu-id="6f066-182">"\_"</span><span class="sxs-lookup"><span data-stu-id="6f066-182">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="6f066-183">Advanced Matrix 概念</span><span class="sxs-lookup"><span data-stu-id="6f066-183">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="6f066-184">我們現在將矩陣的操作延伸到[*特徵值、特徵向量*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)和[*指數*](https://en.wikipedia.org/wiki/Matrix_exponential)，這會形成一組我們所需的基本工具，以描述和執行量子演算法。</span><span class="sxs-lookup"><span data-stu-id="6f066-184">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="6f066-185">特徵值和特徵向量</span><span class="sxs-lookup"><span data-stu-id="6f066-185">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="6f066-186">假設 $ M $ 是正方形矩陣，而 $ v $ 則是不是全部零向量的向量（亦即，所有專案都等於0的向量 $ $ ）。</span><span class="sxs-lookup"><span data-stu-id="6f066-186">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="6f066-187">我們假設 $ v $ 是 M 的[*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ， $ 如果是 $ $ = 數位 c 的 Mv cv $ $ $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-187">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="6f066-188">我們說 $ c $ 是對應[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)至 eigenvector v 的 eigenvalue $ $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-188">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="6f066-189">在一般情況 $ $ 下，矩陣 M 可以將向量轉換成任何其他向量，但 eigenvector 是特殊的，因為它會保留不變，但會乘以數位。</span><span class="sxs-lookup"><span data-stu-id="6f066-189">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="6f066-190">請注意，如果 $ v $ 是具有 eigenvalue c 的 eigenvector $ $ ，則 $ av $ 也是 $ $ 具有相同 eigenvalue 的 eigenvector （適用于任何非零 a）。</span><span class="sxs-lookup"><span data-stu-id="6f066-190">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="6f066-191">例如，針對身分識別矩陣，每個向量 $ v $ 都是 eigenvalue 1 的 $ eigenvector $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-191">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="6f066-192">另舉一個例子，請考慮一個[*對角線矩陣*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D， $ 其對角線上只有非零的專案：</span><span class="sxs-lookup"><span data-stu-id="6f066-192">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="6f066-193">d_1 & 0 0 0 & \\\\ & d_2 & 0 \\\\ 0 & & d_3 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="6f066-193">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="6f066-194">向量</span><span class="sxs-lookup"><span data-stu-id="6f066-194">The vectors</span></span>

$$<span data-ttu-id="6f066-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 和 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="6f066-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="6f066-196">這是此矩陣的特徵向量， $ 分別具有特徵值 d_1 $ 、 $ d_2 $ 和 $ d_3 $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-196">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="6f066-197">如果 $ d_1 $ 、 $ d_2 $ 和 $ d_3 $ 是相異數位，則這些向量（及其倍數）是矩陣 d 的唯一特徵向量 $ $ 。一般而言，如果是對角矩陣，就很容易閱讀特徵值和特徵向量。</span><span class="sxs-lookup"><span data-stu-id="6f066-197">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="6f066-198">特徵值是顯示在對角線上的所有數位，而其各自的特徵向量是單位向量，其中一個專案等於 $ 1 $ ，而其餘專案則等於 $ 0 $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-198">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="6f066-199">請注意，在上述範例中，D 的特徵向量會 $ $ 形成 $ 三維向量的基礎 $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-199">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="6f066-200">「基礎」是一組向量，可讓任何向量以線性組合的方式寫入。</span><span class="sxs-lookup"><span data-stu-id="6f066-200">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="6f066-201">更明確、 $ v_1 $ 、 $ v_2 $ 和 $ v_3 $ 組成基礎，如果 $ 可以將任何向量 v $ 撰寫為 $ v a_1 v_1 + a_2 v_2 + a_3 v_3，a_1 = $ $ $ 、 $ a_2 $ 和 $ a_3 $ 的數位。</span><span class="sxs-lookup"><span data-stu-id="6f066-201">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="6f066-202">回想一下，Hermitian 矩陣（也稱為自我 adjoint）是一個複雜的方形矩陣，它等於它自己的複雜共軛轉型，而單一矩陣則是一個複雜的正方形矩陣，其反向等於其 adjoint 或複雜的共軛轉型。</span><span class="sxs-lookup"><span data-stu-id="6f066-202">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="6f066-203">對於 Hermitian 和單一矩陣，這基本上是在配量運算中唯一遇到的矩陣，有一個稱為[*spectral 定理*](https://en.wikipedia.org/wiki/Spectral_theorem)的一般結果，它會判斷提示下列事項：對於任何 Hermitian 或單一矩陣 $ M $ ，都有一個單一 $ U， $ 例如 $ M = u ^ \dagger d U $ 適用于某個對角線矩陣 $ D $ 。此外，D 的對角線專案 $ $ 會是 M 的特徵值 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-203">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="6f066-204">我們已經知道如何計算對角線矩陣 D 的特徵值和特徵向量 $ $ 。使用此定理時，我們知道如果 $ v $ 是 $ 具有 eigenvalue c 的 D eigenvector （也就是 $ $ $ $ Dv = cv $ ），則 $ U ^ \dagger v $ 會是 eigenvector，而 $ $ eigenvalue c 則是 M $ $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-204">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="6f066-205">這是因為</span><span class="sxs-lookup"><span data-stu-id="6f066-205">This is because</span></span>

$$<span data-ttu-id="6f066-206">M （U ^ \dagger v） = u ^ \dagger d U （u ^ \dagger v） = U ^ \dagger d （u u ^ \dagger ） v = u ^ \dagger d v = c U ^ \dagger v。$$</span><span class="sxs-lookup"><span data-stu-id="6f066-206">M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="6f066-207">矩陣指數</span><span class="sxs-lookup"><span data-stu-id="6f066-207">Matrix Exponentials</span></span>
<span data-ttu-id="6f066-208">[*矩陣指數*](https://en.wikipedia.org/wiki/Matrix_exponential)也可以定義為與指數函數完全相似。</span><span class="sxs-lookup"><span data-stu-id="6f066-208">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="6f066-209">矩陣 a 的矩陣指數， $ $ 可以表示為</span><span class="sxs-lookup"><span data-stu-id="6f066-209">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="6f066-210">e ^ A = \boldone + a + \frac { a ^ 2 } { 2！ } + \frac {答 ^ 3 } { 3！}+\cdots</span><span class="sxs-lookup"><span data-stu-id="6f066-210">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="6f066-211">這一點很重要，因為配量機械時間演進是由 $ e ^ { IB } $ for Hermitian matrix $ B $ 形式的單一矩陣所描述。 基於這個理由，執行矩陣指數是量子運算的基本部分，因此問 # 會提供內建常式來描述這些作業。</span><span class="sxs-lookup"><span data-stu-id="6f066-211">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="6f066-212">有許多方法可以在傳統電腦上計算矩陣指數，而在一般的數值將逼近中，這種指數是使用危險太。</span><span class="sxs-lookup"><span data-stu-id="6f066-212">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="6f066-213">請參閱[*Cleve Moler 和 Charles Van 貸款。「用來計算矩陣指數的十九可疑方法」。SIAM 計算期刊評論20.4 （1978）： 801-836*](https://doi.org/10.1137/S00361445024180) ，取得涉及挑戰的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6f066-213">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="6f066-214">若要瞭解如何計算矩陣的指數，最簡單的方式是透過該矩陣的特徵值和特徵向量。</span><span class="sxs-lookup"><span data-stu-id="6f066-214">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="6f066-215">具體來說，上述的 spectral 定理指出，針對每個 Hermitian 或單一矩陣， $ $ 有一個單一矩陣 $ U $ 和一個對角線矩陣 $ D $ ，例如 $ = U ^ \dagger d u $ 。 由於 unitarity 的屬性，我們擁有 $ ^ 2 = u ^ \dagger D ^ 2 u $ ，同樣地，任何 power $ p $ $ A ^ p = u ^ \dagger d ^ p u $ 。 如果我們將此取代為運算子指數的運算子定義，我們會取得：</span><span class="sxs-lookup"><span data-stu-id="6f066-215">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="6f066-216">e ^ A = U ^ \dagger \left （ \boldone + d + \frac { d ^ 2 } { 2！ } + \cdots \right ）U = u ^ \dagger \begin{bmatrix} \exp （D_ { 11 } ） & 0 & \cdots & 0 \\\\ 0 & \exp （D_ { 22 } ） & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp （D_ { NN } ） \end{bmatrix} U。$$</span><span class="sxs-lookup"><span data-stu-id="6f066-216">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="6f066-217">換句話說，如果您轉換成矩陣的 eigenbasis， $ $ 則計算矩陣的指數就相當於計算矩陣特徵值的一般指數。</span><span class="sxs-lookup"><span data-stu-id="6f066-217">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="6f066-218">由於配量計算中的許多作業都牽涉到執行矩陣指數，所以轉換成矩陣 eigenbasis 以簡化執行運算子指數的這項技巧，會經常出現，而且是在許多量子演算法背後的基礎，例如本指南稍後討論的 Trotter – Plat'home co. 樣式的量子模擬方法。</span><span class="sxs-lookup"><span data-stu-id="6f066-218">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="6f066-219">另一個有用的屬性是，如果 $ b $ 同時是單一和 Hermitian，即 $ b = b ^ { -1 } = B ^ \dagger $ then $ b ^ 2 = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="6f066-219">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="6f066-220">藉由將此規則套用至矩陣指數的上方展開，以及將 $ \boldone $ 和 $ B 詞彙群組在 $ 一起，就可以看到任何實際值 $ x 身分 $ 識別</span><span class="sxs-lookup"><span data-stu-id="6f066-220">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

$$<span data-ttu-id="6f066-221">e ^ { iBx } = \boldone \cos （x） + iB\sin （x）$$</span><span class="sxs-lookup"><span data-stu-id="6f066-221">e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="6f066-222">手.</span><span class="sxs-lookup"><span data-stu-id="6f066-222">holds.</span></span> <span data-ttu-id="6f066-223">這項技巧特別有用，因為它可讓您瞭解動作矩陣指數所擁有的原因，即使 b 的維度以指數方式表示， $ $ 當 $ b $ 同時為單一和 Hermitian 時，特殊情況也是如此。</span><span class="sxs-lookup"><span data-stu-id="6f066-223">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
