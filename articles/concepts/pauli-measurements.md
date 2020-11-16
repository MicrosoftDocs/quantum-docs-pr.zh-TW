---
<span data-ttu-id="26919-101">標題： Pauli 度量描述：瞭解如何使用單一和多重量子位的 Pauli 度量運算。</span><span class="sxs-lookup"><span data-stu-id="26919-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="26919-102">作者： bradben uid： pauli ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：非 loc 文章：</span><span class="sxs-lookup"><span data-stu-id="26919-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="26919-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="26919-103">"Q#"</span></span>
- <span data-ttu-id="26919-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="26919-104">"$$v"</span></span>
- <span data-ttu-id="26919-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="26919-105">"$$"</span></span>
- <span data-ttu-id="26919-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="26919-106">"$$"</span></span>
- <span data-ttu-id="26919-107">"$"</span><span class="sxs-lookup"><span data-stu-id="26919-107">"$"</span></span>
- <span data-ttu-id="26919-108">"$"</span><span class="sxs-lookup"><span data-stu-id="26919-108">"$"</span></span>
- <span data-ttu-id="26919-109">"$"</span><span class="sxs-lookup"><span data-stu-id="26919-109">"$"</span></span>
- <span data-ttu-id="26919-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="26919-110">"$$"</span></span>
- <span data-ttu-id="26919-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="26919-111">"\cdots"</span></span>
- <span data-ttu-id="26919-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="26919-112">"bmatrix"</span></span>
- <span data-ttu-id="26919-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="26919-113">"\ddots"</span></span>
- <span data-ttu-id="26919-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="26919-114">"\equiv"</span></span>
- <span data-ttu-id="26919-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="26919-115">"\sum"</span></span>
- <span data-ttu-id="26919-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="26919-116">"\begin"</span></span>
- <span data-ttu-id="26919-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="26919-117">"\end"</span></span>
- <span data-ttu-id="26919-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="26919-118">"\sqrt"</span></span>
- <span data-ttu-id="26919-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="26919-119">"\otimes"</span></span>
- <span data-ttu-id="26919-120">"{"</span><span class="sxs-lookup"><span data-stu-id="26919-120">"{"</span></span>
- <span data-ttu-id="26919-121">"}"</span><span class="sxs-lookup"><span data-stu-id="26919-121">"}"</span></span>
- <span data-ttu-id="26919-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="26919-122">"\text"</span></span>
- <span data-ttu-id="26919-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="26919-123">"\phi"</span></span>
- <span data-ttu-id="26919-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="26919-124">"\kappa"</span></span>
- <span data-ttu-id="26919-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="26919-125">"\psi"</span></span>
- <span data-ttu-id="26919-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="26919-126">"\alpha"</span></span>
- <span data-ttu-id="26919-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="26919-127">"\beta"</span></span>
- <span data-ttu-id="26919-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="26919-128">"\gamma"</span></span>
- <span data-ttu-id="26919-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="26919-129">"\delta"</span></span>
- <span data-ttu-id="26919-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="26919-130">"\omega"</span></span>
- <span data-ttu-id="26919-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="26919-131">"\bra"</span></span>
- <span data-ttu-id="26919-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="26919-132">"\ket"</span></span>
- <span data-ttu-id="26919-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="26919-133">"\boldone"</span></span>
- <span data-ttu-id="26919-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="26919-134">"\\\\"</span></span>
- <span data-ttu-id="26919-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="26919-135">"\\"</span></span>
- <span data-ttu-id="26919-136">"="</span><span class="sxs-lookup"><span data-stu-id="26919-136">"="</span></span>
- <span data-ttu-id="26919-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="26919-137">"\frac"</span></span>
- <span data-ttu-id="26919-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="26919-138">"\text"</span></span>
- <span data-ttu-id="26919-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="26919-139">"\mapsto"</span></span>
- <span data-ttu-id="26919-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="26919-140">"\dagger"</span></span>
- <span data-ttu-id="26919-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="26919-141">"\to"</span></span>
- <span data-ttu-id="26919-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="26919-142">"\begin{cases}"</span></span>
- <span data-ttu-id="26919-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="26919-143">"\end{cases}"</span></span>
- <span data-ttu-id="26919-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="26919-144">"\operatorname"</span></span>
- <span data-ttu-id="26919-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="26919-145">"\braket"</span></span>
- <span data-ttu-id="26919-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="26919-146">"\id"</span></span>
- <span data-ttu-id="26919-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="26919-147">"\expect"</span></span>
- <span data-ttu-id="26919-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="26919-148">"\defeq"</span></span>
- <span data-ttu-id="26919-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="26919-149">"\variance"</span></span>
- <span data-ttu-id="26919-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="26919-150">"\dd"</span></span>
- <span data-ttu-id="26919-151">"&"</span><span class="sxs-lookup"><span data-stu-id="26919-151">"&"</span></span>
- <span data-ttu-id="26919-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="26919-152">"\begin{align}"</span></span>
- <span data-ttu-id="26919-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="26919-153">"\end{align}"</span></span>
- <span data-ttu-id="26919-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="26919-154">"\Lambda"</span></span>
- <span data-ttu-id="26919-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="26919-155">"\lambda"</span></span>
- <span data-ttu-id="26919-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="26919-156">"\Omega"</span></span>
- <span data-ttu-id="26919-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="26919-157">"\mathrm"</span></span>
- <span data-ttu-id="26919-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="26919-158">"\left"</span></span>
- <span data-ttu-id="26919-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="26919-159">"\right"</span></span>
- <span data-ttu-id="26919-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="26919-160">"\qquad"</span></span>
- <span data-ttu-id="26919-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="26919-161">"\times"</span></span>
- <span data-ttu-id="26919-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="26919-162">"\big"</span></span>
- <span data-ttu-id="26919-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="26919-163">"\langle"</span></span>
- <span data-ttu-id="26919-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="26919-164">"\rangle"</span></span>
- <span data-ttu-id="26919-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="26919-165">"\bigg"</span></span>
- <span data-ttu-id="26919-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="26919-166">"\Big"</span></span>
- <span data-ttu-id="26919-167">"|"</span><span class="sxs-lookup"><span data-stu-id="26919-167">"|"</span></span>
- <span data-ttu-id="26919-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="26919-168">"\mathbb"</span></span>
- <span data-ttu-id="26919-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="26919-169">"\vec"</span></span>
- <span data-ttu-id="26919-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="26919-170">"\in"</span></span>
- <span data-ttu-id="26919-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="26919-171">"\texttt"</span></span>
- <span data-ttu-id="26919-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="26919-172">"\ne"</span></span>
- <span data-ttu-id="26919-173">"<"</span><span class="sxs-lookup"><span data-stu-id="26919-173">"<"</span></span>
- <span data-ttu-id="26919-174">">"</span><span class="sxs-lookup"><span data-stu-id="26919-174">">"</span></span>
- <span data-ttu-id="26919-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="26919-175">"\leq"</span></span>
- <span data-ttu-id="26919-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="26919-176">"\geq"</span></span>
- <span data-ttu-id="26919-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="26919-177">"~~"</span></span>
- <span data-ttu-id="26919-178">"~"</span><span class="sxs-lookup"><span data-stu-id="26919-178">"~"</span></span>
- <span data-ttu-id="26919-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="26919-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="26919-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="26919-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="26919-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="26919-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="26919-182">Pauli 測量</span><span class="sxs-lookup"><span data-stu-id="26919-182">Pauli Measurements</span></span>

