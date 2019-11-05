---
title: '問 # 技巧-全部整合 |Microsoft Docs'
description: 問與答技巧-全部整合在一起
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183262"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="7991f-103">全部放在一起： Teleportation</span><span class="sxs-lookup"><span data-stu-id="7991f-103">Putting it All Together: Teleportation</span></span> #
<span data-ttu-id="7991f-104">讓我們回到配量[線路](xref:microsoft.quantum.concepts.circuits)中所定義之 teleportation 電路的範例。</span><span class="sxs-lookup"><span data-stu-id="7991f-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="7991f-105">我們將使用它來說明我們到目前為止所學到的概念。</span><span class="sxs-lookup"><span data-stu-id="7991f-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="7991f-106">以下針對不熟悉理論的使用者提供配量 teleportation 的說明，後面接著 Q # 中的程式碼執行逐步解說。</span><span class="sxs-lookup"><span data-stu-id="7991f-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="7991f-107">量子 Teleportation：理論</span><span class="sxs-lookup"><span data-stu-id="7991f-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="7991f-108">「量子 teleportation」是一種將不明的量子狀態（我們稱為「__訊息__」）從某個位置的 qubit 傳送至另一個位置 qubit 的技術（我們會將這些 qubits 稱為「__這裡__」和「__該處__」，分別為）。</span><span class="sxs-lookup"><span data-stu-id="7991f-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="7991f-109">我們可以使用 Dirac 標記法，將__訊息__表示為向量：</span><span class="sxs-lookup"><span data-stu-id="7991f-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="7991f-110">$ $ \ket{\psi} = \Alpha\ket{0} + \Beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="7991f-111">因為我們不知道 $ \Alpha $ 和 $ \Beta $ 的值，所以我們無法得知__訊息__qubit 的狀態。</span><span class="sxs-lookup"><span data-stu-id="7991f-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="7991f-112">步驟1：建立光子狀態</span><span class="sxs-lookup"><span data-stu-id="7991f-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="7991f-113">為了傳送__訊息__，我們需要 qubit__這裡__的光子__與 qubit。__</span><span class="sxs-lookup"><span data-stu-id="7991f-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="7991f-114">這是藉由套用 Hadamard 閘道，後面接著 CNOT-CONTAINS 閘道來達成。</span><span class="sxs-lookup"><span data-stu-id="7991f-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="7991f-115">讓我們看看這些閘道作業背後的數學運算。</span><span class="sxs-lookup"><span data-stu-id="7991f-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="7991f-116">我們會從__這裡__的 qubits 開始，__並在__$ \ket{0}$ 狀態中。</span><span class="sxs-lookup"><span data-stu-id="7991f-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="7991f-117">Entangling 這些 qubits 之後，它們就會處於下列狀態：</span><span class="sxs-lookup"><span data-stu-id="7991f-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="7991f-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} （\ket{00} + \ket{11}） $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="7991f-119">步驟2：傳送訊息</span><span class="sxs-lookup"><span data-stu-id="7991f-119">Step 2: Send the message</span></span>
<span data-ttu-id="7991f-120">若要傳送__訊息__，我們首先要以__message__ __qubit 和 qubit__做為輸入來套用 cnot-contains 閘道（__訊息__qubit 是控制項，而__這裡__qubit 是目標 qubit，在此例中為）。</span><span class="sxs-lookup"><span data-stu-id="7991f-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="7991f-121">可以寫入此輸入狀態：</span><span class="sxs-lookup"><span data-stu-id="7991f-121">This input state can be written:</span></span>

<span data-ttu-id="7991f-122">$ $ \ket{\psi}\ket{\phi ^ +} = （\Alpha\ket{0} + \Beta\ket{1}）（\frac{1}{\sqrt{2}} （\ket{00} + \ket{11}）） $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="7991f-123">這會展開為：</span><span class="sxs-lookup"><span data-stu-id="7991f-123">This expands to:</span></span>

