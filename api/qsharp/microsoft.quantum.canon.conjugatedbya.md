---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: ConjugatedByA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: eaa104039b857f0469ddc0aaba97698eca20860d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207338"
---
# <a name="conjugatedbya-function"></a><span data-ttu-id="d97ee-102">ConjugatedByA 函式</span><span class="sxs-lookup"><span data-stu-id="d97ee-102">ConjugatedByA function</span></span>

<span data-ttu-id="d97ee-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d97ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d97ee-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d97ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d97ee-105">指定外部和內部作業時，會傳回由外部作業 conjugates 內部作業的新作業。</span><span class="sxs-lookup"><span data-stu-id="d97ee-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="d97ee-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d97ee-106">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="d97ee-107">outerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="d97ee-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d97ee-108">作業 $U $，其應用於共軛 $V $。</span><span class="sxs-lookup"><span data-stu-id="d97ee-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="d97ee-109">請注意，$U $ 的外部作業需要 adjointable，但不需要是可控制的。</span><span class="sxs-lookup"><span data-stu-id="d97ee-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="d97ee-110">innerOperation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="d97ee-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d97ee-111">作業 $V $ 正在 conjugated。</span><span class="sxs-lookup"><span data-stu-id="d97ee-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="d97ee-112">輸出： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="d97ee-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d97ee-113">由單一 $U ^ {\dagger} V U $ 表示其動作的新作業。</span><span class="sxs-lookup"><span data-stu-id="d97ee-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d97ee-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="d97ee-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d97ee-115">不要</span><span class="sxs-lookup"><span data-stu-id="d97ee-115">'T</span></span>

<span data-ttu-id="d97ee-116">每個內部和外部作業作用所在的目標型別。</span><span class="sxs-lookup"><span data-stu-id="d97ee-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="d97ee-117">備註</span><span class="sxs-lookup"><span data-stu-id="d97ee-117">Remarks</span></span>

<span data-ttu-id="d97ee-118">外部作業一律會假設為 adjointable，但不需要進行控制，才能讓合併作業成為可控制的。</span><span class="sxs-lookup"><span data-stu-id="d97ee-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="d97ee-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d97ee-119">See Also</span></span>

- [<span data-ttu-id="d97ee-120">Canon. ConjugatedByA</span><span class="sxs-lookup"><span data-stu-id="d97ee-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="d97ee-121">Canon. ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="d97ee-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="d97ee-122">Canon. ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="d97ee-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="d97ee-123">Canon. ApplyWith</span><span class="sxs-lookup"><span data-stu-id="d97ee-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)