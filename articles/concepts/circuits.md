---
<span data-ttu-id="8f005-101">標題：量子線路描述：瞭解如何使用量子電路圖表以視覺化方式呈現簡單且複雜的量子運算。</span><span class="sxs-lookup"><span data-stu-id="8f005-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="8f005-102">author： QuantumWriter uid： benbra ms... ms. date： 12/11/2017 ms. 主題：非 loc 文章：</span><span class="sxs-lookup"><span data-stu-id="8f005-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="8f005-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="8f005-103">"Q#"</span></span>
- <span data-ttu-id="8f005-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="8f005-104">"$$v"</span></span>
- <span data-ttu-id="8f005-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="8f005-105">"$$"</span></span>
- <span data-ttu-id="8f005-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="8f005-106">"$$"</span></span>
- <span data-ttu-id="8f005-107">"$"</span><span class="sxs-lookup"><span data-stu-id="8f005-107">"$"</span></span>
- <span data-ttu-id="8f005-108">"$"</span><span class="sxs-lookup"><span data-stu-id="8f005-108">"$"</span></span>
- <span data-ttu-id="8f005-109">"$"</span><span class="sxs-lookup"><span data-stu-id="8f005-109">"$"</span></span>
- <span data-ttu-id="8f005-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="8f005-110">"$$"</span></span>
- <span data-ttu-id="8f005-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="8f005-111">"\cdots"</span></span>
- <span data-ttu-id="8f005-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="8f005-112">"bmatrix"</span></span>
- <span data-ttu-id="8f005-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="8f005-113">"\ddots"</span></span>
- <span data-ttu-id="8f005-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="8f005-114">"\equiv"</span></span>
- <span data-ttu-id="8f005-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="8f005-115">"\sum"</span></span>
- <span data-ttu-id="8f005-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="8f005-116">"\begin"</span></span>
- <span data-ttu-id="8f005-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="8f005-117">"\end"</span></span>
- <span data-ttu-id="8f005-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="8f005-118">"\sqrt"</span></span>
- <span data-ttu-id="8f005-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="8f005-119">"\otimes"</span></span>
- <span data-ttu-id="8f005-120">"{"</span><span class="sxs-lookup"><span data-stu-id="8f005-120">"{"</span></span>
- <span data-ttu-id="8f005-121">"}"</span><span class="sxs-lookup"><span data-stu-id="8f005-121">"}"</span></span>
- <span data-ttu-id="8f005-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="8f005-122">"\text"</span></span>
- <span data-ttu-id="8f005-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="8f005-123">"\phi"</span></span>
- <span data-ttu-id="8f005-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="8f005-124">"\kappa"</span></span>
- <span data-ttu-id="8f005-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="8f005-125">"\psi"</span></span>
- <span data-ttu-id="8f005-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="8f005-126">"\alpha"</span></span>
- <span data-ttu-id="8f005-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="8f005-127">"\beta"</span></span>
- <span data-ttu-id="8f005-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="8f005-128">"\gamma"</span></span>
- <span data-ttu-id="8f005-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="8f005-129">"\delta"</span></span>
- <span data-ttu-id="8f005-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="8f005-130">"\omega"</span></span>
- <span data-ttu-id="8f005-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="8f005-131">"\bra"</span></span>
- <span data-ttu-id="8f005-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="8f005-132">"\ket"</span></span>
- <span data-ttu-id="8f005-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="8f005-133">"\boldone"</span></span>
- <span data-ttu-id="8f005-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="8f005-134">"\\\\"</span></span>
- <span data-ttu-id="8f005-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="8f005-135">"\\"</span></span>
- <span data-ttu-id="8f005-136">"="</span><span class="sxs-lookup"><span data-stu-id="8f005-136">"="</span></span>
- <span data-ttu-id="8f005-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="8f005-137">"\frac"</span></span>
- <span data-ttu-id="8f005-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="8f005-138">"\text"</span></span>
- <span data-ttu-id="8f005-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="8f005-139">"\mapsto"</span></span>
- <span data-ttu-id="8f005-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="8f005-140">"\dagger"</span></span>
- <span data-ttu-id="8f005-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="8f005-141">"\to"</span></span>
- <span data-ttu-id="8f005-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="8f005-142">"\begin{cases}"</span></span>
- <span data-ttu-id="8f005-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="8f005-143">"\end{cases}"</span></span>
- <span data-ttu-id="8f005-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="8f005-144">"\operatorname"</span></span>
- <span data-ttu-id="8f005-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="8f005-145">"\braket"</span></span>
- <span data-ttu-id="8f005-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="8f005-146">"\id"</span></span>
- <span data-ttu-id="8f005-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="8f005-147">"\expect"</span></span>
- <span data-ttu-id="8f005-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="8f005-148">"\defeq"</span></span>
- <span data-ttu-id="8f005-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="8f005-149">"\variance"</span></span>
- <span data-ttu-id="8f005-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="8f005-150">"\dd"</span></span>
- <span data-ttu-id="8f005-151">"&"</span><span class="sxs-lookup"><span data-stu-id="8f005-151">"&"</span></span>
- <span data-ttu-id="8f005-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="8f005-152">"\begin{align}"</span></span>
- <span data-ttu-id="8f005-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="8f005-153">"\end{align}"</span></span>
- <span data-ttu-id="8f005-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="8f005-154">"\Lambda"</span></span>
- <span data-ttu-id="8f005-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="8f005-155">"\lambda"</span></span>
- <span data-ttu-id="8f005-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="8f005-156">"\Omega"</span></span>
- <span data-ttu-id="8f005-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="8f005-157">"\mathrm"</span></span>
- <span data-ttu-id="8f005-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="8f005-158">"\left"</span></span>
- <span data-ttu-id="8f005-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="8f005-159">"\right"</span></span>
- <span data-ttu-id="8f005-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="8f005-160">"\qquad"</span></span>
- <span data-ttu-id="8f005-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="8f005-161">"\times"</span></span>
- <span data-ttu-id="8f005-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="8f005-162">"\big"</span></span>
- <span data-ttu-id="8f005-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="8f005-163">"\langle"</span></span>
- <span data-ttu-id="8f005-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="8f005-164">"\rangle"</span></span>
- <span data-ttu-id="8f005-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="8f005-165">"\bigg"</span></span>
- <span data-ttu-id="8f005-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="8f005-166">"\Big"</span></span>
- <span data-ttu-id="8f005-167">"|"</span><span class="sxs-lookup"><span data-stu-id="8f005-167">"|"</span></span>
- <span data-ttu-id="8f005-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="8f005-168">"\mathbb"</span></span>
- <span data-ttu-id="8f005-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="8f005-169">"\vec"</span></span>
- <span data-ttu-id="8f005-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="8f005-170">"\in"</span></span>
- <span data-ttu-id="8f005-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="8f005-171">"\texttt"</span></span>
- <span data-ttu-id="8f005-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="8f005-172">"\ne"</span></span>
- <span data-ttu-id="8f005-173">"<"</span><span class="sxs-lookup"><span data-stu-id="8f005-173">"<"</span></span>
- <span data-ttu-id="8f005-174">">"</span><span class="sxs-lookup"><span data-stu-id="8f005-174">">"</span></span>
- <span data-ttu-id="8f005-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="8f005-175">"\leq"</span></span>
- <span data-ttu-id="8f005-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="8f005-176">"\geq"</span></span>
- <span data-ttu-id="8f005-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="8f005-177">"~~"</span></span>
- <span data-ttu-id="8f005-178">"~"</span><span class="sxs-lookup"><span data-stu-id="8f005-178">"~"</span></span>
- <span data-ttu-id="8f005-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="8f005-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="8f005-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="8f005-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="8f005-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="8f005-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="8f005-182">量子線路</span><span class="sxs-lookup"><span data-stu-id="8f005-182">Quantum Circuits</span></span>
<span data-ttu-id="8f005-183">請考慮一下單一轉換 $ \text { CNOT } _ { 01 } (H \otimes 1) $ 。</span><span class="sxs-lookup"><span data-stu-id="8f005-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="8f005-184">此閘道序列對於量子運算而言很重要，因為它會建立一個充分纏結雙量子位狀態：</span><span class="sxs-lookup"><span data-stu-id="8f005-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="8f005-185">$$\mathrm{CNOT } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left (\ket { 00 }  +  \ket { 11 } \right) ，$$</span><span class="sxs-lookup"><span data-stu-id="8f005-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="8f005-186">具有這項或更高複雜度的作業在量子演算法和量子錯誤修正中很常見，因此，其視覺效果有一個簡單的方法，稱為 *量子電路圖* ，因此應該會有很大的降低。</span><span class="sxs-lookup"><span data-stu-id="8f005-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram* .</span></span>
<span data-ttu-id="8f005-187">準備此充分纏結量子狀態的電路圖為：</span><span class="sxs-lookup"><span data-stu-id="8f005-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="8f005-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="8f005-189"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-190">![充分纏結雙量子位狀態的電路圖](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="8f005-191">量子電路圖慣例</span><span class="sxs-lookup"><span data-stu-id="8f005-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="8f005-192">當您瞭解用來表示量子電路的慣例之後，這種適用于量子作業的視覺化語言可以更容易消化。</span><span class="sxs-lookup"><span data-stu-id="8f005-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="8f005-193">我們會在下方探討這些慣例。</span><span class="sxs-lookup"><span data-stu-id="8f005-193">We review these conventions below.</span></span>

