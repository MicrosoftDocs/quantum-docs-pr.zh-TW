---
<span data-ttu-id="806e3-101">標題： Dirac 標記法描述：瞭解如何使用 Dirac 標記法來表示量子狀態，以及模擬量子作業。</span><span class="sxs-lookup"><span data-stu-id="806e3-101">title: Dirac notation description: Learn about using Dirac notation to represent quantum states and to simulate quantum operations.</span></span>
<span data-ttu-id="806e3-102">作者： QuantumWriter uid： dirac ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：非 loc 文章：</span><span class="sxs-lookup"><span data-stu-id="806e3-102">author: QuantumWriter uid: microsoft.quantum.concepts.dirac ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="806e3-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="806e3-103">"Q#"</span></span>
- <span data-ttu-id="806e3-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="806e3-104">"$$v"</span></span>
- <span data-ttu-id="806e3-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="806e3-105">"$$"</span></span>
- <span data-ttu-id="806e3-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="806e3-106">"$$"</span></span>
- <span data-ttu-id="806e3-107">"$"</span><span class="sxs-lookup"><span data-stu-id="806e3-107">"$"</span></span>
- <span data-ttu-id="806e3-108">"$"</span><span class="sxs-lookup"><span data-stu-id="806e3-108">"$"</span></span>
- <span data-ttu-id="806e3-109">"$"</span><span class="sxs-lookup"><span data-stu-id="806e3-109">"$"</span></span>
- <span data-ttu-id="806e3-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="806e3-110">"$$"</span></span>
- <span data-ttu-id="806e3-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="806e3-111">"\cdots"</span></span>
- <span data-ttu-id="806e3-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="806e3-112">"bmatrix"</span></span>
- <span data-ttu-id="806e3-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="806e3-113">"\ddots"</span></span>
- <span data-ttu-id="806e3-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="806e3-114">"\equiv"</span></span>
- <span data-ttu-id="806e3-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="806e3-115">"\sum"</span></span>
- <span data-ttu-id="806e3-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="806e3-116">"\begin"</span></span>
- <span data-ttu-id="806e3-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="806e3-117">"\end"</span></span>
- <span data-ttu-id="806e3-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="806e3-118">"\sqrt"</span></span>
- <span data-ttu-id="806e3-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="806e3-119">"\otimes"</span></span>
- <span data-ttu-id="806e3-120">"{"</span><span class="sxs-lookup"><span data-stu-id="806e3-120">"{"</span></span>
- <span data-ttu-id="806e3-121">"}"</span><span class="sxs-lookup"><span data-stu-id="806e3-121">"}"</span></span>
- <span data-ttu-id="806e3-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="806e3-122">"\text"</span></span>
- <span data-ttu-id="806e3-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="806e3-123">"\phi"</span></span>
- <span data-ttu-id="806e3-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="806e3-124">"\kappa"</span></span>
- <span data-ttu-id="806e3-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="806e3-125">"\psi"</span></span>
- <span data-ttu-id="806e3-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="806e3-126">"\alpha"</span></span>
- <span data-ttu-id="806e3-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="806e3-127">"\beta"</span></span>
- <span data-ttu-id="806e3-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="806e3-128">"\gamma"</span></span>
- <span data-ttu-id="806e3-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="806e3-129">"\delta"</span></span>
- <span data-ttu-id="806e3-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="806e3-130">"\omega"</span></span>
- <span data-ttu-id="806e3-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="806e3-131">"\bra"</span></span>
- <span data-ttu-id="806e3-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="806e3-132">"\ket"</span></span>
- <span data-ttu-id="806e3-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="806e3-133">"\boldone"</span></span>
- <span data-ttu-id="806e3-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="806e3-134">"\\\\"</span></span>
- <span data-ttu-id="806e3-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="806e3-135">"\\"</span></span>
- <span data-ttu-id="806e3-136">"="</span><span class="sxs-lookup"><span data-stu-id="806e3-136">"="</span></span>
- <span data-ttu-id="806e3-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="806e3-137">"\frac"</span></span>
- <span data-ttu-id="806e3-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="806e3-138">"\text"</span></span>
- <span data-ttu-id="806e3-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="806e3-139">"\mapsto"</span></span>
- <span data-ttu-id="806e3-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="806e3-140">"\dagger"</span></span>
- <span data-ttu-id="806e3-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="806e3-141">"\to"</span></span>
- <span data-ttu-id="806e3-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="806e3-142">"\begin{cases}"</span></span>
- <span data-ttu-id="806e3-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="806e3-143">"\end{cases}"</span></span>
- <span data-ttu-id="806e3-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="806e3-144">"\operatorname"</span></span>
- <span data-ttu-id="806e3-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="806e3-145">"\braket"</span></span>
- <span data-ttu-id="806e3-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="806e3-146">"\id"</span></span>
- <span data-ttu-id="806e3-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="806e3-147">"\expect"</span></span>
- <span data-ttu-id="806e3-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="806e3-148">"\defeq"</span></span>
- <span data-ttu-id="806e3-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="806e3-149">"\variance"</span></span>
- <span data-ttu-id="806e3-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="806e3-150">"\dd"</span></span>
- <span data-ttu-id="806e3-151">"&"</span><span class="sxs-lookup"><span data-stu-id="806e3-151">"&"</span></span>
- <span data-ttu-id="806e3-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="806e3-152">"\begin{align}"</span></span>
- <span data-ttu-id="806e3-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="806e3-153">"\end{align}"</span></span>
- <span data-ttu-id="806e3-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="806e3-154">"\Lambda"</span></span>
- <span data-ttu-id="806e3-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="806e3-155">"\lambda"</span></span>
- <span data-ttu-id="806e3-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="806e3-156">"\Omega"</span></span>
- <span data-ttu-id="806e3-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="806e3-157">"\mathrm"</span></span>
- <span data-ttu-id="806e3-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="806e3-158">"\left"</span></span>
- <span data-ttu-id="806e3-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="806e3-159">"\right"</span></span>
- <span data-ttu-id="806e3-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="806e3-160">"\qquad"</span></span>
- <span data-ttu-id="806e3-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="806e3-161">"\times"</span></span>
- <span data-ttu-id="806e3-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="806e3-162">"\big"</span></span>
- <span data-ttu-id="806e3-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="806e3-163">"\langle"</span></span>
- <span data-ttu-id="806e3-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="806e3-164">"\rangle"</span></span>
- <span data-ttu-id="806e3-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="806e3-165">"\bigg"</span></span>
- <span data-ttu-id="806e3-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="806e3-166">"\Big"</span></span>
- <span data-ttu-id="806e3-167">"|"</span><span class="sxs-lookup"><span data-stu-id="806e3-167">"|"</span></span>
- <span data-ttu-id="806e3-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="806e3-168">"\mathbb"</span></span>
- <span data-ttu-id="806e3-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="806e3-169">"\vec"</span></span>
- <span data-ttu-id="806e3-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="806e3-170">"\in"</span></span>
- <span data-ttu-id="806e3-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="806e3-171">"\texttt"</span></span>
- <span data-ttu-id="806e3-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="806e3-172">"\ne"</span></span>
- <span data-ttu-id="806e3-173">"<"</span><span class="sxs-lookup"><span data-stu-id="806e3-173">"<"</span></span>
- <span data-ttu-id="806e3-174">">"</span><span class="sxs-lookup"><span data-stu-id="806e3-174">">"</span></span>
- <span data-ttu-id="806e3-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="806e3-175">"\leq"</span></span>
- <span data-ttu-id="806e3-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="806e3-176">"\geq"</span></span>
- <span data-ttu-id="806e3-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="806e3-177">"~~"</span></span>
- <span data-ttu-id="806e3-178">"~"</span><span class="sxs-lookup"><span data-stu-id="806e3-178">"~"</span></span>
- <span data-ttu-id="806e3-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="806e3-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="806e3-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="806e3-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="806e3-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="806e3-181">"\_"</span></span>

