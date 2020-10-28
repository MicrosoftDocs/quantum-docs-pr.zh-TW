---
<span data-ttu-id="8f005-101">標題：量子線路描述：瞭解如何使用量子電路圖表以視覺化方式呈現簡單且複雜的量子運算。</span><span class="sxs-lookup"><span data-stu-id="8f005-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="8f005-102">author： QuantumWriter uid： benbra ms... ms. date： 12/11/2017 ms. 主題：非 loc 文章：</span><span class="sxs-lookup"><span data-stu-id="8f005-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="8f005-103">":::no-loc(Q#):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-103">":::no-loc(Q#):::"</span></span>
- <span data-ttu-id="8f005-104">":::no-loc($$v):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-104">":::no-loc($$v):::"</span></span>
- <span data-ttu-id="8f005-105">":::no-loc($$):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-105">":::no-loc($$):::"</span></span>
- <span data-ttu-id="8f005-106">":::no-loc($$):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-106">":::no-loc($$):::"</span></span>
- <span data-ttu-id="8f005-107">":::no-loc($):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-107">":::no-loc($):::"</span></span>
- <span data-ttu-id="8f005-108">":::no-loc($):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-108">":::no-loc($):::"</span></span>
- <span data-ttu-id="8f005-109">":::no-loc($):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-109">":::no-loc($):::"</span></span>
- <span data-ttu-id="8f005-110">":::no-loc($$):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-110">":::no-loc($$):::"</span></span>
- <span data-ttu-id="8f005-111">":::no-loc(\cdots):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-111">":::no-loc(\cdots):::"</span></span>
- <span data-ttu-id="8f005-112">":::no-loc(bmatrix):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-112">":::no-loc(bmatrix):::"</span></span>
- <span data-ttu-id="8f005-113">":::no-loc(\ddots):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-113">":::no-loc(\ddots):::"</span></span>
- <span data-ttu-id="8f005-114">":::no-loc(\equiv):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-114">":::no-loc(\equiv):::"</span></span>
- <span data-ttu-id="8f005-115">":::no-loc(\sum):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-115">":::no-loc(\sum):::"</span></span>
- <span data-ttu-id="8f005-116">":::no-loc(\begin):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-116">":::no-loc(\begin):::"</span></span>
- <span data-ttu-id="8f005-117">":::no-loc(\end):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-117">":::no-loc(\end):::"</span></span>
- <span data-ttu-id="8f005-118">":::no-loc(\sqrt):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-118">":::no-loc(\sqrt):::"</span></span>
- <span data-ttu-id="8f005-119">":::no-loc(\otimes):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-119">":::no-loc(\otimes):::"</span></span>
- <span data-ttu-id="8f005-120">":::no-loc({):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-120">":::no-loc({):::"</span></span>
- <span data-ttu-id="8f005-121">":::no-loc(}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-121">":::no-loc(}):::"</span></span>
- <span data-ttu-id="8f005-122">":::no-loc(\text):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-122">":::no-loc(\text):::"</span></span>
- <span data-ttu-id="8f005-123">":::no-loc(\phi):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-123">":::no-loc(\phi):::"</span></span>
- <span data-ttu-id="8f005-124">":::no-loc(\kappa):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-124">":::no-loc(\kappa):::"</span></span>
- <span data-ttu-id="8f005-125">":::no-loc(\psi):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-125">":::no-loc(\psi):::"</span></span>
- <span data-ttu-id="8f005-126">":::no-loc(\alpha):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-126">":::no-loc(\alpha):::"</span></span>
- <span data-ttu-id="8f005-127">":::no-loc(\beta):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-127">":::no-loc(\beta):::"</span></span>
- <span data-ttu-id="8f005-128">":::no-loc(\gamma):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-128">":::no-loc(\gamma):::"</span></span>
- <span data-ttu-id="8f005-129">":::no-loc(\delta):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-129">":::no-loc(\delta):::"</span></span>
- <span data-ttu-id="8f005-130">":::no-loc(\omega):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-130">":::no-loc(\omega):::"</span></span>
- <span data-ttu-id="8f005-131">":::no-loc(\bra):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-131">":::no-loc(\bra):::"</span></span>
- <span data-ttu-id="8f005-132">":::no-loc(\ket):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-132">":::no-loc(\ket):::"</span></span>
- <span data-ttu-id="8f005-133">":::no-loc(\boldone):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-133">":::no-loc(\boldone):::"</span></span>
- <span data-ttu-id="8f005-134">":::no-loc(\\\\):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-134">":::no-loc(\\\\):::"</span></span>
- <span data-ttu-id="8f005-135">":::no-loc(\\):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-135">":::no-loc(\\):::"</span></span>
- <span data-ttu-id="8f005-136">":::no-loc(=):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-136">":::no-loc(=):::"</span></span>
- <span data-ttu-id="8f005-137">":::no-loc(\frac):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-137">":::no-loc(\frac):::"</span></span>
- <span data-ttu-id="8f005-138">":::no-loc(\text):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-138">":::no-loc(\text):::"</span></span>
- <span data-ttu-id="8f005-139">":::no-loc(\mapsto):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-139">":::no-loc(\mapsto):::"</span></span>
- <span data-ttu-id="8f005-140">":::no-loc(\dagger):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-140">":::no-loc(\dagger):::"</span></span>
- <span data-ttu-id="8f005-141">":::no-loc(\to):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-141">":::no-loc(\to):::"</span></span>
- <span data-ttu-id="8f005-142">":::no-loc(\begin{cases}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-142">":::no-loc(\begin{cases}):::"</span></span>
- <span data-ttu-id="8f005-143">":::no-loc(\end{cases}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-143">":::no-loc(\end{cases}):::"</span></span>
- <span data-ttu-id="8f005-144">":::no-loc(\operatorname):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-144">":::no-loc(\operatorname):::"</span></span>
- <span data-ttu-id="8f005-145">":::no-loc(\braket):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-145">":::no-loc(\braket):::"</span></span>
- <span data-ttu-id="8f005-146">":::no-loc(\id):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-146">":::no-loc(\id):::"</span></span>
- <span data-ttu-id="8f005-147">":::no-loc(\expect):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-147">":::no-loc(\expect):::"</span></span>
- <span data-ttu-id="8f005-148">":::no-loc(\defeq):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-148">":::no-loc(\defeq):::"</span></span>
- <span data-ttu-id="8f005-149">":::no-loc(\variance):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-149">":::no-loc(\variance):::"</span></span>
- <span data-ttu-id="8f005-150">":::no-loc(\dd):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-150">":::no-loc(\dd):::"</span></span>
- <span data-ttu-id="8f005-151">":::no-loc(&):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-151">":::no-loc(&):::"</span></span>
- <span data-ttu-id="8f005-152">":::no-loc(\begin{align}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-152">":::no-loc(\begin{align}):::"</span></span>
- <span data-ttu-id="8f005-153">":::no-loc(\end{align}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-153">":::no-loc(\end{align}):::"</span></span>
- <span data-ttu-id="8f005-154">":::no-loc(\Lambda):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-154">":::no-loc(\Lambda):::"</span></span>
- <span data-ttu-id="8f005-155">":::no-loc(\lambda):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-155">":::no-loc(\lambda):::"</span></span>
- <span data-ttu-id="8f005-156">":::no-loc(\Omega):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-156">":::no-loc(\Omega):::"</span></span>
- <span data-ttu-id="8f005-157">":::no-loc(\mathrm):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-157">":::no-loc(\mathrm):::"</span></span>
- <span data-ttu-id="8f005-158">":::no-loc(\left):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-158">":::no-loc(\left):::"</span></span>
- <span data-ttu-id="8f005-159">":::no-loc(\right):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-159">":::no-loc(\right):::"</span></span>
- <span data-ttu-id="8f005-160">":::no-loc(\qquad):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-160">":::no-loc(\qquad):::"</span></span>
- <span data-ttu-id="8f005-161">":::no-loc(\times):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-161">":::no-loc(\times):::"</span></span>
- <span data-ttu-id="8f005-162">":::no-loc(\big):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-162">":::no-loc(\big):::"</span></span>
- <span data-ttu-id="8f005-163">":::no-loc(\langle):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-163">":::no-loc(\langle):::"</span></span>
- <span data-ttu-id="8f005-164">":::no-loc(\rangle):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-164">":::no-loc(\rangle):::"</span></span>
- <span data-ttu-id="8f005-165">":::no-loc(\bigg):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-165">":::no-loc(\bigg):::"</span></span>
- <span data-ttu-id="8f005-166">":::no-loc(\Big):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-166">":::no-loc(\Big):::"</span></span>
- <span data-ttu-id="8f005-167">":::no-loc(|):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-167">":::no-loc(|):::"</span></span>
- <span data-ttu-id="8f005-168">":::no-loc(\mathbb):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-168">":::no-loc(\mathbb):::"</span></span>
- <span data-ttu-id="8f005-169">":::no-loc(\vec):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-169">":::no-loc(\vec):::"</span></span>
- <span data-ttu-id="8f005-170">":::no-loc(\in):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-170">":::no-loc(\in):::"</span></span>
- <span data-ttu-id="8f005-171">":::no-loc(\texttt):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-171">":::no-loc(\texttt):::"</span></span>
- <span data-ttu-id="8f005-172">":::no-loc(\ne):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-172">":::no-loc(\ne):::"</span></span>
- <span data-ttu-id="8f005-173">":::no-loc(<):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-173">":::no-loc(<):::"</span></span>
- <span data-ttu-id="8f005-174">":::no-loc(>):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-174">":::no-loc(>):::"</span></span>
- <span data-ttu-id="8f005-175">":::no-loc(\leq):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-175">":::no-loc(\leq):::"</span></span>
- <span data-ttu-id="8f005-176">":::no-loc(\geq):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-176">":::no-loc(\geq):::"</span></span>
- <span data-ttu-id="8f005-177">":::no-loc(~~):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-177">":::no-loc(~~):::"</span></span>
- <span data-ttu-id="8f005-178">":::no-loc(~):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-178">":::no-loc(~):::"</span></span>
- <span data-ttu-id="8f005-179">":::no-loc(\begin{bmatrix}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-179">":::no-loc(\begin{bmatrix}):::"</span></span>
- <span data-ttu-id="8f005-180">":::no-loc(\end{bmatrix}):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-180">":::no-loc(\end{bmatrix}):::"</span></span>
- <span data-ttu-id="8f005-181">":::no-loc(\_):::"</span><span class="sxs-lookup"><span data-stu-id="8f005-181">":::no-loc(\_):::"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="8f005-182">量子線路</span><span class="sxs-lookup"><span data-stu-id="8f005-182">Quantum Circuits</span></span>
<span data-ttu-id="8f005-183">請考慮一下單一轉換 :::no-loc($)::: :::no-loc(\text)::: :::no-loc({)::: CNOT :::no-loc(})::: _ :::no-loc({)::: 01 :::no-loc(})::: (H :::no-loc(\otimes)::: 1) :::no-loc($)::: 。</span><span class="sxs-lookup"><span data-stu-id="8f005-183">Consider for a moment the unitary transformation :::no-loc($)::::::no-loc(\text)::::::no-loc({)::: CNOT:::no-loc(}):::_:::no-loc({):::01:::no-loc(}):::(H:::no-loc(\otimes)::: 1):::no-loc($):::.</span></span>
<span data-ttu-id="8f005-184">此閘道序列對於量子運算而言很重要，因為它會建立一個充分纏結雙量子位狀態：</span><span class="sxs-lookup"><span data-stu-id="8f005-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="8f005-185">:::no-loc($$)::::::no-loc(\mathrm)::::::no-loc({):::CNOT :::no-loc(})::: _ :::no-loc({)::: 01 :::no-loc(})::: (H :::no-loc(\otimes)::: 1) :::no-loc(\ket)::: :::no-loc({)::: 00 :::no-loc(})::: :::no-loc(=)::: :::no-loc(\frac)::: :::no-loc({)::: 1 :::no-loc(})::: :::no-loc({)::: :::no-loc(\sqrt)::: :::no-loc({)::: 2 :::no-loc(})::: :::no-loc(})::: :::no-loc(\left)::: (:::no-loc(\ket)::: :::no-loc({)::: 00 :::no-loc(}):::  +  :::no-loc(\ket)::: :::no-loc({)::: 11 :::no-loc(})::: :::no-loc(\right):::) ，:::no-loc($$):::</span><span class="sxs-lookup"><span data-stu-id="8f005-185">:::no-loc($$)::::::no-loc(\mathrm)::::::no-loc({):::CNOT:::no-loc(}):::_:::no-loc({):::01:::no-loc(}):::(H:::no-loc(\otimes)::: 1):::no-loc(\ket)::::::no-loc({):::00:::no-loc(})::: :::no-loc(=)::: :::no-loc(\frac)::::::no-loc({):::1:::no-loc(})::::::no-loc({)::::::no-loc(\sqrt)::::::no-loc({):::2:::no-loc(})::::::no-loc(})::: :::no-loc(\left):::(:::no-loc(\ket)::::::no-loc({):::00:::no-loc(})::: + :::no-loc(\ket)::::::no-loc({):::11:::no-loc(})::: :::no-loc(\right):::),:::no-loc($$):::</span></span>

