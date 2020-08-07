---
<span data-ttu-id="27390-101">標題：配量 oracles 描述：瞭解如何使用並定義量子 oracles，這是用來做為其他演算法輸入的黑色箱作業。</span><span class="sxs-lookup"><span data-stu-id="27390-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="27390-102">author： cgranade uid： oracles ms-chap。作者： Christopher.Granade@microsoft.com ms. 日期：07/11/2018 毫秒。主題：發行項不存在：</span><span class="sxs-lookup"><span data-stu-id="27390-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="27390-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="27390-103">"Q#"</span></span>
- <span data-ttu-id="27390-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="27390-104">"$$v"</span></span>
- <span data-ttu-id="27390-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="27390-105">"$$"</span></span>
- <span data-ttu-id="27390-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="27390-106">"$$"</span></span>
- <span data-ttu-id="27390-107">"$"</span><span class="sxs-lookup"><span data-stu-id="27390-107">"$"</span></span>
- <span data-ttu-id="27390-108">"$"</span><span class="sxs-lookup"><span data-stu-id="27390-108">"$"</span></span>
- <span data-ttu-id="27390-109">"$"</span><span class="sxs-lookup"><span data-stu-id="27390-109">"$"</span></span>
- <span data-ttu-id="27390-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="27390-110">"$$"</span></span>
- <span data-ttu-id="27390-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="27390-111">"\cdots"</span></span>
- <span data-ttu-id="27390-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="27390-112">"bmatrix"</span></span>
- <span data-ttu-id="27390-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="27390-113">"\ddots"</span></span>
- <span data-ttu-id="27390-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="27390-114">"\equiv"</span></span>
- <span data-ttu-id="27390-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="27390-115">"\sum"</span></span>
- <span data-ttu-id="27390-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="27390-116">"\begin"</span></span>
- <span data-ttu-id="27390-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="27390-117">"\end"</span></span>
- <span data-ttu-id="27390-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="27390-118">"\sqrt"</span></span>
- <span data-ttu-id="27390-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="27390-119">"\otimes"</span></span>
- <span data-ttu-id="27390-120">"{"</span><span class="sxs-lookup"><span data-stu-id="27390-120">"{"</span></span>
- <span data-ttu-id="27390-121">"}"</span><span class="sxs-lookup"><span data-stu-id="27390-121">"}"</span></span>
- <span data-ttu-id="27390-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="27390-122">"\text"</span></span>
- <span data-ttu-id="27390-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="27390-123">"\phi"</span></span>
- <span data-ttu-id="27390-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="27390-124">"\kappa"</span></span>
- <span data-ttu-id="27390-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="27390-125">"\psi"</span></span>
- <span data-ttu-id="27390-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="27390-126">"\alpha"</span></span>
- <span data-ttu-id="27390-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="27390-127">"\beta"</span></span>
- <span data-ttu-id="27390-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="27390-128">"\gamma"</span></span>
- <span data-ttu-id="27390-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="27390-129">"\delta"</span></span>
- <span data-ttu-id="27390-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="27390-130">"\omega"</span></span>
- <span data-ttu-id="27390-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="27390-131">"\bra"</span></span>
- <span data-ttu-id="27390-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="27390-132">"\ket"</span></span>
- <span data-ttu-id="27390-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="27390-133">"\boldone"</span></span>
- <span data-ttu-id="27390-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="27390-134">"\\\\"</span></span>
- <span data-ttu-id="27390-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="27390-135">"\\"</span></span>
- <span data-ttu-id="27390-136">"="</span><span class="sxs-lookup"><span data-stu-id="27390-136">"="</span></span>
- <span data-ttu-id="27390-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="27390-137">"\frac"</span></span>
- <span data-ttu-id="27390-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="27390-138">"\text"</span></span>
- <span data-ttu-id="27390-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="27390-139">"\mapsto"</span></span>
- <span data-ttu-id="27390-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="27390-140">"\dagger"</span></span>
- <span data-ttu-id="27390-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="27390-141">"\to"</span></span>
- <span data-ttu-id="27390-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="27390-142">"\begin{cases}"</span></span>
- <span data-ttu-id="27390-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="27390-143">"\end{cases}"</span></span>
- <span data-ttu-id="27390-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="27390-144">"\operatorname"</span></span>
- <span data-ttu-id="27390-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="27390-145">"\braket"</span></span>
- <span data-ttu-id="27390-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="27390-146">"\id"</span></span>
- <span data-ttu-id="27390-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="27390-147">"\expect"</span></span>
- <span data-ttu-id="27390-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="27390-148">"\defeq"</span></span>
- <span data-ttu-id="27390-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="27390-149">"\variance"</span></span>
- <span data-ttu-id="27390-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="27390-150">"\dd"</span></span>
- <span data-ttu-id="27390-151">"&"</span><span class="sxs-lookup"><span data-stu-id="27390-151">"&"</span></span>
- <span data-ttu-id="27390-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="27390-152">"\begin{align}"</span></span>
- <span data-ttu-id="27390-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="27390-153">"\end{align}"</span></span>
- <span data-ttu-id="27390-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="27390-154">"\Lambda"</span></span>
- <span data-ttu-id="27390-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="27390-155">"\lambda"</span></span>
- <span data-ttu-id="27390-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="27390-156">"\Omega"</span></span>
- <span data-ttu-id="27390-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="27390-157">"\mathrm"</span></span>
- <span data-ttu-id="27390-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="27390-158">"\left"</span></span>
- <span data-ttu-id="27390-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="27390-159">"\right"</span></span>
- <span data-ttu-id="27390-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="27390-160">"\qquad"</span></span>
- <span data-ttu-id="27390-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="27390-161">"\times"</span></span>
- <span data-ttu-id="27390-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="27390-162">"\big"</span></span>
- <span data-ttu-id="27390-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="27390-163">"\langle"</span></span>
- <span data-ttu-id="27390-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="27390-164">"\rangle"</span></span>
- <span data-ttu-id="27390-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="27390-165">"\bigg"</span></span>
- <span data-ttu-id="27390-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="27390-166">"\Big"</span></span>
- <span data-ttu-id="27390-167">"|"</span><span class="sxs-lookup"><span data-stu-id="27390-167">"|"</span></span>
- <span data-ttu-id="27390-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="27390-168">"\mathbb"</span></span>
- <span data-ttu-id="27390-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="27390-169">"\vec"</span></span>
- <span data-ttu-id="27390-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="27390-170">"\in"</span></span>
- <span data-ttu-id="27390-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="27390-171">"\texttt"</span></span>
- <span data-ttu-id="27390-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="27390-172">"\ne"</span></span>
- <span data-ttu-id="27390-173">"<"</span><span class="sxs-lookup"><span data-stu-id="27390-173">"<"</span></span>
- <span data-ttu-id="27390-174">">"</span><span class="sxs-lookup"><span data-stu-id="27390-174">">"</span></span>
- <span data-ttu-id="27390-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="27390-175">"\leq"</span></span>
- <span data-ttu-id="27390-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="27390-176">"\geq"</span></span>
- <span data-ttu-id="27390-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="27390-177">"~~"</span></span>
- <span data-ttu-id="27390-178">"~"</span><span class="sxs-lookup"><span data-stu-id="27390-178">"~"</span></span>
- <span data-ttu-id="27390-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="27390-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="27390-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="27390-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="27390-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="27390-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="27390-182">量子 Oracles</span><span class="sxs-lookup"><span data-stu-id="27390-182">Quantum Oracles</span></span>