---

# <a name="dirac-notation"></a><span data-ttu-id="806e3-182">Dirac 標記法</span><span class="sxs-lookup"><span data-stu-id="806e3-182">Dirac Notation</span></span>

<span data-ttu-id="806e3-183">雖然資料行向量標記法線上性代數中是普遍的，但在處理多個量子位時，量子運算通常很繁瑣。</span><span class="sxs-lookup"><span data-stu-id="806e3-183">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="806e3-184">例如，當我們定義 $ \psi $ 為向量時，不會明確地明確指出 $ \psi $ 是資料列或資料行向量。</span><span class="sxs-lookup"><span data-stu-id="806e3-184">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="806e3-185">因此 $ \phi $ ，如果和 $ \psi $ 是向量，則即使定義時，也會不清楚， $ \phi \psi $ 因為在 $ \phi $ 內容中的圖案 $ \psi $ 可能不清楚。</span><span class="sxs-lookup"><span data-stu-id="806e3-185">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="806e3-186">除了向量圖形的混淆之外，使用先前引進的線性代數標記法來表示簡單的向量也相當繁瑣。</span><span class="sxs-lookup"><span data-stu-id="806e3-186">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="806e3-187">例如，如果我們想要描述 $ n $ 個量子位狀態，其中每個量子位都採用0值， $ $ 則我們會正式將狀態表示為</span><span class="sxs-lookup"><span data-stu-id="806e3-187">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="806e3-188">$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="806e3-188">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="806e3-189">當然，評估這個 tensor 產品並不實用，因為向量位於以指數方式表示的大型空間中，因此這個標記法實際上是可使用先前的標記法來指定之狀態的最佳描述。</span><span class="sxs-lookup"><span data-stu-id="806e3-189">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="806e3-190">[*Dirac 標記法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) 藉由呈現新的語言，以符合量子機制的精確需求來解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="806e3-190">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="806e3-191">基於這個理由，我們建議讀者不要將本節中的範例視為如何描述量子狀態的固定處方，而是建議讀者將這些範例視為可以用來精確表達量子概念的建議。</span><span class="sxs-lookup"><span data-stu-id="806e3-191">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="806e3-192">Dirac 標記法中有兩種類型的向量： *bra* 向量和 *ket* 向量，因此命名方式是將它們組成 *braket* 或內部產品。</span><span class="sxs-lookup"><span data-stu-id="806e3-192">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="806e3-193">如果 $ \psi $ 是資料行向量，則可以使用 Dirac 標記法來撰寫它 $ \ket { \psi } $ ，其中 $ \ket { \cdot } $ 表示它是單位資料行向量，亦即*ket*向量。</span><span class="sxs-lookup"><span data-stu-id="806e3-193">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="806e3-194">同樣地，資料列向量 $ \psi ^ \dagger $ 會表示為 $ \bra { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-194">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="806e3-195">換句話說，是藉 $ \psi ^ \dagger $ 由將進入層級複雜結合套用至的 [重設] 的元素來取得 $ \psi $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-195">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="806e3-196">Bra-ket 標記法直接表示 $ \braket { \psi | \psi } $ 是向量的內部乘積，也 $ \psi $ 就是定義 $ 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-196">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="806e3-197">一般來說，如果 $ \psi $ 和 $ \phi $ 是量子狀態向量，其內部產品即 $ \braket { \phi | \psi } $ 表示測量狀態的機率 $ \ket { \psi } $ $ \ket { \phi } $ 為 $ | \braket { \phi | \psi } | ^ 2 $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-197">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="806e3-198">下列慣例可用來描述將零值和一個 (單一量子位計算基礎狀態) 編碼的量子狀態：</span><span class="sxs-lookup"><span data-stu-id="806e3-198">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

$$
<span data-ttu-id="806e3-199">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } 、\qquad</span><span class="sxs-lookup"><span data-stu-id="806e3-199">\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad</span></span>
<span data-ttu-id="806e3-200">\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-200">\begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="806e3-201">範例：使用 Dirac 標記法來表示 Hadamard 作業</span><span class="sxs-lookup"><span data-stu-id="806e3-201">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="806e3-202">下列標記法通常用來描述將 Hadamard 閘道套用至 $ \ket { 0 } $ 和 1 (的狀態， $ \ket { } $ 而這會對應至 $ $ $ $ 布洛赫球體) 上 + x 和 x 方向的單位向量：</span><span class="sxs-lookup"><span data-stu-id="806e3-202">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

