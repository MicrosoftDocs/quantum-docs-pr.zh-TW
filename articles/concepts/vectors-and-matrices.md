---
<span data-ttu-id="1cd24-101">標題：配量計算的向量和矩陣描述：瞭解如何使用向量和矩陣的基本概念。</span><span class="sxs-lookup"><span data-stu-id="1cd24-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="1cd24-102">author： QuantumWriter uid： microsoft 量子.. m. i m. nawiebe@microsoft.com 日期：12/11/2017 毫秒。主題：文章不存在：</span><span class="sxs-lookup"><span data-stu-id="1cd24-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="1cd24-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="1cd24-103">"$$"</span></span>
- <span data-ttu-id="1cd24-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="1cd24-104">"$$"</span></span>
- <span data-ttu-id="1cd24-105">"$"</span><span class="sxs-lookup"><span data-stu-id="1cd24-105">"$"</span></span>
- <span data-ttu-id="1cd24-106">"$"</span><span class="sxs-lookup"><span data-stu-id="1cd24-106">"$"</span></span>
- <span data-ttu-id="1cd24-107">"$"</span><span class="sxs-lookup"><span data-stu-id="1cd24-107">"$"</span></span>
- <span data-ttu-id="1cd24-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="1cd24-108">"$$"</span></span>
- <span data-ttu-id="1cd24-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="1cd24-109">"\cdots"</span></span>
- <span data-ttu-id="1cd24-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="1cd24-110">"bmatrix"</span></span>
- <span data-ttu-id="1cd24-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="1cd24-111">"\ddots"</span></span>
- <span data-ttu-id="1cd24-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="1cd24-112">"\equiv"</span></span>
- <span data-ttu-id="1cd24-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="1cd24-113">"\sum"</span></span>
- <span data-ttu-id="1cd24-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="1cd24-114">"\begin"</span></span>
- <span data-ttu-id="1cd24-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="1cd24-115">"\end"</span></span>
- <span data-ttu-id="1cd24-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="1cd24-116">"\sqrt"</span></span>
- <span data-ttu-id="1cd24-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="1cd24-117">"\otimes"</span></span>
- <span data-ttu-id="1cd24-118">"{"</span><span class="sxs-lookup"><span data-stu-id="1cd24-118">"{"</span></span>
- <span data-ttu-id="1cd24-119">"}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-119">"}"</span></span>
- <span data-ttu-id="1cd24-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="1cd24-120">"\text"</span></span>
- <span data-ttu-id="1cd24-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="1cd24-121">"\phi"</span></span>
- <span data-ttu-id="1cd24-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="1cd24-122">"\kappa"</span></span>
- <span data-ttu-id="1cd24-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="1cd24-123">"\psi"</span></span>
- <span data-ttu-id="1cd24-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="1cd24-124">"\alpha"</span></span>
- <span data-ttu-id="1cd24-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="1cd24-125">"\beta"</span></span>
- <span data-ttu-id="1cd24-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="1cd24-126">"\gamma"</span></span>
- <span data-ttu-id="1cd24-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="1cd24-127">"\delta"</span></span>
- <span data-ttu-id="1cd24-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="1cd24-128">"\omega"</span></span>
- <span data-ttu-id="1cd24-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="1cd24-129">"\bra"</span></span>
- <span data-ttu-id="1cd24-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="1cd24-130">"\ket"</span></span>
- <span data-ttu-id="1cd24-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="1cd24-131">"\boldone"</span></span>
- <span data-ttu-id="1cd24-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="1cd24-132">"\\\\"</span></span>
- <span data-ttu-id="1cd24-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="1cd24-133">"\\"</span></span>
- <span data-ttu-id="1cd24-134">"="</span><span class="sxs-lookup"><span data-stu-id="1cd24-134">"="</span></span>
- <span data-ttu-id="1cd24-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="1cd24-135">"\frac"</span></span>
- <span data-ttu-id="1cd24-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="1cd24-136">"\text"</span></span>
- <span data-ttu-id="1cd24-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="1cd24-137">"\mapsto"</span></span>
- <span data-ttu-id="1cd24-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="1cd24-138">"\dagger"</span></span>
- <span data-ttu-id="1cd24-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="1cd24-139">"\to"</span></span>
- <span data-ttu-id="1cd24-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-140">"\begin{cases}"</span></span>
- <span data-ttu-id="1cd24-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-141">"\end{cases}"</span></span>
- <span data-ttu-id="1cd24-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="1cd24-142">"\operatorname"</span></span>
- <span data-ttu-id="1cd24-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="1cd24-143">"\braket"</span></span>
- <span data-ttu-id="1cd24-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="1cd24-144">"\id"</span></span>
- <span data-ttu-id="1cd24-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="1cd24-145">"\expect"</span></span>
- <span data-ttu-id="1cd24-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="1cd24-146">"\defeq"</span></span>
- <span data-ttu-id="1cd24-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="1cd24-147">"\variance"</span></span>
- <span data-ttu-id="1cd24-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="1cd24-148">"\dd"</span></span>
- <span data-ttu-id="1cd24-149">"&"</span><span class="sxs-lookup"><span data-stu-id="1cd24-149">"&"</span></span>
- <span data-ttu-id="1cd24-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-150">"\begin{align}"</span></span>
- <span data-ttu-id="1cd24-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-151">"\end{align}"</span></span>
- <span data-ttu-id="1cd24-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="1cd24-152">"\Lambda"</span></span>
- <span data-ttu-id="1cd24-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="1cd24-153">"\lambda"</span></span>
- <span data-ttu-id="1cd24-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="1cd24-154">"\Omega"</span></span>
- <span data-ttu-id="1cd24-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="1cd24-155">"\mathrm"</span></span>
- <span data-ttu-id="1cd24-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="1cd24-156">"\left"</span></span>
- <span data-ttu-id="1cd24-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="1cd24-157">"\right"</span></span>
- <span data-ttu-id="1cd24-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="1cd24-158">"\qquad"</span></span>
- <span data-ttu-id="1cd24-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="1cd24-159">"\times"</span></span>
- <span data-ttu-id="1cd24-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="1cd24-160">"\big"</span></span>
- <span data-ttu-id="1cd24-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="1cd24-161">"\langle"</span></span>
- <span data-ttu-id="1cd24-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="1cd24-162">"\rangle"</span></span>
- <span data-ttu-id="1cd24-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="1cd24-163">"\bigg"</span></span>
- <span data-ttu-id="1cd24-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="1cd24-164">"\Big"</span></span>
- <span data-ttu-id="1cd24-165">"|"</span><span class="sxs-lookup"><span data-stu-id="1cd24-165">"|"</span></span>
- <span data-ttu-id="1cd24-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="1cd24-166">"\mathbb"</span></span>
- <span data-ttu-id="1cd24-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="1cd24-167">"\vec"</span></span>
- <span data-ttu-id="1cd24-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="1cd24-168">"\in"</span></span>
- <span data-ttu-id="1cd24-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="1cd24-169">"\texttt"</span></span>
- <span data-ttu-id="1cd24-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="1cd24-170">"\ne"</span></span>
- <span data-ttu-id="1cd24-171">"<"</span><span class="sxs-lookup"><span data-stu-id="1cd24-171">"<"</span></span>
- <span data-ttu-id="1cd24-172">">"</span><span class="sxs-lookup"><span data-stu-id="1cd24-172">">"</span></span>
- <span data-ttu-id="1cd24-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="1cd24-173">"\leq"</span></span>
- <span data-ttu-id="1cd24-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="1cd24-174">"\geq"</span></span>
- <span data-ttu-id="1cd24-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="1cd24-175">"~~"</span></span>
- <span data-ttu-id="1cd24-176">"~"</span><span class="sxs-lookup"><span data-stu-id="1cd24-176">"~"</span></span>
- <span data-ttu-id="1cd24-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="1cd24-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="1cd24-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="1cd24-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="1cd24-179">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="1cd24-180">向量和矩陣</span><span class="sxs-lookup"><span data-stu-id="1cd24-180">Vectors and Matrices</span></span>