<span data-ttu-id="8f005-186">具有這項或更高複雜度的作業在量子演算法和量子錯誤修正中很常見，因此，其視覺效果有一個簡單的方法，稱為 *量子電路圖* ，因此應該會有很大的降低。</span><span class="sxs-lookup"><span data-stu-id="8f005-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram* .</span></span>
<span data-ttu-id="8f005-187">準備此充分纏結量子狀態的電路圖為：</span><span class="sxs-lookup"><span data-stu-id="8f005-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="8f005-188">:::no-loc(<):::!--- ![](.\media\1.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-188">:::no-loc(<):::!--- ![](.\media\1.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-189">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-189">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-190">![充分纏結雙量子位狀態的電路圖](:::no-loc(~):::/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-190">![Circuit diagram for a maximally entangled two-qubit state](:::no-loc(~):::/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="8f005-191">量子電路圖慣例</span><span class="sxs-lookup"><span data-stu-id="8f005-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="8f005-192">當您瞭解用來表示量子電路的慣例之後，這種適用于量子作業的視覺化語言可以更容易消化。</span><span class="sxs-lookup"><span data-stu-id="8f005-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="8f005-193">我們會在下方探討這些慣例。</span><span class="sxs-lookup"><span data-stu-id="8f005-193">We review these conventions below.</span></span>

<span data-ttu-id="8f005-194">在電路圖中，每個實線都描述量子位或更一般量子位的註冊。</span><span class="sxs-lookup"><span data-stu-id="8f005-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="8f005-195">依照慣例，頂端的行是量子位 register :::no-loc($)::: 0 :::no-loc($)::: ，其餘部分則會依序標示。</span><span class="sxs-lookup"><span data-stu-id="8f005-195">By convention, the top line is qubit register :::no-loc($):::0:::no-loc($)::: and the remainder are labeled sequentially.</span></span> <span data-ttu-id="8f005-196">上述的範例電路在兩個量子位 (或等同于一個量子位) 的兩個暫存器上進行描述。</span><span class="sxs-lookup"><span data-stu-id="8f005-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="8f005-197">以一個或多個量子位暫存器為依據的閘道會以方塊表示。</span><span class="sxs-lookup"><span data-stu-id="8f005-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="8f005-198">例如，符號</span><span class="sxs-lookup"><span data-stu-id="8f005-198">For example, the symbol</span></span>

<span data-ttu-id="8f005-199">:::no-loc(<):::!--- ![](.\media\2.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-199">:::no-loc(<):::!--- ![](.\media\2.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-200">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-200">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-201">![Hadamard 作業的符號，可在單一量子位暫存器上運作](:::no-loc(~):::/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-201">![Symbol for a Hadamard operation acting on a single-qubit register](:::no-loc(~):::/media/2.svg)</span></span>

<span data-ttu-id="8f005-202">是在單一量子位登錄上進行的 [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) 作業。</span><span class="sxs-lookup"><span data-stu-id="8f005-202">is a [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="8f005-203">量子閘道會依時間順序排序，最左邊的閘道會先套用至量子位。</span><span class="sxs-lookup"><span data-stu-id="8f005-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="8f005-204">換句話說，如果您將電線畫成固定的配量狀態，則線路會在圖表中的每個閘道之間，從左至右都帶著量子狀態。</span><span class="sxs-lookup"><span data-stu-id="8f005-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="8f005-205">也就是說</span><span class="sxs-lookup"><span data-stu-id="8f005-205">That is to say</span></span> 

<span data-ttu-id="8f005-206">:::no-loc(<):::!--- ![](.\media\3.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-206">:::no-loc(<):::!--- ![](.\media\3.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-207">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-207">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-208">![從左至右套用的量子閘道圖](:::no-loc(~):::/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-208">![Diagram of quantum gates being applied left-to-right](:::no-loc(~):::/media/3.svg)</span></span>

<span data-ttu-id="8f005-209">是單一矩陣 :::no-loc($)::: CBA :::no-loc($)::: 。</span><span class="sxs-lookup"><span data-stu-id="8f005-209">is the unitary matrix :::no-loc($):::CBA:::no-loc($):::.</span></span>
<span data-ttu-id="8f005-210">矩陣乘法遵守相反的慣例：先套用最右邊的矩陣。</span><span class="sxs-lookup"><span data-stu-id="8f005-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="8f005-211">不過，在量子電路圖中，最左邊的閘道會先套用。</span><span class="sxs-lookup"><span data-stu-id="8f005-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="8f005-212">這項差異有時候可能會造成混淆，因此請務必注意線性代數標記法與量子電路圖表之間的這項重大差異。</span><span class="sxs-lookup"><span data-stu-id="8f005-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="8f005-213">量子線路的輸入和輸出</span><span class="sxs-lookup"><span data-stu-id="8f005-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="8f005-214">上述所有先前的範例都有相同數目的線路 (量子位) 輸入至量子閘道，作為量子閘道的線路數目。</span><span class="sxs-lookup"><span data-stu-id="8f005-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="8f005-215">通常，量子電路可能會有比一般輸入更多或更少的輸出。</span><span class="sxs-lookup"><span data-stu-id="8f005-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="8f005-216">不過，這是不可能的，因為所有的量子作業（儲存測量）都是單一的，因此是可還原的。</span><span class="sxs-lookup"><span data-stu-id="8f005-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="8f005-217">如果它們沒有與輸入相同的輸出數目，它們將不會是可還原的，因此不是單一的，這是一項矛盾。</span><span class="sxs-lookup"><span data-stu-id="8f005-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="8f005-218">基於這個理由，在電路圖中繪製的任何方塊都必須有相同數目的線路，才能將它結束。</span><span class="sxs-lookup"><span data-stu-id="8f005-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="8f005-219">多量子位的電路圖表會遵循類似的慣例來進行單一量子位。</span><span class="sxs-lookup"><span data-stu-id="8f005-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="8f005-220">舉例而言，我們可以將兩個量子位的單一作業 B 定義 :::no-loc($)::: :::no-loc($)::: 為 :::no-loc($)::: (H S :::no-loc(\otimes)::: X) :::no-loc($)::: ，並將電路表示為</span><span class="sxs-lookup"><span data-stu-id="8f005-220">As a clarifying example, we can define a two-qubit unitary operation :::no-loc($):::B:::no-loc($)::: to be :::no-loc($):::(H S:::no-loc(\otimes)::: X):::no-loc($)::: and express the circuit equivalently as</span></span>

<span data-ttu-id="8f005-221">:::no-loc(<):::!--- ![](.\media\4.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-221">:::no-loc(<):::!--- ![](.\media\4.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-222">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-222">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-223">![雙量子位單一作業的電路圖](:::no-loc(~):::/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-223">![Circuit diagram of a two-qubit unitary operation](:::no-loc(~):::/media/4.svg)</span></span>

<span data-ttu-id="8f005-224">我們也可以根據 :::no-loc($)::: :::no-loc($)::: 使用電路的內容，在單一雙量子位登錄上查看 B，而不是在 2 1-量子位暫存器上執行動作。</span><span class="sxs-lookup"><span data-stu-id="8f005-224">We can also view :::no-loc($):::B:::no-loc($)::: as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="8f005-225">這類抽象電路圖的最有用的屬性，就是它們可讓您以較高的層級來描述複雜的量子演算法，而不需要將它們編譯成基本閘道。</span><span class="sxs-lookup"><span data-stu-id="8f005-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="8f005-226">這表示您可以直覺大型量子演算法的資料流程，而不需要瞭解演算法內每個副程式如何運作的所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8f005-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="8f005-227">控制的閘道</span><span class="sxs-lookup"><span data-stu-id="8f005-227">Controlled gates</span></span>
<span data-ttu-id="8f005-228">內建在多量子位量子電路圖表中的另一個結構是 control。</span><span class="sxs-lookup"><span data-stu-id="8f005-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="8f005-229">量子單一控制閘道的動作（表示 :::no-loc($)::: :::no-loc(\Lambda)::: (G) :::no-loc($)::: ，其中單一量子位的值會控制 g 的應用程式 :::no-loc($)::: :::no-loc($)::: ），方法是查看下列產品狀態輸入的範例 :::no-loc($)::: :::no-loc(\Lambda)::: (g)  (:::no-loc(\alpha)::: :::no-loc(\ket)::: :::no-loc({)::: 0 :::no-loc(}):::  +  :::no-loc(\beta)::: :::no-loc(\ket)::: :::no-loc({)::: 1 :::no-loc(}):::) :::no-loc(\ket)::: :::no-loc({)::: :::no-loc(\psi)::: :::no-loc(})::: :::no-loc(=)::: :::no-loc(\alpha)::: :::no-loc(\ket)::: :::no-loc({)::: 0 :::no-loc(})::: :::no-loc(\ket)::: :::no-loc({)::: :::no-loc(\psi)::: :::no-loc(}):::  +  :::no-loc(\beta)::: :::no-loc(\ket)::: :::no-loc({)::: 1 :::no-loc(})::: G :::no-loc(\ket)::: :::no-loc({)::: :::no-loc(\psi)::: :::no-loc(})::: :::no-loc($)::: 。也就是說，受控制的閘道會將 :::no-loc($)::: G 套用 :::no-loc($)::: 至包含 if 的註冊， :::no-loc($)::: :::no-loc(\psi)::: :::no-loc($)::: 而且只有在控制項量子位接受值1時才套用 :::no-loc($)::: :::no-loc($)::: 。</span><span class="sxs-lookup"><span data-stu-id="8f005-229">The action of a quantum singly controlled gate, denoted :::no-loc($)::::::no-loc(\Lambda):::(G):::no-loc($):::, where a single qubit's value controls the application of :::no-loc($):::G:::no-loc($):::, can be understood by looking at the following example of a product state input :::no-loc($)::::::no-loc(\Lambda):::(G) (:::no-loc(\alpha)::: :::no-loc(\ket)::::::no-loc({):::0:::no-loc(})::: + :::no-loc(\beta)::: :::no-loc(\ket)::::::no-loc({):::1:::no-loc(}):::) :::no-loc(\ket)::::::no-loc({)::::::no-loc(\psi)::::::no-loc(})::: :::no-loc(=)::: :::no-loc(\alpha)::: :::no-loc(\ket)::::::no-loc({):::0:::no-loc(})::: :::no-loc(\ket)::::::no-loc({)::::::no-loc(\psi)::::::no-loc(})::: + :::no-loc(\beta)::: :::no-loc(\ket)::::::no-loc({):::1:::no-loc(})::: G:::no-loc(\ket)::::::no-loc({)::::::no-loc(\psi)::::::no-loc(})::::::no-loc($):::. That is to say, the controlled gate applies :::no-loc($):::G:::no-loc($)::: to the register containing :::no-loc($)::::::no-loc(\psi)::::::no-loc($)::: if and only if the control qubit takes the value :::no-loc($):::1:::no-loc($):::.</span></span>
<span data-ttu-id="8f005-230">一般而言，我們會將這類受控制的作業描述為</span><span class="sxs-lookup"><span data-stu-id="8f005-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="8f005-231">:::no-loc(<):::!--- ![](.\media\5.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-231">:::no-loc(<):::!--- ![](.\media\5.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-232">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-232">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-233">![單一控制閘道的電路圖](:::no-loc(~):::/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-233">![Circuit diagram of a singly controlled gate](:::no-loc(~):::/media/5.svg)</span></span>

<span data-ttu-id="8f005-234">在這裡，黑色圓圈表示控制閘道的量子位，而垂直線路則代表當控制項量子位接受值1時所套用的單一 :::no-loc($)::: :::no-loc($)::: 。</span><span class="sxs-lookup"><span data-stu-id="8f005-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value :::no-loc($):::1:::no-loc($):::.</span></span>
<span data-ttu-id="8f005-235">在 :::no-loc($)::: g X 和 g Z 的特殊情況下， :::no-loc(=)::: :::no-loc($)::: :::no-loc($)::: :::no-loc(=)::: :::no-loc($)::: 我們引進下列標記法來描述受控制的閘道版本 (請注意，受控制的 X 閘道是[ :::no-loc($)::: CNOT 網 :::no-loc($)::: 關](xref:Microsoft.Quantum.Intrinsic.CNOT)) ：</span><span class="sxs-lookup"><span data-stu-id="8f005-235">For the special cases where :::no-loc($):::G:::no-loc(=):::X:::no-loc($)::: and :::no-loc($):::G:::no-loc(=):::Z:::no-loc($)::: we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [:::no-loc($):::CNOT:::no-loc($)::: gate](xref:Microsoft.Quantum.Intrinsic.CNOT)):</span></span>

<span data-ttu-id="8f005-236">:::no-loc(<):::!--- ![](.\media\6.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-236">:::no-loc(<):::!--- ![](.\media\6.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-237">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-237">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-238">![控制閘道特殊案例的電路圖](:::no-loc(~):::/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-238">![Circuit diagram for special cases of controlled gates](:::no-loc(~):::/media/6.svg)</span></span>

<span data-ttu-id="8f005-239">:::no-loc(Q#)::: 提供自動產生受控制版本之作業的方法，讓程式設計人員不必將這些作業交給程式碼。</span><span class="sxs-lookup"><span data-stu-id="8f005-239">:::no-loc(Q#)::: provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="8f005-240">範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f005-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl :::no-loc({)::: // Auto-generate the controlled specialization of the operation
    H(qubit);
:::no-loc(}):::
```

## <a name="measurement-operator"></a><span data-ttu-id="8f005-241">測量運算子</span><span class="sxs-lookup"><span data-stu-id="8f005-241">Measurement operator</span></span>
<span data-ttu-id="8f005-242">在電路圖中以視覺化方式呈現的其餘作業是測量。</span><span class="sxs-lookup"><span data-stu-id="8f005-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="8f005-243">測量會採用量子位註冊、加以測量，並將結果輸出為傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="8f005-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="8f005-244">度量作業是由計量符號表示，並一律以量子位暫存器的輸入作為輸入， (以實線表示) 並輸出傳統資訊 (以雙線) 表示。</span><span class="sxs-lookup"><span data-stu-id="8f005-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="8f005-245">具體來說，這類 subcircuit 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="8f005-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="8f005-246">:::no-loc(<):::!--- ![](.\media\7.svg) ----:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-246">:::no-loc(<):::!--- ![](.\media\7.svg) ----:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-247">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-247">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-248">![代表測量運算的符號](:::no-loc(~):::/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-248">![Symbol representing a measurement operation](:::no-loc(~):::/media/7.svg)</span></span>

<span data-ttu-id="8f005-249">:::no-loc(Q#)::: 針對此目的實作為 [量值運算子](xref:Microsoft.Quantum.Intrinsic.Measure) 。</span><span class="sxs-lookup"><span data-stu-id="8f005-249">:::no-loc(Q#)::: implements a [Measure operator](xref:Microsoft.Quantum.Intrinsic.Measure) for this purpose.</span></span>
<span data-ttu-id="8f005-250">如需詳細資訊，請參閱 [度量一節](xref:microsoft.quantum.libraries.standard.prelude#measurements) 。</span><span class="sxs-lookup"><span data-stu-id="8f005-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="8f005-251">同樣地，subcircuit</span><span class="sxs-lookup"><span data-stu-id="8f005-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="8f005-252">:::no-loc(<):::!--- ![](.\media\8.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-252">:::no-loc(<):::!--- ![](.\media\8.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-253">:::no-loc(<):::!--找不到可輕鬆將其置中的方法 .。。可能是需要的延伸模組：--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-253">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-254">![代表受控制作業的電路圖](:::no-loc(~):::/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-254">![Circuit diagram representing a controlled operation](:::no-loc(~):::/media/8.svg)</span></span>

<span data-ttu-id="8f005-255">提供傳統方式控制的閘道，其中 G 會套用至實 :::no-loc($)::: :::no-loc($)::: 值為1的傳統控制項位 :::no-loc($)::: :::no-loc($)::: 。</span><span class="sxs-lookup"><span data-stu-id="8f005-255">gives a classically controlled gate, where :::no-loc($):::G:::no-loc($)::: is applied conditioned on the classical control bit being value :::no-loc($):::1:::no-loc($):::.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="8f005-256">遙傳電路圖</span><span class="sxs-lookup"><span data-stu-id="8f005-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="8f005-257">量子遙傳可能是用來說明這些元件的最佳量子演算法。</span><span class="sxs-lookup"><span data-stu-id="8f005-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="8f005-258">您可以瞭解對應的 [量子 Kata](xref:microsoft.quantum.overview.katas) 量子遙傳是在量子電腦中移動資料的一種方法， (或甚至是在量子網路中的遠端量子電腦之間，) 透過使用纏結和測量。</span><span class="sxs-lookup"><span data-stu-id="8f005-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="8f005-259">有趣的是，它實際上能夠將量子狀態（例如指定量子位中的值）從一個量子位移至另一個，而不需要知道量子位的值為何！</span><span class="sxs-lookup"><span data-stu-id="8f005-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="8f005-260">這是必要的，才能讓通訊協定根據量子機制的法律運作。</span><span class="sxs-lookup"><span data-stu-id="8f005-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="8f005-261">量子遙傳線路如下所述;我們也會提供已標注的線路版本，以說明如何讀取量子電路。</span><span class="sxs-lookup"><span data-stu-id="8f005-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="8f005-262">:::no-loc(<):::!--- ![](.\media\tp2.svg) :::no-loc({)::: 寬度 :::no-loc(=)::: 50%:::no-loc(})::: ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="8f005-262">:::no-loc(<):::!--- ![](.\media\tp2.svg):::no-loc({)::: width:::no-loc(=):::50% :::no-loc(})::: ---:::no-loc(>):::</span></span>
<span data-ttu-id="8f005-263">![量子遙傳電路](:::no-loc(~):::/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="8f005-263">![Quantum teleportation circuit](:::no-loc(~):::/media/tp2.svg)</span></span>
