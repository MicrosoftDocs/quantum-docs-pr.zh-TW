---
title: Q# 技術 - 將其全部放在一起
description: 流覽演示量子傳送的基本 Q# 程式。
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030560"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="27205-103">將所有功能放在一起:傳送</span><span class="sxs-lookup"><span data-stu-id="27205-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="27205-104">讓我們回到[量子電路](xref:microsoft.quantum.concepts.circuits)中定義的傳送電路的例子。</span><span class="sxs-lookup"><span data-stu-id="27205-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="27205-105">我們將用它來說明我們迄今學到的概念。</span><span class="sxs-lookup"><span data-stu-id="27205-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="27205-106">下面為不熟悉該理論的人提供量子傳送的說明,隨後在Q# 中介紹代碼實現。</span><span class="sxs-lookup"><span data-stu-id="27205-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="27205-107">量子傳送:理論</span><span class="sxs-lookup"><span data-stu-id="27205-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="27205-108">量子傳送是一種將未知量子狀態(我們稱之為"__消息__")從一個位置的量子位發送到另一個位置的量子位的技術(我們將這些量子位分別稱為"__此處__"和"__此處__"。</span><span class="sxs-lookup"><span data-stu-id="27205-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="27205-109">我們可以使用 Dirac 表示法表示我們__的消息__作為向量:</span><span class="sxs-lookup"><span data-stu-id="27205-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="27205-110">$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$</span><span class="sxs-lookup"><span data-stu-id="27205-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="27205-111">__消息__qubit 的狀態是未知的,因為我們不知道 $_alpha$ 和 $_beta$的值。</span><span class="sxs-lookup"><span data-stu-id="27205-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="27205-112">第一步:建立糾纏狀態</span><span class="sxs-lookup"><span data-stu-id="27205-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="27205-113">為了__發送消息,我們需要____在這裡__的量子位與那裡的量子位糾纏在一__起__。</span><span class="sxs-lookup"><span data-stu-id="27205-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="27205-114">這是通過應用哈達馬德門來實現的,然後是 CNOT 門。</span><span class="sxs-lookup"><span data-stu-id="27205-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="27205-115">讓我們來看看這些門操作背後的數學。</span><span class="sxs-lookup"><span data-stu-id="27205-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="27205-116">我們將從__此處__和__此處__的 qubit 開始{0},兩者都位於 $ket $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="27205-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="27205-117">糾纏這些量子位后,它們處於以下狀態:</span><span class="sxs-lookup"><span data-stu-id="27205-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="27205-118">{1}$$$\ket_phi_= = _frac [sqrt](\ket{2} {00} ={11}\ket) $$$</span><span class="sxs-lookup"><span data-stu-id="27205-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="27205-119">第二步:傳送訊息</span><span class="sxs-lookup"><span data-stu-id="27205-119">Step 2: Send the message</span></span>
<span data-ttu-id="27205-120">為了__發送消息,我們__首先應用一個帶有__消息__qubit的 CNOT 門,__此處__將 qubit 作為輸入(__消息__qubit 是控制項,__此處__的 qubit 是目標 qubit,在這種情況下)。</span><span class="sxs-lookup"><span data-stu-id="27205-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="27205-121">可以寫入此輸入狀態:</span><span class="sxs-lookup"><span data-stu-id="27205-121">This input state can be written:</span></span>

