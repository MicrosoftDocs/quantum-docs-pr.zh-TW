---
<span data-ttu-id="c0b4e-101">標題：配量線路描述：瞭解如何以視覺化方式呈現使用配量線路圖表的簡單和複雜配量作業。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="c0b4e-102">author： QuantumWriter uid： microsoft 量子.. m. m. a m. nawiebe@microsoft.com date： 12/11/2017 ms. 主題：不含 loc 的文章：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="c0b4e-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-103">"Q#"</span></span>
- <span data-ttu-id="c0b4e-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-104">"$$v"</span></span>
- <span data-ttu-id="c0b4e-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-105">"$$"</span></span>
- <span data-ttu-id="c0b4e-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-106">"$$"</span></span>
- <span data-ttu-id="c0b4e-107">"$"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-107">"$"</span></span>
- <span data-ttu-id="c0b4e-108">"$"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-108">"$"</span></span>
- <span data-ttu-id="c0b4e-109">"$"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-109">"$"</span></span>
- <span data-ttu-id="c0b4e-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-110">"$$"</span></span>
- <span data-ttu-id="c0b4e-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-111">"\cdots"</span></span>
- <span data-ttu-id="c0b4e-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-112">"bmatrix"</span></span>
- <span data-ttu-id="c0b4e-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-113">"\ddots"</span></span>
- <span data-ttu-id="c0b4e-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-114">"\equiv"</span></span>
- <span data-ttu-id="c0b4e-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-115">"\sum"</span></span>
- <span data-ttu-id="c0b4e-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-116">"\begin"</span></span>
- <span data-ttu-id="c0b4e-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-117">"\end"</span></span>
- <span data-ttu-id="c0b4e-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-118">"\sqrt"</span></span>
- <span data-ttu-id="c0b4e-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-119">"\otimes"</span></span>
- <span data-ttu-id="c0b4e-120">"{"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-120">"{"</span></span>
- <span data-ttu-id="c0b4e-121">"}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-121">"}"</span></span>
- <span data-ttu-id="c0b4e-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-122">"\text"</span></span>
- <span data-ttu-id="c0b4e-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-123">"\phi"</span></span>
- <span data-ttu-id="c0b4e-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-124">"\kappa"</span></span>
- <span data-ttu-id="c0b4e-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-125">"\psi"</span></span>
- <span data-ttu-id="c0b4e-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-126">"\alpha"</span></span>
- <span data-ttu-id="c0b4e-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-127">"\beta"</span></span>
- <span data-ttu-id="c0b4e-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-128">"\gamma"</span></span>
- <span data-ttu-id="c0b4e-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-129">"\delta"</span></span>
- <span data-ttu-id="c0b4e-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-130">"\omega"</span></span>
- <span data-ttu-id="c0b4e-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-131">"\bra"</span></span>
- <span data-ttu-id="c0b4e-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-132">"\ket"</span></span>
- <span data-ttu-id="c0b4e-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-133">"\boldone"</span></span>
- <span data-ttu-id="c0b4e-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-134">"\\\\"</span></span>
- <span data-ttu-id="c0b4e-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-135">"\\"</span></span>
- <span data-ttu-id="c0b4e-136">"="</span><span class="sxs-lookup"><span data-stu-id="c0b4e-136">"="</span></span>
- <span data-ttu-id="c0b4e-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-137">"\frac"</span></span>
- <span data-ttu-id="c0b4e-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-138">"\text"</span></span>
- <span data-ttu-id="c0b4e-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-139">"\mapsto"</span></span>
- <span data-ttu-id="c0b4e-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-140">"\dagger"</span></span>
- <span data-ttu-id="c0b4e-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-141">"\to"</span></span>
- <span data-ttu-id="c0b4e-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-142">"\begin{cases}"</span></span>
- <span data-ttu-id="c0b4e-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-143">"\end{cases}"</span></span>
- <span data-ttu-id="c0b4e-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-144">"\operatorname"</span></span>
- <span data-ttu-id="c0b4e-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-145">"\braket"</span></span>
- <span data-ttu-id="c0b4e-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-146">"\id"</span></span>
- <span data-ttu-id="c0b4e-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-147">"\expect"</span></span>
- <span data-ttu-id="c0b4e-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-148">"\defeq"</span></span>
- <span data-ttu-id="c0b4e-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-149">"\variance"</span></span>
- <span data-ttu-id="c0b4e-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-150">"\dd"</span></span>
- <span data-ttu-id="c0b4e-151">"&"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-151">"&"</span></span>
- <span data-ttu-id="c0b4e-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-152">"\begin{align}"</span></span>
- <span data-ttu-id="c0b4e-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-153">"\end{align}"</span></span>
- <span data-ttu-id="c0b4e-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-154">"\Lambda"</span></span>
- <span data-ttu-id="c0b4e-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-155">"\lambda"</span></span>
- <span data-ttu-id="c0b4e-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-156">"\Omega"</span></span>
- <span data-ttu-id="c0b4e-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-157">"\mathrm"</span></span>
- <span data-ttu-id="c0b4e-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-158">"\left"</span></span>
- <span data-ttu-id="c0b4e-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-159">"\right"</span></span>
- <span data-ttu-id="c0b4e-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-160">"\qquad"</span></span>
- <span data-ttu-id="c0b4e-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-161">"\times"</span></span>
- <span data-ttu-id="c0b4e-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-162">"\big"</span></span>
- <span data-ttu-id="c0b4e-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-163">"\langle"</span></span>
- <span data-ttu-id="c0b4e-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-164">"\rangle"</span></span>
- <span data-ttu-id="c0b4e-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-165">"\bigg"</span></span>
- <span data-ttu-id="c0b4e-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-166">"\Big"</span></span>
- <span data-ttu-id="c0b4e-167">"|"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-167">"|"</span></span>
- <span data-ttu-id="c0b4e-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-168">"\mathbb"</span></span>
- <span data-ttu-id="c0b4e-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-169">"\vec"</span></span>
- <span data-ttu-id="c0b4e-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-170">"\in"</span></span>
- <span data-ttu-id="c0b4e-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-171">"\texttt"</span></span>
- <span data-ttu-id="c0b4e-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-172">"\ne"</span></span>
- <span data-ttu-id="c0b4e-173">"<"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-173">"<"</span></span>
- <span data-ttu-id="c0b4e-174">">"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-174">">"</span></span>
- <span data-ttu-id="c0b4e-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-175">"\leq"</span></span>
- <span data-ttu-id="c0b4e-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-176">"\geq"</span></span>
- <span data-ttu-id="c0b4e-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-177">"~~"</span></span>
- <span data-ttu-id="c0b4e-178">"~"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-178">"~"</span></span>
- <span data-ttu-id="c0b4e-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="c0b4e-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="c0b4e-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="c0b4e-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="c0b4e-182">量子線路</span><span class="sxs-lookup"><span data-stu-id="c0b4e-182">Quantum Circuits</span></span>
<span data-ttu-id="c0b4e-183">請思考一下單一轉換 $ \text { cnot-contains } _ { 01 } (H \otimes 1) $ 。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="c0b4e-184">此閘道序列對量子運算的基本重要性，因為它會建立最常光子二 qubit 的狀態：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="c0b4e-185">$$\mathrm{Cnot-contains } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left (\ket { 00 }  +  \ket { 11 } \right) ，$$</span><span class="sxs-lookup"><span data-stu-id="c0b4e-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="c0b4e-186">具有此或更大複雜度的作業在配量演算法和量子錯誤更正中是普遍的，因此，它應該是一個簡單的視覺效果方法，稱為配量*線路圖*。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="c0b4e-187">準備此最常光子量子狀態的線路圖表如下：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="c0b4e-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="c0b4e-189"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-190">![最常光子二 qubit 狀態的電路圖](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="c0b4e-191">配量線路圖慣例</span><span class="sxs-lookup"><span data-stu-id="c0b4e-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="c0b4e-192">當您瞭解用來表示配量線路的慣例之後，可以更輕鬆地消化量子作業的視覺化語言，而不是寫下其對等的矩陣。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="c0b4e-193">我們會在下面探討這些慣例。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-193">We review these conventions below.</span></span>

<span data-ttu-id="c0b4e-194">在電路圖中，每一條實線描述一個 qubit 或更普遍的 qubit 暫存器。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="c0b4e-195">依照慣例，第一行是 qubit 暫存器 $ 0 $ ，其餘部分則以順序標示。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="c0b4e-196">上述的範例電路會在兩個 qubits (或等同兩個由一個 qubit) 組成的暫存器上，描述為作用。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="c0b4e-197">以一個或多個 qubit 暫存器為作用的閘道會以方塊表示。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="c0b4e-198">例如，符號</span><span class="sxs-lookup"><span data-stu-id="c0b4e-198">For example, the symbol</span></span>

<span data-ttu-id="c0b4e-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="c0b4e-200"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-201">![Hadamard 作業的符號，適用于單一 qubit 暫存器](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="c0b4e-202">是在單一 qubit 暫存器上運作的[Hadamard](xref:microsoft.quantum.intrinsic.h)作業。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-202">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="c0b4e-203">配量閘道會按照時間順序排列，並以最左邊的閘道作為第一次套用到 qubits 的閘道。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="c0b4e-204">換句話說，如果您將線路畫成包含配量狀態，則電線會從左至右的圖表中的每個閘道顯示配量狀態。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="c0b4e-205">也就是說</span><span class="sxs-lookup"><span data-stu-id="c0b4e-205">That is to say</span></span> 

<span data-ttu-id="c0b4e-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="c0b4e-207"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-208">![由左至右套用的量子閘道圖](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="c0b4e-209">是單一矩陣 $ CBA $ 。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="c0b4e-210">矩陣乘法遵守相反的慣例：第一次套用最右邊的矩陣。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="c0b4e-211">不過，在配量電路圖中，會先套用最左邊的閘道。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="c0b4e-212">這項差異有時可能會造成混淆，因此請務必注意線性代數標記法與配量電路圖之間的顯著差異。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="c0b4e-213">量子線路的輸入和輸出</span><span class="sxs-lookup"><span data-stu-id="c0b4e-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="c0b4e-214">所有先前的範例都具有精確的線路數， (qubits) 輸入到配量閘道，做為從量子閘道的線路數目。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="c0b4e-215">一般來說，配量線路可能會有比一般輸入更多或更少的輸出。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="c0b4e-216">不過，這是不可能的，因為所有的量子作業、儲存量測都是單一的，因此可以還原。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="c0b4e-217">如果它們沒有與輸入相同的輸出數目，它們將無法復原，因此不是單一的，這是一項衝突。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="c0b4e-218">基於這個理由，在電路圖中繪製的任何方塊都必須有相同數目的線路進入結束。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="c0b4e-219">多 qubit 的電路圖表會遵循類似的慣例來進行單一 qubit。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="c0b4e-220">做為說明範例，我們可以定義兩個 qubit 的單一作業 $ B $ $ (H S \otimes X) $ ，並以等同的方式表達線路</span><span class="sxs-lookup"><span data-stu-id="c0b4e-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="c0b4e-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="c0b4e-222"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-223">![兩個 qubit 的單一作業的路線圖](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="c0b4e-224">我們也可以根據 $ $ 使用線路的內容，在單一雙 qubit 暫存器（而不是 2 1-qubit 暫存器）上查看 B。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="c0b4e-225">這類抽象循環圖表表可能是最有用的屬性，因為它們可讓複雜的量子演算法以高階方式描述，而不需要將它們編譯成基本閘道。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="c0b4e-226">這表示您可以針對大型配量演算法取得資料流程的直覺，而不需要瞭解演算法中每個副程式如何工作的所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="c0b4e-227">控制的閘道</span><span class="sxs-lookup"><span data-stu-id="c0b4e-227">Controlled gates</span></span>
<span data-ttu-id="c0b4e-228">另一個內建于多 qubit 配量電路圖的結構是 control。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="c0b4e-229">配量單一控制閘道的動作（以 qubit g) 表示），您 $ \Lambda 可以藉 $ $ $ 由查看下列產品狀態 (輸入的範例，來瞭解如何 (0 $ \Lambda \alpha \ket { }  +  \beta \ket { 1 } \ket { \psi } = \alpha \ket { } \ket { \psi }  +  \beta \ket { } g \ket { \psi } $) 0 的) ，藉此識別出 g 的應用程式 (。也就是說， $ $ 只有在 $ \psi $ 控制項 qubit 接受值 $ 1 $ 時，受控制的閘道才會將 G 套用至包含 if 和的暫存器。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="c0b4e-230">一般來說，我們會在電路圖中描述這類受控制的作業，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="c0b4e-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="c0b4e-232"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-233">![單向控制閘道的路線圖](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="c0b4e-234">在這裡，黑色圓圈代表控制閘道的配量位，而垂直線代表當控制項 qubit 接受值1時所套用的單一 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="c0b4e-235">在 $ g X 和 g Z 的特殊案例中， = $ $ = $ 我們引進了下列標記法來描述控制的閘道版本 (請注意，控制的 X 閘道是[ $ cnot-contains 網 $ 關](xref:microsoft.quantum.intrinsic.cnot)) ：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<span data-ttu-id="c0b4e-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="c0b4e-237"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-238">![控制閘道特殊案例的電路圖](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="c0b4e-239">Q#提供自動產生受控制版本之作業的方法，可讓程式設計人員不必手動撰寫這些作業的程式碼。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="c0b4e-240">範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="c0b4e-241">測量運算子</span><span class="sxs-lookup"><span data-stu-id="c0b4e-241">Measurement operator</span></span>
<span data-ttu-id="c0b4e-242">要在電路圖中視覺化的其餘作業是測量。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="c0b4e-243">測量會採用 qubit 暫存器、加以測量，然後將結果輸出為傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="c0b4e-244">量測作業是由計量符號表示，且一律會以實線) 的 (qubit 暫存器做為輸入，並輸出以雙線) 表示的傳統資訊 (。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="c0b4e-245">具體而言，這類 subcircuit 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="c0b4e-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="c0b4e-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="c0b4e-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="c0b4e-247"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-248">![代表測量運算的符號](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="c0b4e-249">Q#針對此用途來執行[量值運算子](xref:microsoft.quantum.intrinsic.measure)。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-249">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="c0b4e-250">如需詳細資訊，請參閱[測量的一節](xref:microsoft.quantum.libraries.standard.prelude#measurements)。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="c0b4e-251">同樣地，subcircuit</span><span class="sxs-lookup"><span data-stu-id="c0b4e-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="c0b4e-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="c0b4e-253"><!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：--></span><span class="sxs-lookup"><span data-stu-id="c0b4e-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="c0b4e-254">![代表受控制作業的線路圖表](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="c0b4e-255">提供受傳統方式控制的閘道，其中 $ G $ 適用于傳統控制位的值為 $ 1 $ 。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="c0b4e-256">Teleportation 線路圖表</span><span class="sxs-lookup"><span data-stu-id="c0b4e-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="c0b4e-257">量子 teleportation 可能是用來說明這些元件的最佳量子演算法。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="c0b4e-258">您可以學習使用對應的[量子 Kata](xref:microsoft.quantum.overview.katas)量子 teleportation，這是一種在量子電腦中移動資料的方法， (或甚至是在配量網路中的較遠量子電腦之間，) 透過使用會任何牽連和測量。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="c0b4e-259">有趣的是，它實際上能夠將量子狀態（也就是指定 qubit 中的值）從一個 qubit 移到另一個，而不用知道 qubit 的值是什麼！</span><span class="sxs-lookup"><span data-stu-id="c0b4e-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="c0b4e-260">這是通訊協定根據量子機制的法律而必須運作的必要條件。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="c0b4e-261">下面提供量子 teleportation 線路;我們也會提供已標注的電路版本，以說明如何讀取配量線路。</span><span class="sxs-lookup"><span data-stu-id="c0b4e-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="c0b4e-262"><!--- ![](.\media\tp2.svg) { 寬度 = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="c0b4e-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="c0b4e-263">![量子 teleportation 線路](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="c0b4e-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
