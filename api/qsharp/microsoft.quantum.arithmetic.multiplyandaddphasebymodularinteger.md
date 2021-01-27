---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: b1214acc2cafc3fede9fcb6663a435c0b1d2cf4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843068"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="fe398-102">MultiplyAndAddPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="fe398-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="fe398-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fe398-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fe398-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe398-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe398-105">與 MultiplyAndAddByModularInteger 相同，但假設被加數會以 QFT 為基礎來編碼整數。</span><span class="sxs-lookup"><span data-stu-id="fe398-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe398-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fe398-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="fe398-107">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe398-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe398-108">要加入至每個基礎狀態標籤的 $a $ 的整數。</span><span class="sxs-lookup"><span data-stu-id="fe398-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="fe398-109">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe398-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe398-110">模數 $N $ 所採用的加法和乘法。</span><span class="sxs-lookup"><span data-stu-id="fe398-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="fe398-111">乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe398-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fe398-112">代表不帶正負號整數的量子暫存器，其值要加入至的每個基礎狀態標籤 `summand` 。</span><span class="sxs-lookup"><span data-stu-id="fe398-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="fe398-113">phaseSummand： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe398-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="fe398-114">量子暫存器，代表要作為此作業目標的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="fe398-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe398-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe398-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe398-116">備註</span><span class="sxs-lookup"><span data-stu-id="fe398-116">Remarks</span></span>

<span data-ttu-id="fe398-117">假設 `phaseSummand` 最大位設定為0。</span><span class="sxs-lookup"><span data-stu-id="fe398-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="fe398-118">也假設的值 `phaseSummand` 小於 $N $。</span><span class="sxs-lookup"><span data-stu-id="fe398-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe398-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fe398-119">See Also</span></span>

- [<span data-ttu-id="fe398-120">MultiplyAndAddByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="fe398-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)