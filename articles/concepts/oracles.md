---
<span data-ttu-id="c7af2-101">標題：配量 oracles 描述：瞭解如何使用並定義量子 oracles，這是用來做為其他演算法輸入的黑色箱作業。</span><span class="sxs-lookup"><span data-stu-id="c7af2-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="c7af2-102">author： cgranade uid： oracles ms-chap。作者： Christopher.Granade@microsoft.com ms. 日期：07/11/2018 毫秒。主題：發行項不存在：</span><span class="sxs-lookup"><span data-stu-id="c7af2-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="c7af2-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="c7af2-103">"$$"</span></span>
- <span data-ttu-id="c7af2-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="c7af2-104">"$$"</span></span>
- <span data-ttu-id="c7af2-105">"$"</span><span class="sxs-lookup"><span data-stu-id="c7af2-105">"$"</span></span>
- <span data-ttu-id="c7af2-106">"$"</span><span class="sxs-lookup"><span data-stu-id="c7af2-106">"$"</span></span>
- <span data-ttu-id="c7af2-107">"$"</span><span class="sxs-lookup"><span data-stu-id="c7af2-107">"$"</span></span>
- <span data-ttu-id="c7af2-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="c7af2-108">"$$"</span></span>
- <span data-ttu-id="c7af2-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="c7af2-109">"\cdots"</span></span>
- <span data-ttu-id="c7af2-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="c7af2-110">"bmatrix"</span></span>
- <span data-ttu-id="c7af2-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="c7af2-111">"\ddots"</span></span>
- <span data-ttu-id="c7af2-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="c7af2-112">"\equiv"</span></span>
- <span data-ttu-id="c7af2-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="c7af2-113">"\sum"</span></span>
- <span data-ttu-id="c7af2-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="c7af2-114">"\begin"</span></span>
- <span data-ttu-id="c7af2-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="c7af2-115">"\end"</span></span>
- <span data-ttu-id="c7af2-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="c7af2-116">"\sqrt"</span></span>
- <span data-ttu-id="c7af2-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="c7af2-117">"\otimes"</span></span>
- <span data-ttu-id="c7af2-118">"{"</span><span class="sxs-lookup"><span data-stu-id="c7af2-118">"{"</span></span>
- <span data-ttu-id="c7af2-119">"}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-119">"}"</span></span>
- <span data-ttu-id="c7af2-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="c7af2-120">"\text"</span></span>
- <span data-ttu-id="c7af2-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="c7af2-121">"\phi"</span></span>
- <span data-ttu-id="c7af2-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="c7af2-122">"\kappa"</span></span>
- <span data-ttu-id="c7af2-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="c7af2-123">"\psi"</span></span>
- <span data-ttu-id="c7af2-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="c7af2-124">"\alpha"</span></span>
- <span data-ttu-id="c7af2-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="c7af2-125">"\beta"</span></span>
- <span data-ttu-id="c7af2-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="c7af2-126">"\gamma"</span></span>
- <span data-ttu-id="c7af2-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="c7af2-127">"\delta"</span></span>
- <span data-ttu-id="c7af2-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="c7af2-128">"\omega"</span></span>
- <span data-ttu-id="c7af2-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="c7af2-129">"\bra"</span></span>
- <span data-ttu-id="c7af2-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="c7af2-130">"\ket"</span></span>
- <span data-ttu-id="c7af2-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="c7af2-131">"\boldone"</span></span>
- <span data-ttu-id="c7af2-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="c7af2-132">"\\\\"</span></span>
- <span data-ttu-id="c7af2-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="c7af2-133">"\\"</span></span>
- <span data-ttu-id="c7af2-134">"="</span><span class="sxs-lookup"><span data-stu-id="c7af2-134">"="</span></span>
- <span data-ttu-id="c7af2-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="c7af2-135">"\frac"</span></span>
- <span data-ttu-id="c7af2-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="c7af2-136">"\text"</span></span>
- <span data-ttu-id="c7af2-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="c7af2-137">"\mapsto"</span></span>
- <span data-ttu-id="c7af2-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="c7af2-138">"\dagger"</span></span>
- <span data-ttu-id="c7af2-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="c7af2-139">"\to"</span></span>
- <span data-ttu-id="c7af2-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-140">"\begin{cases}"</span></span>
- <span data-ttu-id="c7af2-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-141">"\end{cases}"</span></span>
- <span data-ttu-id="c7af2-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="c7af2-142">"\operatorname"</span></span>
- <span data-ttu-id="c7af2-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="c7af2-143">"\braket"</span></span>
- <span data-ttu-id="c7af2-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="c7af2-144">"\id"</span></span>
- <span data-ttu-id="c7af2-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="c7af2-145">"\expect"</span></span>
- <span data-ttu-id="c7af2-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="c7af2-146">"\defeq"</span></span>
- <span data-ttu-id="c7af2-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="c7af2-147">"\variance"</span></span>
- <span data-ttu-id="c7af2-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="c7af2-148">"\dd"</span></span>
- <span data-ttu-id="c7af2-149">"&"</span><span class="sxs-lookup"><span data-stu-id="c7af2-149">"&"</span></span>
- <span data-ttu-id="c7af2-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-150">"\begin{align}"</span></span>
- <span data-ttu-id="c7af2-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-151">"\end{align}"</span></span>
- <span data-ttu-id="c7af2-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="c7af2-152">"\Lambda"</span></span>
- <span data-ttu-id="c7af2-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="c7af2-153">"\lambda"</span></span>
- <span data-ttu-id="c7af2-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="c7af2-154">"\Omega"</span></span>
- <span data-ttu-id="c7af2-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="c7af2-155">"\mathrm"</span></span>
- <span data-ttu-id="c7af2-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="c7af2-156">"\left"</span></span>
- <span data-ttu-id="c7af2-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="c7af2-157">"\right"</span></span>
- <span data-ttu-id="c7af2-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="c7af2-158">"\qquad"</span></span>
- <span data-ttu-id="c7af2-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="c7af2-159">"\times"</span></span>
- <span data-ttu-id="c7af2-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="c7af2-160">"\big"</span></span>
- <span data-ttu-id="c7af2-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="c7af2-161">"\langle"</span></span>
- <span data-ttu-id="c7af2-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="c7af2-162">"\rangle"</span></span>
- <span data-ttu-id="c7af2-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="c7af2-163">"\bigg"</span></span>
- <span data-ttu-id="c7af2-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="c7af2-164">"\Big"</span></span>
- <span data-ttu-id="c7af2-165">"|"</span><span class="sxs-lookup"><span data-stu-id="c7af2-165">"|"</span></span>
- <span data-ttu-id="c7af2-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="c7af2-166">"\mathbb"</span></span>
- <span data-ttu-id="c7af2-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="c7af2-167">"\vec"</span></span>
- <span data-ttu-id="c7af2-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="c7af2-168">"\in"</span></span>
- <span data-ttu-id="c7af2-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="c7af2-169">"\texttt"</span></span>
- <span data-ttu-id="c7af2-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="c7af2-170">"\ne"</span></span>
- <span data-ttu-id="c7af2-171">"<"</span><span class="sxs-lookup"><span data-stu-id="c7af2-171">"<"</span></span>
- <span data-ttu-id="c7af2-172">">"</span><span class="sxs-lookup"><span data-stu-id="c7af2-172">">"</span></span>
- <span data-ttu-id="c7af2-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="c7af2-173">"\leq"</span></span>
- <span data-ttu-id="c7af2-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="c7af2-174">"\geq"</span></span>
- <span data-ttu-id="c7af2-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="c7af2-175">"~~"</span></span>
- <span data-ttu-id="c7af2-176">"~"</span><span class="sxs-lookup"><span data-stu-id="c7af2-176">"~"</span></span>
- <span data-ttu-id="c7af2-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="c7af2-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c7af2-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="c7af2-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="c7af2-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="c7af2-180">量子 Oracles</span><span class="sxs-lookup"><span data-stu-id="c7af2-180">Quantum Oracles</span></span>

