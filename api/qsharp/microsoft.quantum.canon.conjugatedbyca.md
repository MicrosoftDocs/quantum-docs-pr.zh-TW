---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 54301f991d3bda14e2d2a0a6837ee89d299f2e04
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840822"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="896ec-102">ConjugatedByCA 函式</span><span class="sxs-lookup"><span data-stu-id="896ec-102">ConjugatedByCA function</span></span>

<span data-ttu-id="896ec-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="896ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="896ec-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="896ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="896ec-105">指定外部和內部作業時，會傳回由外部作業 conjugates 內部作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="896ec-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="896ec-106">輸入</span><span class="sxs-lookup"><span data-stu-id="896ec-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="896ec-107">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="896ec-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="896ec-108">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="896ec-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="896ec-109">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="896ec-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj--ctl"></a><span data-ttu-id="896ec-110">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="896ec-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="896ec-111">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="896ec-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="896ec-112">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="896ec-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="896ec-113">由單一 $U ^ {\dagger} V U $ 表示其動作的新作業。</span><span class="sxs-lookup"><span data-stu-id="896ec-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="896ec-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="896ec-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="896ec-115">不要</span><span class="sxs-lookup"><span data-stu-id="896ec-115">'T</span></span>

<span data-ttu-id="896ec-116">每個內部和外部作業作用所在的目標型別。</span><span class="sxs-lookup"><span data-stu-id="896ec-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="896ec-117">備註</span><span class="sxs-lookup"><span data-stu-id="896ec-117">Remarks</span></span>

<span data-ttu-id="896ec-118">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="896ec-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="896ec-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="896ec-119">See Also</span></span>

- [<span data-ttu-id="896ec-120">Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="896ec-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="896ec-121">Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="896ec-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="896ec-122">Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="896ec-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="896ec-123">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="896ec-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)