$$
<span data-ttu-id="806e3-203">\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ，\qquad</span><span class="sxs-lookup"><span data-stu-id="806e3-203">\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad</span></span>
<span data-ttu-id="806e3-204">\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-204">\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="806e3-205">您也可以使用 Dirac 標記法將這些狀態擴充為 $ \ket { 0 } $ 和 $ \ket { 1 } $ 的總和：</span><span class="sxs-lookup"><span data-stu-id="806e3-205">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

$$
<span data-ttu-id="806e3-206">\ket{+}= \frac{1 } { \sqrt { 2 } } (\ket { 0 }  +  \ket { 1 }) ， \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } (\ket { 0 }  -  \ket { 1 }) 。</span><span class="sxs-lookup"><span data-stu-id="806e3-206">\ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="806e3-207">計算基礎向量</span><span class="sxs-lookup"><span data-stu-id="806e3-207">Computational basis vectors</span></span>
<span data-ttu-id="806e3-208">這會示範為何這些狀態通常稱為 *計算基礎*：每個量子狀態一律會表示為計算基礎向量的總和，而這類總和可使用 Dirac 標記法輕鬆表示。</span><span class="sxs-lookup"><span data-stu-id="806e3-208">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="806e3-209">相反地，狀態也會 $ \ket { + } $ $ \ket { - } $ 形成量子狀態的基礎。</span><span class="sxs-lookup"><span data-stu-id="806e3-209">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="806e3-210">您可以從下列事實看出：</span><span class="sxs-lookup"><span data-stu-id="806e3-210">You can see this from the fact that</span></span>

