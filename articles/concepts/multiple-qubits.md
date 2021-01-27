---
<span data-ttu-id="9d406-101">標題：多個量子位描述：瞭解如何在兩個或多個量子位上執行作業。</span><span class="sxs-lookup"><span data-stu-id="9d406-101">title: Multiple qubits description: Learn how to perform operations on two or more qubits.</span></span>
<span data-ttu-id="9d406-102">作者： bradben uid：量子位 ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：概念非 loc：</span><span class="sxs-lookup"><span data-stu-id="9d406-102">author: bradben uid: microsoft.quantum.concepts.multiple-qubits ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="9d406-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="9d406-103">"Q#"</span></span>
- <span data-ttu-id="9d406-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="9d406-104">"$$v"</span></span>
- <span data-ttu-id="9d406-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="9d406-105">"$$"</span></span>
- <span data-ttu-id="9d406-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="9d406-106">"$$"</span></span>
- <span data-ttu-id="9d406-107">"$"</span><span class="sxs-lookup"><span data-stu-id="9d406-107">"$"</span></span>
- <span data-ttu-id="9d406-108">"$"</span><span class="sxs-lookup"><span data-stu-id="9d406-108">"$"</span></span>
- <span data-ttu-id="9d406-109">"$"</span><span class="sxs-lookup"><span data-stu-id="9d406-109">"$"</span></span>
- <span data-ttu-id="9d406-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="9d406-110">"$$"</span></span>
- <span data-ttu-id="9d406-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="9d406-111">"\cdots"</span></span>
- <span data-ttu-id="9d406-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="9d406-112">"bmatrix"</span></span>
- <span data-ttu-id="9d406-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="9d406-113">"\ddots"</span></span>
- <span data-ttu-id="9d406-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="9d406-114">"\equiv"</span></span>
- <span data-ttu-id="9d406-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="9d406-115">"\sum"</span></span>
- <span data-ttu-id="9d406-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="9d406-116">"\begin"</span></span>
- <span data-ttu-id="9d406-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="9d406-117">"\end"</span></span>
- <span data-ttu-id="9d406-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="9d406-118">"\sqrt"</span></span>
- <span data-ttu-id="9d406-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="9d406-119">"\otimes"</span></span>
- <span data-ttu-id="9d406-120">"{"</span><span class="sxs-lookup"><span data-stu-id="9d406-120">"{"</span></span>
- <span data-ttu-id="9d406-121">"}"</span><span class="sxs-lookup"><span data-stu-id="9d406-121">"}"</span></span>
- <span data-ttu-id="9d406-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="9d406-122">"\text"</span></span>
- <span data-ttu-id="9d406-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="9d406-123">"\phi"</span></span>
- <span data-ttu-id="9d406-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="9d406-124">"\kappa"</span></span>
- <span data-ttu-id="9d406-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="9d406-125">"\psi"</span></span>
- <span data-ttu-id="9d406-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="9d406-126">"\alpha"</span></span>
- <span data-ttu-id="9d406-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="9d406-127">"\beta"</span></span>
- <span data-ttu-id="9d406-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="9d406-128">"\gamma"</span></span>
- <span data-ttu-id="9d406-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="9d406-129">"\delta"</span></span>
- <span data-ttu-id="9d406-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="9d406-130">"\omega"</span></span>
- <span data-ttu-id="9d406-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="9d406-131">"\bra"</span></span>
- <span data-ttu-id="9d406-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="9d406-132">"\ket"</span></span>
- <span data-ttu-id="9d406-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="9d406-133">"\boldone"</span></span>
- <span data-ttu-id="9d406-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="9d406-134">"\\\\"</span></span>
- <span data-ttu-id="9d406-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="9d406-135">"\\"</span></span>
- <span data-ttu-id="9d406-136">"="</span><span class="sxs-lookup"><span data-stu-id="9d406-136">"="</span></span>
- <span data-ttu-id="9d406-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="9d406-137">"\frac"</span></span>
- <span data-ttu-id="9d406-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="9d406-138">"\text"</span></span>
- <span data-ttu-id="9d406-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="9d406-139">"\mapsto"</span></span>
- <span data-ttu-id="9d406-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="9d406-140">"\dagger"</span></span>
- <span data-ttu-id="9d406-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="9d406-141">"\to"</span></span>
- <span data-ttu-id="9d406-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="9d406-142">"\begin{cases}"</span></span>
- <span data-ttu-id="9d406-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="9d406-143">"\end{cases}"</span></span>
- <span data-ttu-id="9d406-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="9d406-144">"\operatorname"</span></span>
- <span data-ttu-id="9d406-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="9d406-145">"\braket"</span></span>
- <span data-ttu-id="9d406-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="9d406-146">"\id"</span></span>
- <span data-ttu-id="9d406-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="9d406-147">"\expect"</span></span>
- <span data-ttu-id="9d406-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="9d406-148">"\defeq"</span></span>
- <span data-ttu-id="9d406-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="9d406-149">"\variance"</span></span>
- <span data-ttu-id="9d406-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="9d406-150">"\dd"</span></span>
- <span data-ttu-id="9d406-151">"&"</span><span class="sxs-lookup"><span data-stu-id="9d406-151">"&"</span></span>
- <span data-ttu-id="9d406-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="9d406-152">"\begin{align}"</span></span>
- <span data-ttu-id="9d406-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="9d406-153">"\end{align}"</span></span>
- <span data-ttu-id="9d406-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="9d406-154">"\Lambda"</span></span>
- <span data-ttu-id="9d406-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="9d406-155">"\lambda"</span></span>
- <span data-ttu-id="9d406-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="9d406-156">"\Omega"</span></span>
- <span data-ttu-id="9d406-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="9d406-157">"\mathrm"</span></span>
- <span data-ttu-id="9d406-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="9d406-158">"\left"</span></span>
- <span data-ttu-id="9d406-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="9d406-159">"\right"</span></span>
- <span data-ttu-id="9d406-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="9d406-160">"\qquad"</span></span>
- <span data-ttu-id="9d406-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="9d406-161">"\times"</span></span>
- <span data-ttu-id="9d406-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="9d406-162">"\big"</span></span>
- <span data-ttu-id="9d406-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="9d406-163">"\langle"</span></span>
- <span data-ttu-id="9d406-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="9d406-164">"\rangle"</span></span>
- <span data-ttu-id="9d406-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="9d406-165">"\bigg"</span></span>
- <span data-ttu-id="9d406-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="9d406-166">"\Big"</span></span>
- <span data-ttu-id="9d406-167">"|"</span><span class="sxs-lookup"><span data-stu-id="9d406-167">"|"</span></span>
- <span data-ttu-id="9d406-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="9d406-168">"\mathbb"</span></span>
- <span data-ttu-id="9d406-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="9d406-169">"\vec"</span></span>
- <span data-ttu-id="9d406-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="9d406-170">"\in"</span></span>
- <span data-ttu-id="9d406-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="9d406-171">"\texttt"</span></span>
- <span data-ttu-id="9d406-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="9d406-172">"\ne"</span></span>
- <span data-ttu-id="9d406-173">"<"</span><span class="sxs-lookup"><span data-stu-id="9d406-173">"<"</span></span>
- <span data-ttu-id="9d406-174">">"</span><span class="sxs-lookup"><span data-stu-id="9d406-174">">"</span></span>
- <span data-ttu-id="9d406-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="9d406-175">"\leq"</span></span>
- <span data-ttu-id="9d406-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="9d406-176">"\geq"</span></span>
- <span data-ttu-id="9d406-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="9d406-177">"~~"</span></span>
- <span data-ttu-id="9d406-178">"~"</span><span class="sxs-lookup"><span data-stu-id="9d406-178">"~"</span></span>
- <span data-ttu-id="9d406-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="9d406-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="9d406-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="9d406-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="9d406-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="9d406-181">"\_"</span></span>

