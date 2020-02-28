---
title: '問答 # 標準程式庫中的錯誤修正'
description: '瞭解如何在您的 Q # 程式中使用錯誤更正代碼，同時保護 qubits 的狀態。'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 514fe68f603b9a3a0b4607390719b08a43fe4967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907761"
---
# <a name="error-correction"></a><span data-ttu-id="d4029-103">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="d4029-103">Error Correction</span></span> #

## <a name="introduction"></a><span data-ttu-id="d4029-104">簡介</span><span class="sxs-lookup"><span data-stu-id="d4029-104">Introduction</span></span> ##

<span data-ttu-id="d4029-105">在傳統運算中，如果您想要保護一點以避免發生錯誤，通常可以重復資料位來表示該位的*邏輯位*。</span><span class="sxs-lookup"><span data-stu-id="d4029-105">In classical computing, if one wants to protect a bit against errors, it can often suffice to represent that bit by a *logical bit* by repeating the data bit.</span></span>
<span data-ttu-id="d4029-106">比方說，let $ \overline{0} = $0 是資料位0的編碼方式，我們使用標籤0上方的一條線來表示它是0狀態中位的編碼方式。</span><span class="sxs-lookup"><span data-stu-id="d4029-106">For instance, let $\overline{0} = 000$ be the encoding of the data bit 0, where we use the a line above the label 0 to indicate that it is an encoding of a bit in the 0 state.</span></span>
<span data-ttu-id="d4029-107">如果同樣地，讓 $ \overline{1} = $111，則會有一個簡單的重複程式碼，可防止任何一位翻轉錯誤。</span><span class="sxs-lookup"><span data-stu-id="d4029-107">If we similarly let $\overline{1} = 111$, then we have a simple repetition code that protects against any one bit flip error.</span></span>
<span data-ttu-id="d4029-108">也就是說，如果有三個位的任何一個翻轉，我們就可以採取多數投票來復原邏輯位的狀態。</span><span class="sxs-lookup"><span data-stu-id="d4029-108">That is, if any of the three bits are flipped, then we can recover the state of the logical bit by taking a majority vote.</span></span>
<span data-ttu-id="d4029-109">雖然傳統錯誤修正是此特定範例（建議不[起毛的編碼理論簡介](https://www.springer.com/us/book/9783540641339)）的更豐富主旨，但上述重複程式碼已指向保護配量資訊的可能問題。</span><span class="sxs-lookup"><span data-stu-id="d4029-109">Though classical error correction is a much richer subject that this particular example (we recommend [Lint's introduction to coding theory](https://www.springer.com/us/book/9783540641339)), the repetition code above already points to a possible problem in protecting quantum information.</span></span>
<span data-ttu-id="d4029-110">換句話說，「[無複製定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem)」表示如果我們測量每個個別的 qubit，並使用上述的傳統程式碼來進行大部分的投票，我們就會遺失我們嘗試保護的精確資訊。</span><span class="sxs-lookup"><span data-stu-id="d4029-110">Namely, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implies that if we measure each individual qubit and take a majority vote by analogy to classical code above, then we have lost the precise information that we are trying to protect.</span></span>

<span data-ttu-id="d4029-111">在 [配量] 設定中，我們會看到度量有問題。</span><span class="sxs-lookup"><span data-stu-id="d4029-111">In the quantum setting, we will see that the measurement is problematic.</span></span> <span data-ttu-id="d4029-112">我們仍然可以執行上述編碼。</span><span class="sxs-lookup"><span data-stu-id="d4029-112">We can still implement the encoding above.</span></span>
<span data-ttu-id="d4029-113">這麼做有助於瞭解如何將錯誤更正一般化至量子案例。</span><span class="sxs-lookup"><span data-stu-id="d4029-113">It is helpful to do so to see how we can generalize error correction to the quantum case.</span></span>
<span data-ttu-id="d4029-114">因此，let $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$，並讓 $ \ket{\overline{1}} = \ket{111}$。</span><span class="sxs-lookup"><span data-stu-id="d4029-114">Thus, let $\ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, and let $\ket{\overline{1}} = \ket{111}$.</span></span>
<span data-ttu-id="d4029-115">然後，藉由線性，我們為所有輸入定義了重複的程式碼;例如，$ \ket{\overline{+}} = （\ket{\overline{0}} + \ket{\overline{1}}）/\sqrt{2} = （\ket{000} + \ket{111}）/\sqrt{2}$。</span><span class="sxs-lookup"><span data-stu-id="d4029-115">Then, by linearity, we have defined our repetition code for all inputs; for instance, $\ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}}) / \sqrt{2} = (\ket{000} + \ket{111}) / \sqrt{2}$.</span></span>
<span data-ttu-id="d4029-116">特別是，在中間 qubit 上 $X _1 $ act 時，我們會看到兩個分支中所需的更正精確 $X _1 $： $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left （X_1 \ket{000} + X_1 \ket{111} \right） \\\\ & = \frac{1}{\sqrt{2}} \left （\ket{010} + \ket{101} \right）。</span><span class="sxs-lookup"><span data-stu-id="d4029-116">In particular, letting a bit-flip error $X_1$ act on the middle qubit, we see that the correction needed in both branches is precisely $X_1$: $$ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left( X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{010} + \ket{101} \right).</span></span>
<span data-ttu-id="d4029-117">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d4029-117">\end{align} $$</span></span>