$$
<span data-ttu-id="806e3-211">\ket{0 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) ， \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  -  \ket { - }) 。</span><span class="sxs-lookup"><span data-stu-id="806e3-211">\ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="806e3-212">作為 Dirac 標記法的範例，請考慮使用 braket $ \braket { 0 | 1 } $ ，這是介於 $ 0 $ 和1之間的內部乘積 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-212">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="806e3-213">它可以撰寫為</span><span class="sxs-lookup"><span data-stu-id="806e3-213">It can be written as</span></span> 

<span data-ttu-id="806e3-214">$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 0 \end{bmatrix} \begin{bmatrix} \\\\ 1 \end{bmatrix} = 0。$$</span><span class="sxs-lookup"><span data-stu-id="806e3-214">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="806e3-215">這表示 $ \ket { 0 } $ 和 $ \ket { 1 } $ 是直角向量，表示 $ \braket { 0 | 1 } = \braket { 1 | 0 } = 0 $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-215">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="806e3-216">此外，根據定義 $ \braket { 0 | 0 1 1 1 } = \braket { | } = $ ，這表示這兩個計算基礎向量也可以稱為*orthonormal*。</span><span class="sxs-lookup"><span data-stu-id="806e3-216">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="806e3-217">這些 orthonormal 屬性在下列範例中將會很有用。</span><span class="sxs-lookup"><span data-stu-id="806e3-217">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="806e3-218">如果我們有狀態 $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0， } $ 則因為 $ \braket { 1 | 0 } = 0 $ ，測量 $ 1 $ 的機率為</span><span class="sxs-lookup"><span data-stu-id="806e3-218">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="806e3-219">$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } 。$$</span><span class="sxs-lookup"><span data-stu-id="806e3-219">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="806e3-220">Tensor 產品標記法</span><span class="sxs-lookup"><span data-stu-id="806e3-220">Tensor product notation</span></span>
<span data-ttu-id="806e3-221">Dirac 標記法也包含其中的隱含 tensor product 結構。</span><span class="sxs-lookup"><span data-stu-id="806e3-221">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="806e3-222">這點很重要，因為在量子運算中，兩個不相關的量子暫存器所描述的狀態向量就是兩個狀態向量的 tensor 產品。</span><span class="sxs-lookup"><span data-stu-id="806e3-222">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="806e3-223">如果您想要說明量子計算，很重要的一點是，很重要的是，tensor 產品結構或缺乏。</span><span class="sxs-lookup"><span data-stu-id="806e3-223">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="806e3-224">Tensor 產品結構暗示我們可以撰寫 $ \psi \otimes \phi $ 任何兩個量子狀態向量，也可以 $ \phi $ $ \psi $ 像 $ \ket { \psi } \ket { \phi } $ 明確撰寫一樣， $ \ket { \psi } \otimes \ket { \phi } $ 但 $ \otimes $ 不需要在向量之間撰寫的慣例。</span><span class="sxs-lookup"><span data-stu-id="806e3-224">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="806e3-225">例如，兩個量子位初始化為零狀態的狀態是由</span><span class="sxs-lookup"><span data-stu-id="806e3-225">For example, the state with two qubits initialized to the zero state is given by</span></span>

