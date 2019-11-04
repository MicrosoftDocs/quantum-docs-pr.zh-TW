---
title: 量子線路 |Microsoft Docs
description: 量子線路
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210599"
---
# <a name="quantum-circuits"></a><span data-ttu-id="35a5c-103">量子線路</span><span class="sxs-lookup"><span data-stu-id="35a5c-103">Quantum Circuits</span></span>
<span data-ttu-id="35a5c-104">請思考一下單一轉換 $ \text{CNOT-CONTAINS} _{01}（H\otimes 1） $。</span><span class="sxs-lookup"><span data-stu-id="35a5c-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="35a5c-105">此閘道序列對量子運算的基本重要性，因為它會建立最常光子二 qubit 的狀態：</span><span class="sxs-lookup"><span data-stu-id="35a5c-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="35a5c-106">$ $ \mathrm{CNOT}_{01}（H\otimes 1） \ket{00} = \frac{1}{\sqrt{2}} \left （\ket{00} + \ket{11} \right），$ $</span><span class="sxs-lookup"><span data-stu-id="35a5c-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="35a5c-107">具有此或更大複雜度的作業在配量演算法和量子錯誤更正中是普遍的，因此，它應該是一個簡單的視覺效果方法，稱為配量*線路圖*。</span><span class="sxs-lookup"><span data-stu-id="35a5c-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="35a5c-108">準備此最常光子量子狀態的線路圖表如下：</span><span class="sxs-lookup"><span data-stu-id="35a5c-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="35a5c-109">配量線路圖慣例</span><span class="sxs-lookup"><span data-stu-id="35a5c-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="35a5c-110">當您瞭解用來表示配量線路的慣例之後，可以更輕鬆地消化量子作業的視覺化語言，而不是寫下其對等的矩陣。</span><span class="sxs-lookup"><span data-stu-id="35a5c-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="35a5c-111">我們會在下面探討這些慣例。</span><span class="sxs-lookup"><span data-stu-id="35a5c-111">We review these conventions below.</span></span>

