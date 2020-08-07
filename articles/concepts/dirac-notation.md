---
<span data-ttu-id="04937-101">標題： Dirac 標記法描述：瞭解如何使用 Dirac 標記法來表示配量狀態，以及模擬量子作業。</span><span class="sxs-lookup"><span data-stu-id="04937-101">title: Dirac notation description: Learn about using Dirac notation to represent quantum states and to simulate quantum operations.</span></span>
<span data-ttu-id="04937-102">author： QuantumWriter uid： dirac ms-chap。作者： nawiebe@microsoft.com ms. 日期：12/11/2017 毫秒。主題：發行項不存在：</span><span class="sxs-lookup"><span data-stu-id="04937-102">author: QuantumWriter uid: microsoft.quantum.concepts.dirac ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="04937-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="04937-103">"Q#"</span></span>
- <span data-ttu-id="04937-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="04937-104">"$$v"</span></span>
- <span data-ttu-id="04937-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="04937-105">"$$"</span></span>
- <span data-ttu-id="04937-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="04937-106">"$$"</span></span>
- <span data-ttu-id="04937-107">"$"</span><span class="sxs-lookup"><span data-stu-id="04937-107">"$"</span></span>
- <span data-ttu-id="04937-108">"$"</span><span class="sxs-lookup"><span data-stu-id="04937-108">"$"</span></span>
- <span data-ttu-id="04937-109">"$"</span><span class="sxs-lookup"><span data-stu-id="04937-109">"$"</span></span>
- <span data-ttu-id="04937-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="04937-110">"$$"</span></span>
- <span data-ttu-id="04937-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="04937-111">"\cdots"</span></span>
- <span data-ttu-id="04937-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="04937-112">"bmatrix"</span></span>
- <span data-ttu-id="04937-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="04937-113">"\ddots"</span></span>
- <span data-ttu-id="04937-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="04937-114">"\equiv"</span></span>
- <span data-ttu-id="04937-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="04937-115">"\sum"</span></span>
- <span data-ttu-id="04937-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="04937-116">"\begin"</span></span>
- <span data-ttu-id="04937-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="04937-117">"\end"</span></span>
- <span data-ttu-id="04937-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="04937-118">"\sqrt"</span></span>
- <span data-ttu-id="04937-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="04937-119">"\otimes"</span></span>
- <span data-ttu-id="04937-120">"{"</span><span class="sxs-lookup"><span data-stu-id="04937-120">"{"</span></span>
- <span data-ttu-id="04937-121">"}"</span><span class="sxs-lookup"><span data-stu-id="04937-121">"}"</span></span>
- <span data-ttu-id="04937-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="04937-122">"\text"</span></span>
- <span data-ttu-id="04937-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="04937-123">"\phi"</span></span>
- <span data-ttu-id="04937-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="04937-124">"\kappa"</span></span>
- <span data-ttu-id="04937-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="04937-125">"\psi"</span></span>
- <span data-ttu-id="04937-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="04937-126">"\alpha"</span></span>
- <span data-ttu-id="04937-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="04937-127">"\beta"</span></span>
- <span data-ttu-id="04937-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="04937-128">"\gamma"</span></span>
- <span data-ttu-id="04937-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="04937-129">"\delta"</span></span>
- <span data-ttu-id="04937-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="04937-130">"\omega"</span></span>
- <span data-ttu-id="04937-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="04937-131">"\bra"</span></span>
- <span data-ttu-id="04937-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="04937-132">"\ket"</span></span>
- <span data-ttu-id="04937-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="04937-133">"\boldone"</span></span>
- <span data-ttu-id="04937-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="04937-134">"\\\\"</span></span>
- <span data-ttu-id="04937-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="04937-135">"\\"</span></span>
- <span data-ttu-id="04937-136">"="</span><span class="sxs-lookup"><span data-stu-id="04937-136">"="</span></span>
- <span data-ttu-id="04937-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="04937-137">"\frac"</span></span>
- <span data-ttu-id="04937-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="04937-138">"\text"</span></span>
- <span data-ttu-id="04937-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="04937-139">"\mapsto"</span></span>
- <span data-ttu-id="04937-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="04937-140">"\dagger"</span></span>
- <span data-ttu-id="04937-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="04937-141">"\to"</span></span>
- <span data-ttu-id="04937-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="04937-142">"\begin{cases}"</span></span>
- <span data-ttu-id="04937-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="04937-143">"\end{cases}"</span></span>
- <span data-ttu-id="04937-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="04937-144">"\operatorname"</span></span>
- <span data-ttu-id="04937-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="04937-145">"\braket"</span></span>
- <span data-ttu-id="04937-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="04937-146">"\id"</span></span>
- <span data-ttu-id="04937-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="04937-147">"\expect"</span></span>
- <span data-ttu-id="04937-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="04937-148">"\defeq"</span></span>
- <span data-ttu-id="04937-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="04937-149">"\variance"</span></span>
- <span data-ttu-id="04937-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="04937-150">"\dd"</span></span>
- <span data-ttu-id="04937-151">"&"</span><span class="sxs-lookup"><span data-stu-id="04937-151">"&"</span></span>
- <span data-ttu-id="04937-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="04937-152">"\begin{align}"</span></span>
- <span data-ttu-id="04937-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="04937-153">"\end{align}"</span></span>
- <span data-ttu-id="04937-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="04937-154">"\Lambda"</span></span>
- <span data-ttu-id="04937-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="04937-155">"\lambda"</span></span>
- <span data-ttu-id="04937-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="04937-156">"\Omega"</span></span>
- <span data-ttu-id="04937-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="04937-157">"\mathrm"</span></span>
- <span data-ttu-id="04937-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="04937-158">"\left"</span></span>
- <span data-ttu-id="04937-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="04937-159">"\right"</span></span>
- <span data-ttu-id="04937-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="04937-160">"\qquad"</span></span>
- <span data-ttu-id="04937-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="04937-161">"\times"</span></span>
- <span data-ttu-id="04937-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="04937-162">"\big"</span></span>
- <span data-ttu-id="04937-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="04937-163">"\langle"</span></span>
- <span data-ttu-id="04937-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="04937-164">"\rangle"</span></span>
- <span data-ttu-id="04937-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="04937-165">"\bigg"</span></span>
- <span data-ttu-id="04937-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="04937-166">"\Big"</span></span>
- <span data-ttu-id="04937-167">"|"</span><span class="sxs-lookup"><span data-stu-id="04937-167">"|"</span></span>
- <span data-ttu-id="04937-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="04937-168">"\mathbb"</span></span>
- <span data-ttu-id="04937-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="04937-169">"\vec"</span></span>
- <span data-ttu-id="04937-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="04937-170">"\in"</span></span>
- <span data-ttu-id="04937-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="04937-171">"\texttt"</span></span>
- <span data-ttu-id="04937-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="04937-172">"\ne"</span></span>
- <span data-ttu-id="04937-173">"<"</span><span class="sxs-lookup"><span data-stu-id="04937-173">"<"</span></span>
- <span data-ttu-id="04937-174">">"</span><span class="sxs-lookup"><span data-stu-id="04937-174">">"</span></span>
- <span data-ttu-id="04937-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="04937-175">"\leq"</span></span>
- <span data-ttu-id="04937-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="04937-176">"\geq"</span></span>
- <span data-ttu-id="04937-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="04937-177">"~~"</span></span>
- <span data-ttu-id="04937-178">"~"</span><span class="sxs-lookup"><span data-stu-id="04937-178">"~"</span></span>
- <span data-ttu-id="04937-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="04937-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="04937-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="04937-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="04937-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="04937-181">"\_"</span></span>

