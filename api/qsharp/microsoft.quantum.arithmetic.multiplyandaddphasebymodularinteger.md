---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699577"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="5baa4-102">MultiplyAndAddPhaseByModularInteger 操作</span><span class="sxs-lookup"><span data-stu-id="5baa4-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="5baa4-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5baa4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5baa4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5baa4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5baa4-105">與 MultiplyAndAddByModularInteger 相同，但假設被加數會以 QFT 為基礎來編碼整數。</span><span class="sxs-lookup"><span data-stu-id="5baa4-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="5baa4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5baa4-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="5baa4-107">constMultiplier： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5baa4-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5baa4-108">要加入至每個基礎狀態標籤的 $a $ 的整數。</span><span class="sxs-lookup"><span data-stu-id="5baa4-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="5baa4-109">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5baa4-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5baa4-110">模數 $N $ 所採用的加法和乘法。</span><span class="sxs-lookup"><span data-stu-id="5baa4-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="5baa4-111">乘數： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5baa4-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5baa4-112">代表不帶正負號整數的量子暫存器，其值要加入至的每個基礎狀態標籤 `summand` 。</span><span class="sxs-lookup"><span data-stu-id="5baa4-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="5baa4-113">phaseSummand： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5baa4-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="5baa4-114">量子暫存器，代表要作為此作業目標的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="5baa4-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5baa4-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5baa4-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5baa4-116">備註</span><span class="sxs-lookup"><span data-stu-id="5baa4-116">Remarks</span></span>

<span data-ttu-id="5baa4-117">假設 `phaseSummand` 最大位設定為0。</span><span class="sxs-lookup"><span data-stu-id="5baa4-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="5baa4-118">也假設的值 `phaseSummand` 小於 $N $。</span><span class="sxs-lookup"><span data-stu-id="5baa4-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="5baa4-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5baa4-119">See Also</span></span>

- [<span data-ttu-id="5baa4-120">MultiplyAndAddByModularInteger。</span><span class="sxs-lookup"><span data-stu-id="5baa4-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)