---

# <a name="multiple-qubits"></a><span data-ttu-id="9d406-182">多個量子位</span><span class="sxs-lookup"><span data-stu-id="9d406-182">Multiple Qubits</span></span>

<span data-ttu-id="9d406-183">雖然單一量子位的閘道具有一些可直覺性的功能，例如在指定時間處於一個以上狀態的能力，但如果在量子電腦中只有一部量子位的閘道，則會有一個裝置具有運算能力，即使計算機只允許一個傳統的超級電腦。</span><span class="sxs-lookup"><span data-stu-id="9d406-183">While single-qubit gates possess some counter-intuitive features, such as the ability to be in more than one state at a given time, if all we had in a quantum computer were single-qubit gates then we would have a device with computational power that would be dwarfed by even a calculator let alone a classical supercomputer.</span></span>
<span data-ttu-id="9d406-184">當我們增加量子位數目時，量子運算的真正威力就變得很明顯。</span><span class="sxs-lookup"><span data-stu-id="9d406-184">The true power of quantum computing only becomes evident as we increase the number of qubits.</span></span>
<span data-ttu-id="9d406-185">這種電源有一部分，因為量子狀態向量的向量空間維度會以量子位的數目以指數方式成長。</span><span class="sxs-lookup"><span data-stu-id="9d406-185">This power arises, in part, because the dimension of the vector space of quantum state vectors grows exponentially with the number of qubits.</span></span>
<span data-ttu-id="9d406-186">這表示，雖然單一量子位可以完整模型化，但是模擬50量子位的量子計算可能會推送現有超級電腦的限制。</span><span class="sxs-lookup"><span data-stu-id="9d406-186">This means that while a single qubit can be trivially modeled, simulating a fifty-qubit quantum computation would arguably push the limits of existing supercomputers.</span></span>
<span data-ttu-id="9d406-187">只有一個額外的量子位增加計算的大小會使儲存狀態所需的記憶體 *加倍* ，而且大約會將計算時間 *加倍* 。</span><span class="sxs-lookup"><span data-stu-id="9d406-187">Increasing the size of the computation by only one additional qubit *doubles* the memory required to store the state and roughly *doubles* the computational time.</span></span>
<span data-ttu-id="9d406-188">這種快速的運算能力，就是為什麼具有相對較少量子位的量子電腦，可能會超越某些計算工作最強大的超級電腦。</span><span class="sxs-lookup"><span data-stu-id="9d406-188">This rapid doubling of computational power is why a quantum computer with a relatively small number of qubits can far surpass the most powerful supercomputers of today, tomorrow and beyond for some computational tasks.</span></span>

<span data-ttu-id="9d406-189">為什麼量子狀態向量的指數成長為何？</span><span class="sxs-lookup"><span data-stu-id="9d406-189">Why do we have exponential growth for quantum state vectors?</span></span>  <span data-ttu-id="9d406-190">本節的目標是要探討用來在單一量子位狀態下建立多量子位狀態的規則，以及討論我們必須在閘道集中包含的閘道作業，以形成通用的多量子位量子電腦。</span><span class="sxs-lookup"><span data-stu-id="9d406-190">Our goal in this section is to review the rules used to build multi-qubit states out of single-qubit states as well as discuss the gate operations that we need to include in our gate set to form a universal many-qubit quantum computer.</span></span>
<span data-ttu-id="9d406-191">這些工具絕對需要瞭解程式碼中常用的閘道集 Q# ，也可讓您直覺有關量子效果（例如纏結或干擾）呈現量子運算比傳統運算更強大的原因。</span><span class="sxs-lookup"><span data-stu-id="9d406-191">These tools are absolutely necessary to understand the gate sets that are commonly used in Q# code and also to gain intuition about why quantum effects such as entanglement or interference render quantum computing more powerful than classical computing.</span></span>

## <a name="representing-two-qubits"></a><span data-ttu-id="9d406-192">表示兩個量子位</span><span class="sxs-lookup"><span data-stu-id="9d406-192">Representing Two Qubits</span></span>
<span data-ttu-id="9d406-193">一種和雙量子位狀態之間的主要差異，在於兩個量子位的狀態是四個維度而不是兩個維度。</span><span class="sxs-lookup"><span data-stu-id="9d406-193">The main difference between one- and two-qubit states is that two-qubit states are four dimensional rather than two dimensional.</span></span>
<span data-ttu-id="9d406-194">這是因為兩個量子位狀態的計算基礎是由一量子位狀態的 tensor 產品所組成。</span><span class="sxs-lookup"><span data-stu-id="9d406-194">This is because the computational basis for two-qubit states is formed by the tensor products of one-qubit states.</span></span>  <span data-ttu-id="9d406-195">例如，我們有 \begin{align}</span><span class="sxs-lookup"><span data-stu-id="9d406-195">For example, we have \begin{align}</span></span>
<span data-ttu-id="9d406-196">00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} 、 \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} 、\\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-196">00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} &= \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix},\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\</span></span>
<span data-ttu-id="9d406-197">10 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 0 0 \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ 1 \\\\ 0 \end{bmatrix} 、 \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 0 0 0 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ 1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="9d406-197">10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} &= \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix},\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="9d406-198">很容易看出，n 量子位的量子狀態通常是以 $ $ 維度 2 ^ n 的單位向量（ $ $ 使用此結構）來表示。</span><span class="sxs-lookup"><span data-stu-id="9d406-198">It is easy to see that more generally the quantum state of $n$ qubits is represented by a unit vector of dimension $2^n$ using this construction.</span></span>  <span data-ttu-id="9d406-199">向量</span><span class="sxs-lookup"><span data-stu-id="9d406-199">The vector</span></span>