$$
<span data-ttu-id="806e3-226">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } 0 0 0 0 0。</span><span class="sxs-lookup"><span data-stu-id="806e3-226">\begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="806e3-227">同樣地， $ \ket { 整數 p 的狀態 p } $ $ $ 表示以二進位標記法來編碼整數 p 的量子 $ 狀態 $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-227">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="806e3-228">例如，如果我們想要 $ $ 使用不帶正負號的二進位編碼來表示數位5，我們可以同樣地將它表示為</span><span class="sxs-lookup"><span data-stu-id="806e3-228">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

$$
<span data-ttu-id="806e3-229">\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-229">\ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="806e3-230">在這個標記法中 $ \ket { } $ ，0不需要參考單一量子位狀態，而是*qubit register*儲存二進位編碼為0的量子位 $ $ 暫存器。</span><span class="sxs-lookup"><span data-stu-id="806e3-230">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="806e3-231">這兩種標記法之間的差異通常會從內容中清楚明瞭。</span><span class="sxs-lookup"><span data-stu-id="806e3-231">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="806e3-232">這個慣例有助於簡化第一個可利用下列方式撰寫的範例：</span><span class="sxs-lookup"><span data-stu-id="806e3-232">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

$$
<span data-ttu-id="806e3-233">\begin{bmatrix}1 0 1 0 0 0 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-233">\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="806e3-234">範例：使用 Dirac 標記法描述迭加</span><span class="sxs-lookup"><span data-stu-id="806e3-234">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="806e3-235">如需如何使用 Dirac 標記法來描述量子狀態的另一個範例，請考慮使用下列對等方式來寫入量子狀態，此狀態是對每個長度為 n 的可能位字串的相等迭加 $$</span><span class="sxs-lookup"><span data-stu-id="806e3-235">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

