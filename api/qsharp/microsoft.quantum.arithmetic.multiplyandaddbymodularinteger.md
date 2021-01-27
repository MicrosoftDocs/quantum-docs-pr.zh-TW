---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846507"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="8867c-102">MultiplyAndAddByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="8867c-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="8867c-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8867c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8867c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8867c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8867c-105">在量子位暫存器上，以整數常數執行模組化乘法和 add。</span><span class="sxs-lookup"><span data-stu-id="8867c-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8867c-106">描述</span><span class="sxs-lookup"><span data-stu-id="8867c-106">Description</span></span>

<span data-ttu-id="8867c-107">針對指定的模數，將 map $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{ (b + a \cdot x) \operatorname{mod} N} \end{align} $ $ $N $、常數乘數 $a $ 和被加數 $y $。</span><span class="sxs-lookup"><span data-stu-id="8867c-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="8867c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="8867c-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="8867c-109">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8867c-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8867c-110">要加入至每個基礎狀態標籤的 $a $ 的整數。</span><span class="sxs-lookup"><span data-stu-id="8867c-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="8867c-111">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8867c-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8867c-112">模數 $N $ 所採用的加法和乘法。</span><span class="sxs-lookup"><span data-stu-id="8867c-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="8867c-113">乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8867c-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8867c-114">代表不帶正負號整數的量子暫存器，其值要加入至的每個基礎狀態標籤 `summand` 。</span><span class="sxs-lookup"><span data-stu-id="8867c-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="8867c-115">被加數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8867c-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8867c-116">量子暫存器，代表要作為此作業目標的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="8867c-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8867c-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8867c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8867c-118">備註</span><span class="sxs-lookup"><span data-stu-id="8867c-118">Remarks</span></span>

- <span data-ttu-id="8867c-119">如需電路圖和說明，請參閱[arXiv： quant-ph/0205095V3 頁面 7](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)上的圖6</span><span class="sxs-lookup"><span data-stu-id="8867c-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="8867c-120">此作業對應于 CMULT () MOD (N) 在 [arXiv： quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="8867c-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="8867c-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8867c-121">See Also</span></span>

- [<span data-ttu-id="8867c-122">MultiplyAndAddPhaseByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="8867c-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)