<span data-ttu-id="27205-122">$$$\ket\psi_ket_ket_phi_]= (\alpha_ket{0} {1}={1}\beta_ket)(\frac [sqrt](\ket{2} {00} {11}= \ket)$$</span><span class="sxs-lookup"><span data-stu-id="27205-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="27205-123">這會擴展到:</span><span class="sxs-lookup"><span data-stu-id="27205-123">This expands to:</span></span>

<span data-ttu-id="27205-124">$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span><span class="sxs-lookup"><span data-stu-id="27205-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="27205-125">作為提醒,當控件 qubit 為 1 時,CNOT 門將翻轉目標量子位。</span><span class="sxs-lookup"><span data-stu-id="27205-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="27205-126">因此,例如,$_ket{000}$ 的輸入不會導致任何變化,因為第一個 qubit(控件)為 0。</span><span class="sxs-lookup"><span data-stu-id="27205-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="27205-127">但是,以第一個 qubit 為 1{100}的情況為例 , 例如 ,輸入為 $_ket $。</span><span class="sxs-lookup"><span data-stu-id="27205-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="27205-128">在這種情況下,輸出為 $_ket{110}$,因為第二個 qubit(目標)由 CNOT 門翻轉。</span><span class="sxs-lookup"><span data-stu-id="27205-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="27205-129">現在,讓我們考慮我們的輸出,一旦CNOT門已經按照我們上面的意見採取行動。</span><span class="sxs-lookup"><span data-stu-id="27205-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="27205-130">結果如下：</span><span class="sxs-lookup"><span data-stu-id="27205-130">The result is:</span></span>

<span data-ttu-id="27205-131">{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$</span><span class="sxs-lookup"><span data-stu-id="27205-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="27205-132">發送__消息__的下一步是將 Hadamard 門應用於__消息__qubit(這是每個術語的第一個 qubit)。</span><span class="sxs-lookup"><span data-stu-id="27205-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="27205-133">作為提醒,哈達馬德門執行以下操作:</span><span class="sxs-lookup"><span data-stu-id="27205-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="27205-134">輸入</span><span class="sxs-lookup"><span data-stu-id="27205-134">Input</span></span> | <span data-ttu-id="27205-135">輸出</span><span class="sxs-lookup"><span data-stu-id="27205-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="27205-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="27205-136">$\ket{0}$</span></span>  | <span data-ttu-id="27205-137">$_frac{1}\sqrt{2}[(\ket{0} ={1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="27205-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="27205-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="27205-138">$\ket{1}$</span></span>  | <span data-ttu-id="27205-139">$_frac{1}\sqrt{2}\(\ket{0} -{1}\ket )$</span><span class="sxs-lookup"><span data-stu-id="27205-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="27205-140">如果我們將 Hadamard 門應用於上述輸出的每個術語的第一個 qubit,我們會得到以下結果:</span><span class="sxs-lookup"><span data-stu-id="27205-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="27205-141">$${2}_frac_alpha_sqrt{1}_(\frac _sqrt{2}{0} \c{1}\c =ket )\ket{00} \c =\c_\c_\c_\c_\c_sqrt{2}[(\frac{1}_sqrt{2}\c{0} {1}_ket)\ket{11} ]{2}[frac_beta]_sqrt{1}_(\frac{1}_sqrt{10} {2}\c _c_ket{0} )\ket{1} {01} {2}=\c_beta_sqrt_(_frac{1}_sqrt{2}_(\ket{0} - \ket))\ket $$$$$$$</span><span class="sxs-lookup"><span data-stu-id="27205-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="27205-142">請注意,每個術語都有兩個{1}$frac \sqrt{2}\$$因數。</span><span class="sxs-lookup"><span data-stu-id="27205-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="27205-143">我們可以將這些乘數乘以給出以下結果:</span><span class="sxs-lookup"><span data-stu-id="27205-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="27205-144">$${2}[frac_alpha] (\ket{0} {1}={00} \ket{2}{0} )\ket{1}= \ket{11} \ket )\ket{2} {0} {1}=\c_beta](\ket - \ket)\ket{10} {2}=\c_beta](\ket{0} - \ket)\ket)\ket{1} {01}</span><span class="sxs-lookup"><span data-stu-id="27205-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="27205-145">$_frac{1}{2}$ 因數是每個術語的通用,因此我們現在可以在括弧外將其採用:</span><span class="sxs-lookup"><span data-stu-id="27205-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="27205-146">$${1}{2}\frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span><span class="sxs-lookup"><span data-stu-id="27205-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="27205-147">然後,我們可以將每個術語的括弧相乘:</span><span class="sxs-lookup"><span data-stu-id="27205-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="27205-148">$$ \frac{1}{2}\big[\Alpha\ket{000} + \Alpha\ket{100} +{011} \alpha\ket{111} + \Alpha\ket + \beta\ket{010} -{110} \beta\ket + \Beta\ket{001} - \beta\ket{101}\big] $$</span><span class="sxs-lookup"><span data-stu-id="27205-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="27205-149">第三步:測量結果</span><span class="sxs-lookup"><span data-stu-id="27205-149">Step 3: Measure the result</span></span>