$$
<span data-ttu-id="806e3-236">H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1-1 } \ket { j } = \ket { + } ^ { \otimes n } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-236">H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="806e3-237">在這裡，您可能會想知道為什麼 n 位的總和是從 $ 0 $ 到 $ 2 ^ { n-1 } $ $ $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-237">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="806e3-238">首先要注意的是，有 $ 2 ^ { n 個 } $ 不同的設定， $ n $ 位可以採用。</span><span class="sxs-lookup"><span data-stu-id="806e3-238">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="806e3-239">您可以看到其中一個位可以採用 $ 2 $ 個值，但兩個位可能需要 $ 4 個 $ 值，依此類推。</span><span class="sxs-lookup"><span data-stu-id="806e3-239">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="806e3-240">一般情況下，這表示有 $ 2 ^ n 個 $ 不同的可能位字串，但最大的值是以 $ 1 \cdots 1 = 2 ^ n-1 的其中任何一種， $ 因此它是總和的上限。</span><span class="sxs-lookup"><span data-stu-id="806e3-240">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="806e3-241">請注意，在此範例中，我們不會使用 $ \ket { + } ^ { \otimes n } = \ket { + } $ 來表示為 $ \ket { 0 } ^ { \otimes n } = \ket { 0， } $ 因為此標記慣例通常會保留給計算基礎狀態，且每個量子位都會初始化為零。</span><span class="sxs-lookup"><span data-stu-id="806e3-241">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="806e3-242">雖然這種慣例在這種情況下是合理的，但它並不是在量子運算文獻中採用。</span><span class="sxs-lookup"><span data-stu-id="806e3-242">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="806e3-243">使用 Dirac 標記法來表示線性</span><span class="sxs-lookup"><span data-stu-id="806e3-243">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="806e3-244">Dirac 標記法的另一項不錯的功能，就是它是線性的。</span><span class="sxs-lookup"><span data-stu-id="806e3-244">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="806e3-245">如果我們想要撰寫任何四個量子狀態向量，</span><span class="sxs-lookup"><span data-stu-id="806e3-245">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="806e3-246">$$ (\alpha \ket { \psi }  + \beta \ket { \phi }) \otimes (\gamma \ket { \chi }  +  \delta \ket { \omega }) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } 。$$</span><span class="sxs-lookup"><span data-stu-id="806e3-246">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="806e3-247">也就是說，您可以在 Dirac 標記法中散發 tensor 產品標記法，讓州向量之間的 tensor 產品最後看似一般的乘法。</span><span class="sxs-lookup"><span data-stu-id="806e3-247">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="806e3-248">Bra 向量遵循類似的慣例來 ket 向量。</span><span class="sxs-lookup"><span data-stu-id="806e3-248">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="806e3-249">例如，向量 $ \bra { \psi } \bra { \phi } $ 等同于狀態向量 $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-249">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="806e3-250">如果 ket 向量 $ \ket { \psi } $ 為 $ \alpha \ket { 0 1，則 }  +  \beta \ket { } $ 向量的 bra 向量版本是 $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra { 0 } \alpha ^ \* + \bra { 1 } \beta ^ \* ) $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-250">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="806e3-251">例如，假設我們想要使用量副程式來計算測量狀態 $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 5 0 的機率， } { } \ket { } $ 以將狀態測量為 $ \ket { + } $ 或 $ \ket { - } $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-251">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="806e3-252">然後，裝置會輸出狀態的機率 $ \ket { - } $ 為</span><span class="sxs-lookup"><span data-stu-id="806e3-252">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="806e3-253">$$|\braket{- |\psi}|^ 2 = \left | \frac { 1 } { \sqrt { 2 } } (\bra { 0 }  -  \bra { 1 }) # B2 \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 }) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } 。$$</span><span class="sxs-lookup"><span data-stu-id="806e3-253">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="806e3-254">這種情況下，負號會出現在機率的計算中，是量子干擾的結果，這是量子運算獲得優於傳統運算之優勢的機制之一。</span><span class="sxs-lookup"><span data-stu-id="806e3-254">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="806e3-255">ketbra 或外部產品</span><span class="sxs-lookup"><span data-stu-id="806e3-255">ketbra or outer product</span></span>
<span data-ttu-id="806e3-256">Dirac 標記法中的最後一個值得討論的專案是 *ketbra* 或外部產品。</span><span class="sxs-lookup"><span data-stu-id="806e3-256">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="806e3-257">外部產品會在 Dirac 標記法中表示為 $ \ket { \psi } \bra { \phi } $ ，有時也稱為 ketbras，因為 bras 和 kets 會以與 brakets 相反的順序來進行。</span><span class="sxs-lookup"><span data-stu-id="806e3-257">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="806e3-258">外部產品是透過矩陣乘法來定義，做 $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ 為量子狀態向量 $ \psi $ 和 $ \phi $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-258">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="806e3-259">最簡單且最常見的是此標記法的範例為</span><span class="sxs-lookup"><span data-stu-id="806e3-259">The simplest, and arguably most common example of this notation, is</span></span>