$$
<span data-ttu-id="9d406-200">\begin{bmatrix}\alpha _{ 00 } 01 \\\\ 10 \alpha_ { } \\\\ \alpha _{ 11 } \\\\ \alpha_ { }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-200">\begin{bmatrix} \alpha_{00} \\\\  \alpha_{01} \\\\  \alpha_{10} \\\\  \alpha_{11} \end{bmatrix}</span></span>
$$

<span data-ttu-id="9d406-201">表示在兩個量子位上的量子狀態（如果 $ | \alpha _{ 00 } | ^ 2 + | \alpha_ { 01 } | ^ 2 + | \alpha _{ 10 } | ^ 2 + | \alpha_ { 11 } | ^ 2 1） = $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-201">represents a quantum state on two qubits if $|\alpha_{00}|^2+|\alpha_{01}|^2+|\alpha_{10}|^2+|\alpha_{11}|^2=1$.</span></span> <span data-ttu-id="9d406-202">如同單一量子位，多個量子位的量子狀態向量會保存描述系統行為所需的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="9d406-202">Just as with single qubits, the quantum state vector of multiple qubits holds all the information needed to describe the system's behavior.</span></span>

<span data-ttu-id="9d406-203">如果我們提供兩個不同的量子位，其中一個處於狀態， $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ 而第二個量子位處於狀態 $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ ，則對應的雙量子位狀態為    </span><span class="sxs-lookup"><span data-stu-id="9d406-203">If we are given two separate qubits, one in the state $\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ and a second qubit in the state  $\begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}$, the corresponding two-qubit state is</span></span>

$$
<span data-ttu-id="9d406-204">\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-204">\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}</span></span> 
<span data-ttu-id="9d406-205">=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-205">=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}</span></span>
<span data-ttu-id="9d406-206">= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$</span><span class="sxs-lookup"><span data-stu-id="9d406-206">= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$</span></span>

<span data-ttu-id="9d406-207">其中的作業 $ \otimes $ 稱為 tensor product (或 Kronecker product) 的向量。</span><span class="sxs-lookup"><span data-stu-id="9d406-207">where the operation $\otimes$ is called the tensor product (or Kronecker product) of vectors.</span></span> <span data-ttu-id="9d406-208">請注意，雖然我們可以一律讓兩個單一量子位狀態的 tensor 產品形成雙量子位狀態，但並非所有的雙量子位量子狀態都可以撰寫為兩個單一 tensor 狀態的量子位產品。</span><span class="sxs-lookup"><span data-stu-id="9d406-208">Note that while we can always take the tensor product of two single-qubit states to form a two-qubit state, not all two-qubit quantum states can be written as the tensor product of two single-qubit states.</span></span>
<span data-ttu-id="9d406-209">例如，沒有任何狀態，因此 $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ 其 tensor 產品是狀態    </span><span class="sxs-lookup"><span data-stu-id="9d406-209">For example, there are no states $\psi=\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix}$ and $\phi=\begin{bmatrix} \gamma \\\\  \delta \end{bmatrix}$ such that their tensor product is the state</span></span> 

<span data-ttu-id="9d406-210">$$\psi\otimes\phi = \begin{bmatrix}1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="9d406-210">$$\psi\otimes \phi = \begin{bmatrix} 1/\sqrt{2} \\\\  0 \\\\  0 \\\\  1/\sqrt{2} \end{bmatrix}.$$</span></span> 

