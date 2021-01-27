---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843155"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="c40c6-102">IncrementPhaseByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="c40c6-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="c40c6-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c40c6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c40c6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c40c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c40c6-105">使用階段旋轉，以傳統整數遞增未簽署的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="c40c6-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c40c6-106">描述</span><span class="sxs-lookup"><span data-stu-id="c40c6-106">Description</span></span>

<span data-ttu-id="c40c6-107">假設將 `target` 不帶正負號的整數編碼 $x $ 以位元組由小到大的編碼方式，且 `increment` 等於 $a $。</span><span class="sxs-lookup"><span data-stu-id="c40c6-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="c40c6-108">然後，這項作業會執行單一 $ \ket{x} \mapsto \ket{x + a} $，其中加法會執行模數 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。</span><span class="sxs-lookup"><span data-stu-id="c40c6-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="c40c6-109">輸入</span><span class="sxs-lookup"><span data-stu-id="c40c6-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="c40c6-110">遞增： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c40c6-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c40c6-111">用來遞增的整數 `target` 。</span><span class="sxs-lookup"><span data-stu-id="c40c6-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="c40c6-112">目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c40c6-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="c40c6-113">量子暫存器會以雙重 (QFT) 基礎，使用位元組由大到小的編碼方式來編碼不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="c40c6-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c40c6-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c40c6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c40c6-115">備註</span><span class="sxs-lookup"><span data-stu-id="c40c6-115">Remarks</span></span>

<span data-ttu-id="c40c6-116">請注意，我們已簡化電路，因為遞增是傳統的常數，而不是量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="c40c6-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="c40c6-117">請參閱 [ arXiv： quant-ph/0008033v1 的第6頁 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) 中的圖表，以取得路線圖和說明。</span><span class="sxs-lookup"><span data-stu-id="c40c6-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="c40c6-118">參考資料</span><span class="sxs-lookup"><span data-stu-id="c40c6-118">References</span></span>

- [<span data-ttu-id="c40c6-119">*Thomas G. Draper*、arXiv： quant-ph/0008033</span><span class="sxs-lookup"><span data-stu-id="c40c6-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="c40c6-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c40c6-120">See Also</span></span>

- [<span data-ttu-id="c40c6-121">IncrementByInteger。</span><span class="sxs-lookup"><span data-stu-id="c40c6-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)