---

# <a name="dirac-notation"></a><span data-ttu-id="04937-182">Dirac 標記法</span><span class="sxs-lookup"><span data-stu-id="04937-182">Dirac Notation</span></span>

<span data-ttu-id="04937-183">雖然資料行向量標記法線上性代數中是普遍的，但在處理多個 qubits 時，通常會難以進行量子計算。</span><span class="sxs-lookup"><span data-stu-id="04937-183">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="04937-184">例如，當我們將定義 $ \psi $ 為向量時，不會明確地明確指出 $ \psi $ 是資料列或資料行向量。</span><span class="sxs-lookup"><span data-stu-id="04937-184">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="04937-185">因此，如果和是向量，則即使已定義，也會 $ \phi $ $ \psi $ 同樣不清楚， $ \phi \psi $ 因為在 $ \phi $ 內容中，和的形狀 $ \psi $ 可能不清楚。</span><span class="sxs-lookup"><span data-stu-id="04937-185">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="04937-186">除了向量形狀的多義性外，使用稍早引進的線性代數標記法來表示偶數的簡單向量也非常繁瑣。</span><span class="sxs-lookup"><span data-stu-id="04937-186">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="04937-187">例如，如果我們想要描述 $ $ qubit 狀態，其中每個 qubit 都接受值0， $ $ 則我們會正式地將狀態表示為</span><span class="sxs-lookup"><span data-stu-id="04937-187">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="04937-188">$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="04937-188">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="04937-189">當然，評估此張量產品並不實用，因為向量位於指數大的空間，因此此標記法實際上是可使用先前的標記法提供之狀態的最佳描述。</span><span class="sxs-lookup"><span data-stu-id="04937-189">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="04937-190">[*Dirac 標記法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)會藉由呈現新的語言，以符合精確的量子機制需求，來解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="04937-190">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="04937-191">基於這個理由，我們建議讀者不要查看本節中的範例，做為如何描述配量狀態的一項嚴謹的處方，而是鼓勵讀者將這些內容視為可用於簡化量子概念的建議。</span><span class="sxs-lookup"><span data-stu-id="04937-191">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="04937-192">Dirac 標記法中有兩種類型的向量： *bra*向量和*ket*向量，因此名為，因為當放在一起時，它們會形成*braket*或內部產品。</span><span class="sxs-lookup"><span data-stu-id="04937-192">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="04937-193">如果 $ \psi $ 是資料行向量，我們可以使用 Dirac 標記法將它寫成 $ \ket { \psi } $ ，其中 $ \ket { \cdot } $ 表示它是單位資料行向量，亦即*ket*向量。</span><span class="sxs-lookup"><span data-stu-id="04937-193">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="04937-194">同樣地，資料列向量 $ \psi ^ \dagger $ 也會表示為 $ \bra { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-194">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="04937-195">換句話說，是藉 $ \psi ^ \dagger $ 由將進入取向的複雜 conjugation 套用至的調換元素來取得 $ \psi $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-195">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="04937-196">Bra-ket 標記法直接表示 $ \braket { \psi | \psi } $ 是向量的內部乘積 $ \psi $ 本身，也就是定義 $ 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-196">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="04937-197">更常見的情況是，如果 $ \psi $ 和 $ \phi $ 是配量狀態向量，則其內部產品是 $ \braket { \phi | \psi } $ 指將狀態測量為 $ \ket { \psi } $ $ \ket { \phi } $ $ | \braket { \phi | \psi } | ^ 2 $ 的機率。</span><span class="sxs-lookup"><span data-stu-id="04937-197">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="04937-198">下列慣例是用來描述將零值和一個 (單一 qubit 計算基礎狀態的量子狀態) ：</span><span class="sxs-lookup"><span data-stu-id="04937-198">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

$$
<span data-ttu-id="04937-199">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ，\qquad</span><span class="sxs-lookup"><span data-stu-id="04937-199">\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad</span></span>
<span data-ttu-id="04937-200">\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } 。</span><span class="sxs-lookup"><span data-stu-id="04937-200">\begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="04937-201">範例：代表具有 Dirac 標記法的 Hadamard 作業</span><span class="sxs-lookup"><span data-stu-id="04937-201">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="04937-202">下列標記法通常用來描述將 Hadamard 閘道套用至 $ \ket { 0 } $ 和 $ \ket { 1 } $ (（對應至 $ $ $ $ Bloch) 球體上 + x 和-x 方向的單位向量）所產生的狀態：</span><span class="sxs-lookup"><span data-stu-id="04937-202">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

