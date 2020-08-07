---
<span data-ttu-id="d7322-101">標題： Pauli 測量描述：瞭解如何使用單一和多 qubit 的 Pauli 測量作業。</span><span class="sxs-lookup"><span data-stu-id="d7322-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="d7322-102">author： QuantumWriter uid： pauli ms-chap。作者： nawiebe@microsoft.com ms. 日期：12/11/2017 毫秒。主題：發行項不存在：</span><span class="sxs-lookup"><span data-stu-id="d7322-102">author: QuantumWriter uid: microsoft.quantum.concepts.pauli ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="d7322-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="d7322-103">"Q#"</span></span>
- <span data-ttu-id="d7322-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="d7322-104">"$$v"</span></span>
- <span data-ttu-id="d7322-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="d7322-105">"$$"</span></span>
- <span data-ttu-id="d7322-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="d7322-106">"$$"</span></span>
- <span data-ttu-id="d7322-107">"$"</span><span class="sxs-lookup"><span data-stu-id="d7322-107">"$"</span></span>
- <span data-ttu-id="d7322-108">"$"</span><span class="sxs-lookup"><span data-stu-id="d7322-108">"$"</span></span>
- <span data-ttu-id="d7322-109">"$"</span><span class="sxs-lookup"><span data-stu-id="d7322-109">"$"</span></span>
- <span data-ttu-id="d7322-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="d7322-110">"$$"</span></span>
- <span data-ttu-id="d7322-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="d7322-111">"\cdots"</span></span>
- <span data-ttu-id="d7322-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="d7322-112">"bmatrix"</span></span>
- <span data-ttu-id="d7322-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="d7322-113">"\ddots"</span></span>
- <span data-ttu-id="d7322-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="d7322-114">"\equiv"</span></span>
- <span data-ttu-id="d7322-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="d7322-115">"\sum"</span></span>
- <span data-ttu-id="d7322-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="d7322-116">"\begin"</span></span>
- <span data-ttu-id="d7322-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="d7322-117">"\end"</span></span>
- <span data-ttu-id="d7322-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="d7322-118">"\sqrt"</span></span>
- <span data-ttu-id="d7322-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="d7322-119">"\otimes"</span></span>
- <span data-ttu-id="d7322-120">"{"</span><span class="sxs-lookup"><span data-stu-id="d7322-120">"{"</span></span>
- <span data-ttu-id="d7322-121">"}"</span><span class="sxs-lookup"><span data-stu-id="d7322-121">"}"</span></span>
- <span data-ttu-id="d7322-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="d7322-122">"\text"</span></span>
- <span data-ttu-id="d7322-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="d7322-123">"\phi"</span></span>
- <span data-ttu-id="d7322-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="d7322-124">"\kappa"</span></span>
- <span data-ttu-id="d7322-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="d7322-125">"\psi"</span></span>
- <span data-ttu-id="d7322-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="d7322-126">"\alpha"</span></span>
- <span data-ttu-id="d7322-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="d7322-127">"\beta"</span></span>
- <span data-ttu-id="d7322-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="d7322-128">"\gamma"</span></span>
- <span data-ttu-id="d7322-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="d7322-129">"\delta"</span></span>
- <span data-ttu-id="d7322-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="d7322-130">"\omega"</span></span>
- <span data-ttu-id="d7322-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="d7322-131">"\bra"</span></span>
- <span data-ttu-id="d7322-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="d7322-132">"\ket"</span></span>
- <span data-ttu-id="d7322-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="d7322-133">"\boldone"</span></span>
- <span data-ttu-id="d7322-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="d7322-134">"\\\\"</span></span>
- <span data-ttu-id="d7322-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="d7322-135">"\\"</span></span>
- <span data-ttu-id="d7322-136">"="</span><span class="sxs-lookup"><span data-stu-id="d7322-136">"="</span></span>
- <span data-ttu-id="d7322-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="d7322-137">"\frac"</span></span>
- <span data-ttu-id="d7322-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="d7322-138">"\text"</span></span>
- <span data-ttu-id="d7322-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="d7322-139">"\mapsto"</span></span>
- <span data-ttu-id="d7322-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="d7322-140">"\dagger"</span></span>
- <span data-ttu-id="d7322-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="d7322-141">"\to"</span></span>
- <span data-ttu-id="d7322-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="d7322-142">"\begin{cases}"</span></span>
- <span data-ttu-id="d7322-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="d7322-143">"\end{cases}"</span></span>
- <span data-ttu-id="d7322-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="d7322-144">"\operatorname"</span></span>
- <span data-ttu-id="d7322-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="d7322-145">"\braket"</span></span>
- <span data-ttu-id="d7322-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="d7322-146">"\id"</span></span>
- <span data-ttu-id="d7322-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="d7322-147">"\expect"</span></span>
- <span data-ttu-id="d7322-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="d7322-148">"\defeq"</span></span>
- <span data-ttu-id="d7322-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="d7322-149">"\variance"</span></span>
- <span data-ttu-id="d7322-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="d7322-150">"\dd"</span></span>
- <span data-ttu-id="d7322-151">"&"</span><span class="sxs-lookup"><span data-stu-id="d7322-151">"&"</span></span>
- <span data-ttu-id="d7322-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="d7322-152">"\begin{align}"</span></span>
- <span data-ttu-id="d7322-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="d7322-153">"\end{align}"</span></span>
- <span data-ttu-id="d7322-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="d7322-154">"\Lambda"</span></span>
- <span data-ttu-id="d7322-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="d7322-155">"\lambda"</span></span>
- <span data-ttu-id="d7322-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="d7322-156">"\Omega"</span></span>
- <span data-ttu-id="d7322-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="d7322-157">"\mathrm"</span></span>
- <span data-ttu-id="d7322-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="d7322-158">"\left"</span></span>
- <span data-ttu-id="d7322-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="d7322-159">"\right"</span></span>
- <span data-ttu-id="d7322-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="d7322-160">"\qquad"</span></span>
- <span data-ttu-id="d7322-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="d7322-161">"\times"</span></span>
- <span data-ttu-id="d7322-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="d7322-162">"\big"</span></span>
- <span data-ttu-id="d7322-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="d7322-163">"\langle"</span></span>
- <span data-ttu-id="d7322-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="d7322-164">"\rangle"</span></span>
- <span data-ttu-id="d7322-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="d7322-165">"\bigg"</span></span>
- <span data-ttu-id="d7322-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="d7322-166">"\Big"</span></span>
- <span data-ttu-id="d7322-167">"|"</span><span class="sxs-lookup"><span data-stu-id="d7322-167">"|"</span></span>
- <span data-ttu-id="d7322-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="d7322-168">"\mathbb"</span></span>
- <span data-ttu-id="d7322-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="d7322-169">"\vec"</span></span>
- <span data-ttu-id="d7322-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="d7322-170">"\in"</span></span>
- <span data-ttu-id="d7322-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="d7322-171">"\texttt"</span></span>
- <span data-ttu-id="d7322-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="d7322-172">"\ne"</span></span>
- <span data-ttu-id="d7322-173">"<"</span><span class="sxs-lookup"><span data-stu-id="d7322-173">"<"</span></span>
- <span data-ttu-id="d7322-174">">"</span><span class="sxs-lookup"><span data-stu-id="d7322-174">">"</span></span>
- <span data-ttu-id="d7322-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="d7322-175">"\leq"</span></span>
- <span data-ttu-id="d7322-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="d7322-176">"\geq"</span></span>
- <span data-ttu-id="d7322-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="d7322-177">"~~"</span></span>
- <span data-ttu-id="d7322-178">"~"</span><span class="sxs-lookup"><span data-stu-id="d7322-178">"~"</span></span>
- <span data-ttu-id="d7322-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="d7322-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="d7322-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="d7322-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="d7322-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="d7322-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="d7322-182">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="d7322-182">Pauli Measurements</span></span>