<span data-ttu-id="d4029-118">若要瞭解如何找出這種情況，而不測量我們嘗試保護的非常狀態，請記下每個不同的位會翻轉錯誤對我們的邏輯狀態的意義：</span><span class="sxs-lookup"><span data-stu-id="d4029-118">To see how we can identify that this is the case without measuring the very state we are trying to protect, it is helpful to write down what each different bit flip error does to our logical states:</span></span>

| <span data-ttu-id="d4029-119">錯誤 $E $</span><span class="sxs-lookup"><span data-stu-id="d4029-119">Error $E$</span></span> | <span data-ttu-id="d4029-120">$E \ket{\overline{0}} $</span><span class="sxs-lookup"><span data-stu-id="d4029-120">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="d4029-121">$E \ket{\overline{1}} $</span><span class="sxs-lookup"><span data-stu-id="d4029-121">$E\ket{\overline{1}}$</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d4029-122">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="d4029-122">$\boldone$</span></span> | <span data-ttu-id="d4029-123">$ \ket{000}$</span><span class="sxs-lookup"><span data-stu-id="d4029-123">$\ket{000}$</span></span> | <span data-ttu-id="d4029-124">$ \ket{111}$</span><span class="sxs-lookup"><span data-stu-id="d4029-124">$\ket{111}$</span></span> |
| <span data-ttu-id="d4029-125">$X _0 $</span><span class="sxs-lookup"><span data-stu-id="d4029-125">$X_0$</span></span> | <span data-ttu-id="d4029-126">$ \ket{100}$</span><span class="sxs-lookup"><span data-stu-id="d4029-126">$\ket{100}$</span></span> | <span data-ttu-id="d4029-127">$ \ket{011}$</span><span class="sxs-lookup"><span data-stu-id="d4029-127">$\ket{011}$</span></span> |
| <span data-ttu-id="d4029-128">$X _1 $</span><span class="sxs-lookup"><span data-stu-id="d4029-128">$X_1$</span></span> | <span data-ttu-id="d4029-129">$ \ket{010}$</span><span class="sxs-lookup"><span data-stu-id="d4029-129">$\ket{010}$</span></span> | <span data-ttu-id="d4029-130">$ \ket{101}$</span><span class="sxs-lookup"><span data-stu-id="d4029-130">$\ket{101}$</span></span> |
| <span data-ttu-id="d4029-131">$X _2 $</span><span class="sxs-lookup"><span data-stu-id="d4029-131">$X_2$</span></span> | <span data-ttu-id="d4029-132">$ \ket{001}$</span><span class="sxs-lookup"><span data-stu-id="d4029-132">$\ket{001}$</span></span> | <span data-ttu-id="d4029-133">$ \ket{110}$</span><span class="sxs-lookup"><span data-stu-id="d4029-133">$\ket{110}$</span></span> |