$$
<span data-ttu-id="04937-203">\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ，\qquad</span><span class="sxs-lookup"><span data-stu-id="04937-203">\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad</span></span>
<span data-ttu-id="04937-204">\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } 。</span><span class="sxs-lookup"><span data-stu-id="04937-204">\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="04937-205">您也可以使用 Dirac 標記法，將這些狀態擴充為 $ \ket { 0 } $ 和 $ \ket { 1 } $ 的總和：</span><span class="sxs-lookup"><span data-stu-id="04937-205">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

$$
<span data-ttu-id="04937-206">\ket{+}= \frac{1 } { \sqrt { 2 } } (\ket { 0 }  +  \ket { 1 }) ， \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } (\ket { 0 }  -  \ket { 1 }) 。</span><span class="sxs-lookup"><span data-stu-id="04937-206">\ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="04937-207">計算基礎向量</span><span class="sxs-lookup"><span data-stu-id="04937-207">Computational basis vectors</span></span>
<span data-ttu-id="04937-208">這會示範為什麼這些狀態通常稱為「*計算基礎*」：每個配量狀態一律會以計算基礎向量的總和表示，而這類總和則可以使用 Dirac 標記法輕鬆表示。</span><span class="sxs-lookup"><span data-stu-id="04937-208">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="04937-209">相反地，這也是狀態， $ \ket { + } $ 而且 $ \ket { - } $ 也會構成量子狀態的基礎。</span><span class="sxs-lookup"><span data-stu-id="04937-209">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="04937-210">您可以從下列事實看出</span><span class="sxs-lookup"><span data-stu-id="04937-210">You can see this from the fact that</span></span>

