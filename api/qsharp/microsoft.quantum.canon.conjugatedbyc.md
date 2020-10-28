---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c4c381e40c5a941487bcf78ebe5339574aedb45d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699061"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="1b8e9-102">ConjugatedByC 函式</span><span class="sxs-lookup"><span data-stu-id="1b8e9-102">ConjugatedByC function</span></span>

<span data-ttu-id="1b8e9-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b8e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b8e9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b8e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b8e9-105">指定外部和內部作業時，會傳回由外部作業 conjugates 內部作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="1b8e9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1b8e9-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="1b8e9-107">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="1b8e9-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1b8e9-108">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="1b8e9-109">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="1b8e9-110">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="1b8e9-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="1b8e9-111">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="1b8e9-112">Output： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="1b8e9-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="1b8e9-113">由單一 $U ^ {\dagger} V U $ 表示其動作的新作業。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b8e9-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="1b8e9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b8e9-115">不要</span><span class="sxs-lookup"><span data-stu-id="1b8e9-115">'T</span></span>

<span data-ttu-id="1b8e9-116">每個內部和外部作業作用所在的目標型別。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b8e9-117">備註</span><span class="sxs-lookup"><span data-stu-id="1b8e9-117">Remarks</span></span>

<span data-ttu-id="1b8e9-118">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="1b8e9-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b8e9-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1b8e9-119">See Also</span></span>

- [<span data-ttu-id="1b8e9-120">Canon. ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="1b8e9-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="1b8e9-121">Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="1b8e9-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="1b8e9-122">Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="1b8e9-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="1b8e9-123">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="1b8e9-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)