<span data-ttu-id="26919-183">在先前的討論中，我們著重于計算基礎度量。</span><span class="sxs-lookup"><span data-stu-id="26919-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="26919-184">事實上，量子運算中有其他常見的測量，從標記的角度來看，這在計算基礎測量方面很方便。</span><span class="sxs-lookup"><span data-stu-id="26919-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="26919-185">當您使用時 Q# ，最常見的測量類型可能會是 *Pauli 測量* ，這會將計算基礎度量一般化以包含其他基底的度量，以及不同量子位之間的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="26919-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements* , which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="26919-186">在這種情況下，通常會討論測量 Pauli 運算子，通常是 $ x、Y、z $ 或 $ z \otimes z、x \otimes x、x \otimes Y $ 等運算子。</span><span class="sxs-lookup"><span data-stu-id="26919-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="26919-187">> 在中 Q# ，多量子位的 Pauli 運算子通常是以類型的陣列表示 `Pauli[]` 。</span><span class="sxs-lookup"><span data-stu-id="26919-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="26919-188">> 例如，若要表示 $ X \otimes Z \otimes Y $ ，您可以使用陣列 `[PauliX, PauliZ, PauliY]` 。</span><span class="sxs-lookup"><span data-stu-id="26919-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="26919-189">討論 Pauli 運算子的度量在量子錯誤修正的子欄位中特別常見。</span><span class="sxs-lookup"><span data-stu-id="26919-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="26919-190">在中 Q# ，我們會遵循類似的慣例，我們現在會說明這種替代的度量觀點。</span><span class="sxs-lookup"><span data-stu-id="26919-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="26919-191">在探究有關如何思考 Pauli 測量的詳細資訊之前，請先思考測量量子電腦內的單一量子位對量子狀態的作用。</span><span class="sxs-lookup"><span data-stu-id="26919-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="26919-192">想像一下，我們有 $ 一個 $ 量子位的量子狀態，然後測量一個量子位，立即將該州的 $ 2 ^ n 個可能性的一半 $ 視為一半。</span><span class="sxs-lookup"><span data-stu-id="26919-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="26919-193">換句話說，量測會將量子狀態投射到兩個半空格的其中一個。</span><span class="sxs-lookup"><span data-stu-id="26919-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="26919-194">我們可以將我們認為測量的方式一般化，以反映此直覺。</span><span class="sxs-lookup"><span data-stu-id="26919-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="26919-195">為了簡潔地識別這些 subspaces，我們需要用來描述這些的語言。</span><span class="sxs-lookup"><span data-stu-id="26919-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="26919-196">描述這兩個 subspaces 的其中一種方式，是透過只有兩個唯一特徵值的矩陣來指定它們，慣例會採用 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="26919-197">如需以這種方式描述 subspaces 的簡單範例，請考慮使用 $ Z $ ：</span><span class="sxs-lookup"><span data-stu-id="26919-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="26919-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="26919-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="26919-199">藉由讀取 Pauli-Z 矩陣的對角線 $ 元素 $ ，我們可以看到 $ Z $ 有兩個特徵向量（ $ \ket { 0 } $ 和 $ \ket { 1），以及 } $ 對應的特徵值 $ \pm 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="26919-200">因此，如果我們測量量子位並取得與 `Zero` 狀態 0) 對應的 ($ \ket { } $ ，我們知道量子位的狀態是 $ Z 運算子的 + 1 $ eigenstate $ $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="26919-201">同樣地，如果我們得到 `One` ，我們知道量子位的狀態是 $ z 的-1 $ eigenstate $ $ 。此程式稱為「測量 Pauli Z」的 Pauli 度量語言， $ $ 完全等同于執行計算基礎度量。</span><span class="sxs-lookup"><span data-stu-id="26919-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="26919-202">任何 $ 2 \times 2 $ 矩陣（即單一轉換 Z） $ $ 也會滿足此準則。</span><span class="sxs-lookup"><span data-stu-id="26919-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="26919-203">也就是說，我們也可以使用矩陣 $ a = U ^ \dagger Z u $ ，其中 $ u $ 是任何其他的單一矩陣，以提供矩陣來定義測量結果在其 $ \pm 1 特徵向量中的兩個結果 $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="26919-204">Pauli 量值的標記法會藉由識別 $ X、Y、Z 量測作為對等量值來參考這項單一等價 $ ，以從量子位中得到資訊。</span><span class="sxs-lookup"><span data-stu-id="26919-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="26919-205">為了方便起見，以下提供這些度量。</span><span class="sxs-lookup"><span data-stu-id="26919-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="26919-206">|Pauli 測量  | 單一轉換  |</span><span class="sxs-lookup"><span data-stu-id="26919-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="26919-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="26919-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="26919-208">|$ $ X |$H               $                    |</span><span class="sxs-lookup"><span data-stu-id="26919-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="26919-209">|$ $ Y |$HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="26919-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="26919-210">也就是說，使用這種語言時，「measure Y」相當於套用 $ $ $ HS ^， \dagger $ 然後以計算為基礎來測量，其中是內建的 [`S`](xref:Microsoft.Quantum.Intrinsic.S) 量子作業有時稱為「階段閘道」，且可由單一矩陣模擬</span><span class="sxs-lookup"><span data-stu-id="26919-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:Microsoft.Quantum.Intrinsic.S) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="26919-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="26919-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="26919-212">1 & 0 \\\\ 0 & i \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="26919-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="26919-213">它也相當於將 $ HS ^ 套用 \dagger $ 至量子狀態向量，然後測量 $ Z $ ，讓下列作業相當於 `Measure([PauliY], [q])` ：</span><span class="sxs-lookup"><span data-stu-id="26919-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="26919-214">然後，您可以藉由轉換回計算基礎來找到正確的狀態，將 SH 套用 $ $ 至量子狀態向量; 在上述程式碼片段中，轉換回計算基礎是使用區塊自動處理 `within … apply` 。</span><span class="sxs-lookup"><span data-stu-id="26919-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="26919-215">在中 Q# ，我們假設結果---也就是，從與---狀態互動所解壓縮的傳統資訊是由 `Result` 值 j 零所提供 $ \in \\ { \texttt { } ， \texttt { 一個 } \\ } $ 表示結果是否在 $ $ 所測量 Pauli 運算子的 (-1) ^ j eigenspace 中。</span><span class="sxs-lookup"><span data-stu-id="26919-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="26919-216">多量子位度量</span><span class="sxs-lookup"><span data-stu-id="26919-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="26919-217">多量子位 Pauli 運算子的度量定義類似，如下所示：</span><span class="sxs-lookup"><span data-stu-id="26919-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="26919-218">Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & & \\\\ & -1 & 0 0 0 0 & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 0 1。</span><span class="sxs-lookup"><span data-stu-id="26919-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="26919-219">因此，兩個 Pauli z 運算子的 tensor 產品 $ $ 形成由兩個空格組成的矩陣 $ ，由 + 1 $ 和 $ -1 $ 特徵值組成。</span><span class="sxs-lookup"><span data-stu-id="26919-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="26919-220">就像單一量子位案例一樣，兩者都構成一半的空間，這表示一半的可存取向量空間屬於 $ + 1 $ eigenspace，而剩餘一半到 $ -1 $ eigenspace。</span><span class="sxs-lookup"><span data-stu-id="26919-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="26919-221">一般來說，從 tensor 產品的定義中，任何 Pauli-Z 運算子的 tensor 產品 $ $ 和身分識別也會遵守這一點，都很容易看出。</span><span class="sxs-lookup"><span data-stu-id="26919-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="26919-222">例如，套用至物件的</span><span class="sxs-lookup"><span data-stu-id="26919-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="26919-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="26919-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="26919-224">1 &  0 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="26919-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="26919-226">0 &  0 & -1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="26919-227">0 &  0 &  0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="26919-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="26919-228">同樣地，這類矩陣的任何單一轉換也會描述 \pm 1 特徵值所標記的兩個半空格 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="26919-229">例如， $ x \otimes x = h \otimes h (z \otimes z) H h， \otimes $  從 z HXH 的身分識別 $ = $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="26919-230">類似于量子位案例，所有的雙量子位 Pauli 度量都可以撰寫為 $ u ^ \dagger (Z \otimes \id) u， $ 適用于 $ 4 \times 4 個 $ 單一矩陣 $ u $ 。我們列舉下表中的轉換。</span><span class="sxs-lookup"><span data-stu-id="26919-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="26919-231">>在下表中，我們使用 $ \operatorname { SWAP } $ 來指出矩陣 >$$</span><span class="sxs-lookup"><span data-stu-id="26919-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="26919-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="26919-232">> \begin{align}</span></span>
<span data-ttu-id="26919-233">>     \operatorname{交換 } &=</span><span class="sxs-lookup"><span data-stu-id="26919-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="26919-234">>     \left (\begin { 矩陣}</span><span class="sxs-lookup"><span data-stu-id="26919-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="26919-235">>         1 & 0 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="26919-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="26919-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="26919-238">>0 & 0 & 0 & 1 > \end { 矩陣 } \right) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="26919-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="26919-239">> $$</span><span class="sxs-lookup"><span data-stu-id="26919-239">> $$</span></span>
<span data-ttu-id="26919-240">> 用來模擬內建函式 [`SWAP`](xref:Microsoft.Quantum.Intrinsic) 。</span><span class="sxs-lookup"><span data-stu-id="26919-240">> used to simulate the intrinsic operation [`SWAP`](xref:Microsoft.Quantum.Intrinsic).</span></span>