$$
<span data-ttu-id="04937-211">\ket{0 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) ， \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } (\ket { + }  -  \ket { - }) 。</span><span class="sxs-lookup"><span data-stu-id="04937-211">\ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="04937-212">做為 Dirac 標記法的範例，請考慮使用 braket $ \braket { 0 | 1 } $ ，這是介於 $ 0 $ 和 $ 1 之間的內部產品 $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-212">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="04937-213">它可以撰寫成</span><span class="sxs-lookup"><span data-stu-id="04937-213">It can be written as</span></span> 

<span data-ttu-id="04937-214">$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = 0。$$</span><span class="sxs-lookup"><span data-stu-id="04937-214">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="04937-215">這表示 $ \ket { 0 } $ 和 $ \ket { 1 } $ 是正向向量，表示 $ \braket { 0 | 1 } = \braket { 1 | 0 } = 0 $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-215">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="04937-216">此外，根據定義 $ \braket { 0 | 0 1 1 1 } = \braket { | } = $ ，這表示兩個計算基礎向量也可以稱為*orthonormal*。</span><span class="sxs-lookup"><span data-stu-id="04937-216">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="04937-217">這些 orthonormal 屬性在下列範例中將會很有用。</span><span class="sxs-lookup"><span data-stu-id="04937-217">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="04937-218">如果我們有狀態 $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { 0， } $ 則因為 $ \braket { 1 | 0 } = 0 $ ，測量1的 $ 機率 $ 是</span><span class="sxs-lookup"><span data-stu-id="04937-218">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="04937-219">$$\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } 。$$</span><span class="sxs-lookup"><span data-stu-id="04937-219">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="04937-220">張量產品標記法</span><span class="sxs-lookup"><span data-stu-id="04937-220">Tensor product notation</span></span>
<span data-ttu-id="04937-221">Dirac 標記法也會在其中包含隱含的張量產品結構。</span><span class="sxs-lookup"><span data-stu-id="04937-221">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="04937-222">這一點很重要，因為在量子運算中，兩個不相關的量子暫存器所描述的狀態向量是兩個狀態向量的張量產品。</span><span class="sxs-lookup"><span data-stu-id="04937-222">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="04937-223">如果您想要說明配量計算，就很重要的是，描述張量產品結構或缺乏的架構。</span><span class="sxs-lookup"><span data-stu-id="04937-223">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="04937-224">張量產品結構意指，我們可以撰寫 $ \psi \otimes \phi $ 任何兩個配量狀態向量 $ \phi $ ，而且 $ \psi $ $ \ket { \psi } \ket { \phi } $ 有時會明確寫入為 $ \ket { \psi } \otimes \ket { \phi } $ ，不過 $ \otimes $ 在向量之間寫入的慣例是不必要的。</span><span class="sxs-lookup"><span data-stu-id="04937-224">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="04937-225">例如，具有兩個 qubits 初始化為零狀態的狀態會由指定</span><span class="sxs-lookup"><span data-stu-id="04937-225">For example, the state with two qubits initialized to the zero state is given by</span></span>

