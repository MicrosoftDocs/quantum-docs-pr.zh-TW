---
<span data-ttu-id="72c97-101">標題：量子 oracle 描述：瞭解如何使用和定義量子 oracle、用來作為另一個演算法輸入的黑色 box 作業。</span><span class="sxs-lookup"><span data-stu-id="72c97-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="72c97-102">作者： cgranade uid： oracle ms. 作者： chgranad ms. 日期： 07/11/2018 ms. 主題：不含 loc 的文章：</span><span class="sxs-lookup"><span data-stu-id="72c97-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="72c97-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="72c97-103">"Q#"</span></span>
- <span data-ttu-id="72c97-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="72c97-104">"$$v"</span></span>
- <span data-ttu-id="72c97-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="72c97-105">"$$"</span></span>
- <span data-ttu-id="72c97-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="72c97-106">"$$"</span></span>
- <span data-ttu-id="72c97-107">"$"</span><span class="sxs-lookup"><span data-stu-id="72c97-107">"$"</span></span>
- <span data-ttu-id="72c97-108">"$"</span><span class="sxs-lookup"><span data-stu-id="72c97-108">"$"</span></span>
- <span data-ttu-id="72c97-109">"$"</span><span class="sxs-lookup"><span data-stu-id="72c97-109">"$"</span></span>
- <span data-ttu-id="72c97-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="72c97-110">"$$"</span></span>
- <span data-ttu-id="72c97-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="72c97-111">"\cdots"</span></span>
- <span data-ttu-id="72c97-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="72c97-112">"bmatrix"</span></span>
- <span data-ttu-id="72c97-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="72c97-113">"\ddots"</span></span>
- <span data-ttu-id="72c97-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="72c97-114">"\equiv"</span></span>
- <span data-ttu-id="72c97-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="72c97-115">"\sum"</span></span>
- <span data-ttu-id="72c97-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="72c97-116">"\begin"</span></span>
- <span data-ttu-id="72c97-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="72c97-117">"\end"</span></span>
- <span data-ttu-id="72c97-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="72c97-118">"\sqrt"</span></span>
- <span data-ttu-id="72c97-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="72c97-119">"\otimes"</span></span>
- <span data-ttu-id="72c97-120">"{"</span><span class="sxs-lookup"><span data-stu-id="72c97-120">"{"</span></span>
- <span data-ttu-id="72c97-121">"}"</span><span class="sxs-lookup"><span data-stu-id="72c97-121">"}"</span></span>
- <span data-ttu-id="72c97-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="72c97-122">"\text"</span></span>
- <span data-ttu-id="72c97-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="72c97-123">"\phi"</span></span>
- <span data-ttu-id="72c97-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="72c97-124">"\kappa"</span></span>
- <span data-ttu-id="72c97-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="72c97-125">"\psi"</span></span>
- <span data-ttu-id="72c97-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="72c97-126">"\alpha"</span></span>
- <span data-ttu-id="72c97-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="72c97-127">"\beta"</span></span>
- <span data-ttu-id="72c97-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="72c97-128">"\gamma"</span></span>
- <span data-ttu-id="72c97-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="72c97-129">"\delta"</span></span>
- <span data-ttu-id="72c97-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="72c97-130">"\omega"</span></span>
- <span data-ttu-id="72c97-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="72c97-131">"\bra"</span></span>
- <span data-ttu-id="72c97-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="72c97-132">"\ket"</span></span>
- <span data-ttu-id="72c97-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="72c97-133">"\boldone"</span></span>
- <span data-ttu-id="72c97-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="72c97-134">"\\\\"</span></span>
- <span data-ttu-id="72c97-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="72c97-135">"\\"</span></span>
- <span data-ttu-id="72c97-136">"="</span><span class="sxs-lookup"><span data-stu-id="72c97-136">"="</span></span>
- <span data-ttu-id="72c97-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="72c97-137">"\frac"</span></span>
- <span data-ttu-id="72c97-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="72c97-138">"\text"</span></span>
- <span data-ttu-id="72c97-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="72c97-139">"\mapsto"</span></span>
- <span data-ttu-id="72c97-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="72c97-140">"\dagger"</span></span>
- <span data-ttu-id="72c97-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="72c97-141">"\to"</span></span>
- <span data-ttu-id="72c97-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="72c97-142">"\begin{cases}"</span></span>
- <span data-ttu-id="72c97-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="72c97-143">"\end{cases}"</span></span>
- <span data-ttu-id="72c97-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="72c97-144">"\operatorname"</span></span>
- <span data-ttu-id="72c97-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="72c97-145">"\braket"</span></span>
- <span data-ttu-id="72c97-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="72c97-146">"\id"</span></span>
- <span data-ttu-id="72c97-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="72c97-147">"\expect"</span></span>
- <span data-ttu-id="72c97-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="72c97-148">"\defeq"</span></span>
- <span data-ttu-id="72c97-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="72c97-149">"\variance"</span></span>
- <span data-ttu-id="72c97-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="72c97-150">"\dd"</span></span>
- <span data-ttu-id="72c97-151">"&"</span><span class="sxs-lookup"><span data-stu-id="72c97-151">"&"</span></span>
- <span data-ttu-id="72c97-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="72c97-152">"\begin{align}"</span></span>
- <span data-ttu-id="72c97-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="72c97-153">"\end{align}"</span></span>
- <span data-ttu-id="72c97-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="72c97-154">"\Lambda"</span></span>
- <span data-ttu-id="72c97-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="72c97-155">"\lambda"</span></span>
- <span data-ttu-id="72c97-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="72c97-156">"\Omega"</span></span>
- <span data-ttu-id="72c97-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="72c97-157">"\mathrm"</span></span>
- <span data-ttu-id="72c97-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="72c97-158">"\left"</span></span>
- <span data-ttu-id="72c97-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="72c97-159">"\right"</span></span>
- <span data-ttu-id="72c97-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="72c97-160">"\qquad"</span></span>
- <span data-ttu-id="72c97-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="72c97-161">"\times"</span></span>
- <span data-ttu-id="72c97-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="72c97-162">"\big"</span></span>
- <span data-ttu-id="72c97-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="72c97-163">"\langle"</span></span>
- <span data-ttu-id="72c97-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="72c97-164">"\rangle"</span></span>
- <span data-ttu-id="72c97-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="72c97-165">"\bigg"</span></span>
- <span data-ttu-id="72c97-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="72c97-166">"\Big"</span></span>
- <span data-ttu-id="72c97-167">"|"</span><span class="sxs-lookup"><span data-stu-id="72c97-167">"|"</span></span>
- <span data-ttu-id="72c97-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="72c97-168">"\mathbb"</span></span>
- <span data-ttu-id="72c97-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="72c97-169">"\vec"</span></span>
- <span data-ttu-id="72c97-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="72c97-170">"\in"</span></span>
- <span data-ttu-id="72c97-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="72c97-171">"\texttt"</span></span>
- <span data-ttu-id="72c97-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="72c97-172">"\ne"</span></span>
- <span data-ttu-id="72c97-173">"<"</span><span class="sxs-lookup"><span data-stu-id="72c97-173">"<"</span></span>
- <span data-ttu-id="72c97-174">">"</span><span class="sxs-lookup"><span data-stu-id="72c97-174">">"</span></span>
- <span data-ttu-id="72c97-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="72c97-175">"\leq"</span></span>
- <span data-ttu-id="72c97-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="72c97-176">"\geq"</span></span>
- <span data-ttu-id="72c97-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="72c97-177">"~~"</span></span>
- <span data-ttu-id="72c97-178">"~"</span><span class="sxs-lookup"><span data-stu-id="72c97-178">"~"</span></span>
- <span data-ttu-id="72c97-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="72c97-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="72c97-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="72c97-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="72c97-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="72c97-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="72c97-182">量子 Oracle</span><span class="sxs-lookup"><span data-stu-id="72c97-182">Quantum Oracles</span></span>