$$
<span data-ttu-id="806e3-260">\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 0 0 \\\\ & \end{bmatrix} \qquad \ket { 1 } \bra { 1 } = \begin{bmatrix} 0 \\\\ 1 0 \end{bmatrix} \begin{bmatrix} & 1 \end{bmatrix} = \begin{bmatrix} 0 & \\\\ & \end{bmatrix} 0 0 0 1。</span><span class="sxs-lookup"><span data-stu-id="806e3-260">\ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="806e3-261">Ketbras 通常稱為投影機，因為它們會將量子狀態投射到固定值。</span><span class="sxs-lookup"><span data-stu-id="806e3-261">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="806e3-262">因為這些作業並不是單一 (，也不會保留向量) 的標準，所以量子電腦無法以決定性的方式套用投影機也不會驚訝。</span><span class="sxs-lookup"><span data-stu-id="806e3-262">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="806e3-263">不過，投影機會以美觀的工作來描述測量在量子狀態上的動作。</span><span class="sxs-lookup"><span data-stu-id="806e3-263">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="806e3-264">例如，如果我們將狀態測量 $ \ket { \psi } $ 為0， $ 則 $ 產生的轉換會因為測量結果而發生狀態的結果</span><span class="sxs-lookup"><span data-stu-id="806e3-264">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="806e3-265">$$\ket{\psi}\right \frac 箭 { 號 (\ket { 0 } \bra { 0 }) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } 、$$</span><span class="sxs-lookup"><span data-stu-id="806e3-265">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="806e3-266">因為您需要測量狀態並將其視為 $ \ket { 0 } $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-266">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="806e3-267">再次重申，這類投影機無法以決定性的方式套用到量子電腦上的狀態。</span><span class="sxs-lookup"><span data-stu-id="806e3-267">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="806e3-268">相反地，它們可以用隨機的方式套用，結果 $ \ket { 0 會 } $ 出現一些固定機率。</span><span class="sxs-lookup"><span data-stu-id="806e3-268">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="806e3-269">這類測量結果的機率可以寫成州量子投影機的預期值</span><span class="sxs-lookup"><span data-stu-id="806e3-269">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

$$
<span data-ttu-id="806e3-270">\bra{\psi} (\ket { 0 } \bra { 0 }) \ket { \psi } = | \braket { \psi | 0 } | ^ 2，$$</span><span class="sxs-lookup"><span data-stu-id="806e3-270">\bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="806e3-271">其中說明投影機只是提供一種新方法來表示測量流程。</span><span class="sxs-lookup"><span data-stu-id="806e3-271">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="806e3-272">相反地，我們會考慮將多量子位狀態的第一個量子位測量為1，如此一來， $ $ 我們也可以使用投影機和 Dirac 標記法方便地描述此程式：</span><span class="sxs-lookup"><span data-stu-id="806e3-272">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

$$
<span data-ttu-id="806e3-273">P (\text { 第一個量子位 = 1 }) = \bra { \psi } \left (\ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n 1 } \right) \ket { \psi } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-273">P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="806e3-274">在這裡，識別矩陣可以用 Dirac 標記法的形式方便寫入</span><span class="sxs-lookup"><span data-stu-id="806e3-274">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

$$
<span data-ttu-id="806e3-275">\boldone= \ket{0 } \bra { 0 } + \ket { 1 1 } \bra { } = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="806e3-275">\boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="806e3-276">如果有兩個量子位，則可以將投影機擴充為</span><span class="sxs-lookup"><span data-stu-id="806e3-276">For the case where there are two-qubits the projector can be expanded as</span></span> 

