---
<span data-ttu-id="993de-101">標題：量子運算描述中的向量和矩陣：瞭解如何使用向量和矩陣的基本概念。</span><span class="sxs-lookup"><span data-stu-id="993de-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="993de-102">author： QuantumWriter uid： benbra ms. ms. date： 12/11/2017 ms. 主題：非 loc 文章：</span><span class="sxs-lookup"><span data-stu-id="993de-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="993de-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="993de-103">"Q#"</span></span>
- <span data-ttu-id="993de-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="993de-104">"$$v"</span></span>
- <span data-ttu-id="993de-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="993de-105">"$$"</span></span>
- <span data-ttu-id="993de-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="993de-106">"$$"</span></span>
- <span data-ttu-id="993de-107">"$"</span><span class="sxs-lookup"><span data-stu-id="993de-107">"$"</span></span>
- <span data-ttu-id="993de-108">"$"</span><span class="sxs-lookup"><span data-stu-id="993de-108">"$"</span></span>
- <span data-ttu-id="993de-109">"$"</span><span class="sxs-lookup"><span data-stu-id="993de-109">"$"</span></span>
- <span data-ttu-id="993de-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="993de-110">"$$"</span></span>
- <span data-ttu-id="993de-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="993de-111">"\cdots"</span></span>
- <span data-ttu-id="993de-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="993de-112">"bmatrix"</span></span>
- <span data-ttu-id="993de-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="993de-113">"\ddots"</span></span>
- <span data-ttu-id="993de-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="993de-114">"\equiv"</span></span>
- <span data-ttu-id="993de-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="993de-115">"\sum"</span></span>
- <span data-ttu-id="993de-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="993de-116">"\begin"</span></span>
- <span data-ttu-id="993de-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="993de-117">"\end"</span></span>
- <span data-ttu-id="993de-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="993de-118">"\sqrt"</span></span>
- <span data-ttu-id="993de-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="993de-119">"\otimes"</span></span>
- <span data-ttu-id="993de-120">"{"</span><span class="sxs-lookup"><span data-stu-id="993de-120">"{"</span></span>
- <span data-ttu-id="993de-121">"}"</span><span class="sxs-lookup"><span data-stu-id="993de-121">"}"</span></span>
- <span data-ttu-id="993de-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="993de-122">"\text"</span></span>
- <span data-ttu-id="993de-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="993de-123">"\phi"</span></span>
- <span data-ttu-id="993de-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="993de-124">"\kappa"</span></span>
- <span data-ttu-id="993de-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="993de-125">"\psi"</span></span>
- <span data-ttu-id="993de-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="993de-126">"\alpha"</span></span>
- <span data-ttu-id="993de-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="993de-127">"\beta"</span></span>
- <span data-ttu-id="993de-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="993de-128">"\gamma"</span></span>
- <span data-ttu-id="993de-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="993de-129">"\delta"</span></span>
- <span data-ttu-id="993de-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="993de-130">"\omega"</span></span>
- <span data-ttu-id="993de-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="993de-131">"\bra"</span></span>
- <span data-ttu-id="993de-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="993de-132">"\ket"</span></span>
- <span data-ttu-id="993de-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="993de-133">"\boldone"</span></span>
- <span data-ttu-id="993de-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="993de-134">"\\\\"</span></span>
- <span data-ttu-id="993de-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="993de-135">"\\"</span></span>
- <span data-ttu-id="993de-136">"="</span><span class="sxs-lookup"><span data-stu-id="993de-136">"="</span></span>
- <span data-ttu-id="993de-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="993de-137">"\frac"</span></span>
- <span data-ttu-id="993de-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="993de-138">"\text"</span></span>
- <span data-ttu-id="993de-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="993de-139">"\mapsto"</span></span>
- <span data-ttu-id="993de-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="993de-140">"\dagger"</span></span>
- <span data-ttu-id="993de-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="993de-141">"\to"</span></span>
- <span data-ttu-id="993de-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="993de-142">"\begin{cases}"</span></span>
- <span data-ttu-id="993de-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="993de-143">"\end{cases}"</span></span>
- <span data-ttu-id="993de-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="993de-144">"\operatorname"</span></span>
- <span data-ttu-id="993de-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="993de-145">"\braket"</span></span>
- <span data-ttu-id="993de-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="993de-146">"\id"</span></span>
- <span data-ttu-id="993de-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="993de-147">"\expect"</span></span>
- <span data-ttu-id="993de-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="993de-148">"\defeq"</span></span>
- <span data-ttu-id="993de-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="993de-149">"\variance"</span></span>
- <span data-ttu-id="993de-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="993de-150">"\dd"</span></span>
- <span data-ttu-id="993de-151">"&"</span><span class="sxs-lookup"><span data-stu-id="993de-151">"&"</span></span>
- <span data-ttu-id="993de-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="993de-152">"\begin{align}"</span></span>
- <span data-ttu-id="993de-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="993de-153">"\end{align}"</span></span>
- <span data-ttu-id="993de-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="993de-154">"\Lambda"</span></span>
- <span data-ttu-id="993de-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="993de-155">"\lambda"</span></span>
- <span data-ttu-id="993de-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="993de-156">"\Omega"</span></span>
- <span data-ttu-id="993de-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="993de-157">"\mathrm"</span></span>
- <span data-ttu-id="993de-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="993de-158">"\left"</span></span>
- <span data-ttu-id="993de-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="993de-159">"\right"</span></span>
- <span data-ttu-id="993de-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="993de-160">"\qquad"</span></span>
- <span data-ttu-id="993de-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="993de-161">"\times"</span></span>
- <span data-ttu-id="993de-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="993de-162">"\big"</span></span>
- <span data-ttu-id="993de-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="993de-163">"\langle"</span></span>
- <span data-ttu-id="993de-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="993de-164">"\rangle"</span></span>
- <span data-ttu-id="993de-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="993de-165">"\bigg"</span></span>
- <span data-ttu-id="993de-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="993de-166">"\Big"</span></span>
- <span data-ttu-id="993de-167">"|"</span><span class="sxs-lookup"><span data-stu-id="993de-167">"|"</span></span>
- <span data-ttu-id="993de-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="993de-168">"\mathbb"</span></span>
- <span data-ttu-id="993de-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="993de-169">"\vec"</span></span>
- <span data-ttu-id="993de-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="993de-170">"\in"</span></span>
- <span data-ttu-id="993de-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="993de-171">"\texttt"</span></span>
- <span data-ttu-id="993de-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="993de-172">"\ne"</span></span>
- <span data-ttu-id="993de-173">"<"</span><span class="sxs-lookup"><span data-stu-id="993de-173">"<"</span></span>
- <span data-ttu-id="993de-174">">"</span><span class="sxs-lookup"><span data-stu-id="993de-174">">"</span></span>
- <span data-ttu-id="993de-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="993de-175">"\leq"</span></span>
- <span data-ttu-id="993de-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="993de-176">"\geq"</span></span>
- <span data-ttu-id="993de-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="993de-177">"~~"</span></span>
- <span data-ttu-id="993de-178">"~"</span><span class="sxs-lookup"><span data-stu-id="993de-178">"~"</span></span>
- <span data-ttu-id="993de-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="993de-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="993de-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="993de-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="993de-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="993de-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="993de-182">向量和矩陣</span><span class="sxs-lookup"><span data-stu-id="993de-182">Vectors and Matrices</span></span>