<span data-ttu-id="9d406-211">這種量子位狀態（無法撰寫為單一量子位狀態的 tensor 產品）稱為「纏結狀態」;這兩個量子位稱為「 [*纏結*](https://en.wikipedia.org/wiki/Quantum_entanglement)」。</span><span class="sxs-lookup"><span data-stu-id="9d406-211">Such a two-qubit state, which cannot be written as the tensor product of single-qubit states, is called an "entangled state"; the two qubits are said to be [*entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).</span></span>  <span data-ttu-id="9d406-212">鬆散說，因為量子狀態無法被視為單一量子位狀態的 tensor 產品，所以狀態保留的資訊並不會個別局限于量子位的其中一個。</span><span class="sxs-lookup"><span data-stu-id="9d406-212">Loosely speaking, because the quantum state cannot be thought of as a tensor product of single qubit states, the information that the state holds is not confined to either of the qubits individually.</span></span>  <span data-ttu-id="9d406-213">相反地，此資訊會以非本機方式儲存在這兩個狀態之間的相互關聯中。</span><span class="sxs-lookup"><span data-stu-id="9d406-213">Rather, the information is stored non-locally in the correlations between the two states.</span></span>  <span data-ttu-id="9d406-214">這種非區域資訊是在傳統運算上的量子運算的主要區別功能之一，也是許多量子通訊協定（包括 [量子遙傳](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) 和 [量子錯誤修正](xref:microsoft.quantum.libraries.error-correction)）不可或缺的功能。</span><span class="sxs-lookup"><span data-stu-id="9d406-214">This non-locality of information is one of the major distinguishing features of quantum computing over classical computing and is essential for a number of quantum protocols including [quantum teleportation](https://github.com/microsoft/Quantum/tree/main/samples/getting-started/teleportation) and [quantum error correction](xref:microsoft.quantum.libraries.error-correction).</span></span>

## <a name="measuring-two-qubit-states"></a><span data-ttu-id="9d406-215">測量 Two-Qubit 狀態</span><span class="sxs-lookup"><span data-stu-id="9d406-215">Measuring Two-Qubit States</span></span> ##
<span data-ttu-id="9d406-216">測量兩個量子位的狀態非常類似于單一量子位測量。</span><span class="sxs-lookup"><span data-stu-id="9d406-216">Measuring two-qubit states is very similar to single-qubit measurements.</span></span> <span data-ttu-id="9d406-217">測量狀態</span><span class="sxs-lookup"><span data-stu-id="9d406-217">Measuring the state</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="9d406-218">\alpha_{ 00 } 01 \\\\ \alpha_ { }\\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-218">\alpha_{00} \\\\ \alpha_{01} \\\\</span></span> 
        <span data-ttu-id="9d406-219">\alpha_{ 10 } 11 \\\\ \alpha_ {}</span><span class="sxs-lookup"><span data-stu-id="9d406-219">\alpha_{10} \\\\ \alpha_{11}</span></span>
    \end{bmatrix}
$$

<span data-ttu-id="9d406-220">會 $ 產生 $ 具有機率 $ | \alpha _{ 00 } | ^ 2 $ 、 $ $ 01 $ 、 | 機率 \alpha_ 為 { 01 } | ^ 2、10（機率 $ $ $ 為 $ | \alpha _{ 10 ^ 2） } | $ 和 $ 11 $ （機率 $ 為 | 11 \alpha_ { } | ^ 2 $ ）的00。</span><span class="sxs-lookup"><span data-stu-id="9d406-220">yields $00$ with probability $|\alpha_{00}|^2$, $01$ with probability $|\alpha_{01}|^2$, $10$ with probability $|\alpha_{10}|^2$, and $11$ with probability $|\alpha_{11}|^2$.</span></span> <span data-ttu-id="9d406-221">已刻意將變數 $ \alpha _{ 00 } 、 \alpha_ { 01 } 、 \alpha _{ 10 } $ 和 $ 11 \alpha_ { } $ 命名為清除此連接。</span><span class="sxs-lookup"><span data-stu-id="9d406-221">The variables $\alpha_{00}, \alpha_{01}, \alpha_{10},$ and $\alpha_{11}$ were deliberately named to make this connection clear.</span></span> <span data-ttu-id="9d406-222">在測量之後，如果結果為00，則 $ $ 雙量子位系統的量子狀態已折迭，而且現在是</span><span class="sxs-lookup"><span data-stu-id="9d406-222">After the measurement, if the outcome is $00$ then the quantum state of the two-qubit system has collapsed and is now</span></span>

$$
    <span data-ttu-id="9d406-223">演講 \equiv</span><span class="sxs-lookup"><span data-stu-id="9d406-223">00 \equiv</span></span>
    \begin{bmatrix}
        <span data-ttu-id="9d406-224">1 \\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-224">1 \\\\</span></span> 
        <span data-ttu-id="9d406-225">0 \\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-225">0 \\\\</span></span> 
        <span data-ttu-id="9d406-226">0 \\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-226">0 \\\\</span></span> 
        <span data-ttu-id="9d406-227">0 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="9d406-227">0 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="9d406-228">您也可以只測量一個雙量子位量子狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="9d406-228">It is also possible to measure just one qubit of a two-qubit quantum state.</span></span> <span data-ttu-id="9d406-229">如果您只測量其中一個量子位，測量的影響會稍微不同，因為整個狀態不會折迭為計算基礎狀態，而是只會折迭為一個子系統。</span><span class="sxs-lookup"><span data-stu-id="9d406-229">In cases where you measure only one of the qubits, the impact of measurement is subtly different because the entire state is not collapsed to a computational basis state, rather it is collapsed to only one sub-system.</span></span>  <span data-ttu-id="9d406-230">換句話說，在這種情況下，只會測量一個量子位，而不是全部的子系統。</span><span class="sxs-lookup"><span data-stu-id="9d406-230">In other words, in such cases measuring only one qubit only collapses one of the subsystems but not all of them.</span></span>  

<span data-ttu-id="9d406-231">若要瞭解這一點，請考慮測量下列狀態的第一個量子位，其形成方式是 $ $ 在兩個量子位上套用 Hadamard 轉換 H （最初設定為 "0" 狀態）： $$</span><span class="sxs-lookup"><span data-stu-id="9d406-231">To see this consider measuring the first qubit of the following state, which is formed by applying the Hadamard transform $H$ on two qubits initially set to the "0" state: $$</span></span>
<span data-ttu-id="9d406-232">H ^ 2 ( 1 0 1 0) 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1-1-1 1 0 0 0 1 2 1 1 1 1 1 1 2 1 2 1 2 1 1 1 1 1 1 1 { \otimes } \left \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \right = \frac { } { } \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} = \frac { } { } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { } = & \frac { } { \sqrt { 2 } } \begin{bmatrix} 1 2 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{bmatrix} \\\\ \text { 結果 } = 1 & \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 0 \\\\ \\\\ 1 \\\\ 1 \end{bmatrix} \\\\ \end{cases} 。  </span><span class="sxs-lookup"><span data-stu-id="9d406-232">H^{\otimes 2} \left( \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 & -1 & 1 & -1 \\\\ 1 & 1 & -1 & -1 \\\\ 1 & -1 & -1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0\end{bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \mapsto \begin{cases}\text{outcome }=0 & \frac{1}{\sqrt{2}}\begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{outcome }=1 & \frac{1}{\sqrt{2}}\begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\  \end{cases}.</span></span>
$$
<span data-ttu-id="9d406-233">這兩個結果有50% 的機率發生。</span><span class="sxs-lookup"><span data-stu-id="9d406-233">Both outcomes have 50% probability of occurring.</span></span>  <span data-ttu-id="9d406-234">這兩個結果的結果為50% 的機率，這是因為 $ $ $ $ 第一個量子位上的初始量子狀態向量在交換0和1的情況下是不變的。</span><span class="sxs-lookup"><span data-stu-id="9d406-234">The outcome being 50% probability for both can be intuited from the fact that the initial quantum state vector is invariant under swapping $0$ with $1$ on the first qubit.</span></span>

<span data-ttu-id="9d406-235">測量第一個或第二個量子位的數學規則很簡單。</span><span class="sxs-lookup"><span data-stu-id="9d406-235">The mathematical rule for measuring the first or second qubit is simple.</span></span>  <span data-ttu-id="9d406-236">如果我們讓 $ e_k $ 成為 $ { 計算基礎向量的 k ^ \Rm } $ ，並讓 $ S $ 成為所有 e_k 的集合，讓有 $ 問題的 $ 量子位採用值1做 $ $ 為 k 的值 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-236">If we let $e_k$ be the $k^{\rm th}$ computational basis vector and let $S$ be the set of all $e_k$ such that the qubit in question takes the value $1$ for that value of $k$.</span></span>  <span data-ttu-id="9d406-237">例如，如果我們想要測量第一個量子位，則 $ $ 會包含 $ e_1 \equiv 10 $ 和 $ e_3 \equiv 11 $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-237">For example, if we are interested in measuring the first qubit then $S$ would consist of $e_1\equiv 10$ and $e_3\equiv 11$.</span></span>  <span data-ttu-id="9d406-238">同樣地，如果我們對第二個量子位有興趣，則 $ $ 會包含 $ e_2 \equiv 01 $ 和 $ e_3 \equiv 11 $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-238">Similarly, if we are interested in the second qubit $S$ would consist of $e_2\equiv 01$ and $e_3 \equiv 11$.</span></span>  <span data-ttu-id="9d406-239">然後，測量所選量子位為1的機率 $ $ 是針對狀態向量 $\psi$</span><span class="sxs-lookup"><span data-stu-id="9d406-239">Then the probability of measuring the chosen qubit to be $1$ is for state vector $\psi$</span></span>

$$
<span data-ttu-id="9d406-240">P (\text { 結果 } = 1) = \sum _ { e_k \text { 的 } } \psi ^ \dagger e_k e_k ^ \dagger \psi 。</span><span class="sxs-lookup"><span data-stu-id="9d406-240">P(\text{outcome}=1)= \sum_{e_k \text{ in the set } S}\psi^\dagger e_k e_k^\dagger \psi.</span></span>
$$

> [!NOTE]
<span data-ttu-id="9d406-241">> 在這份檔中，我們使用位元組由小到小的格式來標記計算基礎。</span><span class="sxs-lookup"><span data-stu-id="9d406-241">> In this document we are using the little-endian format to label the computational basis.</span></span> <span data-ttu-id="9d406-242">以位元組由小到大的格式來說，最不重要的位會最先出現。</span><span class="sxs-lookup"><span data-stu-id="9d406-242">In little endian format, the least significant bits come first.</span></span> <span data-ttu-id="9d406-243">例如，以位元組由大到小的格式來表示四個數字，以位001的字串表示。</span><span class="sxs-lookup"><span data-stu-id="9d406-243">For example, the number four in little-endian format is represented by the string of bits 001.</span></span>

<span data-ttu-id="9d406-244">因為每個量子位量值只能產生 $ 0 $ 或 $ 1，所以 $ 測量0的機率 $ $ 只是 $ 1-P (\text { 結果 } = 1) $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-244">Since each qubit measurement can only yield $0$ or $1$, the probability of measuring $0$ is simply $1-P(\text{outcome}=1)$.</span></span>  <span data-ttu-id="9d406-245">這就是為什麼我們只針對測量1的機率明確提供公式 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-245">This is why we only explicitly give a formula for the probability of measuring $1$.</span></span>

<span data-ttu-id="9d406-246">這類測量對狀態的動作可以數學表示</span><span class="sxs-lookup"><span data-stu-id="9d406-246">The action that such a measurement has on the state can be expressed mathematically as</span></span>

$$
<span data-ttu-id="9d406-247">\psi\mapsto \frac{\sum_ { e_k \text { 的 } } e_k e_k ^ \dagger \psi } { \sqrt { P (\text { 結果 } = 1) } } 。</span><span class="sxs-lookup"><span data-stu-id="9d406-247">\psi \mapsto \frac{\sum_{e_k \text{ in the set } S} e_k e_k^\dagger \psi}{\sqrt{P(\text{outcome}=1)}}.</span></span>
$$

<span data-ttu-id="9d406-248">謹慎的讀者可能會擔心測量的機率為零時，會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="9d406-248">The cautious reader may worry about what happens when the probability of the measurement is zero.</span></span>  <span data-ttu-id="9d406-249">雖然在這種情況下，結果狀態在技術上是未定義的，但我們永遠不需要擔心這類 eventualities，因為機率為零！</span><span class="sxs-lookup"><span data-stu-id="9d406-249">While the resultant state is technically undefined in this case, we never need to worry about such eventualities because the probability is zero!</span></span>


<span data-ttu-id="9d406-250">如果我們採用 $ \psi $ 上面所提供的統一狀態向量，並且想要測量第一個量子位，</span><span class="sxs-lookup"><span data-stu-id="9d406-250">If we take $\psi$ to be the uniform state vector given above and are interested in measuring the first qubit then</span></span> 

$$
<span data-ttu-id="9d406-251">P (\text { 測量第一個量子位 } = 1) = (\psi ^ \dagger e_1) # B4 e_1 ^ \dagger \psi) + (\psi ^ \dagger e_3) # B8 e_3 ^ \dagger \psi) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2。</span><span class="sxs-lookup"><span data-stu-id="9d406-251">P(\text{measurement of first qubit}=1) = (\psi^\dagger e_1)(e_1^\dagger \psi)+(\psi^\dagger e_3)(e_3^\dagger \psi)=|e_1^\dagger \psi|^2+|e_3^\dagger \psi|^2.</span></span>
$$

<span data-ttu-id="9d406-252">請注意，這只是測量結果10和11所預期的兩個機率的總和 $ ， $ $ 全都是 $ 要測量的量子位。</span><span class="sxs-lookup"><span data-stu-id="9d406-252">Note that this is just the sum of the two probabilities that would be expected for measuring the results $10$ and $11$ were all the qubits to be measured.</span></span>
<span data-ttu-id="9d406-253">在我們的範例中，這會評估為</span><span class="sxs-lookup"><span data-stu-id="9d406-253">For our example, this evaluates to</span></span>

$$
<span data-ttu-id="9d406-254">\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 & 0 1 1 1 \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ 1 \end{bmatrix} \right | ^ 2 + 1 4 0 0 0 1 1 1 1 \frac { } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 = \frac { 1 } { 2 } 。</span><span class="sxs-lookup"><span data-stu-id="9d406-254">\frac{1}{4}\left|\begin{bmatrix}0&0&1&0\end{bmatrix}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right|^2+\frac{1}{4}\left|\begin{bmatrix}0&0&0&1\end{bmatrix}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right|^2=\frac{1}{2}.</span></span>
$$

<span data-ttu-id="9d406-255">這完全符合我們直覺告訴我們機率的結果。</span><span class="sxs-lookup"><span data-stu-id="9d406-255">which perfectly matches what our intuition tells us the probability should be.</span></span>  <span data-ttu-id="9d406-256">同樣地，狀態也可以撰寫為</span><span class="sxs-lookup"><span data-stu-id="9d406-256">Similarly, the state can be written as</span></span>

$$
<span data-ttu-id="9d406-257">\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 } { 2 } } } = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-257">\frac{\frac{e_1}{2}+\frac{e_3}{2}}{\sqrt{\frac{1}{2}}}=\frac{1}{\sqrt{2}}\begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1\end{bmatrix}</span></span>
$$