$$
<span data-ttu-id="04937-226">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { } = \ket { } \ket { } 0 0 0 0 0。</span><span class="sxs-lookup"><span data-stu-id="04937-226">\begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="04937-227">同樣地， $ \ket { integer p 的狀態 p } $ $ $ 代表以二進位標記法編碼的量子狀態，也就是整數 $ p $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-227">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="04937-228">例如，如果我們想要 $ 使用不帶正負號的二進位編碼來表示數位5， $ 我們可以同樣地將其表示為</span><span class="sxs-lookup"><span data-stu-id="04937-228">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

$$
<span data-ttu-id="04937-229">\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } 。</span><span class="sxs-lookup"><span data-stu-id="04937-229">\ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="04937-230">在此標記法中 $ \ket { } $ ，0不需要參考單一 qubit 狀態，而是*qubit*暫存器，儲存二進位編碼為 $ 0 $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-230">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="04937-231">這兩種標記法之間的差異通常會從內容中清楚明瞭。</span><span class="sxs-lookup"><span data-stu-id="04937-231">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="04937-232">此慣例適用于簡化第一個範例，可以透過下列任何方式撰寫：</span><span class="sxs-lookup"><span data-stu-id="04937-232">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

$$
<span data-ttu-id="04937-233">\begin{bmatrix}1 0 1 0 0 0 0 0 0 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { } = | \cdots \rangle = \ket { } ^ { \otimes n } = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="04937-233">\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="04937-234">範例：描述具有 Dirac 標記法的重迭</span><span class="sxs-lookup"><span data-stu-id="04937-234">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="04937-235">如需如何使用 Dirac 標記法來描述配量狀態的另一個範例，請考慮下列寫入配量狀態的相同方式，這是在每個長度為 n 的可能位字串上相等的重迭 $$</span><span class="sxs-lookup"><span data-stu-id="04937-235">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