<span data-ttu-id="d4029-134">為了保護我們所編碼的狀態，我們必須能夠區分彼此和身分識別 $ \boldone $ 之間的三個錯誤，而不區分 $ \ket{\overline{0}} $ 和 $ \ket{\overline{1}} $。</span><span class="sxs-lookup"><span data-stu-id="d4029-134">In order to protect the state that we're encoding, we need to be able to distinguish the three errors from each other and from the identity $\boldone$ without distinguishing between $\ket{\overline{0}}$ and $\ket{\overline{1}}$.</span></span>
<span data-ttu-id="d4029-135">例如，如果我們測量 $Z _0 $，在無錯誤情況下，我們會針對 $ \ket{\overline{0}} $ 和 $ \ket{\overline{1}} $ 取得不同的結果，因此會折迭編碼的狀態。</span><span class="sxs-lookup"><span data-stu-id="d4029-135">For example, if we measure $Z_0$, we get a different result for $\ket{\overline{0}}$ and $\ket{\overline{1}}$ in the no-error case, so that collapses the encoded state.</span></span>
<span data-ttu-id="d4029-136">另一方面，請考慮測量 $Z _0 Z_1 $，這是每個計算基礎狀態中前兩個位的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="d4029-136">On the other hand, consider measuring $Z_0 Z_1$, the parity of the first two bits in each computational basis state.</span></span>
<span data-ttu-id="d4029-137">回想一下，Pauli 運算子的每個測量都會檢查要測量的狀態會對應到哪個 eigenvalue，因此針對上表中的每個 state $ \ket{\psi} $，我們可以計算 $Z _0 Z_1 \ket{\psi} $ 來查看是否取得 $ \pm\ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="d4029-137">Recall that each measurement of a Pauli operator checks which eigenvalue  the state being measured corresponds to, so for each state $\ket{\psi}$ in the table above, we can compute $Z_0 Z_1 \ket{\psi}$ to see if we get $\pm\ket{\psi}$.</span></span>
<span data-ttu-id="d4029-138">請注意，$Z _0 Z_1 \ket{000} = \ket{000}$，該 $Z _0 Z_1 \ket{111} = \ket{111}$，如此一來，我們就會得出這項測量的結果，使兩者的編碼狀態相同。</span><span class="sxs-lookup"><span data-stu-id="d4029-138">Note that $Z_0 Z_1 \ket{000} = \ket{000}$ and that $Z_0 Z_1 \ket{111} = \ket{111}$, so that we conclude that this measurement does the same thing to both encoded states.</span></span>
<span data-ttu-id="d4029-139">另一方面，$Z _0 Z_1 \ket{100} =-\ket{100}$ and $Z _0 Z_1 \ket{011} =-\ket{011}$，因此測量 $Z _0 Z_1 $ 的結果，會顯示有關發生錯誤的實用資訊。</span><span class="sxs-lookup"><span data-stu-id="d4029-139">On the other hand, $Z_0 Z_1 \ket{100} = - \ket{100}$ and $Z_0 Z_1 \ket{011} = -\ket{011}$, so the result of measuring $Z_0 Z_1$ reveals useful information about which error occurred.</span></span>

<span data-ttu-id="d4029-140">為了強調此情況，我們會重複上表，但在每個資料列上新增測量 $Z _0 Z_1 $ 和 $Z _1 Z_2 $ 的結果。</span><span class="sxs-lookup"><span data-stu-id="d4029-140">To emphasize this, we repeat the table above, but add the results of measuring $Z_0 Z_1$ and $Z_1 Z_2$ on each row.</span></span>
<span data-ttu-id="d4029-141">我們會以觀察到的 eigenvalue 正負號（$ + $ 或 $-$）來表示每個測量的結果，分別對應至 `Zero` 和 `One`的 Q # `Result` 值。</span><span class="sxs-lookup"><span data-stu-id="d4029-141">We denote the results of each measurement by the sign of the eigenvalue that is observed, either $+$ or $-$, corresponding to the Q# `Result` values of `Zero` and `One`, respectively.</span></span>