<span data-ttu-id="9d406-258">同樣地，根據我們的直覺。</span><span class="sxs-lookup"><span data-stu-id="9d406-258">again in accordance with our intuition.</span></span>

## <a name="two-qubit-operations"></a><span data-ttu-id="9d406-259">Two-Qubit 作業</span><span class="sxs-lookup"><span data-stu-id="9d406-259">Two-Qubit Operations</span></span>
<span data-ttu-id="9d406-260">如同在單一量子位案例中，任何單一轉換都是量子位上的有效作業。</span><span class="sxs-lookup"><span data-stu-id="9d406-260">As in the single-qubit case, any unitary transformation is a valid operation on qubits.</span></span> <span data-ttu-id="9d406-261">一般情況下，n 量子位的單一轉換 $ $ 是大小為 $ $ $ 2 ^ n \times 2 ^ n (的矩陣 U， $ 因此它會在大小為 $ 2 ^ n) 的向量上運作 $ ，例如 $ U ^ { -1 } = U ^ \dagger $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-261">In general, a unitary transformation on $n$ qubits is a matrix $U$ of size $2^n \times 2^n$ (so that it acts on vectors of size $2^n$), such that $U^{-1} = U^\dagger$.</span></span>
<span data-ttu-id="9d406-262">例如，CNOT (控制-不) 閘道是常用的雙量子位閘道，並以下列的單一矩陣表示：</span><span class="sxs-lookup"><span data-stu-id="9d406-262">For example, the CNOT (controlled-NOT) gate is a commonly used two-qubit gate and is represented by the following unitary matrix:</span></span>