$$
<span data-ttu-id="04937-236">H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } 。</span><span class="sxs-lookup"><span data-stu-id="04937-236">H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="04937-237">在這裡，您可能會想知道總和為何會從 $ 0 $ 到 $ 2 ^ { n } -1 $ 的 $ n $ 位。</span><span class="sxs-lookup"><span data-stu-id="04937-237">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="04937-238">首先要注意的是，有 $ 2 ^ { n 個 } $ 不同的設定 $ $ 可接受 n 位。</span><span class="sxs-lookup"><span data-stu-id="04937-238">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="04937-239">您可以看到，其中一個位可以接受2個 $ $ 值，但兩個位可以接受 $ 4 個值等等 $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-239">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="04937-240">一般來說，這表示有 $ 2 ^ n 個不同的 $ 可能位字串，但在其中任何一個中編碼的最大值 $ \cdots 為 1 1 = 2 ^ n-1 $ ，因此是總和的上限。</span><span class="sxs-lookup"><span data-stu-id="04937-240">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="04937-241">在此範例中，我們不會將 $ \ket { + } ^ { \otimes n 用於 } = \ket { + } $ 類似 $ \ket { 0 } ^ { \otimes n } = \ket { 0， } $ 因為此標記慣例通常會保留給每個 qubit 初始化為零的計算基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="04937-241">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="04937-242">雖然這種慣例在此情況下很合理，但不會在「量子計算」文獻中採用。</span><span class="sxs-lookup"><span data-stu-id="04937-242">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="04937-243">使用 Dirac 標記法來表示線性</span><span class="sxs-lookup"><span data-stu-id="04937-243">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="04937-244">Dirac 標記法還有另一項不錯的功能，就是它是線性的事實。</span><span class="sxs-lookup"><span data-stu-id="04937-244">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="04937-245">如果我們想要撰寫四個量子狀態向量，</span><span class="sxs-lookup"><span data-stu-id="04937-245">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="04937-246">$$ (\alpha \ket { \psi }  + \beta \ket { \phi }) \otimes (\gamma \ket { \chi }  +  \delta \ket { \omega }) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } 。$$</span><span class="sxs-lookup"><span data-stu-id="04937-246">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="04937-247">也就是說，您可以在 Dirac 標記法中散發張量產品標記法，讓州向量之間的張量產品看起來就像一般乘法。</span><span class="sxs-lookup"><span data-stu-id="04937-247">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="04937-248">Bra 向量遵循類似的慣例來 ket 向量。</span><span class="sxs-lookup"><span data-stu-id="04937-248">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="04937-249">例如，向量等同于 $ \bra { \psi } \bra { \phi } $ $ \psi ^ \dagger \otimes \phi ^ \dagger = \psi \otimes \phi) ^ (\dagger $ 的狀態向量。</span><span class="sxs-lookup"><span data-stu-id="04937-249">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="04937-250">如果 ket 向量 $ \ket { \psi } $ 為 $ \alpha \ket { 0 1，則 }  +  \beta \ket { } $ 向量的 bra 向量版本會 $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra { 0 } \alpha ^ \* + \bra { 1 } \beta ^ \* ) $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-250">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="04937-251">例如，假設我們想要計算測量狀態 $ \ket { \psi } = \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 5 0 的機率，方法是使用配量 } { 程式來測量狀態 } \ket { } $ 為 $ \ket { + } $ 或 $ \ket { - } $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-251">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="04937-252">然後，裝置會輸出狀態為的機率 $ \ket { - } $ 為</span><span class="sxs-lookup"><span data-stu-id="04937-252">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="04937-253">$$|\braket{- |\psi}|^ 2 = \left | \frac { 1 } { \sqrt { 2 } } (\bra { 0 }  -  \bra { 1 }) # B2 \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 }) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } 。$$</span><span class="sxs-lookup"><span data-stu-id="04937-253">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="04937-254">負號出現在機率計算中的事實，是一種量子干擾的表現，這是配量運算透過傳統運算獲得優勢的機制之一。</span><span class="sxs-lookup"><span data-stu-id="04937-254">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="04937-255">ketbra 或外部產品</span><span class="sxs-lookup"><span data-stu-id="04937-255">ketbra or outer product</span></span>
<span data-ttu-id="04937-256">在 Dirac 標記法中，值得討論的最後一個專案是*ketbra*或外部產品。</span><span class="sxs-lookup"><span data-stu-id="04937-256">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="04937-257">外部產品在 Dirac 標記法中是以形式呈現 $ \ket { \psi } \bra { \phi } $ ，有時也稱為 ketbras，因為 bras 和 kets 發生的順序與 brakets 相反。</span><span class="sxs-lookup"><span data-stu-id="04937-257">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="04937-258">外部產品是透過矩陣乘法定義，做 $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ 為量子狀態向量 $ \psi $ 和 $ \phi $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-258">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="04937-259">最簡單且可說是此標記法的最常見範例，就是</span><span class="sxs-lookup"><span data-stu-id="04937-259">The simplest, and arguably most common example of this notation, is</span></span>