<span data-ttu-id="35a5c-112">在電路圖中，每一條實線描述一個 qubit 或更普遍的 qubit 暫存器。</span><span class="sxs-lookup"><span data-stu-id="35a5c-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="35a5c-113">依照慣例，最上方的行會是 qubit register $0 $，其餘部分則會依序標示。</span><span class="sxs-lookup"><span data-stu-id="35a5c-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="35a5c-114">上述的範例電路會在兩個 qubits （或兩個由一個 qubit 組成的暫存器）上描述為作用。</span><span class="sxs-lookup"><span data-stu-id="35a5c-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="35a5c-115">以一個或多個 qubit 暫存器為作用的閘道會以方塊表示。</span><span class="sxs-lookup"><span data-stu-id="35a5c-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="35a5c-116">例如，符號</span><span class="sxs-lookup"><span data-stu-id="35a5c-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="35a5c-117">是作用於單一 qubit 暫存器的[Hadamard](xref:microsoft.quantum.primitive.h)閘道。</span><span class="sxs-lookup"><span data-stu-id="35a5c-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="35a5c-118">配量閘道會按照時間順序排列，並以最左邊的閘道作為第一次套用到 qubits 的閘道。</span><span class="sxs-lookup"><span data-stu-id="35a5c-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="35a5c-119">換句話說，如果您將線路畫成包含配量狀態，則電線會從左至右的圖表中的每個閘道顯示配量狀態。</span><span class="sxs-lookup"><span data-stu-id="35a5c-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="35a5c-120">也就是說</span><span class="sxs-lookup"><span data-stu-id="35a5c-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="35a5c-121">是單一矩陣 $CBA $。</span><span class="sxs-lookup"><span data-stu-id="35a5c-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="35a5c-122">矩陣乘法遵守相反的慣例：第一次套用最右邊的矩陣。</span><span class="sxs-lookup"><span data-stu-id="35a5c-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="35a5c-123">不過，在配量電路圖中，會先套用最左邊的閘道。</span><span class="sxs-lookup"><span data-stu-id="35a5c-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="35a5c-124">這項差異有時可能會造成混淆，因此請務必注意線性代數標記法與配量電路圖之間的顯著差異。</span><span class="sxs-lookup"><span data-stu-id="35a5c-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="35a5c-125">量子線路的輸入和輸出</span><span class="sxs-lookup"><span data-stu-id="35a5c-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="35a5c-126">所有先前的範例都具有與量子閘道相同的線路（qubits）輸入數目，做為配量閘道的線路數目。</span><span class="sxs-lookup"><span data-stu-id="35a5c-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="35a5c-127">一般來說，配量線路可能會有比一般輸入更多或更少的輸出。</span><span class="sxs-lookup"><span data-stu-id="35a5c-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="35a5c-128">不過，這是不可能的，因為所有的量子作業、儲存量測都是單一的，因此可以還原。</span><span class="sxs-lookup"><span data-stu-id="35a5c-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="35a5c-129">如果它們沒有與輸入相同的輸出數目，它們將無法復原，因此不是單一的，這是一項衝突。</span><span class="sxs-lookup"><span data-stu-id="35a5c-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="35a5c-130">基於這個理由，在電路圖中繪製的任何方塊都必須有相同數目的線路進入結束。</span><span class="sxs-lookup"><span data-stu-id="35a5c-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="35a5c-131">多 qubit 的電路圖表會遵循類似的慣例來進行單一 qubit。</span><span class="sxs-lookup"><span data-stu-id="35a5c-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="35a5c-132">做為說明範例，我們可以定義兩個 qubit 的單一作業 $B $ 設為 $ （H S\otimes X） $，並以相同的方式表達電路</span><span class="sxs-lookup"><span data-stu-id="35a5c-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="35a5c-133">我們也可以將 $B $ 視為在單一雙 qubit 暫存器上採取動作，而不是 2 1-qubit 暫存器，視使用電路的內容而定。</span><span class="sxs-lookup"><span data-stu-id="35a5c-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="35a5c-134">這類抽象循環圖表表可能是最有用的屬性，因為它們可讓複雜的量子演算法以高階方式描述，而不需要將它們編譯成基本閘道。</span><span class="sxs-lookup"><span data-stu-id="35a5c-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="35a5c-135">這表示您可以針對大型配量演算法取得資料流程的直覺，而不需要瞭解演算法中每個副程式如何工作的所有詳細資料。</span><span class="sxs-lookup"><span data-stu-id="35a5c-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="35a5c-136">控制的閘道</span><span class="sxs-lookup"><span data-stu-id="35a5c-136">Controlled gates</span></span>
<span data-ttu-id="35a5c-137">另一個內建于多 qubit 配量電路圖的結構是 control。</span><span class="sxs-lookup"><span data-stu-id="35a5c-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="35a5c-138">配量單一控制閘道（表示 $ \Lambda （G） $）的動作，其中單一 qubit 的值會控制 $G $ 的應用程式，您可以查看下列產品狀態輸入 $ \Lambda （G）的範例（\Alpha \ket{0} + \Beta \ket）來瞭解其內容{1}） \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \Beta \ket{1} G\ket {\ psi} $。</span><span class="sxs-lookup"><span data-stu-id="35a5c-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="35a5c-139">也就是說，只有在控制項 qubit 接受值 $1 $ 時，受控制的閘道才會將 $G $ 套用至包含 $ \psi $ 的暫存器。</span><span class="sxs-lookup"><span data-stu-id="35a5c-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="35a5c-140">一般來說，我們會在電路圖中描述這類受控制的作業，如下所示：</span><span class="sxs-lookup"><span data-stu-id="35a5c-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="35a5c-141">在這裡，黑色圓圈代表控制閘道的配量位，而垂直線代表當控制項 qubit 接受值 $1 $ 時所套用的單一。</span><span class="sxs-lookup"><span data-stu-id="35a5c-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="35a5c-142">針對 $G = X $ 且 $G = Z $ 的特殊情況，我們引進了下列標記法來描述控制的閘道版本（請注意，受控制的 X 閘道是[$CNOT $](xref:microsoft.quantum.primitive.cnot)閘道）：</span><span class="sxs-lookup"><span data-stu-id="35a5c-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="35a5c-143">問 # 提供自動產生受控制版本之作業的方法，可讓程式設計人員不必手動撰寫這些作業的程式碼。</span><span class="sxs-lookup"><span data-stu-id="35a5c-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="35a5c-144">範例如下所示：</span><span class="sxs-lookup"><span data-stu-id="35a5c-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="35a5c-145">測量運算子</span><span class="sxs-lookup"><span data-stu-id="35a5c-145">Measurement operator</span></span>
<span data-ttu-id="35a5c-146">要在電路圖中視覺化的其餘作業是測量。</span><span class="sxs-lookup"><span data-stu-id="35a5c-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="35a5c-147">測量會採用 qubit 暫存器、加以測量，然後將結果輸出為傳統資訊。</span><span class="sxs-lookup"><span data-stu-id="35a5c-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="35a5c-148">測量作業是由計量符號表示，且一律會接受 qubit 暫存器的輸入（以實線表示），並輸出傳統資訊（以雙線表示）。</span><span class="sxs-lookup"><span data-stu-id="35a5c-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="35a5c-149">具體而言，這類 subcircuit 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="35a5c-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="35a5c-150">![測量電路](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="35a5c-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="35a5c-151">問 # 會針對此用途來實行[量值運算子](xref:microsoft.quantum.primitive.measure)。</span><span class="sxs-lookup"><span data-stu-id="35a5c-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="35a5c-152">如需詳細資訊，請參閱[測量的一節](xref:microsoft.quantum.libraries.standard.prelude#measurements)。</span><span class="sxs-lookup"><span data-stu-id="35a5c-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="35a5c-153">同樣地，subcircuit</span><span class="sxs-lookup"><span data-stu-id="35a5c-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="35a5c-154">提供受傳統方式控制的閘道，其中 $G $ 會套用至傳統控制位的值 $1 $。</span><span class="sxs-lookup"><span data-stu-id="35a5c-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="35a5c-155">Teleportation 線路圖表</span><span class="sxs-lookup"><span data-stu-id="35a5c-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="35a5c-156">[量子 teleportation](xref:microsoft.quantum.techniques.puttingittogether)可能是用來說明這些元件的最佳量子演算法。</span><span class="sxs-lookup"><span data-stu-id="35a5c-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="35a5c-157">「量子 teleportation」是一種方法，可透過使用會任何牽連和測量，在量子電腦（或甚至是量子網路中的較遠的量子電腦之間）移動資料。</span><span class="sxs-lookup"><span data-stu-id="35a5c-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="35a5c-158">有趣的是，它實際上能夠將量子狀態（也就是指定 qubit 中的值）從一個 qubit 移到另一個，而不用知道 qubit 的值是什麼！</span><span class="sxs-lookup"><span data-stu-id="35a5c-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="35a5c-159">這是通訊協定根據量子機制的法律而必須運作的必要條件。</span><span class="sxs-lookup"><span data-stu-id="35a5c-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="35a5c-160">下面提供量子 teleportation 線路;我們也會提供已標注的電路版本，以說明如何讀取配量線路。</span><span class="sxs-lookup"><span data-stu-id="35a5c-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