$$
<span data-ttu-id="9d406-263">\operatorname{CNOT } = \begin{bmatrix} 1 \ 0 \ 0 \ 0  \\\\  0 \ 1 \ 0 \ 0 \\\\  0 0 \ 0 \ 0 \ 1 \\\\  0 \ 0 \ 1 \ 0 \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-263">\operatorname{CNOT} = \begin{bmatrix} 1\ 0\ 0\ 0  \\\\  0\ 1\ 0\ 0 \\\\  0\ 0\ 0\ 1 \\\\  0\ 0\ 1\ 0 \end{bmatrix}</span></span>
$$

<span data-ttu-id="9d406-264">我們也可以在這兩個量子位上套用單一量子位閘道，形成雙量子位的閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-264">We can also form two-qubit gates by applying single-qubit gates on both qubits.</span></span> <span data-ttu-id="9d406-265">例如，如果我們套用閘道</span><span class="sxs-lookup"><span data-stu-id="9d406-265">For example, if we apply the gates</span></span> 

$$
\begin{bmatrix}
<span data-ttu-id="9d406-266">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-266">a\ b\\\\ c\ d \end{bmatrix}</span></span>
$$

<span data-ttu-id="9d406-267">及</span><span class="sxs-lookup"><span data-stu-id="9d406-267">and</span></span>

$$\begin{bmatrix}
<span data-ttu-id="9d406-268">e \ f \\\\ g h h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-268">e\ f\\\\ g\ h \end{bmatrix}</span></span>
$$

<span data-ttu-id="9d406-269">第一個和第二個量子位，這相當於套用 tensor 產品所指定的兩個量子位的單一專案： $$\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-269">to the first and second qubits, respectively, this is equivalent to applying the two-qubit unitary given by their tensor product: $$\begin{bmatrix}</span></span>
<span data-ttu-id="9d406-270">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="9d406-270">a\ b\\\\ c\ d \end{bmatrix}</span></span>
\otimes 
\begin{bmatrix}
<span data-ttu-id="9d406-271">e \ f \\\\ g h h \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="9d406-271">e\ f\\\\ g\ h \end{bmatrix}=</span></span>
    \begin{bmatrix}
    <span data-ttu-id="9d406-272">ae \ af \ bf \\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-272">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="9d406-273">ag \ ah \ bg \ bh \\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-273">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="9d406-274">ce \ cf \ de \ df \\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-274">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="9d406-275">cg \ ch \ dg \ dh \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="9d406-275">cg\ ch\ dg\ dh \end{bmatrix}.$$</span></span>
<span data-ttu-id="9d406-276">因此，我們可以採用一些已知單一量子位閘道的 tensor 產品，形成雙量子位的閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-276">Thus we can form two-qubit gates by taking the tensor product of some known single-qubit gates.</span></span> <span data-ttu-id="9d406-277">雙量子位管制的一些範例包括 $ h \otimes h $ 、 $ x \otimes \boldone $ 和 $ x \otimes Z $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-277">Some examples of two-qubit gates include $H \otimes H$, $X \otimes \boldone$, and $X \otimes Z$.</span></span>

<span data-ttu-id="9d406-278">請注意，雖然任何兩個單一量子位的閘道都是藉由取得 tensor 產品來定義雙量子位的閘道，但反向的情況並不成立。</span><span class="sxs-lookup"><span data-stu-id="9d406-278">Note that while any two single-qubit gates define a two-qubit gate by taking their tensor product, the converse is not true.</span></span> <span data-ttu-id="9d406-279">並非所有的雙量子位閘道都可以撰寫成單一量子位閘道的 tensor 產品。</span><span class="sxs-lookup"><span data-stu-id="9d406-279">Not all two-qubit gates can be written as the tensor product of single-qubit gates.</span></span>  <span data-ttu-id="9d406-280">這類閘道稱為 *entangling* 閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-280">Such a gate is called an *entangling* gate.</span></span> <span data-ttu-id="9d406-281">Entangling 閘道的其中一個範例是 CNOT 閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-281">One example of an entangling gate is the CNOT gate.</span></span>