<span data-ttu-id="d7322-183">在先前的討論中，我們著重于計算基礎測量。</span><span class="sxs-lookup"><span data-stu-id="d7322-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="d7322-184">事實上，從標記的角度來看，在計量運算中所發生的其他常見測量，在計算基礎測量方面很方便表達。</span><span class="sxs-lookup"><span data-stu-id="d7322-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="d7322-185">當您使用時 Q# ，最常見的測量類型可能是*Pauli 測量*，這會將計算基礎測量一般化以包含其他基底的度量，以及不同 qubits 之間的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="d7322-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="d7322-186">在這種情況下，通常會討論測量 Pauli 運算子，通常是如 $ x、Y、z $ 或 $ z \otimes z、x \otimes x、x \otimes Y $ 等等的運算子。</span><span class="sxs-lookup"><span data-stu-id="d7322-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="d7322-187">>在中 Q# ，多 qubit 的 Pauli 運算子通常會由類型的陣列表示 `Pauli[]` 。</span><span class="sxs-lookup"><span data-stu-id="d7322-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="d7322-188">>例如，若要表示 $ X \otimes Z \otimes Y $ ，您可以使用陣列 `[PauliX, PauliZ, PauliY]` 。</span><span class="sxs-lookup"><span data-stu-id="d7322-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="d7322-189">討論 Pauli 運算子方面的測量，特別是在量子錯誤更正的子欄位中。</span><span class="sxs-lookup"><span data-stu-id="d7322-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="d7322-190">在中 Q# ，我們會遵循類似的慣例，我們現在會說明這種替代的度量觀點。</span><span class="sxs-lookup"><span data-stu-id="d7322-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="d7322-191">在探究到如何思考 Pauli 測量的詳細資料之前，請考慮測量量子電腦內的單一 qubit 對量子狀態的作用。</span><span class="sxs-lookup"><span data-stu-id="d7322-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="d7322-192">假設我們有一個 qubit 的配量 $ $ 狀態，然後測量一個 qubit 立即的規則 $ $ ，這是狀態可能出現在 2 ^ n 個可能性的一半。</span><span class="sxs-lookup"><span data-stu-id="d7322-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="d7322-193">換句話說，測量會將量子狀態投射到兩個半形的其中一個。</span><span class="sxs-lookup"><span data-stu-id="d7322-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="d7322-194">我們可以將我們認為測量的方式一般化，以反映此直覺。</span><span class="sxs-lookup"><span data-stu-id="d7322-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="d7322-195">為了簡潔地識別這些 subspaces，我們需要用來描述它們的語言。</span><span class="sxs-lookup"><span data-stu-id="d7322-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="d7322-196">描述兩個 subspaces 的其中一種方式，就是透過僅具有兩個唯一特徵值的矩陣來指定它們，慣例是 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="d7322-197">如需以這種方式描述 subspaces 的簡單範例，請考慮使用 $ Z $ ：</span><span class="sxs-lookup"><span data-stu-id="d7322-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="d7322-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="d7322-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="d7322-199">藉由讀取 Pauli-Z 矩陣的對角線 $ 元素 $ ，我們可以看到 $ Z $ 有兩個特徵向量（ $ \ket { 0 } $ 和 $ \ket { 1 } $ ），以及對應的特徵值 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="d7322-200">因此，如果我們測量 qubit，並取得 `Zero` 對應至狀態 $ \ket { 0) 的 (} $ ，我們就知道 qubit 的狀態是 $ Z 運算子的 + 1 $ eigenstate $ $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="d7322-201">同樣地，如果我們取得 `One` ，我們知道我們的 qubit 狀態是 z 的 $ -1 $ eigenstate $ $ 。此程式稱為「測量 Pauli Z」的 Pauli 度量語言， $ $ 完全等同于執行計算基礎測量。</span><span class="sxs-lookup"><span data-stu-id="d7322-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="d7322-202">任何 $ \times $ 屬於 Z 的單一轉換的 2 2 矩陣 $ $ 也都符合此準則。</span><span class="sxs-lookup"><span data-stu-id="d7322-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="d7322-203">也就是說，我們也可以使用一個 $ = u ^ \dagger Z u 的矩陣 $ ，其中 $ u $ 是任何其他的單一矩陣，以提供一個矩陣，在其 $ \pm 1 特徵向量中定義度量的兩個結果 $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="d7322-204">Pauli 量值的標記法會藉由 $ 將 X、Y、Z 量值識別為對等的測量值，來參考這個單一等價項， $ 以取得來自 qubit 的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7322-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="d7322-205">為了方便起見，以下提供這些測量。</span><span class="sxs-lookup"><span data-stu-id="d7322-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="d7322-206">|Pauli 測量 | 單一轉換|</span><span class="sxs-lookup"><span data-stu-id="d7322-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="d7322-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="d7322-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="d7322-208">|$ $ X |$H               $                    |</span><span class="sxs-lookup"><span data-stu-id="d7322-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="d7322-209">|$ $ Y |$HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="d7322-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="d7322-210">也就是說，使用這種語言，「測量 $ Y」等同于套用 $ $ HS ^， \dagger $ 然後以計算為基礎，其中是內建 [`S`](xref:microsoft.quantum.intrinsic.s) 的量子作業，有時稱為「階段閘道」，而且可以由單一矩陣模擬</span><span class="sxs-lookup"><span data-stu-id="d7322-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="d7322-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="d7322-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="d7322-212">1 & 0 \\\\ 0 & i \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="d7322-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="d7322-213">這也相當於將 $ HS ^ 套用 \dagger $ 到量子狀態向量，然後測量 $ Z $ ，讓下列作業相當於 `Measure([PauliY], [q])` ：</span><span class="sxs-lookup"><span data-stu-id="d7322-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="d7322-214">藉由轉換回計算基礎來尋找正確的狀態，這是將 $ SH 套用 $ 到量子狀態向量的數量; 在上述程式碼片段中，轉換回計算基礎的動作會透過使用區塊來自動處理 `within … apply` 。</span><span class="sxs-lookup"><span data-stu-id="d7322-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="d7322-215">在中 Q# ，我們會將結果---也就是，從與---狀態互動所解壓縮的傳統資訊是由 `Result` 值 $ j \in \\ { \texttt { 零提供 } ， \texttt { 一個 } \\ } $ 表示結果是否在 $ Pauli 運算子的 (-1) ^ j $ eigenspace 中。</span><span class="sxs-lookup"><span data-stu-id="d7322-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="d7322-216">多 qubit 測量</span><span class="sxs-lookup"><span data-stu-id="d7322-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="d7322-217">多 qubit Pauli 運算子的度量定義類似，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7322-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="d7322-218">Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & -1 0 0 0 0 & \\\\ & & & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1。</span><span class="sxs-lookup"><span data-stu-id="d7322-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="d7322-219">因此，兩個 Pauli z 運算子的張量產品會 $ $ 形成一個矩陣，其中包含由 $ + 1 $ 和 $ -1 特徵值 $ 組成的兩個空格。</span><span class="sxs-lookup"><span data-stu-id="d7322-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="d7322-220">就像單一 qubit 的情況一樣，兩者都構成一半空間，這表示可存取的兩個向量空間一半屬於 $ + 1 $ eigenspace，其餘一半則是 $ -1 $ eigenspace。</span><span class="sxs-lookup"><span data-stu-id="d7322-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="d7322-221">一般來說，您可以從張量產品的定義中查看 Pauli-Z 運算子的任何張量產品，以及身分 $ $ 識別也會遵守這項功能。</span><span class="sxs-lookup"><span data-stu-id="d7322-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="d7322-222">例如</span><span class="sxs-lookup"><span data-stu-id="d7322-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="d7322-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="d7322-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="d7322-224">1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="d7322-225">0 & 1 & 0 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="d7322-226">0 & 0 & -1 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="d7322-227">0 & 0 & 0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="d7322-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="d7322-228">如前所述，這類矩陣的任何單一轉換也會描述 \pm 1 特徵值所標示的兩個半形 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="d7322-229">例如， $ x \otimes x = h \otimes h (z z， \otimes \otimes $ 從 z HXH 的識別) H $ h = $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="d7322-230">類似于一 qubit 的情況，所有的雙 qubit Pauli 量值都可以撰寫為 $ u ^ \dagger (Z \otimes \id) u $ （適用于 $ 4 4 的 \times $ 單一矩陣 $ U） $ 。我們會列舉下表中的轉換。</span><span class="sxs-lookup"><span data-stu-id="d7322-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="d7322-231">>在下表中，我們使用 $ \operatorname { SWAP } $ 來表示矩陣 >$$</span><span class="sxs-lookup"><span data-stu-id="d7322-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="d7322-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="d7322-232">> \begin{align}</span></span>
<span data-ttu-id="d7322-233">>     \operatorname{交換 } &=</span><span class="sxs-lookup"><span data-stu-id="d7322-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="d7322-234">>     \left (\begin { 矩陣}</span><span class="sxs-lookup"><span data-stu-id="d7322-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="d7322-235">>1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="d7322-236">>0 & 0 & 1 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="d7322-237">>0 & 1 & 0 & 0\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="d7322-238">>0 0 0 & & & 1 > \end { 矩陣 } \right) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="d7322-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="d7322-239">> $$</span><span class="sxs-lookup"><span data-stu-id="d7322-239">> $$</span></span>
<span data-ttu-id="d7322-240">>用來模擬內部作業 [`SWAP`](xref:microsoft.quantum.intrinsic) 。</span><span class="sxs-lookup"><span data-stu-id="d7322-240">> used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

