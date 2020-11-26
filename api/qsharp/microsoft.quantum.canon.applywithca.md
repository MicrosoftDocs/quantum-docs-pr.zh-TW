---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: e86c452e9693c5a4d0d4e5a36471ab46bbf66dfe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208137"
---
# <a name="applywithca-operation"></a><span data-ttu-id="db100-102">ApplyWithCA 操作</span><span class="sxs-lookup"><span data-stu-id="db100-102">ApplyWithCA operation</span></span>

<span data-ttu-id="db100-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db100-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db100-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db100-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db100-105">假設有兩個作業，請將其套用為另一個作業的 conjugated。</span><span class="sxs-lookup"><span data-stu-id="db100-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="db100-106">描述</span><span class="sxs-lookup"><span data-stu-id="db100-106">Description</span></span>

<span data-ttu-id="db100-107">假設有兩個作業，分別由單一運算子 $U $ 和 $V $，則會以 $U ^ {\dagger} V U $ 的順序套用。</span><span class="sxs-lookup"><span data-stu-id="db100-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="db100-108">也就是說，這項作業會透過 $U $ conjugated，來實 $V $ 所指定的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="db100-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="db100-109">輸入</span><span class="sxs-lookup"><span data-stu-id="db100-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="db100-110">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="db100-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="db100-111">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="db100-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="db100-112">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="db100-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="db100-113">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="db100-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="db100-114">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="db100-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="db100-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="db100-115">target : 'T</span></span>

<span data-ttu-id="db100-116">要提供給外部和內部作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="db100-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db100-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db100-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db100-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="db100-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db100-119">不要</span><span class="sxs-lookup"><span data-stu-id="db100-119">'T</span></span>

<span data-ttu-id="db100-120">每個內部和外部作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="db100-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="db100-121">備註</span><span class="sxs-lookup"><span data-stu-id="db100-121">Remarks</span></span>

<span data-ttu-id="db100-122">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="db100-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="db100-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="db100-123">See Also</span></span>

- [<span data-ttu-id="db100-124">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="db100-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="db100-125">Canon. ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="db100-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="db100-126">Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="db100-126">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)