<span data-ttu-id="1cd24-181">若要瞭解配量運算，必須熟悉向量和矩陣。</span><span class="sxs-lookup"><span data-stu-id="1cd24-181">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="1cd24-182">我們會提供下面簡要介紹，並建議讀者閱讀線性代數的標準參考，例如*Strang、G. (1993) 。 (Vol 的線性代數簡介。 3) 。Wellesley、MA： Wellesley-康橋按下*或線上參考（例如[線性代數](http://joshua.smcvt.edu/linearalgebra/)）。</span><span class="sxs-lookup"><span data-stu-id="1cd24-182">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="1cd24-183">資料行向量 (或單純的[*向量*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ 的維度 (或大小) $ n $ 是 n 複數的集合， $ $ $ (v_1，v_2，\ldots，v_n) $ 排列為資料行：</span><span class="sxs-lookup"><span data-stu-id="1cd24-183">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

$$<span data-ttu-id="1cd24-184">&=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-184">v =\begin{bmatrix}</span></span>
<span data-ttu-id="1cd24-185">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-185">v_1\\\\</span></span>
<span data-ttu-id="1cd24-186">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-186">v_2\\\\</span></span>
<span data-ttu-id="1cd24-187">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-187">\vdots\\\\</span></span>
<span data-ttu-id="1cd24-188">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="1cd24-188">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="1cd24-189">向量 v 的標準 $ $ 定義為 $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-189">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="1cd24-190">向量稱為「單位」（ (），或者，如果它的「標準」是1，則稱為「[*單位向量*](https://en.wikipedia.org/wiki/Unit_vector)) $ $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-190">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="1cd24-191">向量 v 的[*adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ $ 是 $ 以 v ^ 表示 \dagger $ ，且定義為下列資料列向量 $ \* $ ，其中代表共軛複數。</span><span class="sxs-lookup"><span data-stu-id="1cd24-191">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

$$<span data-ttu-id="1cd24-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="1cd24-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="1cd24-193">將兩個向量相乘的最常見方式是透過[*內部產品*](https://en.wikipedia.org/wiki/Inner_product_space)，也稱為「點積」。</span><span class="sxs-lookup"><span data-stu-id="1cd24-193">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="1cd24-194">內部產品會將一個向量投射到另一個向量，而且對於描述如何以其他更簡單的向量的總和來表達一個向量非常有價值。</span><span class="sxs-lookup"><span data-stu-id="1cd24-194">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="1cd24-195">U 和 v 之間的內部產品 $ $ $ $ （表示 $ \left \langle u、v） \right \rangle $ 定義為</span><span class="sxs-lookup"><span data-stu-id="1cd24-195">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
\langle<span data-ttu-id="1cd24-196">u、v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n。</span><span class="sxs-lookup"><span data-stu-id="1cd24-196"> u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="1cd24-197">此標記法也允許將向量 v 的 $ 標準 $ 寫成 $ \sqrt { \langle v，v \rangle } $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-197">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="1cd24-198">我們可以將向量與數位 c 相乘 $ $ ，以形成新的向量，其專案會乘以 $ c $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-198">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="1cd24-199">我們也可以加入兩個向量 $ u $ 和 $ v $ 來形成新的向量，其專案為 $ u $ 和 v 專案的總和 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-199">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="1cd24-200">這些作業如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cd24-200">These operations are depicted below:</span></span>

$$<span data-ttu-id="1cd24-201">\mathrm{若為 } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-201">\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="1cd24-202">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-202">u_1\\\\</span></span>
<span data-ttu-id="1cd24-203">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-203">u_2\\\\</span></span>
<span data-ttu-id="1cd24-204">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-204">\vdots\\\\</span></span>
<span data-ttu-id="1cd24-205">u_n \end{bmatrix} ~ \mathrm { 和}~</span><span class="sxs-lookup"><span data-stu-id="1cd24-205">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="1cd24-206">&=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-206">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="1cd24-207">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-207">v_1\\\\</span></span>
    <span data-ttu-id="1cd24-208">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-208">v_2\\\\</span></span>
    <span data-ttu-id="1cd24-209">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-209">\vdots\\\\</span></span>
    <span data-ttu-id="1cd24-210">v_n \end{bmatrix} ， ~ \mathrm { 然後}~</span><span class="sxs-lookup"><span data-stu-id="1cd24-210">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="1cd24-211">au + bv=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-211">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="1cd24-212">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-212">au_1+bv_1\\\\</span></span>
<span data-ttu-id="1cd24-213">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-213">au_2+bv_2\\\\</span></span>
<span data-ttu-id="1cd24-214">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-214">\vdots\\\\</span></span>
<span data-ttu-id="1cd24-215">au_n + bv_n \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-215">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="1cd24-216">大小[*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics))為 $ m n 的 \times 矩陣 $ 是 $ $ 以 m 個數據列和 n 個數據行排列之 mn 複數的集合，如下 $ $ $ $ 所示：</span><span class="sxs-lookup"><span data-stu-id="1cd24-216">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

$$<span data-ttu-id="1cd24-217">分鐘=</span><span class="sxs-lookup"><span data-stu-id="1cd24-217">M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="1cd24-218">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-218">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="1cd24-219">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-219">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="1cd24-220">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-220">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
\end{bmatrix}<span data-ttu-id="1cd24-221">.$$</span><span class="sxs-lookup"><span data-stu-id="1cd24-221">.$$</span></span>

<span data-ttu-id="1cd24-222">請注意，維度 n 的 $ 向量 $ 只是大小為 $ n 1 的 \times 矩陣 $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-222">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="1cd24-223">如同向量，我們可以將矩陣與數位 $ c 相乘 $ 以取得新的矩陣，其中每個專案都會乘以 $ c $ ，而我們可以加入相同大小的兩個矩陣，以產生新的矩陣，其專案為兩個矩陣之個別專案的總和。</span><span class="sxs-lookup"><span data-stu-id="1cd24-223">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="1cd24-224">矩陣乘法和張量產品</span><span class="sxs-lookup"><span data-stu-id="1cd24-224">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="1cd24-225">我們也可以 $ 將維度 m n 的兩個矩陣 m $ $ \times $ 和 $ n $ 個維度 $ n p 相乘， \times $ 以取得 $ $ 維度 m p 的新矩陣 p $ ，如下所示 \times $ ：</span><span class="sxs-lookup"><span data-stu-id="1cd24-225">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="1cd24-226">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-226">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="1cd24-227">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-227">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="1cd24-228">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}</span><span class="sxs-lookup"><span data-stu-id="1cd24-228">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="1cd24-229">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-229">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="1cd24-230">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-230">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="1cd24-231">N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="1cd24-231">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="1cd24-232">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1 p}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-232">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="1cd24-233">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-233">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="1cd24-234">P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}</span><span class="sxs-lookup"><span data-stu-id="1cd24-234">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="1cd24-235">其中 P 的專案 $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-235">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="1cd24-236">例如， $ P_ 11 的專案 { } $ 是 M 的第一個資料列的內部乘積 $ ， $ 其中第一個資料行是 $ N $ 。請注意，由於向量只是一個特殊的矩陣案例，因此此定義會延伸至矩陣向量乘法。</span><span class="sxs-lookup"><span data-stu-id="1cd24-236">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="1cd24-237">我們考慮的所有矩陣都是方形矩陣，其中資料列和資料行的數目相等，或只對應于1個數據行的向量 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-237">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="1cd24-238">一個特殊的正方形矩陣是[*識別矩陣*](https://en.wikipedia.org/wiki/Identity_matrix)，表示 $ \boldone $ ，其所有的對角線元素都等於 $ 1 $ ，其餘元素則等於 $ 0 $ ：</span><span class="sxs-lookup"><span data-stu-id="1cd24-238">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="1cd24-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="1cd24-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
~~<span data-ttu-id="1cd24-241"> \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-241"> \ddots\\\\</span></span>
<span data-ttu-id="1cd24-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="1cd24-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="1cd24-243">若為正方形矩陣 $ a $ ，我們假設矩陣 $ B $ 是其[*反向*](https://en.wikipedia.org/wiki/Invertible_matrix)的（如果 $ AB BA） = = \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-243">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="1cd24-244">矩陣的反向不需要存在，但當它存在時，它是唯一的，而我們表示它是 $ ^ { -1 } $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-244">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="1cd24-245">對於任何矩陣 $ m $ 而言，m 的 adjoint 或共軛 $ 轉 $ 類型是一個矩陣 $ N， $ 因此 $ N_ { ij } = M_ { ji } ^ \* $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-245">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="1cd24-246">M 的 adjoint $ $ 通常是以 $ m ^ 表示 \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-246">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="1cd24-247">我們說 $ $ ，如果有[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ UU ^ \dagger = u ^ \dagger u 或對等的 = \boldone $ $ u ^ { -1 } = U ^ \dagger $ ，矩陣 U 就是單一。</span><span class="sxs-lookup"><span data-stu-id="1cd24-247">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="1cd24-248">單一矩陣的最重要屬性可能是它們保留向量的標準。</span><span class="sxs-lookup"><span data-stu-id="1cd24-248">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="1cd24-249">發生這種情況的原因是</span><span class="sxs-lookup"><span data-stu-id="1cd24-249">This happens because</span></span> 

$$<span data-ttu-id="1cd24-250">\langlev，v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v 2，u v \rangle 。$$</span><span class="sxs-lookup"><span data-stu-id="1cd24-250">\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="1cd24-251">$ $ 如果[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) $ m = m ^ \dagger $ ，則矩陣 M 稱為 Hermitian。</span><span class="sxs-lookup"><span data-stu-id="1cd24-251">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="1cd24-252">最後，[*張量產品*](https://en.wikipedia.org/wiki/Tensor_product) (或 Kronecker 產品) ， $ 大小為 m n 的兩個矩陣 m， $ $ \times $ 而大小為 $ $ $ p q， \times $ 則是較大的矩陣 $ p = M \otimes n $ 大小的 $ mp \times nq $ ，並從 $ M $ 和 n 取得， $ $ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="1cd24-252">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="1cd24-253">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="1cd24-253">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="1cd24-254">M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-254">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="1cd24-255">M_ { m1 } ~~ \cdots ~~ M_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="1cd24-255">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="1cd24-256">N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-256">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="1cd24-257">N_ { p1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="1cd24-257">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="1cd24-258">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="1cd24-258">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="1cd24-259">M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-259">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="1cd24-260">M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="1cd24-260">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="1cd24-261">M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-261">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    \end{bmatrix}<span data-ttu-id="1cd24-262">.</span><span class="sxs-lookup"><span data-stu-id="1cd24-262">.</span></span>
\end{align}

<span data-ttu-id="1cd24-263">這會更清楚地示範一些範例：</span><span class="sxs-lookup"><span data-stu-id="1cd24-263">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="1cd24-264">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="1cd24-264">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="1cd24-265">a \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-265">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        \\\\<span data-ttu-id="1cd24-266">[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-266">[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    =<span data-ttu-id="1cd24-267">\begin{bmatrix}a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ 是\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-267"> \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="1cd24-268">和</span><span class="sxs-lookup"><span data-stu-id="1cd24-268">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="1cd24-269">a \ b \\\\ c \ d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-269">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="1cd24-270">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-270">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="1cd24-271">為\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-271">a\begin{bmatrix}</span></span>
    <span data-ttu-id="1cd24-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-272">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="1cd24-273">位元組\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-273">b\begin{bmatrix}</span></span>
    <span data-ttu-id="1cd24-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \\\\<span data-ttu-id="1cd24-275">[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-275">[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="1cd24-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="1cd24-277">d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-277">d\begin{bmatrix}</span></span>
    <span data-ttu-id="1cd24-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="1cd24-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="1cd24-279">ae \ af \ bf\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-279">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="1cd24-280">ag \ ah \ bg \ bh\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-280">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="1cd24-281">ce \ cf \ de \ df\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-281">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="1cd24-282">cg \ ch \ dg \ dh \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-282">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="1cd24-283">張量產品的最後一個有用的標記慣例是，對於任何向量 $ v $ 或矩陣 $ M 而言， $ $ v ^ { \otimes n } $ 或 $ M ^ { \otimes n } $ 是針對 $ n $ 折重複張量產品的短期。</span><span class="sxs-lookup"><span data-stu-id="1cd24-283">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="1cd24-284">例如︰</span><span class="sxs-lookup"><span data-stu-id="1cd24-284">For example:</span></span>

\begin{align}
&<span data-ttu-id="1cd24-285">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} ， \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1- \\\\ 1 \\\\ -1 \\\\ 1 \end{bmatrix} ，\\\\</span><span class="sxs-lookup"><span data-stu-id="1cd24-285">\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  &<span data-ttu-id="1cd24-286">\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ， \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="1cd24-286">\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