$$
<span data-ttu-id="806e3-277">\ket{1 1 1 1 } \bra { } \otimes \id = \ket { } \bra { } \otimes (\ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 }) = \ket { 10 } \bra { 10 }  +  \ket { 11 11 } \bra { 11 } 。</span><span class="sxs-lookup"><span data-stu-id="806e3-277">\ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="806e3-278">接著，我們可以看到這與使用資料行向量標記法之 multiqubit 狀態的度量 likelihoods 相關討論一致：</span><span class="sxs-lookup"><span data-stu-id="806e3-278">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

$$
<span data-ttu-id="806e3-279">P (\text { first 量子位 = 1 }) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2$$</span><span class="sxs-lookup"><span data-stu-id="806e3-279">P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="806e3-280">符合多量子位測量的討論。</span><span class="sxs-lookup"><span data-stu-id="806e3-280">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="806e3-281">不過，在多量子位的情況下，此結果的一般化會稍微比使用 Dirac 標記法來表示，而非資料行向量標記法，而且完全等於先前的處理方式。</span><span class="sxs-lookup"><span data-stu-id="806e3-281">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="806e3-282">密度運算子</span><span class="sxs-lookup"><span data-stu-id="806e3-282">Density operators</span></span>

<span data-ttu-id="806e3-283">另一個用來表示使用 Dirac 標記法的實用運算子是 *密度運算子*，有時也稱為 *州運算子*。</span><span class="sxs-lookup"><span data-stu-id="806e3-283">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="806e3-284">量子狀態向量的密度運算子採用 $ \rho 形式 = \ket { \psi } \bra { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="806e3-284">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="806e3-285">以矩陣（而非向量）表示狀態的這個概念通常很方便，因為它提供了一個便利的方式來表示機率計算，同時也可讓您在相同的形式中描述統計的不確定性以及量子不確定性。</span><span class="sxs-lookup"><span data-stu-id="806e3-285">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="806e3-286">一般量子狀態運算子（而不是向量）在量子運算的某些區域中很普遍，但不需要瞭解此欄位的基本概念。</span><span class="sxs-lookup"><span data-stu-id="806e3-286">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="806e3-287">針對感興趣的讀者，建議您閱讀中提供的其中一個參考書， [以取得詳細資訊](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="806e3-287">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="806e3-288">Q# 等同于量子狀態的閘道序列</span><span class="sxs-lookup"><span data-stu-id="806e3-288">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="806e3-289">最後值得一提的一點是量子標記法和程式 Q# 設計語言：在本文的驗證中，我們提到量子狀態是量子運算中資訊的基礎物件。</span><span class="sxs-lookup"><span data-stu-id="806e3-289">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="806e3-290">這可能會令人驚訝，因為沒有 Q# 量子狀態的概念。</span><span class="sxs-lookup"><span data-stu-id="806e3-290">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="806e3-291">相反地，所有狀態只會由用來準備這些狀態的作業描述。</span><span class="sxs-lookup"><span data-stu-id="806e3-291">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="806e3-292">先前的範例是這個的絕佳圖解。</span><span class="sxs-lookup"><span data-stu-id="806e3-292">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="806e3-293">我們可以將結果表示為 $ H ^ { \otimes n } \ket { 0 } $ ，而不是對暫存器中的每個量子位字串表示統一迭加。</span><span class="sxs-lookup"><span data-stu-id="806e3-293">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="806e3-294">以指數方式縮短的狀態原因不但能讓我們傳統方式原因，還可以精確地定義透過軟體堆疊傳播以實行演算法所需的作業。</span><span class="sxs-lookup"><span data-stu-id="806e3-294">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="806e3-295">基於這個理由， Q# 設計用來發出閘道順序，而不是量子狀態; 不過，在理論層級上，這兩個觀點是相等的。</span><span class="sxs-lookup"><span data-stu-id="806e3-295">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
