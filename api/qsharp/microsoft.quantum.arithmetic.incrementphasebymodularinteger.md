---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699846"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="8ad7d-102">IncrementPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="8ad7d-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="8ad7d-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8ad7d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8ad7d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ad7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ad7d-105">以整數常數執行量子位暫存器的模組化增量。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="8ad7d-106">描述</span><span class="sxs-lookup"><span data-stu-id="8ad7d-106">Description</span></span>

<span data-ttu-id="8ad7d-107">讓我們以 `increment` $a $）來表示， `modulus` $N $ 和以 $y $ 編碼的整數 `target` 。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="8ad7d-108">然後，此作業會執行下列轉換： \begin{align} \ket{y} \mapsto \ket{ (y + a) \operatorname{mod} N} \end{align} 整數以為基礎的位元組由大到小的格式進行編碼。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="8ad7d-109">輸入</span><span class="sxs-lookup"><span data-stu-id="8ad7d-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="8ad7d-110">遞增： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ad7d-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ad7d-111">要加入 $y $ 的整數遞增 $a $。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="8ad7d-112">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ad7d-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ad7d-113">Mods > $y + a $ 的整數 $N $。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="8ad7d-114">目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8ad7d-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="8ad7d-115">整數 $y $ in 階段編碼的位元組由大到小的格式， `increment` $a $ 新增至。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ad7d-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ad7d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8ad7d-117">備註</span><span class="sxs-lookup"><span data-stu-id="8ad7d-117">Remarks</span></span>

<span data-ttu-id="8ad7d-118">假設 `target` 最大位設定為0。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="8ad7d-119">也假設目標的值小於 $N $。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="8ad7d-120">如需電路圖和說明，請參閱 [arXiv： quant-ph/0205095V3 第5頁](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5)上的圖5。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ad7d-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8ad7d-121">See Also</span></span>

- [<span data-ttu-id="8ad7d-122">IncrementByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="8ad7d-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)