<span data-ttu-id="27205-150">由於__這裡____和那裡__糾纏,__任何測量在這裡__將影響__那裡__的狀態。</span><span class="sxs-lookup"><span data-stu-id="27205-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="27205-151">如果我們測量第一個和第二量子位(__消息__和__這裡__),我們可以知道__處於__什麼狀態,由於這種糾纏的屬性。</span><span class="sxs-lookup"><span data-stu-id="27205-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="27205-152">如果我們測量並獲取結果 00,疊加將摺疊,僅保留與此結果一致的術語。</span><span class="sxs-lookup"><span data-stu-id="27205-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="27205-153">那是 $_alpha\ket{000} \beta\ket{001}$。</span><span class="sxs-lookup"><span data-stu-id="27205-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="27205-154">這可以重構為 $\ket{00}(\alpha\ket{1}{0} \beta_ket )$。</span><span class="sxs-lookup"><span data-stu-id="27205-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="27205-155">因此,如果我們將第一個和第二個 qubit 測量為 00,我們知道第三個 qubit,__有__,處於狀態 $(\Alpha\ket\beta\ket)$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="27205-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="27205-156">如果我們測量並獲取結果 01,疊加將摺疊,僅保留與此結果一致的術語。</span><span class="sxs-lookup"><span data-stu-id="27205-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="27205-157">那是 $_alpha\ket{011} \beta\ket{010}$。</span><span class="sxs-lookup"><span data-stu-id="27205-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="27205-158">這可以重構為 $\ket{01}(\alpha\ket{0}{1} \beta_ket )$。</span><span class="sxs-lookup"><span data-stu-id="27205-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="27205-159">因此,如果我們測量第一個和第二個量子位為 01,我們知道第三個 qubit,__有__,在狀態 $(\Alpha\ket\beta\ket)$。{1} {0}</span><span class="sxs-lookup"><span data-stu-id="27205-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="27205-160">如果我們測量並獲取結果 10,疊加將摺疊,僅保留與此結果一致的術語。</span><span class="sxs-lookup"><span data-stu-id="27205-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="27205-161">那是 $_alpha\ket{100} -\beta\ket{101}$。</span><span class="sxs-lookup"><span data-stu-id="27205-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="27205-162">這可以重構為 $\ket{10}(\alpha\ket{1}{0} -_beta_ket )$。</span><span class="sxs-lookup"><span data-stu-id="27205-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="27205-163">因此,如果我們將第一個和第二個量子位度量為 10,我們知道第三個 qubit,__有__,處於狀態 $(\alpha_ket-_beta_ket)$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="27205-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="27205-164">如果我們測量並獲取結果 11,疊加將摺疊,僅保留與此結果一致的術語。</span><span class="sxs-lookup"><span data-stu-id="27205-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="27205-165">那是 $_alpha\ket{111} -\beta\ket{110}$。</span><span class="sxs-lookup"><span data-stu-id="27205-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="27205-166">這可以重構為 $\ket{11}(\alpha\ket{0}{1} -_beta_ket )$。</span><span class="sxs-lookup"><span data-stu-id="27205-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="27205-167">因此,如果我們將第一個和第二個量子位度量為 11,我們知道第三個 qubit,__有__,處於狀態 $(\alpha_ket-_beta_ket)$。{1} {0}</span><span class="sxs-lookup"><span data-stu-id="27205-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="27205-168">第 4 步:解釋結果</span><span class="sxs-lookup"><span data-stu-id="27205-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="27205-169">作為提醒,我們希望傳送的原始__資訊__是:</span><span class="sxs-lookup"><span data-stu-id="27205-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="27205-170">$$$\ket_psi] = \alpha\ket{0} ={1} \beta\ket $$$</span><span class="sxs-lookup"><span data-stu-id="27205-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="27205-171">我們需要將__那裡的__qubit放入此狀態,以便接收的狀態是預期狀態。</span><span class="sxs-lookup"><span data-stu-id="27205-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="27205-172">如果我們測量並得到的結果為 00,則第三個 qubit,__有__,處於狀態 $(\alpha\ket\beta\ket)$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="27205-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="27205-173">由於這是預期__的消息__,因此無需更改。</span><span class="sxs-lookup"><span data-stu-id="27205-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="27205-174">如果我們測量並得到 01 的結果,則第三個 qubit,__有__,處於狀態 $(\alpha\ket\beta_ket)$。{1} {0}</span><span class="sxs-lookup"><span data-stu-id="27205-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="27205-175">這與預期__消息__不同,但是應用 NOT 門會給我們所需的狀態 $(\alpha\ket\beta\ket)$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="27205-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="27205-176">如果我們測量並得到 10 的結果,則第三個 qubit,__有__,在狀態 $(\alpha\ket{0} -_beta_ket)$。{1}</span><span class="sxs-lookup"><span data-stu-id="27205-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="27205-177">這與預期__消息__不同,但是應用 Z 門會給我們所需的狀態 $(\Alpha\ket\beta\ket)$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="27205-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="27205-178">如果我們測量並得到 11 的結果,那麼第三個 qubit,__有__,是在狀態 $(\alpha\ket{1} -_beta_ket)$。{0}</span><span class="sxs-lookup"><span data-stu-id="27205-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="27205-179">這與預期__消息__不同,但是應用 NOT 門後跟 Z 門會給我們所需的狀態 $(\alpha\ket\beta_ket)$。{0} {1}</span><span class="sxs-lookup"><span data-stu-id="27205-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="27205-180">總之,如果我們測量第一個量子位為 1,則應用 Z 門。</span><span class="sxs-lookup"><span data-stu-id="27205-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="27205-181">如果我們測量第二個量子位為 1,則應用 NOT 門。</span><span class="sxs-lookup"><span data-stu-id="27205-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="27205-182">摘要</span><span class="sxs-lookup"><span data-stu-id="27205-182">Summary</span></span>
<span data-ttu-id="27205-183">下面顯示了實現傳送的教科書量子電路。</span><span class="sxs-lookup"><span data-stu-id="27205-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="27205-184">從左至右移動,您可以看到:</span><span class="sxs-lookup"><span data-stu-id="27205-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="27205-185">第1步:通過應用哈達馬德門和CNOT門,__在這裡____和那裡__糾纏。</span><span class="sxs-lookup"><span data-stu-id="27205-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="27205-186">第 2 步 __:使用__CNOT 門和哈達馬德門發送消息。</span><span class="sxs-lookup"><span data-stu-id="27205-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="27205-187">步驟 3:測量第一和第二個量子位,__消息__和__這裡__。</span><span class="sxs-lookup"><span data-stu-id="27205-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="27205-188">步驟 4:根據步驟 3 中的測量結果應用不門或 Z 門。</span><span class="sxs-lookup"><span data-stu-id="27205-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['傳送(msg: Qubit, 有 : Qubit) : 單位'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="27205-190">量子傳送:代碼</span><span class="sxs-lookup"><span data-stu-id="27205-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="27205-191">我們有用於量子傳送的電路:</span><span class="sxs-lookup"><span data-stu-id="27205-191">We have our circuit for quantum teleportation:</span></span>

!['傳送(msg: Qubit, 有 : Qubit) : 單位'](~/media/teleportation.svg)

<span data-ttu-id="27205-193">現在,我們可以將此量子電路中的每個步驟轉換為 Q#。</span><span class="sxs-lookup"><span data-stu-id="27205-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="27205-194">步驟 0:定義</span><span class="sxs-lookup"><span data-stu-id="27205-194">Step 0: Definition</span></span>
<span data-ttu-id="27205-195">當我們執行傳送時,我們必須知道我們想要__發送的資訊__,以及我們希望發送的位置(__那裡__)。</span><span class="sxs-lookup"><span data-stu-id="27205-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="27205-196">因此,我們首先定義一個新的傳送運運運,該操作給定兩個 qubit`msg`作為`there`參數 , 和 :</span><span class="sxs-lookup"><span data-stu-id="27205-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="27205-197">我們還需要分配一個通過`here``using`塊實現的量子位:</span><span class="sxs-lookup"><span data-stu-id="27205-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="27205-198">第一步:建立糾纏狀態</span><span class="sxs-lookup"><span data-stu-id="27205-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="27205-199">然後`here`,我們可以`there`@"microsoft.quantum.intrinsic.h"使用@"microsoft.quantum.intrinsic.cnot"和操作創建和之間的糾纏對:</span><span class="sxs-lookup"><span data-stu-id="27205-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="27205-200">第二步:傳送訊息</span><span class="sxs-lookup"><span data-stu-id="27205-200">Step 2: Send the message</span></span>
<span data-ttu-id="27205-201">然後,我們使用下一個 $_運算符名稱[CNOT_$ 和 $H$ 門來移動我們的消息庫比特:</span><span class="sxs-lookup"><span data-stu-id="27205-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="27205-202">第3步&4:測量和解釋結果</span><span class="sxs-lookup"><span data-stu-id="27205-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="27205-203">最後,我們使用@"microsoft.quantum.intrinsic.m"執行測量並執行必要的門操作以獲得所需的狀態,`if`如語句所述:</span><span class="sxs-lookup"><span data-stu-id="27205-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="27205-204">第 5 步:重新啟動量子位寄存器</span><span class="sxs-lookup"><span data-stu-id="27205-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="27205-205">在每個 Q# 操作結束時,我們需要讓狀態中的 qubit{0}$\ket $$。</span><span class="sxs-lookup"><span data-stu-id="27205-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="27205-206">我們可以使用@"microsoft.quantum.intrinsic.reset"重新啟動所有量子位到零狀態,這將完成我們的操作。</span><span class="sxs-lookup"><span data-stu-id="27205-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