<span data-ttu-id="7991f-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\Beta}{\sqrt{2}} \ket{100} + \frac{\Beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="7991f-125">提醒您，當控制項 qubit 為1時，CNOT-CONTAINS 閘道會翻轉目標 qubit。</span><span class="sxs-lookup"><span data-stu-id="7991f-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="7991f-126">例如，$ \ket{000}$ 的輸入將不會變更，因為第一個 qubit （控制項）為0。</span><span class="sxs-lookup"><span data-stu-id="7991f-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="7991f-127">不過，在第一個 qubit 為1的情況下，例如 $ \ket{100}$ 的輸入。</span><span class="sxs-lookup"><span data-stu-id="7991f-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="7991f-128">在此實例中，輸出為 $ \ket{110}$，因為第二個 qubit （目標）是由 CNOT-CONTAINS 閘道翻轉。</span><span class="sxs-lookup"><span data-stu-id="7991f-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="7991f-129">現在，讓我們在 CNOT-CONTAINS 閘道對上述輸入進行動作之後，考慮我們的輸出。</span><span class="sxs-lookup"><span data-stu-id="7991f-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="7991f-130">結果如下：</span><span class="sxs-lookup"><span data-stu-id="7991f-130">The result is:</span></span>

<span data-ttu-id="7991f-131">$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\Beta}{\sqrt{2}} \ket{110} + \frac{\Beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="7991f-132">傳送__訊息__的下一個步驟是將 Hadamard 閘道套用至__訊息__qubit （這是每個詞彙的第一個 qubit）。</span><span class="sxs-lookup"><span data-stu-id="7991f-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="7991f-133">提醒您，Hadamard 閘道會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7991f-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="7991f-134">輸入</span><span class="sxs-lookup"><span data-stu-id="7991f-134">Input</span></span> | <span data-ttu-id="7991f-135">輸出</span><span class="sxs-lookup"><span data-stu-id="7991f-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="7991f-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="7991f-136">$\ket{0}$</span></span>  | <span data-ttu-id="7991f-137">$ \frac{1}{\sqrt{2}} （\ket{0} + \ket{1}） $</span><span class="sxs-lookup"><span data-stu-id="7991f-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="7991f-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="7991f-138">$\ket{1}$</span></span>  | <span data-ttu-id="7991f-139">$ \frac{1}{\sqrt{2}} （\ket{0}-\ket{1}） $</span><span class="sxs-lookup"><span data-stu-id="7991f-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="7991f-140">如果我們將 Hadamard 閘道套用至上述輸出中每個詞彙的第一個 qubit，我們會得到下列結果：</span><span class="sxs-lookup"><span data-stu-id="7991f-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="7991f-141">$ $ \frac{\Alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{00} + \frac{\Alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{11} + \frac{\Beta}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）） \ket{10} + \frac{\Beta}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）） \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="7991f-142">請注意，每個詞彙都有 $2 \frac{1}{\sqrt{2}} $ 因素。</span><span class="sxs-lookup"><span data-stu-id="7991f-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="7991f-143">我們可以將這些結果相乘，以提供下列結果：</span><span class="sxs-lookup"><span data-stu-id="7991f-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="7991f-144">$ $ \frac{\Alpha}{2}（\ket{0} + \ket{1}） \ket{00} + \frac{\Alpha}{2}（\ket{0} + \ket{1}） \ket{11} + \frac{\Beta}{2}（\ket{0}-\ket{1}） \ket{10} + \frac{\Beta}{2}（\ket{0}-\ket{1}） \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="7991f-145">$ \Frac{1}{2}$ 因素是每個詞彙通用的，因此我們現在可以將其帶到括弧外：</span><span class="sxs-lookup"><span data-stu-id="7991f-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="7991f-146">$ $ \frac{1}{2}\big [\Alpha （\ket{0} + \ket{1}） \ket{00} + \Alpha （\ket{0} + \ket{1}） \ket{11} + \Beta （\ket{0}-\ket{1}） \ket{10} + \Beta （\ket{0}-\ket{1}） \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="7991f-147">然後，我們可以將每個詞彙的括弧相乘，以提供：</span><span class="sxs-lookup"><span data-stu-id="7991f-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="7991f-148">$ $ \frac{1}{2}\big [\Alpha\ket{000} + \Alpha\ket{100} + \Alpha\ket{011} + \Alpha\ket{111} + \Beta\ket{010}-\Beta\ket{110} + \Beta\ket{001}-\Beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="7991f-149">步驟3：測量結果</span><span class="sxs-lookup"><span data-stu-id="7991f-149">Step 3: Measure the result</span></span>

<span data-ttu-id="7991f-150">由於__這裡__ __還有__光子，因此__這裡__的任何測量都會影響到__該處__的狀態。</span><span class="sxs-lookup"><span data-stu-id="7991f-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="7991f-151">如果我們測量第一個和第二個 qubit （__訊息__和__此處__），我們就可以瞭解因為會任何牽連的這個屬性而__存在__的狀態。</span><span class="sxs-lookup"><span data-stu-id="7991f-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="7991f-152">如果我們測量並取得結果00，重迭會折迭，只留下與此結果一致的詞彙。</span><span class="sxs-lookup"><span data-stu-id="7991f-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7991f-153">這是 $ \Alpha\ket{000} + \Beta\ket{001}$。</span><span class="sxs-lookup"><span data-stu-id="7991f-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="7991f-154">這可以重構為 $ \ket{00}（\Alpha\ket{0} + \Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="7991f-155">因此 __，如果__我們將第一個和第二個 qubit 測量成00，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{0} + \Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="7991f-156">如果我們測量並取得結果01，則重迭會折迭，只留下與此結果一致的詞彙。</span><span class="sxs-lookup"><span data-stu-id="7991f-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7991f-157">這是 $ \Alpha\ket{011} + \Beta\ket{010}$。</span><span class="sxs-lookup"><span data-stu-id="7991f-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="7991f-158">這可以重構為 $ \ket{01}（\Alpha\ket{1} + \Beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="7991f-159">因此 __，如果__我們將第一個和第二個 qubit 測量成01，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{1} + \Beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="7991f-160">如果我們測量結果10，就會折迭重迭，只留下與此結果一致的條款。</span><span class="sxs-lookup"><span data-stu-id="7991f-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7991f-161">這是 $ \Alpha\ket{100}-\Beta\ket{101}$。</span><span class="sxs-lookup"><span data-stu-id="7991f-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="7991f-162">這可以重構為 $ \ket{10}（\Alpha\ket{0}-\Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="7991f-163">因此 __，如果__我們將第一個和第二個 qubit 測量為10，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{0}-\Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="7991f-164">如果我們測量並得到結果11，重迭會折迭，只留下與此結果一致的詞彙。</span><span class="sxs-lookup"><span data-stu-id="7991f-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="7991f-165">這是 $ \Alpha\ket{111}-\Beta\ket{110}$。</span><span class="sxs-lookup"><span data-stu-id="7991f-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="7991f-166">這可以重構為 $ \ket{11}（\Alpha\ket{1}-\Beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="7991f-167">因此 __，如果__我們將第一個和第二個 qubit 測量為11，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{1}-\Beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="7991f-168">步驟4：解讀結果</span><span class="sxs-lookup"><span data-stu-id="7991f-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="7991f-169">提醒您，我們想要傳送的原始__訊息__是：</span><span class="sxs-lookup"><span data-stu-id="7991f-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="7991f-170">$ $ \ket{\psi} = \Alpha\ket{0} + \Beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="7991f-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="7991f-171">我們需要__取得此狀態的 qubit，__ 讓 [已接收] 狀態是預期的狀態。</span><span class="sxs-lookup"><span data-stu-id="7991f-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="7991f-172">如果我們測量並得到00的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{0} + \Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="7991f-173">由於這是預期的__訊息__，因此不需要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="7991f-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="7991f-174">如果我們測量並得到01的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{1} + \Beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="7991f-175">這與預期的__訊息__不同，但套用 NOT 閘道會提供所需的狀態 $ （\Alpha\ket{0} + \Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="7991f-176">如果我們測量並得到10的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{0}-\Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="7991f-177">這與預期的__訊息__不同，不過，套用 Z 閘道會提供所需的狀態 $ （\Alpha\ket{0} + \Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="7991f-178">如果我們測量並得到11的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{1}-\Beta\ket{0}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="7991f-179">這與預期的__訊息__不同，但套用的 NOT 閘道後面接著 Z 閘道會提供所需的 state $ （\Alpha\ket{0} + \Beta\ket{1}） $。</span><span class="sxs-lookup"><span data-stu-id="7991f-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="7991f-180">總而言之，如果我們測量，而第一個 qubit 是1，則會套用 Z 閘道。</span><span class="sxs-lookup"><span data-stu-id="7991f-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="7991f-181">如果我們測量，而第二個 qubit 是1，則會套用 NOT 閘道。</span><span class="sxs-lookup"><span data-stu-id="7991f-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="7991f-182">摘要</span><span class="sxs-lookup"><span data-stu-id="7991f-182">Summary</span></span>
<span data-ttu-id="7991f-183">如下所示，這是用來執行 teleportation 的文字書本量子線路。</span><span class="sxs-lookup"><span data-stu-id="7991f-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="7991f-184">從左至右移動，您可以看到：</span><span class="sxs-lookup"><span data-stu-id="7991f-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="7991f-185">步驟1：__在這裡__Entangling __，並__套用 HADAMARD 閘道和 cnot-contains 閘道。</span><span class="sxs-lookup"><span data-stu-id="7991f-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="7991f-186">步驟2：使用 CNOT-CONTAINS 閘道和 Hadamard 閘道來傳送__訊息__。</span><span class="sxs-lookup"><span data-stu-id="7991f-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="7991f-187">步驟3：測量第一個和第二個 qubits、__訊息__和__此處__。</span><span class="sxs-lookup"><span data-stu-id="7991f-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="7991f-188">步驟4：套用非閘道或 Z 閘道，視步驟3中的測量結果而定。</span><span class="sxs-lookup"><span data-stu-id="7991f-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' 傳送（msg： Qubit，有： Qubit）： Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="7991f-190">量子 Teleportation：程式碼</span><span class="sxs-lookup"><span data-stu-id="7991f-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="7991f-191">我們有配量 teleportation 的線路：</span><span class="sxs-lookup"><span data-stu-id="7991f-191">We have our circuit for quantum teleportation:</span></span>

![' 傳送（msg： Qubit，有： Qubit）： Unit '](~/media/teleportation.svg)

<span data-ttu-id="7991f-193">我們現在可以將此配量電路中的每個步驟轉譯為 Q #。</span><span class="sxs-lookup"><span data-stu-id="7991f-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="7991f-194">步驟0：定義</span><span class="sxs-lookup"><span data-stu-id="7991f-194">Step 0: Definition</span></span>
<span data-ttu-id="7991f-195">當我們執行 teleportation 時，我們必須知道想要傳送的__訊息__，以及我們想要傳送給它的位置（__這裡__）。</span><span class="sxs-lookup"><span data-stu-id="7991f-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="7991f-196">基於這個理由，我們一開始會定義一個新的「傳送」作業，以提供兩個 qubits 做為引數，`msg` 和 `there`：</span><span class="sxs-lookup"><span data-stu-id="7991f-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="7991f-197">我們也需要配置一個 qubit `here`，以 `using` 組塊達成：</span><span class="sxs-lookup"><span data-stu-id="7991f-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="7991f-198">步驟1：建立光子狀態</span><span class="sxs-lookup"><span data-stu-id="7991f-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="7991f-199">然後，我們可以使用 @"microsoft.quantum.primitive.h" 和 @"microsoft.quantum.primitive.cnot" 作業，在 `here` 和 `there` 之間建立光子組：</span><span class="sxs-lookup"><span data-stu-id="7991f-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.primitive.h" and @"microsoft.quantum.primitive.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="7991f-200">步驟2：傳送訊息</span><span class="sxs-lookup"><span data-stu-id="7991f-200">Step 2: Send the message</span></span>
<span data-ttu-id="7991f-201">接著，我們會使用下一個 $ \operatorname{CNOT} $ 和 $H $ 閘道來移動訊息 qubit：</span><span class="sxs-lookup"><span data-stu-id="7991f-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="7991f-202">步驟 3 & 4：測量並解讀結果</span><span class="sxs-lookup"><span data-stu-id="7991f-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="7991f-203">最後，我們會使用 @"microsoft.quantum.primitive.m" 來執行測量，並執行必要的閘道作業，以取得所需的狀態，如 `if` 的語句所表示：</span><span class="sxs-lookup"><span data-stu-id="7991f-203">Finally, we use @"microsoft.quantum.primitive.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="7991f-204">這會完成 teleportation 運算子的定義，因此我們可以解除配置 `here`、結束主體，並結束作業。</span><span class="sxs-lookup"><span data-stu-id="7991f-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