$$
<span data-ttu-id="04937-260">\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\\\ 0 & 0 \end{bmatrix} \qquad \ket { 1 } \bra { 1 } = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \begin{bmatrix} 0 & 1 \end{bmatrix} = \begin{bmatrix} 0 & \\\\ & \end{bmatrix} 0 0 1。</span><span class="sxs-lookup"><span data-stu-id="04937-260">\ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="04937-261">Ketbras 通常稱為投影機，因為它們會將配量狀態投射到固定值上。</span><span class="sxs-lookup"><span data-stu-id="04937-261">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="04937-262">因為這些作業不是單一 (，甚至不會保留向量) 的標準，所以量子電腦無法以決定性的方式套用投影機。</span><span class="sxs-lookup"><span data-stu-id="04937-262">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="04937-263">不過，投影機會執行一項美觀的作業來描述測量在配量狀態上的動作。</span><span class="sxs-lookup"><span data-stu-id="04937-263">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="04937-264">例如，如果我們將某個狀態測量 $ \ket { \psi } $ 為0，則 $ 產生的轉換會 $ 因為測量而導致狀態體驗為</span><span class="sxs-lookup"><span data-stu-id="04937-264">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="04937-265">$$\ket{\psi}\right \frac 箭 { 號 (\ket { 0 } \bra { 0 }) \ket { \psi } } { | \braket { 0 0 | \psi } | } = \ket { } ，$$</span><span class="sxs-lookup"><span data-stu-id="04937-265">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="04937-266">如果您要測量狀態，並將其尋找為0，則會預期為一 $ \ket { } $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-266">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="04937-267">再次重申，這類投影機無法以決定性的方式套用到量子電腦上的狀態。</span><span class="sxs-lookup"><span data-stu-id="04937-267">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="04937-268">相反地，它們最適合用來隨機套用，結果 $ \ket { 0 會 } $ 出現一些固定機率。</span><span class="sxs-lookup"><span data-stu-id="04937-268">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="04937-269">這類測量的機率可能會以狀態中的「量子投影機」預期值來寫入</span><span class="sxs-lookup"><span data-stu-id="04937-269">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

$$
<span data-ttu-id="04937-270">\bra{\psi} (\ket { 0 } \bra { 0 }) \ket { \psi } = | \braket { \psi | 0 } | ^ 2，$$</span><span class="sxs-lookup"><span data-stu-id="04937-270">\bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="04937-271">其中說明投影機只是提供一種新的方式來表達測量流程。</span><span class="sxs-lookup"><span data-stu-id="04937-271">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="04937-272">如果改為考慮將多 qubit 狀態的第一個 qubit 測量為1， $ $ 則我們也可以使用投影機和 Dirac 標記法來方便地描述此程式：</span><span class="sxs-lookup"><span data-stu-id="04937-272">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

$$
<span data-ttu-id="04937-273">P (\text { 第一個 qubit = 1 }) = \bra { \psi } \left (\ket { 1 } \bra { } \otimes \boldone ^ { \otimes 個 n-1 個 } \right) \ket { \psi } 。</span><span class="sxs-lookup"><span data-stu-id="04937-273">P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="04937-274">在這裡，您可以用 Dirac 標記法輕鬆地將身分識別矩陣寫成</span><span class="sxs-lookup"><span data-stu-id="04937-274">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

$$
<span data-ttu-id="04937-275">\boldone= \ket{0 } \bra { 0 1 1 1 } + \ket { } \bra { } = \begin{bmatrix} & 0 \\\\ 0 & 1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="04937-275">\boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="04937-276">在有兩個 qubits 的情況下，投影機可以擴充為</span><span class="sxs-lookup"><span data-stu-id="04937-276">For the case where there are two-qubits the projector can be expanded as</span></span> 