<span data-ttu-id="9d406-282">受控制-非閘道後方的直覺可一般化至任意的閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-282">The intuition behind a controlled-not gate can be generalized to arbitrary gates.</span></span>  <span data-ttu-id="9d406-283">一般而言，受控制的閘道是做為身分識別 (ie 除非特定量子位為1，否則不會有任何動作) $ $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-283">A controlled gate in general is a gate that acts as identity (ie it has no action) unless a specific qubit is $1$.</span></span>  <span data-ttu-id="9d406-284">在此案例中，我們會針對標示為 x 的量子位來代表受控制的單一控制項， $ $ 其中 $ \Lambda \_ x (U) $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-284">We denote a controlled unitary, controlled in this case on the qubit labeled $x$, with a $\Lambda\_x(U)$.</span></span>  <span data-ttu-id="9d406-285">例如 $ \Lambda _0 (U) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ 和 $ \Lambda \_ 0 (U) e \_ { 0 } \otimes { \psi } = e \_ { 0 } \otimes { \psi } $ ，其中 $ e \_ 0 $ 和 $ e \_ 1 $ 是對應至值 $ 0 $ 和1之單一量子位的計算基礎向量 $ $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-285">As an example $\Lambda_0(U) e\_{1}\otimes {\psi}=e\_{1}\otimes U{\psi}$ and $\Lambda\_0(U) e\_{0}\otimes {\psi}=e\_{0}\otimes{\psi}$, where $e\_0$ and $e\_1$ are the computational basis vectors for a single qubit corresponding to the values $0$ and $1$.</span></span>  <span data-ttu-id="9d406-286">例如，請考慮下列受控制的 $ z 網 $ 關，我們可以將其表示為 $$</span><span class="sxs-lookup"><span data-stu-id="9d406-286">For example, consider the following controlled-$Z$ gate then we can express this as $$</span></span>
<span data-ttu-id="9d406-287">\Lambda\_0 (Z) 1 0 0 0 0 1 0 0 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & 1 0 0 0 0 & \\\\ & & & -1 \end{bmatrix} = (\boldone \otimes H) \operatorname { CNOT } (\boldone \otimes H) 。</span><span class="sxs-lookup"><span data-stu-id="9d406-287">\Lambda\_0(Z)= \begin{bmatrix}1&0&0&0\\\\0&1&0&0\\\\0&0&1&0\\\\0&0&0&-1 \end{bmatrix}=(\boldone\otimes H)\operatorname{CNOT}(\boldone\otimes H).</span></span>
$$

<span data-ttu-id="9d406-288">以有效率的方式建立控制的 unitaries 是一項重大挑戰。</span><span class="sxs-lookup"><span data-stu-id="9d406-288">Building controlled unitaries in an efficient manner is a major challenge.</span></span>  <span data-ttu-id="9d406-289">執行這項作業的最簡單方式，就是形成基礎閘道的控制版本資料庫，並以其控制的對應項取代原始單一作業中的每個基本閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-289">The simplest way to implement this requires forming a database of controlled versions of fundamental gates and replacing every fundamental gate in the original unitary operation with its controlled counterpart.</span></span>  <span data-ttu-id="9d406-290">這通常是相當浪費的工作，而且聰明的深入解析通常可以用來將幾個閘道取代為受控制的版本，以達成相同的影響。</span><span class="sxs-lookup"><span data-stu-id="9d406-290">This is often quite wasteful and clever insight often can be used to just replace a few gates with controlled versions to achieve the same impact.</span></span>  <span data-ttu-id="9d406-291">基於這個理由，我們在架構中提供的功能，就是在已知優化的手動調整版本時，執行控制或允許使用者定義受控制版本的單一方法。</span><span class="sxs-lookup"><span data-stu-id="9d406-291">For this reason, we provide in our framework the ability to perform either the naive method of controlling or allow the user to define a controlled version of the unitary if an optimized hand-tuned version is known.</span></span>

<span data-ttu-id="9d406-292">閘道也可以使用傳統資訊來控制。</span><span class="sxs-lookup"><span data-stu-id="9d406-292">Gates can also be controlled using classical information.</span></span>  <span data-ttu-id="9d406-293">例如，傳統方式控制的非閘道只是一般的非閘道，但只有在傳統位是 $ 1 而不是量子位時才適用 $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-293">A classically controlled not-gate, for example, is just an ordinary not-gate but it is only applied if a classical bit is $1$ as opposed to a quantum bit.</span></span>  <span data-ttu-id="9d406-294">在這種情況下，傳統方式控制的閘道可視為量副程式代碼中的 if 語句，其中的閘道只會在程式碼的一個分支中套用。</span><span class="sxs-lookup"><span data-stu-id="9d406-294">In this sense, a classically controlled gate can be thought of as an if statement in the quantum code wherein the gate is applied only in one branch of the code.</span></span>


<span data-ttu-id="9d406-295">如同在單一量子位案例中，如果有任何 $ 4 \times 個 $ 單一矩陣可將此集合中的閘道乘積設定為任意有效位數，則雙量子位閘道集會設定為通用。</span><span class="sxs-lookup"><span data-stu-id="9d406-295">As in the single-qubit case, a two-qubit gate set is universal if any $4\times 4$ unitary matrix can be approximated by a product of gates from this set to arbitrary precision.</span></span>
<span data-ttu-id="9d406-296">通用閘道集合的其中一個範例是 Hadamard 閘道、T 閘道和 CNOT 閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-296">One example of a universal gate set is the Hadamard gate, the T gate, and the CNOT gate.</span></span> <span data-ttu-id="9d406-297">藉由取得這些閘道的產品，我們可以將兩個量子位上的任何單一矩陣近似。</span><span class="sxs-lookup"><span data-stu-id="9d406-297">By taking products of these gates, we can approximate any unitary matrix on two qubits.</span></span>

