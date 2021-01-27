---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: ApplyWithC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 393db9f8ce092100abc157ace1ee9fbbb3b06d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850398"
---
# <a name="applywithc-operation"></a><span data-ttu-id="28c48-102">ApplyWithC 操作</span><span class="sxs-lookup"><span data-stu-id="28c48-102">ApplyWithC operation</span></span>

<span data-ttu-id="28c48-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28c48-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28c48-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28c48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28c48-105">假設有兩個作業，請將其套用為另一個作業的 conjugated。</span><span class="sxs-lookup"><span data-stu-id="28c48-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="28c48-106">描述</span><span class="sxs-lookup"><span data-stu-id="28c48-106">Description</span></span>

<span data-ttu-id="28c48-107">假設有兩個作業，分別由單一運算子 $U $ 和 $V $，則會以 $U ^ {\dagger} V U $ 的順序套用。</span><span class="sxs-lookup"><span data-stu-id="28c48-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="28c48-108">也就是說，這項作業會透過 $U $ conjugated，來實 $V $ 所指定的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="28c48-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="28c48-109">輸入</span><span class="sxs-lookup"><span data-stu-id="28c48-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="28c48-110">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="28c48-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="28c48-111">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="28c48-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="28c48-112">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="28c48-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-ctl"></a><span data-ttu-id="28c48-113">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="28c48-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="28c48-114">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="28c48-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="28c48-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="28c48-115">target : 'T</span></span>

<span data-ttu-id="28c48-116">要提供給外部和內部作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="28c48-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28c48-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28c48-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28c48-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="28c48-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28c48-119">不要</span><span class="sxs-lookup"><span data-stu-id="28c48-119">'T</span></span>

<span data-ttu-id="28c48-120">每個內部和外部作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="28c48-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="28c48-121">備註</span><span class="sxs-lookup"><span data-stu-id="28c48-121">Remarks</span></span>

<span data-ttu-id="28c48-122">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="28c48-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="28c48-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28c48-123">See Also</span></span>

- [<span data-ttu-id="28c48-124">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="28c48-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="28c48-125">Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="28c48-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="28c48-126">Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="28c48-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)