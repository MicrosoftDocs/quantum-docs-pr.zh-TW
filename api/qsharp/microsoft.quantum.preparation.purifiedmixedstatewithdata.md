---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229948"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="e799b-102">PurifiedMixedStateWithData 函式</span><span class="sxs-lookup"><span data-stu-id="e799b-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="e799b-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e799b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e799b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e799b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e799b-105">傳回作業，此作業會準備指定混合狀態的淨化，並以代表指定資料集合的暫存器纏結。</span><span class="sxs-lookup"><span data-stu-id="e799b-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="e799b-106">「具有資料的 purified 混合狀態」指的是表單Σi √ pi | i ⟩ | xi ⟩ | garbagei ⟩的狀態，其中每個 xi 都是 bitstring 編碼的額外資料 | i ⟩。</span><span class="sxs-lookup"><span data-stu-id="e799b-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="e799b-107"> https://arxiv.org/pdf/1805.03662.pdf?page=15如需進一步討論，請參閱。</span><span class="sxs-lookup"><span data-stu-id="e799b-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="e799b-108">描述</span><span class="sxs-lookup"><span data-stu-id="e799b-108">Description</span></span>

<span data-ttu-id="e799b-109">使用量子 ROM 技術來代表指定的密度矩陣，並以狀態準備作業傳回該標記法。</span><span class="sxs-lookup"><span data-stu-id="e799b-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="e799b-110">尤其是，假設有一份 $N $ 係數 $ \ Alpha_j $，以及 _與每個係數相關聯的 bitstring $ \vec{x} j $。此函式會傳回使用量子 ROM 技術的作業，以準備近似值 $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {n-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ （混合狀態 $ $ \begin{align} \rho = \sum_{j = 0} ^ {n-1} \ frac {| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}、\end{align} $ $，其中每個 $p _j $ 是指定係數 $ \ Alpha_j $ 的近似值，例如 $ $ \begin{align} \left |p_j-\frac{| \ Alpha_j |}{\ sum_k | \ Alpha_k |}每個 $j $ 的 \le \frac{\epsilon}{N} \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="e799b-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="e799b-111">傳遞索引暫存器和垃圾量子位註冊時，一開始在 state $ \ket {0} \ket{00\cdots 0} 中，傳回的作業會將兩個暫存器準備入淨化 of $ \tilde \rho $、$ $ \begin{align} \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}、\end{align} $ $，以便重設和解除配置垃圾註冊制定在目標錯誤 $ \epsilon $ 中所需的準備。</span><span class="sxs-lookup"><span data-stu-id="e799b-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="e799b-112">輸入</span><span class="sxs-lookup"><span data-stu-id="e799b-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e799b-113">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e799b-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e799b-114">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="e799b-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="e799b-115">係數： ([Double](xref:microsoft.quantum.lang-ref.double)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) []</span><span class="sxs-lookup"><span data-stu-id="e799b-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="e799b-116">$N $ 係數的陣列，用來指定基礎狀態的機率，以及與每個係數相關聯的 bitstring $ \vec{x} _j $。</span><span class="sxs-lookup"><span data-stu-id="e799b-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="e799b-117">負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="e799b-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="e799b-118">輸出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="e799b-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="e799b-119">一種作業，會將 $ \tilde \rho $ 做為淨化的聯結，以做為聯合索引和垃圾登錄的。</span><span class="sxs-lookup"><span data-stu-id="e799b-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="e799b-120">備註</span><span class="sxs-lookup"><span data-stu-id="e799b-120">Remarks</span></span>

<span data-ttu-id="e799b-121">提供給這項作業的係數會以1個標準的形式正規化，讓係數一律視為描述有效的類別機率分佈。</span><span class="sxs-lookup"><span data-stu-id="e799b-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="e799b-122">參考</span><span class="sxs-lookup"><span data-stu-id="e799b-122">References</span></span>

- <span data-ttu-id="e799b-123">使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e799b-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="e799b-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e799b-124">See Also</span></span>

- [<span data-ttu-id="e799b-125">PurifiedMixedState。</span><span class="sxs-lookup"><span data-stu-id="e799b-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)