| <span data-ttu-id="d4029-142">錯誤 $E $</span><span class="sxs-lookup"><span data-stu-id="d4029-142">Error $E$</span></span> | <span data-ttu-id="d4029-143">$E \ket{\overline{0}} $</span><span class="sxs-lookup"><span data-stu-id="d4029-143">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="d4029-144">$E \ket{\overline{1}} $</span><span class="sxs-lookup"><span data-stu-id="d4029-144">$E\ket{\overline{1}}$</span></span> | <span data-ttu-id="d4029-145">$Z _0 Z_1 $ 的結果</span><span class="sxs-lookup"><span data-stu-id="d4029-145">Result of $Z_0 Z_1$</span></span> | <span data-ttu-id="d4029-146">$Z _1 Z_2 $ 的結果</span><span class="sxs-lookup"><span data-stu-id="d4029-146">Result of $Z_1 Z_2$</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="d4029-147">$ \boldone $</span><span class="sxs-lookup"><span data-stu-id="d4029-147">$\boldone$</span></span> | <span data-ttu-id="d4029-148">$ \ket{000}$</span><span class="sxs-lookup"><span data-stu-id="d4029-148">$\ket{000}$</span></span> | <span data-ttu-id="d4029-149">$ \ket{111}$</span><span class="sxs-lookup"><span data-stu-id="d4029-149">$\ket{111}$</span></span> | $+$ | $+$ |
| <span data-ttu-id="d4029-150">$X _0 $</span><span class="sxs-lookup"><span data-stu-id="d4029-150">$X_0$</span></span> | <span data-ttu-id="d4029-151">$ \ket{100}$</span><span class="sxs-lookup"><span data-stu-id="d4029-151">$\ket{100}$</span></span> | <span data-ttu-id="d4029-152">$ \ket{011}$</span><span class="sxs-lookup"><span data-stu-id="d4029-152">$\ket{011}$</span></span> | $-$ | $+$ |
| <span data-ttu-id="d4029-153">$X _1 $</span><span class="sxs-lookup"><span data-stu-id="d4029-153">$X_1$</span></span> | <span data-ttu-id="d4029-154">$ \ket{010}$</span><span class="sxs-lookup"><span data-stu-id="d4029-154">$\ket{010}$</span></span> | <span data-ttu-id="d4029-155">$ \ket{101}$</span><span class="sxs-lookup"><span data-stu-id="d4029-155">$\ket{101}$</span></span> | $-$ | $-$ |
| <span data-ttu-id="d4029-156">$X _2 $</span><span class="sxs-lookup"><span data-stu-id="d4029-156">$X_2$</span></span> | <span data-ttu-id="d4029-157">$ \ket{001}$</span><span class="sxs-lookup"><span data-stu-id="d4029-157">$\ket{001}$</span></span> | <span data-ttu-id="d4029-158">$ \ket{110}$</span><span class="sxs-lookup"><span data-stu-id="d4029-158">$\ket{110}$</span></span> | $+$ | $-$ |

<span data-ttu-id="d4029-159">因此，這兩個度量的結果會唯一判斷發生的位翻轉錯誤，但不會顯示我們所編碼之狀態的任何相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d4029-159">Thus, the results of the two measurements uniquely determines which bit-flip error occurred, but without revealing any information about which state we encoded.</span></span>
<span data-ttu-id="d4029-160">我們將這些結果稱為「*症狀*」，並參考將症狀對應到導致它復原的錯誤的*程式。*</span><span class="sxs-lookup"><span data-stu-id="d4029-160">We call these results a *syndrome*, and refer to the process of mapping a syndrome back to the error that caused it as *recovery*.</span></span>
<span data-ttu-id="d4029-161">特別是，我們強調復原是一種*傳統*的推斷程式，它會將發生的症狀視為其輸入，並傳回如何修正可能發生之任何錯誤的處方。</span><span class="sxs-lookup"><span data-stu-id="d4029-161">In particular, we emphasize that recovery is a *classical* inference procedure which takes as its input the syndrome which occurred, and returns a prescription for how to fix any errors that may have occurred.</span></span>