## <a name="many-qubit-systems"></a><span data-ttu-id="9d406-298">Many-Qubit 系統</span><span class="sxs-lookup"><span data-stu-id="9d406-298">Many-Qubit Systems</span></span>
<span data-ttu-id="9d406-299">我們會遵循在兩個量子位案例中所探索到的相同模式，從較小的系統建立多量子位的量子狀態。</span><span class="sxs-lookup"><span data-stu-id="9d406-299">We follow exactly the same patterns explored in the two-qubit case to build many-qubit quantum states from smaller systems.</span></span>  <span data-ttu-id="9d406-300">這種狀態的建立方式是形成較小狀態的 tensor 產品。</span><span class="sxs-lookup"><span data-stu-id="9d406-300">Such states are built by forming tensor products of smaller states.</span></span>  <span data-ttu-id="9d406-301">例如，請考慮 $ $ 在量子電腦中編碼位字串1011001。</span><span class="sxs-lookup"><span data-stu-id="9d406-301">For example, consider encoding the bit string $1011001$ in a quantum computer.</span></span>  <span data-ttu-id="9d406-302">我們可以將此編碼為</span><span class="sxs-lookup"><span data-stu-id="9d406-302">We can encode this as</span></span>

$$
<span data-ttu-id="9d406-303">1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="9d406-303">1011001 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="9d406-304">量子閘道的運作方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="9d406-304">Quantum gates work in exactly the same way.</span></span>  <span data-ttu-id="9d406-305">例如，如果我們想要將 X 網 $ $ 關套用至第一個量子位，然後在第二個和第三個量子位之間執行 CNOT，我們可以將這種轉換表達為</span><span class="sxs-lookup"><span data-stu-id="9d406-305">For example, if we wish to apply the $X$ gate to the first qubit and then perform a CNOT between the second and third qubits we may express this transformation as</span></span>

\begin{align}
<span data-ttu-id="9d406-306">& (X \otimes \operatorname { CNOT } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 1 0 1 0 0 1\end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="9d406-306">&(X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\  1 \end{bmatrix}\\\\</span></span>
<span data-ttu-id="9d406-307">&\qquad\qquad\equiv 0011001。 \end{align}</span><span class="sxs-lookup"><span data-stu-id="9d406-307">&\qquad\qquad\equiv 0011001. \end{align}</span></span>

<span data-ttu-id="9d406-308">在許多量子位系統中，通常需要配置和解除配置作為量子電腦暫存記憶體的量子位。</span><span class="sxs-lookup"><span data-stu-id="9d406-308">In many qubit systems, there is often a need to allocate and deallocate qubits that serve as temporary memory for the quantum computer.</span></span>  <span data-ttu-id="9d406-309">這類量子位稱為 ancilla。</span><span class="sxs-lookup"><span data-stu-id="9d406-309">Such a qubit is called an ancilla.</span></span>  <span data-ttu-id="9d406-310">根據預設，我們假設量子位狀態會在 $ 配置時初始化為 e_0 $ 。</span><span class="sxs-lookup"><span data-stu-id="9d406-310">By default we assume the qubit state is initialized to $e_0$ upon allocation.</span></span>  <span data-ttu-id="9d406-311">我們會進一步假設在 $ $ 解除配置之前再次傳回 e_0。</span><span class="sxs-lookup"><span data-stu-id="9d406-311">We further assume that it is returned again to $e_0$ before deallocation.</span></span>  <span data-ttu-id="9d406-312">這項假設很重要，因為如果 ancilla 量子位在解除配置時，與另一個量子位暫存器變成纏結，解除配置的程式將會損毀 ancilla。</span><span class="sxs-lookup"><span data-stu-id="9d406-312">This assumption is important because if an ancilla qubit becomes entangled with another qubit register when it becomes deallocated then the process of deallocation will damage the ancilla.</span></span>  <span data-ttu-id="9d406-313">基於這個理由，我們一定會假設這類量子位會在發行前還原為其初始狀態。</span><span class="sxs-lookup"><span data-stu-id="9d406-313">For this reason, we always assume that such qubits are reverted to their initial state before being released.</span></span>

<span data-ttu-id="9d406-314">最後，雖然需要將新的閘道新增至閘道，以達成兩個量子位量子電腦的通用量子運算，但是在多量子位的情況下，不需要引進任何新的閘道。</span><span class="sxs-lookup"><span data-stu-id="9d406-314">Finally, although new gates needed to be added to our gate set to achieve universal quantum computing for two qubit quantum computers, no new gates need to be introduced in the multi-qubit case.</span></span>  <span data-ttu-id="9d406-315">閘道 $ H $ 、 $ T $ 和 CNOT 形成許多量子位上的通用閘道，因為任何一般的單一轉換都可分成一系列的兩個量子位旋轉。</span><span class="sxs-lookup"><span data-stu-id="9d406-315">The gates $H$, $T$ and CNOT form a universal gate set on many qubits because any general unitary transformation can be broken into a series of two qubit rotations.</span></span>  <span data-ttu-id="9d406-316">接著，我們可以利用針對兩個量子位案例開發的理論，並在有許多量子位的情況下再次使用它。</span><span class="sxs-lookup"><span data-stu-id="9d406-316">We then can leverage the theory developed for the two-qubit case and use it again here when we have many qubits.</span></span>

<span data-ttu-id="9d406-317">雖然我們使用到目前為止的線性代數標記法可以用來描述多量子位的狀態，但隨著我們增加狀態的大小，就會變得越來越繁瑣。</span><span class="sxs-lookup"><span data-stu-id="9d406-317">While the linear algebraic notation that we have been using thus far can certainly be used to describe multi-qubit states, it becomes increasingly cumbersome as we increase the size of the states.</span></span>  <span data-ttu-id="9d406-318">例如，針對長度為7位字串所產生的資料行向量為 $ 128 $ 維度，這會使用先前所述的標記法來表示它。</span><span class="sxs-lookup"><span data-stu-id="9d406-318">The resulting column-vector for a length 7 bit string, for example, is $128$ dimensional, which makes expressing it using the notation described previously very cumbersome.</span></span>  <span data-ttu-id="9d406-319">基於這個理由，我們接下來會在量子運算中呈現常見的標記法，讓我們可以簡要地描述這些高維度的向量。</span><span class="sxs-lookup"><span data-stu-id="9d406-319">For this reason, we next present a common notation in quantum computing that allows us to concisely describe these high-dimensional vectors.</span></span>