<span data-ttu-id="27390-183">Oracle $ O $ 是「黑箱」作業，用來做為另一個演算法的輸入。</span><span class="sxs-lookup"><span data-stu-id="27390-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="27390-184">通常，這類作業會使用傳統函式 $ f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m 來定義， \\ } $ 這會接受 $ n 位的 $ 二進位輸入，並產生 $ m $ 位二進位輸出。</span><span class="sxs-lookup"><span data-stu-id="27390-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="27390-185">若要這麼做，請考慮特定的二進位輸入 $ x = (x_ { 0 } ，x_ { 1 } ，\dots ..，x_ { n-1 }) $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="27390-186">我們可以將 qubit 狀態標示為 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="27390-187">我們可能會先嘗試定義 $ o， $ 讓 $ o \ket { x } = \ket { f (x) } $ ，但這有幾個問題。</span><span class="sxs-lookup"><span data-stu-id="27390-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="27390-188">首先， $ f $ 可能會有不同的輸入和輸出大小 ($ n \ne m $) ，因此套用 $ O $ 會變更暫存器中的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="27390-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="27390-189">第二，即使 $ n = m $ ，函式也可能無法反轉：如果 $ f (x) = f (y) $ 用於某些 $ x \ne y $ ，則是 $ o \ket { x } = o \ket { y， } $ 但 $ o ^ \dagger o \ket { x } \ne o \dagger \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="27390-190">這表示我們無法建立 adjoint 作業 $ O ^ \dagger $ ，oracles 必須為其定義 adjoint。</span><span class="sxs-lookup"><span data-stu-id="27390-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="27390-191">依其對計算基礎狀態的影響來定義 oracle</span><span class="sxs-lookup"><span data-stu-id="27390-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="27390-192">我們可以藉由引進 m qubits 的第二個暫存器來處理這兩個問題， $ $ 以保存我們的解答。</span><span class="sxs-lookup"><span data-stu-id="27390-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="27390-193">然後，我們將定義 oracle 在所有計算基礎狀態的效果：對於所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0，1 \\ } ^ m $ ，</span><span class="sxs-lookup"><span data-stu-id="27390-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="27390-194">O (\ket { x } \otimes \ket { y }) = \ket { x } \otimes \ket { y \oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="27390-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="27390-195">現在 $ = ，我們已透過結構化 o o ^ \dagger $ ，因此我們解決了這兩個先前的問題。</span><span class="sxs-lookup"><span data-stu-id="27390-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="27390-196">>若要查看 $ o = o ^ { \dagger } $ ，請注意 $ o ^ 2 = \boldone $ 自 $ \oplus b \oplus b = a $ for all $ a、b \in \: ：： no-loc ( {) ：：：0、1 \: ：： no-loc (} ) ：：： $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="27390-197">>因此， $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="27390-198">重要的是，以這種方式為每個計算基礎狀態 x y 定義 oracle， $ \ket { } \ket { } $ 也會定義 $ O $ 對任何其他狀態的行為。</span><span class="sxs-lookup"><span data-stu-id="27390-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="27390-199">這會立即遵循 $ $ ，如同所有的配量作業，其作用所在的狀態都是線性的。</span><span class="sxs-lookup"><span data-stu-id="27390-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="27390-200">請考慮 Hadamard 作業，例如，它是由 $ h \ket { 0 } = \ket { + } $ 和 $ H \ket { 1 } = \ket { - } $ 所定義。</span><span class="sxs-lookup"><span data-stu-id="27390-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="27390-201">如果我們想要知道 $ h 的 $ 作用如何 $ \ket { + } $ ，我們可以使用這個 $ h $ 是線性的。</span><span class="sxs-lookup"><span data-stu-id="27390-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="27390-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H (\ket { 0 }  +  \ket { 1 }) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 }) \\\\</span><span class="sxs-lookup"><span data-stu-id="27390-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="27390-203">&= \frac{1 } { \sqrt { 2 } } (\ket { + }  +  \ket { - }) = \frac 12 (\ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 }) = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="27390-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="27390-204">在定義 oracle O 的情況下 $ $ ，我們可以同樣地使用 $ \ket { \psi } $ n + m qubits 上的任何狀態都 $ $ 可以撰寫為</span><span class="sxs-lookup"><span data-stu-id="27390-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="27390-205">\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="27390-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="27390-206">其中 $ \alpha ： \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C } $ 代表狀態的係數 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="27390-207">因此，</span><span class="sxs-lookup"><span data-stu-id="27390-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="27390-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x、y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="27390-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="27390-209">&= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y \oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="27390-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="27390-210">階段 oracles</span><span class="sxs-lookup"><span data-stu-id="27390-210">Phase oracles</span></span>
<span data-ttu-id="27390-211">或者，我們可以根據對 $ O 的輸入套用階段，將 f 編碼 $ 成 oracle $ O $ _phase_ $ $ 。比方說，我們可能會定義 $ O $$$</span><span class="sxs-lookup"><span data-stu-id="27390-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="27390-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } 。</span><span class="sxs-lookup"><span data-stu-id="27390-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="27390-213">如果某個階段在一開始是以計算基礎狀態 x 進行暫存器 $ \ket { } $ ，則此階段為全域階段，因此無法觀察。</span><span class="sxs-lookup"><span data-stu-id="27390-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="27390-214">但是，如果套用至重迭或做為受控制的作業，這類 oracle 可能是非常強大的資源。</span><span class="sxs-lookup"><span data-stu-id="27390-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="27390-215">例如，假設有一個階段的 oracle $ O_f $ 適用于單一 qubit 函數 $ f $ 。</span><span class="sxs-lookup"><span data-stu-id="27390-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="27390-216">請$$</span><span class="sxs-lookup"><span data-stu-id="27390-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="27390-217">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="27390-217">O_f \ket{+}</span></span>
        <span data-ttu-id="27390-218">&=O_f (\ket {0 }  +  \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="27390-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="27390-219">&= ( # A1-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="27390-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="27390-220">&= (-1) ^ { f (0) } (\ket { 0 } + (-1) ^ { f (1) -f (0) } \ket { 1 }) / \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="27390-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="27390-221">&= (-1) ^ { f (0) } Z ^ { f (0) -f (1) } \ket { + } 。</span><span class="sxs-lookup"><span data-stu-id="27390-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="27390-222">更常見的情況是，可以放寬了 oracles 的兩個觀點來代表傳回實數的傳統函式，而不只是單一位。</span><span class="sxs-lookup"><span data-stu-id="27390-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="27390-223">選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用此 oracle。</span><span class="sxs-lookup"><span data-stu-id="27390-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="27390-224">例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依賴以第一種方式實作為的 oracle，而[Grover 的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依賴以第二種方式實施的 oracle。</span><span class="sxs-lookup"><span data-stu-id="27390-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="27390-225">如需更多詳細資訊，建議您在[Gilyén *et al*1711.00465](https://arxiv.org/abs/1711.00465)中進行討論。</span><span class="sxs-lookup"><span data-stu-id="27390-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