<span data-ttu-id="993de-183">對向量和矩陣的熟悉程度，是瞭解量子運算的關鍵。</span><span class="sxs-lookup"><span data-stu-id="993de-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="993de-184">我們提供以下的簡短簡介，並且有興趣的讀者建議您閱讀線性代數的標準參考，例如 *Strang、g. (1993) 。線性代數的簡介 (Vol. 3) 。Wellesley，MA： Wellesley-康橋按* 或線上參考，例如 [線性代數](http://joshua.smcvt.edu/linearalgebra/)。</span><span class="sxs-lookup"><span data-stu-id="993de-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="993de-185">資料行向量 (或單純是 [*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ 的維度 (或大小) $ n $ 是 n 複數的集合 $ $ $ ， (v_1、v_2、\ldots、v_n) $ 排列成資料行：</span><span class="sxs-lookup"><span data-stu-id="993de-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="993de-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="993de-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-187">v_1\\\\</span></span>
<span data-ttu-id="993de-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-188">v_2\\\\</span></span>
<span data-ttu-id="993de-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-189">\vdots\\\\</span></span>
<span data-ttu-id="993de-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="993de-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="993de-191">向量 v 的標準 $ $ 定義為 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="993de-192">向量稱為「單位」（ (），或者，如果其標準為1，則會被稱為 [*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="993de-193">向量 v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 會 $ 以 v ^ 表示， \dagger $ 並定義為下列資料列向量 $ \* $ ，其中表示共軛複數。</span><span class="sxs-lookup"><span data-stu-id="993de-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="993de-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="993de-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="993de-195">將兩個向量相乘的最常見方法是透過 [*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)（也稱為「點」產品）。</span><span class="sxs-lookup"><span data-stu-id="993de-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="993de-196">內部產品可將一個向量投射到另一個向量，而且很有説明，可描述如何以其他更簡單的向量的總和來表達一個向量。</span><span class="sxs-lookup"><span data-stu-id="993de-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="993de-197">U 和 v 之間的內部產品 $ $ $ $ （表示 $ \left \langle u、v） \right \rangle $ 定義為</span><span class="sxs-lookup"><span data-stu-id="993de-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="993de-198">\langleu，v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。</span><span class="sxs-lookup"><span data-stu-id="993de-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="993de-199">此標記法也可讓向量 v 的 $ 標準 $ 撰寫為 $ \sqrt { \langle v，v \rangle } $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="993de-200">我們可以將向量乘以數位 $ c $ 來形成新的向量，其專案會乘以 $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="993de-201">我們也可以新增兩個向量 $ u $ 和 $ v $ 來形成新的向量，其專案為 $ u $ 和 v 專案的總和 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="993de-202">這些作業如下所示：</span><span class="sxs-lookup"><span data-stu-id="993de-202">These operations are depicted below:</span></span>

<span data-ttu-id="993de-203">$$\mathrm{If } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="993de-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-204">u_1\\\\</span></span>
<span data-ttu-id="993de-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-205">u_2\\\\</span></span>
<span data-ttu-id="993de-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-206">\vdots\\\\</span></span>
<span data-ttu-id="993de-207">u_n \end{bmatrix} ~ \mathrm { 和}~</span><span class="sxs-lookup"><span data-stu-id="993de-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="993de-208">V =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="993de-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-209">v_1\\\\</span></span>
    <span data-ttu-id="993de-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-210">v_2\\\\</span></span>
    <span data-ttu-id="993de-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-211">\vdots\\\\</span></span>
    <span data-ttu-id="993de-212">v_n \end{bmatrix} ， ~ \mathrm { 則}~</span><span class="sxs-lookup"><span data-stu-id="993de-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="993de-213">au + bv =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="993de-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="993de-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="993de-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-216">\vdots\\\\</span></span>
<span data-ttu-id="993de-217">au_n + bv_n \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="993de-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="993de-218">大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))為 $ m n 的 \times 矩陣 $ 是 $ mn 複數的集合 $ ，以 m 個 $ 資料 $ 列和 n 個數據行排列， $ $ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="993de-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="993de-219">$$M =</span><span class="sxs-lookup"><span data-stu-id="993de-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="993de-220">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="993de-221">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="993de-222">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="993de-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="993de-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="993de-224">請注意，維度 n 的 $ 向量 $ 只是大小為 $ n 1 的 \times 矩陣 $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="993de-225">如同向量，我們可以將矩陣與數位 c 相乘， $ $ 以取得新的矩陣，其中每個專案都與 $ c 相乘 $ ，而且我們可以加入兩個相同大小的矩陣，以產生新的矩陣，其專案是兩個矩陣之個別專案的總和。</span><span class="sxs-lookup"><span data-stu-id="993de-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="993de-226">矩陣乘法和 Tensor 產品</span><span class="sxs-lookup"><span data-stu-id="993de-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="993de-227">我們也可以將維度 $ m n 和 n 的兩個矩陣 m 乘以維度 $ $ \times $ $ $ $ n \times p， $ 以取得 $ $ 維度 $ m p 的 \times $ 新矩陣 p，如下所示：</span><span class="sxs-lookup"><span data-stu-id="993de-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="993de-228">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="993de-229">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="993de-230">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}</span><span class="sxs-lookup"><span data-stu-id="993de-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="993de-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="993de-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="993de-233">N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="993de-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="993de-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="993de-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="993de-236">P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}</span><span class="sxs-lookup"><span data-stu-id="993de-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="993de-237">其中 P 的專案 $ $ 是 $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="993de-238">例如， $ P_ 11 的專案 { } $ 是 M 的第一個資料列的內部乘積 $ $ ，第一個資料行是 $ N $ 。請注意，因為向量只是矩陣的特殊案例，所以這個定義會延伸至矩陣向量乘法。</span><span class="sxs-lookup"><span data-stu-id="993de-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="993de-239">我們所考慮的所有矩陣都是正方形矩陣，其中資料列和資料行的數目相等，或僅對應至1個數據行的向量 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="993de-240">一個特殊的正方形矩陣是[*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ 其所有對角線元素等於 $ 1 $ ，其餘元素等於 $ 0 $ ：</span><span class="sxs-lookup"><span data-stu-id="993de-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="993de-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="993de-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="993de-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="993de-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="993de-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="993de-245">如果是正方形矩陣 $ a $ ，則 $ $ 如果 AB BA，則會將矩陣 B 作為[*反向*](https://en.wikipedia.org/wiki/Invertible_matrix) $ = = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="993de-246">矩陣的反向需要不存在，但當其存在時，就表示它是唯一的，而且我們會將它表示 $ 為 ^ { -1 } $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="993de-247">對於任何矩陣 $ m $ ，M 的 adjoint 或共軛變換 $ $ 是矩陣 N， $ $ 因此 $ N_ { ij } = M_ { ji } ^ \* $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="993de-248">M 的 adjoint $ $ 通常是以 $ m ^ 表示 \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="993de-249">假設矩陣 $ u $ 是[*單一*](https://en.wikipedia.org/wiki/Unitary_matrix)的，如果是 $ UU ^ \dagger = u ^ \dagger u = \boldone $ 或等同的 $ u ^ { -1 } = u ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="993de-250">單一矩陣的最重要屬性可能是它們保留向量的標準。</span><span class="sxs-lookup"><span data-stu-id="993de-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="993de-251">發生這種情況的原因是</span><span class="sxs-lookup"><span data-stu-id="993de-251">This happens because</span></span> 

<span data-ttu-id="993de-252">$$\langlev，v v \rangle = ^ \dagger v = v ^ \dagger u ^ { -1 } U v v = ^ \dagger u ^ \dagger u v = \langle u v. u v \rangle 。$$</span><span class="sxs-lookup"><span data-stu-id="993de-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="993de-253">$ $ [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix)如果 $ m m ^，則會將矩陣 m 視為 Hermitian = \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="993de-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="993de-254">最後， [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker product) 兩個大小為 $ $ m n 的 $ 矩陣 \times $ ，而 $ n $ 的大小 $ p \times q $ 則是大型 $ mp nq 大小的矩陣 p = M \otimes n $ $ \times $ ，而且是從 $ M $ 和 $ n $ 取得，如下所示：</span><span class="sxs-lookup"><span data-stu-id="993de-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="993de-255">M \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="993de-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="993de-256">M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="993de-257">M_ { m1 } ~~ \cdots ~~ M_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="993de-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="993de-258">N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="993de-259">N_ { p1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="993de-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="993de-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="993de-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="993de-261">M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="993de-262">M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="993de-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="993de-263">M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="993de-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="993de-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="993de-265">以下是更好的示範範例：</span><span class="sxs-lookup"><span data-stu-id="993de-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="993de-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="993de-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="993de-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="993de-268">\\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="993de-269">=\begin{bmatrix}a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="993de-270">及</span><span class="sxs-lookup"><span data-stu-id="993de-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="993de-271">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="993de-272">e \ f \\\\ g h h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="993de-273">的\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="993de-274">e \ f \\\\ g h h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="993de-275">B\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="993de-276">e \ f \\\\ g h h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="993de-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="993de-278">e \ f \\\\ g h h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="993de-279">D\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="993de-280">e \ f \\\\ g h h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="993de-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="993de-281">ae \ af \ bf \\\\</span><span class="sxs-lookup"><span data-stu-id="993de-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="993de-282">ag \ ah \ bg \ bh \\\\</span><span class="sxs-lookup"><span data-stu-id="993de-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="993de-283">ce \ cf \ de \ df \\\\</span><span class="sxs-lookup"><span data-stu-id="993de-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="993de-284">cg \ ch \ dg \ dh \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="993de-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="993de-285">關於 tensor 產品的最後一個實用標記慣例，就是，針對任何向量 $ v $ 或矩陣 $ M $ ， $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 都是對 $ n $ 折迭重複 tensor 產品的簡短。</span><span class="sxs-lookup"><span data-stu-id="993de-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="993de-286">例如：</span><span class="sxs-lookup"><span data-stu-id="993de-286">For example:</span></span>

\begin{align}
<span data-ttu-id="993de-287">&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} 、\\\\</span><span class="sxs-lookup"><span data-stu-id="993de-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="993de-288">&\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 0 0 0 } = \begin{bmatrix} & & & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & \\\\ & & & \end{bmatrix} 0 1 0 0 0 0。</span><span class="sxs-lookup"><span data-stu-id="993de-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
