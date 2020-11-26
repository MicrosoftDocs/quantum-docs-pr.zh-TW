---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: ApplyWithA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: b8847d4b3ddb88031ef360f183b86f6483706cc6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207865"
---
# <a name="applywitha-operation"></a><span data-ttu-id="28e58-102">ApplyWithA 操作</span><span class="sxs-lookup"><span data-stu-id="28e58-102">ApplyWithA operation</span></span>

<span data-ttu-id="28e58-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28e58-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28e58-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28e58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28e58-105">假設有兩個作業，請將其套用為另一個作業的 conjugated。</span><span class="sxs-lookup"><span data-stu-id="28e58-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="28e58-106">描述</span><span class="sxs-lookup"><span data-stu-id="28e58-106">Description</span></span>

<span data-ttu-id="28e58-107">假設有兩個作業，分別由單一運算子 $U $ 和 $V $，則會以 $U ^ {\dagger} V U $ 的順序套用。</span><span class="sxs-lookup"><span data-stu-id="28e58-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="28e58-108">也就是說，這項作業會透過 $U $ conjugated，來實 $V $ 所指定的單一運算子。</span><span class="sxs-lookup"><span data-stu-id="28e58-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="28e58-109">輸入</span><span class="sxs-lookup"><span data-stu-id="28e58-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="28e58-110">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="28e58-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="28e58-111">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="28e58-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="28e58-112">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="28e58-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="28e58-113">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="28e58-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="28e58-114">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="28e58-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="28e58-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="28e58-115">target : 'T</span></span>

<span data-ttu-id="28e58-116">要提供給外部和內部作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="28e58-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28e58-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28e58-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28e58-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="28e58-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28e58-119">不要</span><span class="sxs-lookup"><span data-stu-id="28e58-119">'T</span></span>

<span data-ttu-id="28e58-120">每個內部和外部作業作用所在的目標。</span><span class="sxs-lookup"><span data-stu-id="28e58-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="28e58-121">備註</span><span class="sxs-lookup"><span data-stu-id="28e58-121">Remarks</span></span>

<span data-ttu-id="28e58-122">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="28e58-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="28e58-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28e58-123">See Also</span></span>

- [<span data-ttu-id="28e58-124">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="28e58-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="28e58-125">Canon. ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="28e58-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="28e58-126">Canon. ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="28e58-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)