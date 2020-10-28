---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: ConjugatedByCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699060"
---
# <a name="conjugatedbyca-function"></a><span data-ttu-id="4e204-102">ConjugatedByCA 函式</span><span class="sxs-lookup"><span data-stu-id="4e204-102">ConjugatedByCA function</span></span>

<span data-ttu-id="4e204-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e204-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e204-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e204-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e204-105">指定外部和內部作業時，會傳回由外部作業 conjugates 內部作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="4e204-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4e204-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4e204-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="4e204-107">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="4e204-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4e204-108">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="4e204-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="4e204-109">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="4e204-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-adj--ctl"></a><span data-ttu-id="4e204-110">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4e204-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4e204-111">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="4e204-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="4e204-112">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4e204-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4e204-113">由單一 $U ^ {\dagger} V U $ 表示其動作的新作業。</span><span class="sxs-lookup"><span data-stu-id="4e204-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4e204-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="4e204-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e204-115">不要</span><span class="sxs-lookup"><span data-stu-id="4e204-115">'T</span></span>

<span data-ttu-id="4e204-116">每個內部和外部作業作用所在的目標型別。</span><span class="sxs-lookup"><span data-stu-id="4e204-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e204-117">備註</span><span class="sxs-lookup"><span data-stu-id="4e204-117">Remarks</span></span>

<span data-ttu-id="4e204-118">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="4e204-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e204-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4e204-119">See Also</span></span>

- [<span data-ttu-id="4e204-120">Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="4e204-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="4e204-121">Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="4e204-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="4e204-122">Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="4e204-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="4e204-123">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="4e204-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)