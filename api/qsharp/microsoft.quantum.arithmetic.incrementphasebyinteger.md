---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699851"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="b62e8-102">IncrementPhaseByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="b62e8-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="b62e8-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b62e8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b62e8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b62e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b62e8-105">使用階段旋轉，以傳統整數遞增未簽署的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="b62e8-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="b62e8-106">描述</span><span class="sxs-lookup"><span data-stu-id="b62e8-106">Description</span></span>

<span data-ttu-id="b62e8-107">假設將 `target` 不帶正負號的整數編碼 $x $ 以位元組由小到大的編碼方式，且 `increment` 等於 $a $。</span><span class="sxs-lookup"><span data-stu-id="b62e8-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="b62e8-108">然後，這項作業會執行單一 $ \ket{x} \mapsto \ket{x + a} $，其中加法會執行模數 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。</span><span class="sxs-lookup"><span data-stu-id="b62e8-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="b62e8-109">輸入</span><span class="sxs-lookup"><span data-stu-id="b62e8-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="b62e8-110">遞增： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b62e8-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b62e8-111">用來遞增的整數 `target` 。</span><span class="sxs-lookup"><span data-stu-id="b62e8-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="b62e8-112">目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b62e8-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="b62e8-113">量子暫存器會以雙重 (QFT) 基礎，使用位元組由大到小的編碼方式來編碼不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="b62e8-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b62e8-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b62e8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b62e8-115">備註</span><span class="sxs-lookup"><span data-stu-id="b62e8-115">Remarks</span></span>

<span data-ttu-id="b62e8-116">請注意，我們已簡化電路，因為遞增是傳統的常數，而不是量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="b62e8-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="b62e8-117">請參閱 [ arXiv： quant-ph/0008033v1 的第6頁 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) 中的圖表，以取得路線圖和說明。</span><span class="sxs-lookup"><span data-stu-id="b62e8-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="b62e8-118">參考</span><span class="sxs-lookup"><span data-stu-id="b62e8-118">References</span></span>

- [<span data-ttu-id="b62e8-119">*Thomas G. Draper* 、arXiv： quant-ph/0008033</span><span class="sxs-lookup"><span data-stu-id="b62e8-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="b62e8-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b62e8-120">See Also</span></span>

- [<span data-ttu-id="b62e8-121">IncrementByInteger。</span><span class="sxs-lookup"><span data-stu-id="b62e8-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)