<span data-ttu-id="d7322-241">|Pauli 測量 | 單一轉換|</span><span class="sxs-lookup"><span data-stu-id="d7322-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="d7322-242">|$ \otimes \boldone Z $| $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="d7322-242">| $Z \otimes \boldone$ | $\boldone \otimes \boldone$ |</span></span>
<span data-ttu-id="d7322-243">|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|</span><span class="sxs-lookup"><span data-stu-id="d7322-243">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="d7322-244">|$ \otimes \boldone X $| $\otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="d7322-244">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="d7322-245">|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="d7322-245">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="d7322-246">|$\boldone \otimesZ $ | $ \operatorname { 交換 } $|</span><span class="sxs-lookup"><span data-stu-id="d7322-246">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="d7322-247">|$\boldone \otimesX $ | $ (H \otimes \boldone) \operatorname { 交換 } $|</span><span class="sxs-lookup"><span data-stu-id="d7322-247">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="d7322-248">|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone) \operatorname { SWAP } $|</span><span class="sxs-lookup"><span data-stu-id="d7322-248">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="d7322-249">|$Z \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="d7322-249">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="d7322-250">|$X \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes \boldone) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-250">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="d7322-251">|$Y \otimesZ $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes \boldone) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-251">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="d7322-252">|$Z \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-252">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="d7322-253">|$X \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-253">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="d7322-254">|$Y \otimesX $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-254">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="d7322-255">|$Z \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (\boldone \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-255">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="d7322-256">|$X \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (H \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-256">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="d7322-257">|$Y \otimesY $ | $ \operatorname { cnot-contains } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="d7322-257">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="d7322-258">在這裡，作業 [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) 會因為下列原因而出現。</span><span class="sxs-lookup"><span data-stu-id="d7322-258">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="d7322-259">不包含矩陣的每個 Pauli 量值， $ \boldone $ 都相當於上述推理的單一到 $ z \otimes $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-259">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="d7322-260">$Z z 的特徵值 \otimes $ 僅取決於組成每個計算基礎向量的 qubits 同位檢查，而受控制的非作業則是用來計算此同位，並將其儲存在第一位。</span><span class="sxs-lookup"><span data-stu-id="d7322-260">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="d7322-261">然後在測量第一個位之後，我們就可以復原結果半形的識別，這相當於測量 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="d7322-261">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="d7322-262">另一個注意事項：雖然假設測量 $ z \otimes z $ 的方式相當於依序測量 $ z \otimes \mathbb { 1 } $ 和 $ \mathbb { 1 } \otimes z $ ，但此假設為 false。</span><span class="sxs-lookup"><span data-stu-id="d7322-262">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="d7322-263">原因是測量 $ z \otimes z 將配 $ 量狀態投射到 $ 這些運算子的 + 1 $ 或 $ -1 $ eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="d7322-263">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="d7322-264">測量 $ z \otimes \mathbb { 1 } $ ，然後再 $ \mathbb { } \otimes $ 將配量狀態向量投射到 z 1 的一半空間 $ \otimes \mathbb { } $ ，然後到 $ \mathbb { 1 } \otimes z $ 的一半空間。因為有四個計算基礎的向量，同時執行這兩個度量會將狀態縮減為四分之一空間，因而減少為單一計算基礎向量。</span><span class="sxs-lookup"><span data-stu-id="d7322-264">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="d7322-265">Qubits 之間的相互關聯</span><span class="sxs-lookup"><span data-stu-id="d7322-265">Correlations between qubits</span></span>
<span data-ttu-id="d7322-266">另一個查看 Pauli 矩陣（例如 x x 或 z z）之張量產品的方式， $ \otimes $ $ \otimes $ 是這些測量可讓您查看儲存在兩個 qubits 之間相互關聯中的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7322-266">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="d7322-267">測量 $ X \otimes \id $ 可讓您查看本機儲存在第一個 qubit 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7322-267">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="d7322-268">雖然這兩種類型的測量在量子運算中也同樣有價值，但前者也會照亮量子運算的威力。</span><span class="sxs-lookup"><span data-stu-id="d7322-268">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="d7322-269">它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一 qubit 中，而是會一次儲存在所有 qubits 中，因此，只有透過聯合 (測量來查看（例如 $ z \otimes z) ， $ 這項資訊才會變成資訊清單。</span><span class="sxs-lookup"><span data-stu-id="d7322-269">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="d7322-270">例如，在錯誤修正中，我們通常會想要瞭解在學習嘗試保護的狀態時，所發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="d7322-270">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="d7322-271">「[翻轉」程式碼範例會示範](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)如何使用 $ z \otimes z \otimes \id $ 和 $ \id \otimes z \otimes $ < z 等度量來執行這項操作。--TODO：只要有位翻轉程式碼範例在上線上，就會將此變更為範例瀏覽器的連結。</span><span class="sxs-lookup"><span data-stu-id="d7322-271">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="d7322-272">也可以測量任意的 Pauli 運算子，例如 $ X \otimes Y \otimes Z \otimes \boldone $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-272">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="d7322-273">Pauli 運算子的所有這類張量產品只有兩個特徵值 $ \pm 1 $ ，而這兩個 eigenspaces 構成整個向量空間的半個空格。</span><span class="sxs-lookup"><span data-stu-id="d7322-273">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="d7322-274">因此，它們會符合上面所述的需求。</span><span class="sxs-lookup"><span data-stu-id="d7322-274">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="d7322-275">在中 Q# ， $ $ 如果測量結果產生 eigenspace 的正負號 $ (-1) ^ j，這類測量就會傳回 j $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-275">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="d7322-276">將 Pauli 測量當做內建的功能會很 Q# 有説明，因為測量這類運算子需要較長的受控制-NOT 閘道和基礎轉換鏈，以描述將作業 $ $ 表示為 Z 和之張量產品所需的 diagonalizing U 閘道 $ $ $ \id $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-276">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="d7322-277">藉由指定您想要執行上述其中一項預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎測量提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7322-277">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="d7322-278">Q#自動為您處理所有必要的基礎轉換。</span><span class="sxs-lookup"><span data-stu-id="d7322-278">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="d7322-279">如需詳細資訊，請參閱 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 和 [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 作業。</span><span class="sxs-lookup"><span data-stu-id="d7322-279">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="d7322-280">無複製定理</span><span class="sxs-lookup"><span data-stu-id="d7322-280">The No-Cloning Theorem</span></span>

<span data-ttu-id="d7322-281">量子資訊功能強大。</span><span class="sxs-lookup"><span data-stu-id="d7322-281">Quantum information is powerful.</span></span>
<span data-ttu-id="d7322-282">這讓我們能夠執行令人驚奇的事，像是以指數方式比最佳的傳統演算法更快，或有效率地模擬傳統方式需要指數成本才能正確模擬的相互關聯 electron 系統。</span><span class="sxs-lookup"><span data-stu-id="d7322-282">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="d7322-283">不過，配量運算的功能有一些限制。</span><span class="sxs-lookup"><span data-stu-id="d7322-283">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="d7322-284">其中一項限制是由*無複製定理*所提供。</span><span class="sxs-lookup"><span data-stu-id="d7322-284">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="d7322-285">未複製的定理是名為的恰如其。</span><span class="sxs-lookup"><span data-stu-id="d7322-285">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="d7322-286">它不允許由量子電腦複製一般量子狀態。</span><span class="sxs-lookup"><span data-stu-id="d7322-286">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="d7322-287">定理證明十分簡單。</span><span class="sxs-lookup"><span data-stu-id="d7322-287">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="d7322-288">雖然不復制定理的完整證明在這裡的討論方面有點技術性，但在我們的範圍內沒有其他輔助 qubits 的證明是在領域 (輔助 qubits 會 qubits 用於計算期間的臨時空間，而且很容易在中使用和管理 Q# ，請參閱借用的[qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)) 。</span><span class="sxs-lookup"><span data-stu-id="d7322-288">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="d7322-289">對於這類的量子電腦，複製作業必須由單一矩陣描述。</span><span class="sxs-lookup"><span data-stu-id="d7322-289">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="d7322-290">我們不允許測量，因為它會損毀我們嘗試要複製的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="d7322-290">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="d7322-291">為了模擬複製作業，我們想要使用單一矩陣來擁有屬性，$$</span><span class="sxs-lookup"><span data-stu-id="d7322-291">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="d7322-292">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="d7322-292">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="d7322-293">適用于任何狀態 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-293">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="d7322-294">矩陣乘法的線性屬性會指出，針對任何第二個量子狀態 $ \ket { \phi } $ ，</span><span class="sxs-lookup"><span data-stu-id="d7322-294">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="d7322-295">U \left [ \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="d7322-295">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="d7322-296">&= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="d7322-296">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="d7322-297">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-297">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="d7322-298">&= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="d7322-298">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="d7322-299">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="d7322-299">\right) \\\\</span></span>
    <span data-ttu-id="d7322-300">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right \right) ) 。</span><span class="sxs-lookup"><span data-stu-id="d7322-300">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="d7322-301">這提供了不復制定理背後的基礎直覺：任何複製不明量子狀態的裝置，都必須在其複製的至少部分狀態中引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="d7322-301">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="d7322-302">雖然在輸入狀態上以線性方式執行 cloner 的主要假設是透過新增和測量輔助 qubits 來違反，這類互動也會透過測量統計資料來流失系統的相關資訊，並避免在這種情況下進行完全複製。</span><span class="sxs-lookup"><span data-stu-id="d7322-302">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="d7322-303">如需更完整的無複製定理證明，請參閱[以取得詳細資訊](xref:microsoft.quantum.more-information)。</span><span class="sxs-lookup"><span data-stu-id="d7322-303">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="d7322-304">無複製定理對於區分量子運算而言非常重要，因為如果您可以在較低的情況中複製配量狀態，則會被授與從配量狀態學習的近乎神奇功能。</span><span class="sxs-lookup"><span data-stu-id="d7322-304">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="d7322-305">事實上，您可能違反了海森堡的 vaunted 不確定性原則。</span><span class="sxs-lookup"><span data-stu-id="d7322-305">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="d7322-306">或者，您可以使用最佳的 cloner 從複雜的配量散發取得單一範例，並瞭解您可能會從一個範例中瞭解該散發的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="d7322-306">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="d7322-307">這就像是您翻轉一間的一門硬幣，然後告訴朋友，其回應結果為「啊，該硬幣的分佈必須以 $ p = 0.512643 \ ldots $ ！」</span><span class="sxs-lookup"><span data-stu-id="d7322-307">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="d7322-308">這類語句不會 sensical，因為 (列印頭結果的其中一項資訊) 只是無法提供編碼散發所需的許多資訊，而不需要大量的先前資訊。</span><span class="sxs-lookup"><span data-stu-id="d7322-308">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="d7322-309">同樣地，如果沒有先前的資訊，我們就無法完全複製量子狀態，因為我們無法在不知道 p 的情況下準備集團這類的硬幣 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="d7322-309">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="d7322-310">在量子運算中，資訊不是免費的。</span><span class="sxs-lookup"><span data-stu-id="d7322-310">Information is not free in quantum computing.</span></span>
<span data-ttu-id="d7322-311">每個 qubit 都有提供一項資訊，而不復制定理顯示沒有任何後門可被利用，來解決系統與在其上叫用之騒之間的基本取捨。</span><span class="sxs-lookup"><span data-stu-id="d7322-311">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