<span data-ttu-id="8f005-194">在電路圖中，每個實線都描述量子位或更一般量子位的註冊。</span><span class="sxs-lookup"><span data-stu-id="8f005-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="8f005-195">依照慣例，頂端的行是量子位 register $ 0 $ ，其餘部分則會依序標示。</span><span class="sxs-lookup"><span data-stu-id="8f005-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="8f005-196">上述的範例電路在兩個量子位 (或等同于一個量子位) 的兩個暫存器上進行描述。</span><span class="sxs-lookup"><span data-stu-id="8f005-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="8f005-197">以一個或多個量子位暫存器為依據的閘道會以方塊表示。</span><span class="sxs-lookup"><span data-stu-id="8f005-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="8f005-198">例如，符號</span><span class="sxs-lookup"><span data-stu-id="8f005-198">For example, the symbol</span></span>

<span data-ttu-id="8f005-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="8f005-200"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-201">![Hadamard 作業的符號，可在單一量子位暫存器上運作](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="8f005-202">是在單一量子位登錄上進行的 [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) 作業。</span><span class="sxs-lookup"><span data-stu-id="8f005-202">is a [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="8f005-203">量子閘道會依時間順序排序，最左邊的閘道會先套用至量子位。</span><span class="sxs-lookup"><span data-stu-id="8f005-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="8f005-204">換句話說，如果您將電線畫成固定的配量狀態，則線路會在圖表中的每個閘道之間，從左至右都帶著量子狀態。</span><span class="sxs-lookup"><span data-stu-id="8f005-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="8f005-205">也就是說</span><span class="sxs-lookup"><span data-stu-id="8f005-205">That is to say</span></span> 

<span data-ttu-id="8f005-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="8f005-207"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-208">![從左至右套用的量子閘道圖](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="8f005-209">是單一矩陣 $ CBA $ 。</span><span class="sxs-lookup"><span data-stu-id="8f005-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="8f005-210">矩陣乘法遵守相反的慣例：先套用最右邊的矩陣。</span><span class="sxs-lookup"><span data-stu-id="8f005-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="8f005-211">不過，在量子電路圖中，最左邊的閘道會先套用。</span><span class="sxs-lookup"><span data-stu-id="8f005-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="8f005-212">這項差異有時候可能會造成混淆，因此請務必注意線性代數標記法與量子電路圖表之間的這項重大差異。</span><span class="sxs-lookup"><span data-stu-id="8f005-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="8f005-213">量子線路的輸入和輸出</span><span class="sxs-lookup"><span data-stu-id="8f005-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="8f005-214">上述所有先前的範例都有相同數目的線路 (量子位) 輸入至量子閘道，作為量子閘道的線路數目。</span><span class="sxs-lookup"><span data-stu-id="8f005-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="8f005-215">通常，量子電路可能會有比一般輸入更多或更少的輸出。</span><span class="sxs-lookup"><span data-stu-id="8f005-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="8f005-216">不過，這是不可能的，因為所有的量子作業（儲存測量）都是單一的，因此是可還原的。</span><span class="sxs-lookup"><span data-stu-id="8f005-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="8f005-217">如果它們沒有與輸入相同的輸出數目，它們將不會是可還原的，因此不是單一的，這是一項矛盾。</span><span class="sxs-lookup"><span data-stu-id="8f005-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="8f005-218">基於這個理由，在電路圖中繪製的任何方塊都必須有相同數目的線路，才能將它結束。</span><span class="sxs-lookup"><span data-stu-id="8f005-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="8f005-219">多量子位的電路圖表會遵循類似的慣例來進行單一量子位。</span><span class="sxs-lookup"><span data-stu-id="8f005-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="8f005-220">舉例而言，我們可以將兩個量子位的單一作業 B 定義 $ $ 為 $ (H S \otimes X) $ ，並將電路表示為</span><span class="sxs-lookup"><span data-stu-id="8f005-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="8f005-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="8f005-222"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-223">![雙量子位單一作業的電路圖](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="8f005-224">我們也可以根據 $ $ 使用電路的內容，在單一雙量子位登錄上查看 B，而不是在 2 1-量子位暫存器上執行動作。</span><span class="sxs-lookup"><span data-stu-id="8f005-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="8f005-225">這類抽象電路圖的最有用的屬性，就是它們可讓您以較高的層級來描述複雜的量子演算法，而不需要將它們編譯成基本閘道。</span><span class="sxs-lookup"><span data-stu-id="8f005-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="8f005-226">這表示您可以直覺大型量子演算法的資料流程，而不需要瞭解演算法內每個副程式如何運作的所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8f005-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="8f005-227">控制的閘道</span><span class="sxs-lookup"><span data-stu-id="8f005-227">Controlled gates</span></span>
<span data-ttu-id="8f005-228">內建在多量子位量子電路圖表中的另一個結構是 control。</span><span class="sxs-lookup"><span data-stu-id="8f005-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="8f005-229">量子單一控制閘道的動作（表示 $ \Lambda (G) $ ，其中單一量子位的值會控制 g 的應用程式 $ $ ），方法是查看下列產品狀態輸入的範例 $ \Lambda (g)  (\alpha \ket { 0 }  +  \beta \ket { 1 }) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ 。也就是說，受控制的閘道會將 $ G 套用 $ 至包含 if 的註冊， $ \psi $ 而且只有在控制項量子位接受值1時才套用 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="8f005-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="8f005-230">一般而言，我們會將這類受控制的作業描述為</span><span class="sxs-lookup"><span data-stu-id="8f005-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="8f005-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="8f005-232"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-233">![單一控制閘道的電路圖](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="8f005-234">在這裡，黑色圓圈表示控制閘道的量子位，而垂直線路則代表當控制項量子位接受值1時所套用的單一 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="8f005-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="8f005-235">在 $ g X 和 g Z 的特殊情況下， = $ $ = $ 我們引進下列標記法來描述受控制的閘道版本 (請注意，受控制的 X 閘道是[ $ CNOT 網 $ 關](xref:Microsoft.Quantum.Intrinsic.CNOT)) ：</span><span class="sxs-lookup"><span data-stu-id="8f005-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:Microsoft.Quantum.Intrinsic.CNOT)):</span></span>

<span data-ttu-id="8f005-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="8f005-237"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-238">![控制閘道特殊案例的電路圖](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="8f005-239">Q# 提供自動產生受控制版本之作業的方法，讓程式設計人員不必將這些作業交給程式碼。</span><span class="sxs-lookup"><span data-stu-id="8f005-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="8f005-240">範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f005-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="8f005-241">測量運算子</span><span class="sxs-lookup"><span data-stu-id="8f005-241">Measurement operator</span></span>
<span data-ttu-id="8f005-242">在電路圖中以視覺化方式呈現的其餘作業是測量。</span><span class="sxs-lookup"><span data-stu-id="8f005-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="8f005-243">測量會採用量子位註冊、加以測量，並將結果輸出為傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="8f005-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="8f005-244">度量作業是由計量符號表示，並一律以量子位暫存器的輸入作為輸入， (以實線表示) 並輸出傳統資訊 (以雙線) 表示。</span><span class="sxs-lookup"><span data-stu-id="8f005-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="8f005-245">具體來說，這類 subcircuit 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="8f005-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="8f005-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="8f005-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="8f005-247"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-248">![代表測量運算的符號](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="8f005-249">Q# 針對此目的實作為 [量值運算子](xref:Microsoft.Quantum.Intrinsic.Measure) 。</span><span class="sxs-lookup"><span data-stu-id="8f005-249">Q# implements a [Measure operator](xref:Microsoft.Quantum.Intrinsic.Measure) for this purpose.</span></span>
<span data-ttu-id="8f005-250">如需詳細資訊，請參閱 [度量一節](xref:microsoft.quantum.libraries.standard.prelude#measurements) 。</span><span class="sxs-lookup"><span data-stu-id="8f005-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="8f005-251">同樣地，subcircuit</span><span class="sxs-lookup"><span data-stu-id="8f005-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="8f005-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="8f005-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="8f005-253"><!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="8f005-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="8f005-254">![代表受控制作業的電路圖](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="8f005-255">提供傳統方式控制的閘道，其中 G 會套用至實 $ $ 值為1的傳統控制項位 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="8f005-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="8f005-256">遙傳電路圖</span><span class="sxs-lookup"><span data-stu-id="8f005-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="8f005-257">量子遙傳可能是用來說明這些元件的最佳量子演算法。</span><span class="sxs-lookup"><span data-stu-id="8f005-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="8f005-258">您可以瞭解對應的 [量子 Kata](xref:microsoft.quantum.overview.katas) 量子遙傳是在量子電腦中移動資料的一種方法， (或甚至是在量子網路中的遠端量子電腦之間，) 透過使用纏結和測量。</span><span class="sxs-lookup"><span data-stu-id="8f005-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="8f005-259">有趣的是，它實際上能夠將量子狀態（例如指定量子位中的值）從一個量子位移至另一個，而不需要知道量子位的值為何！</span><span class="sxs-lookup"><span data-stu-id="8f005-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="8f005-260">這是必要的，才能讓通訊協定根據量子機制的法律運作。</span><span class="sxs-lookup"><span data-stu-id="8f005-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="8f005-261">量子遙傳線路如下所述;我們也會提供已標注的線路版本，以說明如何讀取量子電路。</span><span class="sxs-lookup"><span data-stu-id="8f005-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="8f005-262"><!--- ![](.\media\tp2.svg) { 寬度 = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="8f005-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="8f005-263">![量子遙傳電路](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