> [!NOTE]
> <span data-ttu-id="d4029-162">上述的位翻轉程式碼只能針對單一的位翻轉錯誤進行更正;也就是在單一 qubit 上運作的 `X` 作業。</span><span class="sxs-lookup"><span data-stu-id="d4029-162">The bit-flip code above can only correct against single bit-flip errors; that is, an `X` operation acting on a single qubit.</span></span>
> <span data-ttu-id="d4029-163">將 `X` 套用至一個以上的 qubit 會在復原後，將 $ \ket{\overline{0}} $ 對應到 $ \ket{\overline{1}} $。</span><span class="sxs-lookup"><span data-stu-id="d4029-163">Applying `X` to more than one qubit will map $\ket{\overline{0}}$ to $\ket{\overline{1}}$ following recovery.</span></span>
> <span data-ttu-id="d4029-164">同樣地，套用階段翻轉作業 `Z` 會將 $ \ket{\overline{1}} $ 對應至 $-\ket{\overline{1}} $，因此會將 $ \ket{\overline{+}} $ 對應至 $ \ket{\overline{-}} $。</span><span class="sxs-lookup"><span data-stu-id="d4029-164">Similarly, applying a phase flip operation `Z` will map $\ket{\overline{1}}$ to $-\ket{\overline{1}}$, and hence will map $\ket{\overline{+}}$ to $\ket{\overline{-}}$.</span></span>
> <span data-ttu-id="d4029-165">一般來說，可以建立代碼來處理較大的錯誤數目，以及處理 $Z $ 錯誤以及 $X $ 錯誤。</span><span class="sxs-lookup"><span data-stu-id="d4029-165">More generally, codes can be created to handle larger number of errors, and to handle $Z$ errors as well as $X$ errors.</span></span>

<span data-ttu-id="d4029-166">我們可以在對所有程式碼狀態採取相同方式的量子錯誤更正中描述度量的深入解析，就是穩定的*形式*的本質。</span><span class="sxs-lookup"><span data-stu-id="d4029-166">The insight that we can describe measurements in quantum error correction that act the same way on all code states, is the essence of the *stabilizer formalism*.</span></span>
<span data-ttu-id="d4029-167">Q # canon 提供了一個架構，可描述從穩定程式碼進行編碼和解碼，以及描述如何從錯誤中復原。</span><span class="sxs-lookup"><span data-stu-id="d4029-167">The Q# canon provides a framework for describing encoding into and decoding from stabilizer codes, and for describing how one recovers from errors.</span></span>
<span data-ttu-id="d4029-168">在本節中，我們會將此架構及其應用程式描述為一些簡單的量子錯誤更正代碼。</span><span class="sxs-lookup"><span data-stu-id="d4029-168">In this section, we describe this framework and its application to a few simple quantum error-correcting codes.</span></span>