<span data-ttu-id="26919-241">|Pauli 測量     | 單一轉換  |</span><span class="sxs-lookup"><span data-stu-id="26919-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="26919-242">|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|</span><span class="sxs-lookup"><span data-stu-id="26919-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="26919-243">|$ \otimes \boldone X $| $\otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="26919-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="26919-244">|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="26919-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="26919-245">|$\boldone \otimesZ $ | $ \operatorname { 交換 } $|</span><span class="sxs-lookup"><span data-stu-id="26919-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="26919-246">|$\boldone \otimesX $ | $ (H \otimes \boldone) \operatorname { 交換 } $|</span><span class="sxs-lookup"><span data-stu-id="26919-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="26919-247">|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone) \operatorname { 交換 } $|</span><span class="sxs-lookup"><span data-stu-id="26919-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="26919-248">|$Z \otimesZ $ | $ \operatorname { CNOT } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="26919-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="26919-249">|$X \otimesZ $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone) $|</span><span class="sxs-lookup"><span data-stu-id="26919-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="26919-250">|$Y \otimesZ $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone) $|</span><span class="sxs-lookup"><span data-stu-id="26919-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="26919-251">|$Z \otimesX $ | $ \operatorname { CNOT } \_ { 10 } (\boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="26919-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="26919-252">|$X \otimesX $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="26919-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="26919-253">|$Y \otimesX $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="26919-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="26919-254">|$Z \otimesY $ | $ \operatorname { CNOT } \_ { 10 } (\boldone \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="26919-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="26919-255">|$X \otimesY $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="26919-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="26919-256">|$Y \otimesY $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes hs ^ \dagger) $|</span><span class="sxs-lookup"><span data-stu-id="26919-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="26919-257">在此， [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) 會因為下列原因而出現作業。</span><span class="sxs-lookup"><span data-stu-id="26919-257">Here, the [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) operation appears for the following reason.</span></span>
<span data-ttu-id="26919-258">每個不含矩陣的 Pauli 量值 $ \boldone $ 都等同于上述推理的單一至 $ z \otimes z $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="26919-259">$Z z 的特徵值 \otimes $ 只取決於構成每個計算基礎向量之量子位的同位，且受控制的作業不會用來計算這個同位，並將其儲存在第一個位。</span><span class="sxs-lookup"><span data-stu-id="26919-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="26919-260">然後，在測量第一個位之後，我們可以復原產生之半形的身分識別，這相當於測量 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="26919-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="26919-261">另一個注意事項：雖然假設測量 $ z \otimes z 與 $ 依序測量 $ z \otimes \mathbb { 1 和 1 Z 的方式相同，但 } $ 這項 $ \mathbb { 假設會 } \otimes $ 是 false。</span><span class="sxs-lookup"><span data-stu-id="26919-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="26919-262">原因是測量 $ Z z 會 \otimes $ 將量子狀態投射到 $ 這些運算子的 + 1 $ 或 $ -1 $ eigenstate 中。</span><span class="sxs-lookup"><span data-stu-id="26919-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="26919-263">測量 $ z \otimes \mathbb { 1 } $ ，然後 $ \mathbb { } \otimes 按 1 z， $ 將量子狀態向量先投射到 Z 1 的一半空間 $ \otimes \mathbb { } $ ，然後再到 $ \mathbb { 1 } \otimes z $ 的半個空格。由於有四個計算基礎向量，執行這兩個測量可將狀態減少到四分之一空間，因此會將其縮減為單一計算基礎向量。</span><span class="sxs-lookup"><span data-stu-id="26919-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="26919-264">量子位元之間的關聯性</span><span class="sxs-lookup"><span data-stu-id="26919-264">Correlations between qubits</span></span>
<span data-ttu-id="26919-265">另一種查看 Pauli 矩陣（例如 $ x x 或 z z） tensor 產品的方式 \otimes $ $ \otimes $ ，就是這些測量資料可讓您查看儲存在兩個量子位之間相互關聯的資訊。</span><span class="sxs-lookup"><span data-stu-id="26919-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="26919-266">測量 $ X \otimes \id $ 可讓您查看在第一個量子位中儲存在本機的資訊。</span><span class="sxs-lookup"><span data-stu-id="26919-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="26919-267">雖然這兩種類型的度量在量子運算中同樣有價值，但前者也會導致量子運算的威力。</span><span class="sxs-lookup"><span data-stu-id="26919-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="26919-268">它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一量子位中，而是會一次儲存在所有量子位中，因此只會透過聯合 (度量來查看它（例如 $ Z \otimes z $) 會將這項資訊變成資訊清單）。</span><span class="sxs-lookup"><span data-stu-id="26919-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="26919-269">例如，在錯誤修正中，我們通常會想要瞭解在學習到我們想要保護的狀態時，發生了什麼錯誤。</span><span class="sxs-lookup"><span data-stu-id="26919-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="26919-270">[位在程式碼範例](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)中的範例示範如何使用 $ Z \otimes z \otimes \id $ 和 $ \id \otimes z \otimes z $ < 等度量來進行。--TODO：當位翻轉程式碼範例在上線上時，請將此變更為範例瀏覽器的連結。</span><span class="sxs-lookup"><span data-stu-id="26919-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="26919-271">您也可以測量任意 Pauli 運算子（例如 $ X \otimes Y \otimes Z \otimes \boldone $ ）。</span><span class="sxs-lookup"><span data-stu-id="26919-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="26919-272">Pauli 運算子的所有這類 tensor 產品只有兩個特徵值 $ \pm 1 $ ，而 eigenspaces 則構成整個向量空間的一半空格。</span><span class="sxs-lookup"><span data-stu-id="26919-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="26919-273">因此，它們會符合上述的需求。</span><span class="sxs-lookup"><span data-stu-id="26919-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="26919-274">在中 Q# ， $ $ 如果測量結果產生 eigenspace 的正負號 $ (-1) ^ j 的結果，這類測量結果會傳回 j $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="26919-275">將 Pauli 量測視為中的內建功能 Q# 很有説明，因為測量這類運算子需要較長的控制-非管制和基礎轉換鏈，以描述將作業 $ $ 表示為 Z 和 tensor 產品所需的 diagonalizing U 閘道 $ $ $ \id $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="26919-276">藉由指定您想要執行上述其中一個預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎度量能提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="26919-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="26919-277">Q# 自動為您處理所有必要的基礎轉換。</span><span class="sxs-lookup"><span data-stu-id="26919-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="26919-278">如需詳細資訊，請參閱 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 和 [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) 作業。</span><span class="sxs-lookup"><span data-stu-id="26919-278">For more information, see the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) and [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="26919-279">No-Cloning 定理</span><span class="sxs-lookup"><span data-stu-id="26919-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="26919-280">量子資訊的功能強大。</span><span class="sxs-lookup"><span data-stu-id="26919-280">Quantum information is powerful.</span></span>
<span data-ttu-id="26919-281">它讓我們能夠以更快的速度，比最知名的傳統演算法更快地進行一些令人驚奇的事，像是更有效率地模擬傳統方式需要指數成本才能精確模擬的相關 electron 系統。</span><span class="sxs-lookup"><span data-stu-id="26919-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="26919-282">不過，量子運算的威力有一些限制。</span><span class="sxs-lookup"><span data-stu-id="26919-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="26919-283">這種限制是由 *無複製定理* 所提供。</span><span class="sxs-lookup"><span data-stu-id="26919-283">One such limitation is given by the *No-Cloning Theorem* .</span></span>

<span data-ttu-id="26919-284">No-Cloning 的定理會恰如其命名。</span><span class="sxs-lookup"><span data-stu-id="26919-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="26919-285">它不允許量子電腦複製一般量子狀態。</span><span class="sxs-lookup"><span data-stu-id="26919-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="26919-286">定理證明很簡單。</span><span class="sxs-lookup"><span data-stu-id="26919-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="26919-287">雖然沒有複製定理的完整證明在這裡討論的技術並不多，但在我們的 (範圍內沒有額外輔助量子位的證明是在計算期間用於臨時空間，而在中很容易使用和管理 Q# ，請參閱 [借用量子位](xref:microsoft.quantum.guide.qubits#borrowed-qubits)) 。</span><span class="sxs-lookup"><span data-stu-id="26919-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="26919-288">針對這類量子電腦，複製作業必須由單一矩陣描述。</span><span class="sxs-lookup"><span data-stu-id="26919-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="26919-289">我們不允許進行度量，因為它會損毀我們嘗試複製的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="26919-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="26919-290">為了模擬複製作業，我們想要使用單一矩陣來取得屬性 $$</span><span class="sxs-lookup"><span data-stu-id="26919-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="26919-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="26919-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="26919-292">適用于任何狀態 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="26919-293">矩陣乘法的線性屬性工作表示，在任何第二個量子狀態 $ \ket { \phi } $ 下，</span><span class="sxs-lookup"><span data-stu-id="26919-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="26919-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="26919-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="26919-295">&= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="26919-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="26919-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="26919-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="26919-297">&= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="26919-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="26919-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="26919-298">\right) \\\\</span></span>
    <span data-ttu-id="26919-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left (\ket { \phi } + \ket { \psi } \right \right) ) 。</span><span class="sxs-lookup"><span data-stu-id="26919-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="26919-300">這會提供 No-Cloning 定理背後的基本直覺：任何複製未知量子狀態的裝置，都必須在其所複製的部分狀態下引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="26919-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="26919-301">雖然 cloner 在輸入狀態上以線性方式運作的關鍵假設是透過新增和測量輔助量子位，所以這類互動也會透過測量統計資料來洩漏系統的相關資訊，並防止在這類情況下進行完全複製。</span><span class="sxs-lookup"><span data-stu-id="26919-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="26919-302">如需更完整的 No-Cloning 定理詳細 [資訊](xref:microsoft.quantum.more-information)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="26919-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="26919-303">No-Cloning 定理對於量子運算很重要，因為如果您可以更經濟的方式複製量子狀態，則會獲得從量子狀態學習的近乎神奇功能。</span><span class="sxs-lookup"><span data-stu-id="26919-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="26919-304">事實上，您可能違反了海森堡的 vaunted 不確定性原則。</span><span class="sxs-lookup"><span data-stu-id="26919-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="26919-305">或者，您也可以使用最佳的 cloner，從複雜的量子散發取得單一範例，並從單一範例學習該散發的所有相關資訊。</span><span class="sxs-lookup"><span data-stu-id="26919-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="26919-306">這就像是您將硬幣和觀察到的結果，然後在告知朋友的結果中，他們會回應「必須使用 $ p = 0.512643 \ ldots $ ！來讓那個硬幣的分佈有利</span><span class="sxs-lookup"><span data-stu-id="26919-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="26919-307">這類的語句不會 sensical，因為 (列印頭結果的其中一項資訊，) 只是無法提供在沒有大量先前資訊的情況下編碼散發所需的許多資訊。</span><span class="sxs-lookup"><span data-stu-id="26919-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="26919-308">同樣地，在沒有先前資訊的情況下，我們無法完全複製量子狀態，因為我們無法在不知道 p 的情況下準備集團這類的硬幣 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="26919-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="26919-309">在量子運算中，資訊不是免費的。</span><span class="sxs-lookup"><span data-stu-id="26919-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="26919-310">測量的每個量子位都提供一項資訊，而 No-Cloning 定理指出沒有任何後門程式可被入侵，以因應系統與在其上叫用之干擾之間的基本取捨。</span><span class="sxs-lookup"><span data-stu-id="26919-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