$$
<span data-ttu-id="04937-277">\ket{1 1 1 } \bra { } \otimes \id = \ket { } \bra { 1 } \otimes (\ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 }) = \ket { 10 } \bra { 10 }  +  \ket { 11 11 } \bra { } 。</span><span class="sxs-lookup"><span data-stu-id="04937-277">\ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="04937-278">然後，我們可以看到這與使用資料行向量標記法之 multiqubit 狀態的度量 likelihoods 討論一致：</span><span class="sxs-lookup"><span data-stu-id="04937-278">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

$$
<span data-ttu-id="04937-279">P (\text { first qubit = 1 }) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e 11 \_ { } ^ \dagger) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2，$$</span><span class="sxs-lookup"><span data-stu-id="04937-279">P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="04937-280">其中符合多 qubit 的測量討論。</span><span class="sxs-lookup"><span data-stu-id="04937-280">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="04937-281">不過，此結果對多 qubit 案例的一般化，使用 Dirac 標記法比資料行向量標記法更直接表達，而且完全等同于先前的處理。</span><span class="sxs-lookup"><span data-stu-id="04937-281">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="04937-282">密度運算子</span><span class="sxs-lookup"><span data-stu-id="04937-282">Density operators</span></span>

<span data-ttu-id="04937-283">另一個使用 Dirac 標記法來表示的有用運算子是*密度運算子*，有時也稱為「*狀態運算子*」。</span><span class="sxs-lookup"><span data-stu-id="04937-283">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="04937-284">量子狀態向量的密度運算子採用 $ \rho 格式 = \ket { \psi } \bra { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="04937-284">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="04937-285">將狀態表示為矩陣（而不是向量）的這個概念通常很方便，因為它提供便利的方式來表示機率計算，也允許一個描述統計不確定性以及相同形式內的量子不確定性。</span><span class="sxs-lookup"><span data-stu-id="04937-285">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="04937-286">一般的量子狀態運算子（而不是向量）在量子運算的某些區域中很普遍，但不一定要瞭解此欄位的基本概念。</span><span class="sxs-lookup"><span data-stu-id="04937-286">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="04937-287">對於感興趣的讀者，建議您閱讀中所提供的其中一個參考書籍，[以取得詳細資訊](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="04937-287">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="04937-288">Q#閘道序列相當於量子狀態</span><span class="sxs-lookup"><span data-stu-id="04937-288">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="04937-289">關於量子標記法和程式設計語言的最後一點 Q# ：我們在本檔的萌芽中提到，配量狀態是量子運算中資訊的基本物件。</span><span class="sxs-lookup"><span data-stu-id="04937-289">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="04937-290">這可能會令人驚訝，因為沒有配 Q# 量狀態的概念。</span><span class="sxs-lookup"><span data-stu-id="04937-290">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="04937-291">相反地，所有狀態只會由用來準備它們的作業來描述。</span><span class="sxs-lookup"><span data-stu-id="04937-291">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="04937-292">先前的範例是這個的絕佳說明。</span><span class="sxs-lookup"><span data-stu-id="04937-292">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="04937-293">我們可以將結果表示為 $ H ^ { \otimes n } \ket { 0 } $ ，而不是在暫存器中的每個配量位字串上表示統一的重迭。</span><span class="sxs-lookup"><span data-stu-id="04937-293">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="04937-294">這種狀態的指數較短描述不僅具有我們可以傳統方式其相關原因的優點，還會簡明扼要地定義透過軟體堆疊傳播以執行演算法所需的作業。</span><span class="sxs-lookup"><span data-stu-id="04937-294">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="04937-295">基於這個理由，的 Q# 設計是用來發出閘道序列，而不是配量狀態; 不過，理論層級的兩個觀點是相等的。</span><span class="sxs-lookup"><span data-stu-id="04937-295">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