> [!TIP]
> <span data-ttu-id="d4029-169">完整的穩定形式簡介已超出本節的範圍。</span><span class="sxs-lookup"><span data-stu-id="d4029-169">A full introduction to the stabilizer formalism is beyond the scope of this section.</span></span>
> <span data-ttu-id="d4029-170">我們參考讀者有興趣深入瞭解[Gottesman 2009](https://arxiv.org/abs/0904.2557)。</span><span class="sxs-lookup"><span data-stu-id="d4029-170">We refer readers interested in learning more to [Gottesman 2009](https://arxiv.org/abs/0904.2557).</span></span>

## <a name="representing-error-correcting-codes-in-q"></a><span data-ttu-id="d4029-171">代表 Q 中的錯誤修正代碼#</span><span class="sxs-lookup"><span data-stu-id="d4029-171">Representing Error Correcting Codes in Q#</span></span> ##

<span data-ttu-id="d4029-172">為了協助指定錯誤更正代碼，Q # canon 會提供數個不同的使用者定義類型：</span><span class="sxs-lookup"><span data-stu-id="d4029-172">To help specify error correcting codes, the Q# canon provides several distinct user-defined types:</span></span>

- <span data-ttu-id="d4029-173"><xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`：表示 qubits 的暫存器應解讀為錯誤更正程式碼的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="d4029-173"><xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: Denotes that a register of qubits should be interpreted as the code block of an error-correcting code.</span></span>
- <span data-ttu-id="d4029-174"><xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`：表示測量結果的陣列應解讀為在程式碼區塊上測量的症狀。</span><span class="sxs-lookup"><span data-stu-id="d4029-174"><xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: Denotes that an array of measurement results should be interpreted as the syndrome measured on a code block.</span></span>
- <span data-ttu-id="d4029-175"><xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`：表示應該使用*傳統*函數來解讀症狀，並傳回應套用的更正。</span><span class="sxs-lookup"><span data-stu-id="d4029-175"><xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: Denotes that a *classical* function should be used to interpret a syndrome and return a correction that should be applied.</span></span>
- <span data-ttu-id="d4029-176"><xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`：表示作業會使用 qubits 來代表資料和全新的 ancilla qubits，以便產生錯誤更正程式碼的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="d4029-176"><xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: Denotes that an operation takes qubits representing data along with fresh ancilla qubits in order to produce a code block of an error-correcting code.</span></span>
- <span data-ttu-id="d4029-177"><xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`：表示作業會 decompose 的程式碼區塊將錯誤修正為數據 qubits，以及用來代表症狀資訊的 ancilla qubits。</span><span class="sxs-lookup"><span data-stu-id="d4029-177"><xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: Denotes than an operation decomposes a code block of an error correcting code into the data qubits and the ancilla qubits used to represent syndrome information.</span></span>
- <span data-ttu-id="d4029-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`：代表應該用來從程式碼區塊中解壓縮症狀資訊的作業，而不會影響程式碼所保護的狀態。</span><span class="sxs-lookup"><span data-stu-id="d4029-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: Denotes an operation that should be used to extract syndrome information from a code block, without disturbing the state protected by the code.</span></span>

<span data-ttu-id="d4029-179">最後，canon 會提供 <xref:microsoft.quantum.errorcorrection.qecc> 類型，以收集定義配量錯誤更正程式碼所需的其他類型。</span><span class="sxs-lookup"><span data-stu-id="d4029-179">Finally, the canon provides the <xref:microsoft.quantum.errorcorrection.qecc> type to collect the other types required to define a quantum error-correcting code.</span></span> <span data-ttu-id="d4029-180">與每個穩定配量代碼相關聯的程式碼長度 $n $、邏輯 qubits 的 $k $，以及 $d $ 的最小距離，通常會以標記法⟦ $n $，$k $，$d $ ⟧中，以方便群組在一起。</span><span class="sxs-lookup"><span data-stu-id="d4029-180">Associated with each stabilizer quantum code is the code length $n$, the number $k$ of logical qubits, and the minimum distance $d$, often conveniently grouped together in the notation ⟦$n$, $k$, $d$⟧.</span></span> <span data-ttu-id="d4029-181">例如，<xref:microsoft.quantum.errorcorrection.bitflipcode> 函式會定義⟦3，1，1⟧位翻轉程式碼：</span><span class="sxs-lookup"><span data-stu-id="d4029-181">For example, the <xref:microsoft.quantum.errorcorrection.bitflipcode> function defines the ⟦3, 1, 1⟧ bit flip code:</span></span>

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

<span data-ttu-id="d4029-182">請注意，`QECC` 類型不*包含復原*功能。</span><span class="sxs-lookup"><span data-stu-id="d4029-182">Notice that the `QECC` type does *not* include a recovery function.</span></span>
<span data-ttu-id="d4029-183">這可讓我們變更用於更正錯誤的復原功能，而不需變更程式碼本身的定義;這項功能特別適用于將特性度量的意見反應納入復原所假設的模型中。</span><span class="sxs-lookup"><span data-stu-id="d4029-183">This allows us to change the recovery function that is used in correcting errors without changing the definition of the code itself; this ability is in particular useful when incorporating feedback from characterization measurements into the model assumed by recovery.</span></span>

<span data-ttu-id="d4029-184">以這種方式定義程式碼之後，我們可以使用 <xref:microsoft.quantum.errorcorrection.recover> 作業從錯誤中復原：</span><span class="sxs-lookup"><span data-stu-id="d4029-184">Once a code is defined in this way, we can use the <xref:microsoft.quantum.errorcorrection.recover> operation to recover from errors:</span></span>

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

<span data-ttu-id="d4029-185">我們會在[位翻轉程式碼範例](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)中更詳細地探索此功能。</span><span class="sxs-lookup"><span data-stu-id="d4029-185">We explore this in more detail in the [bit flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code).</span></span>

<span data-ttu-id="d4029-186">除了比對程式碼之外，還提供了[五個 qubit 完美程式](https://arxiv.org/abs/quant-ph/9602019)代碼的 canon，以及[七 qubit 的程式碼](https://arxiv.org/abs/quant-ph/9705052)，兩者都可以更正任意的單一 qubit 錯誤。</span><span class="sxs-lookup"><span data-stu-id="d4029-186">Aside from the bit-flip code, the Q# canon is provided with implementations of the [five-qubit perfect code](https://arxiv.org/abs/quant-ph/9602019), and the [seven-qubit code](https://arxiv.org/abs/quant-ph/9705052), both of which can correct an arbitrary single-qubit error.</span></span>
