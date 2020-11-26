---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230016"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="75ce9-102">PurifiedMixedState 函式</span><span class="sxs-lookup"><span data-stu-id="75ce9-102">PurifiedMixedState function</span></span>

<span data-ttu-id="75ce9-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="75ce9-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="75ce9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75ce9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75ce9-105">傳回準備指定混合狀態之淨化的作業。</span><span class="sxs-lookup"><span data-stu-id="75ce9-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="75ce9-106">「Purified 混合狀態」指的是由係數 {pi} 所指定的表單 | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩的狀態。</span><span class="sxs-lookup"><span data-stu-id="75ce9-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="75ce9-107">此表單的狀態可以縮減為混合狀態ρ≔ pi | i ⟩⟨ i |藉由追蹤「垃圾」註冊 (也就是在計算基礎中為對角的混合狀態) 。</span><span class="sxs-lookup"><span data-stu-id="75ce9-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="75ce9-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15如需進一步討論，請參閱。</span><span class="sxs-lookup"><span data-stu-id="75ce9-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="75ce9-109">描述</span><span class="sxs-lookup"><span data-stu-id="75ce9-109">Description</span></span>

<span data-ttu-id="75ce9-110">使用量子 ROM 技術來代表指定的密度矩陣，並以狀態準備作業傳回該標記法。</span><span class="sxs-lookup"><span data-stu-id="75ce9-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="75ce9-111">尤其是，假設有一個 $N $ 係數 $ \ Alpha_j $ 的清單，此函式會傳回使用量子 ROM 技術的作業，以準備近似值 $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ （混合狀態 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1-1} \ frac {| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j}、\end{align} $ $，其中每個 $p _j $ 是指定係數 $ \ Alpha_j $ 的近似值，例如 $ $ \begin{align} \left |p_j-\frac{| \ Alpha_j |}{\ sum_k | \ Alpha_k |}每個 $j $ 的 \le \frac{\epsilon}{N} \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="75ce9-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="75ce9-112">傳遞索引暫存器和垃圾量子位註冊時，一開始在 state $ \ket {0} \ket{00\cdots 0} 中，傳回的作業會將兩個暫存器準備入淨化 of $ \tilde \rho $、$ $ \begin{align} \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}、\end{align} $ $，以便重設和解除配置垃圾註冊制定在目標錯誤 $ \epsilon $ 中所需的準備工作。</span><span class="sxs-lookup"><span data-stu-id="75ce9-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="75ce9-113">輸入</span><span class="sxs-lookup"><span data-stu-id="75ce9-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="75ce9-114">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="75ce9-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="75ce9-115">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="75ce9-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="75ce9-116">係數： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="75ce9-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="75ce9-117">$N $ 係數的陣列，指定基礎狀態的機率。</span><span class="sxs-lookup"><span data-stu-id="75ce9-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="75ce9-118">負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="75ce9-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="75ce9-119">輸出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="75ce9-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="75ce9-120">一種作業，會將 $ \tilde \rho $ 做為淨化的聯結，以做為聯合索引和垃圾登錄的。</span><span class="sxs-lookup"><span data-stu-id="75ce9-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="75ce9-121">備註</span><span class="sxs-lookup"><span data-stu-id="75ce9-121">Remarks</span></span>

<span data-ttu-id="75ce9-122">提供給這項作業的係數會以1個標準的形式正規化，讓係數一律視為描述有效的類別機率分佈。</span><span class="sxs-lookup"><span data-stu-id="75ce9-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="75ce9-123">參考</span><span class="sxs-lookup"><span data-stu-id="75ce9-123">References</span></span>

- <span data-ttu-id="75ce9-124">使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="75ce9-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="75ce9-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="75ce9-125">See Also</span></span>

- [<span data-ttu-id="75ce9-126">PurifiedMixedStateWithData。</span><span class="sxs-lookup"><span data-stu-id="75ce9-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)