<span data-ttu-id="72c97-183">Oracle $ O $ 是「黑箱」作業，可作為另一個演算法的輸入。</span><span class="sxs-lookup"><span data-stu-id="72c97-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="72c97-184">通常，這類作業是使用傳統函 $ 式（f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m）來定義，此函式 \\ } $ 會採用 $ n $ 位二進位輸入並產生 $ m $ 位二進位輸出。</span><span class="sxs-lookup"><span data-stu-id="72c97-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="72c97-185">若要這樣做，請考慮特定的二進位輸入 $ x = (x_ { 0 } 、x_ { 1 } 、\dots .. x_ { n-1 }) $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="72c97-186">我們可以將量子位狀態標記為 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="72c97-187">我們可能會先嘗試定義 $ o， $ 讓 $ o \ket { x } = \ket { f (x) } $ ，但這有幾個問題。</span><span class="sxs-lookup"><span data-stu-id="72c97-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="72c97-188">首先， $ f $ 可能會有不同的輸入和輸出大小 ($ n \ne m $) ，因此套用 $ O $ 會變更暫存器中的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="72c97-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="72c97-189">其次，即使 $ n = m，函式 $ 也可能無法反轉：如果 $ f (x) = f (y) $ 用於某些 $ x \ne y $ ，則為 $ o \ket { x o y， } = \ket { } $ 但 $ o ^ \dagger o \ket { x o x o } \ne \dagger \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="72c97-190">這表示我們無法建立 adjoint 作業 $ O ^ \dagger $ ，oracle 必須為它們定義 adjoint。</span><span class="sxs-lookup"><span data-stu-id="72c97-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="72c97-191">依據計算基礎狀態的影響來定義 oracle</span><span class="sxs-lookup"><span data-stu-id="72c97-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="72c97-192">我們可以藉由引進第二個 $ m 量子位註冊來保存我們的答案，來處理這兩個問題 $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="72c97-193">接著，我們會定義 oracle 在所有計算基礎狀態的效果：所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0、1 \\ } ^ m $ 、</span><span class="sxs-lookup"><span data-stu-id="72c97-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="72c97-194">O (\ket { x } \otimes \ket { y }) = \ket { x } \otimes \ket { y \oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="72c97-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="72c97-195">現在 $ o = o o o \dagger $ x 的結構，因此我們解決了這兩個先前的問題。</span><span class="sxs-lookup"><span data-stu-id="72c97-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="72c97-196">>若要查看該 $ o = o ^ { \dagger } $ ，請注意 $ o ^ 2， = \boldone $ 因為 $ \oplus b \oplus b = a $ for all $ a，b \in \: ：： no loc ( {) ：：：0，1 \: ：： no loc (} ) ： $ ：：。</span><span class="sxs-lookup"><span data-stu-id="72c97-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="72c97-197">>因此， $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) x } = \ket { } \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="72c97-198">重要的是，以這種方式為每個計算基礎狀態定義 oracle， $ \ket { x } \ket { y } $ 也會定義 $ O $ 對任何其他狀態的運作方式。</span><span class="sxs-lookup"><span data-stu-id="72c97-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="72c97-199">這 $ $ 項作業會立即從像是所有量子作業這樣的事實，在其作用的狀態中是線性的。</span><span class="sxs-lookup"><span data-stu-id="72c97-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="72c97-200">請考慮 Hadamard 作業，例如，由 $ h \ket { 0 } = \ket { + } $ 和 $ h \ket { 1 定義 } = \ket { - } $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="72c97-201">如果我們想要知道 $ h h 如何 $ 運作 $ \ket { + } $ ，我們可以使用該 $ h $ 為線性，</span><span class="sxs-lookup"><span data-stu-id="72c97-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="72c97-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h (\ket { 0 }  +  \ket { 1 }) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 }) \\\\</span><span class="sxs-lookup"><span data-stu-id="72c97-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="72c97-203">&= \frac{1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) = \frac 12 (\ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 }) = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="72c97-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="72c97-204">在定義 oracle O 的情況下 $ $ ，我們可以同樣地使用 $ \ket { \psi } $ n + m 量子位上的任何狀態都 $ $ 可以撰寫為</span><span class="sxs-lookup"><span data-stu-id="72c97-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="72c97-205">\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="72c97-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="72c97-206">其中 $ \alpha ： \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C } $ 代表狀態的係數 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="72c97-207">因此，</span><span class="sxs-lookup"><span data-stu-id="72c97-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="72c97-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x、y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="72c97-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="72c97-209">&= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y \oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="72c97-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="72c97-210">階段 oracle</span><span class="sxs-lookup"><span data-stu-id="72c97-210">Phase oracles</span></span>
<span data-ttu-id="72c97-211">另外，我們也可以 $ $ $ $ 根據輸入至 O 來套用_階段_，將 f 編碼為 oracle O $ $ 。比方說，我們可能會定義 $ O $$$</span><span class="sxs-lookup"><span data-stu-id="72c97-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="72c97-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } 。</span><span class="sxs-lookup"><span data-stu-id="72c97-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="72c97-213">如果 oracle 階段一開始是以計算基礎狀態 x 作為基礎 $ \ket { } $ ，則這個階段是全域階段，因此無法觀察。</span><span class="sxs-lookup"><span data-stu-id="72c97-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="72c97-214">但是如果套用至迭加或做為受控制的作業，則這類 oracle 可能是非常強大的資源。</span><span class="sxs-lookup"><span data-stu-id="72c97-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="72c97-215">例如，假設有一個階段 oracle $ O_f $ 量子位函式 $ f $ 。</span><span class="sxs-lookup"><span data-stu-id="72c97-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="72c97-216">然後 $$</span><span class="sxs-lookup"><span data-stu-id="72c97-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="72c97-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="72c97-217">O_f \ket{+}</span></span>
        <span data-ttu-id="72c97-218">&=O_f (\ket {0 }  +  \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="72c97-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="72c97-219">&= ( # A1-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="72c97-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="72c97-220">&= (-1) ^ { f (0) } (\ket { 0 } + (-1) ^ { f (1) -f (0) } \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="72c97-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="72c97-221">&= (-1) ^ { f (0) } Z ^ { f (0) -f (1) } \ket { + } 。</span><span class="sxs-lookup"><span data-stu-id="72c97-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="72c97-222">更常見的是，oracle 的這兩個觀點都可以放寬了來代表傳回實數的傳統函式，而不是只有一個位。</span><span class="sxs-lookup"><span data-stu-id="72c97-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="72c97-223">選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用這種 oracle。</span><span class="sxs-lookup"><span data-stu-id="72c97-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="72c97-224">例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) 依賴以第一種方式執行的 oracle，而 [格羅弗的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm) 則依賴以第二種方式實作為的 oracle。</span><span class="sxs-lookup"><span data-stu-id="72c97-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="72c97-225">如需更多詳細資料，我們建議[您*et al*Gilyén](https://arxiv.org/abs/1711.00465)中的討論，例如1711.00465。</span><span class="sxs-lookup"><span data-stu-id="72c97-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