<span data-ttu-id="c7af2-181">Oracle $ O $ 是「黑箱」作業，用來做為另一個演算法的輸入。</span><span class="sxs-lookup"><span data-stu-id="c7af2-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="c7af2-182">通常，這類作業會使用傳統函式 $ f： \\ { 0、1 \\ } ^ n \to \\ { 0、1 ^ m 來定義， \\ } $ 這會接受 $ n 位的 $ 二進位輸入，並產生 $ m $ 位二進位輸出。</span><span class="sxs-lookup"><span data-stu-id="c7af2-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="c7af2-183">若要這麼做，請考慮特定的二進位輸入 $ x = （x_ { 0 } ，x_ { 1 } ，\dots ..，x_ { n-1 } ） $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="c7af2-184">我們可以將 qubit 狀態標示為 $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="c7af2-185">我們可能會先嘗試定義 $ o， $ 使 $ o \ket { x } = \ket { f （x） } $ ，但這有幾個問題。</span><span class="sxs-lookup"><span data-stu-id="c7af2-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="c7af2-186">首先， $ f $ 可能會有不同的輸入和輸出大小（ $ n \ne m $ ），因此套用 $ O $ 會變更暫存器中的 qubits 數目。</span><span class="sxs-lookup"><span data-stu-id="c7af2-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="c7af2-187">第二，即使 $ n = m $ ，函式也可能無法反轉：如果 $ f （x） = f （y） $ 用於某個 $ x \ne y $ ，則為 $ o \ket { x } = o \ket { y， } $ 但 $ o ^ \dagger o x o \ket { } \ne \dagger \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="c7af2-188">這表示我們無法建立 adjoint 作業 $ O ^ \dagger $ ，oracles 必須為其定義 adjoint。</span><span class="sxs-lookup"><span data-stu-id="c7af2-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="c7af2-189">依其對計算基礎狀態的影響來定義 oracle</span><span class="sxs-lookup"><span data-stu-id="c7af2-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="c7af2-190">我們可以藉由引進 m qubits 的第二個暫存器來處理這兩個問題， $ $ 以保存我們的解答。</span><span class="sxs-lookup"><span data-stu-id="c7af2-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="c7af2-191">然後，我們將定義 oracle 在所有計算基礎狀態的效果：對於所有 $ x \in \\ { 0、1 \\ } ^ n $ 和 $ y \in \\ { 0，1 \\ } ^ m $ ，</span><span class="sxs-lookup"><span data-stu-id="c7af2-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="c7af2-192">O （ \ket { x } \otimes \ket { y } ） = \ket { x } \otimes \ket { y \oplus f （x） } 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="c7af2-193">現在 $ = ，我們已透過結構化 o o ^ \dagger $ ，因此我們解決了這兩個先前的問題。</span><span class="sxs-lookup"><span data-stu-id="c7af2-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="c7af2-194">若要查看 $ o = o ^ { \dagger } $ ，請注意 $ o ^ 2 = \boldone $ 自 $ \oplus b \oplus b = a $ 對所有 $ a、b \in \[ ！OP.NO-LOC （{）] 0，1 \[ ！OP.無-LOC （}）] $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="c7af2-195">因此， $ O \ket { x } \ket { y \oplus f （x） } = \ket { x } \ket { y \oplus f （x） \oplus f （x） } = \ket { x } \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="c7af2-196">重要的是，以這種方式為每個計算基礎狀態 x y 定義 oracle， $ \ket { } \ket { } $ 也會定義 $ O $ 對任何其他狀態的行為。</span><span class="sxs-lookup"><span data-stu-id="c7af2-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="c7af2-197">這會立即遵循 $ $ ，如同所有的配量作業，其作用所在的狀態都是線性的。</span><span class="sxs-lookup"><span data-stu-id="c7af2-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="c7af2-198">請考慮 Hadamard 作業，例如，它是由 $ h \ket { 0 } = \ket { + } $ 和 $ H \ket { 1 } = \ket { - } $ 所定義。</span><span class="sxs-lookup"><span data-stu-id="c7af2-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="c7af2-199">如果我們想要知道 $ h 的 $ 作用如何 $ \ket { + } $ ，我們可以使用這個 $ h $ 是線性的。</span><span class="sxs-lookup"><span data-stu-id="c7af2-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="c7af2-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H （ \ket { 0 }  +  \ket { 1 } ） = \frac { 1 } { \sqrt { 2 } } （h \ket { 0 } + H \ket { 1 } ）\\\\</span><span class="sxs-lookup"><span data-stu-id="c7af2-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="c7af2-201">= \frac{1 } { \sqrt { 2 } } （ \ket { + }  +  \ket { - } ） = \frac 12 （ \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ） = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="c7af2-202">在定義 oracle O 的情況下 $ $ ，我們可以同樣地使用 $ \ket { \psi } $ n + m qubits 上的任何狀態都 $ $ 可以撰寫為</span><span class="sxs-lookup"><span data-stu-id="c7af2-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="c7af2-203">{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha （x，y） \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="c7af2-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="c7af2-204">其中 $ \alpha ： \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C } $ 代表狀態的係數 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="c7af2-205">因此，</span><span class="sxs-lookup"><span data-stu-id="c7af2-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="c7af2-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha （x，y） \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m （x，y） O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="c7af2-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="c7af2-207">= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha （x，y） \ket { x } \ket { y \oplus f （x） } 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="c7af2-208">階段 oracles</span><span class="sxs-lookup"><span data-stu-id="c7af2-208">Phase oracles</span></span>
<span data-ttu-id="c7af2-209">或者，我們可以根據對 $ O 的輸入套用階段，將 f 編碼 $ 成 oracle $ O $ _phase_ $ $ 。比方說，我們可能會定義 $ O $$$</span><span class="sxs-lookup"><span data-stu-id="c7af2-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="c7af2-210">O \ket { x } = （-1） ^ { f （x） } \ket { x } 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="c7af2-211">如果某個階段在一開始是以計算基礎狀態 x 進行暫存器 $ \ket { } $ ，則此階段為全域階段，因此無法觀察。</span><span class="sxs-lookup"><span data-stu-id="c7af2-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="c7af2-212">但是，如果套用至重迭或做為受控制的作業，這類 oracle 可能是非常強大的資源。</span><span class="sxs-lookup"><span data-stu-id="c7af2-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="c7af2-213">例如，假設有一個階段的 oracle $ O_f $ 適用于單一 qubit 函數 $ f $ 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="c7af2-214">請$$</span><span class="sxs-lookup"><span data-stu-id="c7af2-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="c7af2-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="c7af2-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="c7af2-216">=O_f （ \ket { 0 }  +  \ket { 1 } ）/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="c7af2-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="c7af2-217">=（（-1） ^ { f （0） } \ket { 0 } + （-1） ^ { f （1） } \ket { 1 } ）/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="c7af2-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="c7af2-218">=（-1） ^ { f （0） } （ \ket { 0 } + （-1） ^ { f （1）-f （0） } \ket { 1 } ）/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="c7af2-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="c7af2-219">=（-1） ^ { f （0） } Z ^ { f （0）-f （1） } \ket { + } 。</span><span class="sxs-lookup"><span data-stu-id="c7af2-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="c7af2-220">更常見的情況是，可以放寬了 oracles 的兩個觀點來代表傳回實數的傳統函式，而不只是單一位。</span><span class="sxs-lookup"><span data-stu-id="c7af2-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="c7af2-221">選擇最佳的 oracle 執行方式，主要取決於如何在指定的演算法內使用此 oracle。</span><span class="sxs-lookup"><span data-stu-id="c7af2-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="c7af2-222">例如， [Deutsch Jozsa 演算法](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)依賴以第一種方式實作為的 oracle，而[Grover 的演算法](https://en.wikipedia.org/wiki/Grover's_algorithm)依賴以第二種方式實施的 oracle。</span><span class="sxs-lookup"><span data-stu-id="c7af2-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="c7af2-223">如需更多詳細資訊，建議您在[Gilyén *et al*1711.00465](https://arxiv.org/abs/1711.00465)中進行討論。</span><span class="sxs-lookup"><span data-stu-id="c7af2-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
