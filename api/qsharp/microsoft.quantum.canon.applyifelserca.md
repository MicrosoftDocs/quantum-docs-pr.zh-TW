---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: c48d75323f036ebce1a316382a05cd2578db47a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699297"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="db7a3-102">ApplyIfElseRCA 操作</span><span class="sxs-lookup"><span data-stu-id="db7a3-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="db7a3-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db7a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db7a3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db7a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db7a3-105">根據傳統結果的值，套用兩個單一作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="db7a3-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="db7a3-106">描述</span><span class="sxs-lookup"><span data-stu-id="db7a3-106">Description</span></span>

<span data-ttu-id="db7a3-107">因此 `result` ， `zeroOp` `zeroInput` 當等於時，會將作業套用至做為其輸入， `result` `Zero` 並適用 `oneOp(oneInput)` 于 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="db7a3-108">輸入</span><span class="sxs-lookup"><span data-stu-id="db7a3-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="db7a3-109">結果： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="db7a3-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="db7a3-110">用來判斷是否已套用或的測量結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-adj--ctl"></a><span data-ttu-id="db7a3-111">zeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="db7a3-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="db7a3-112">要在其上套用的單一作業 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="db7a3-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="db7a3-113">zeroInput : 'T</span></span>

<span data-ttu-id="db7a3-114">要在何時提供的輸入 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-adj--ctl"></a><span data-ttu-id="db7a3-115">oneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="db7a3-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="db7a3-116">要在其上套用的單一作業 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="db7a3-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="db7a3-117">oneInput : 'U</span></span>

<span data-ttu-id="db7a3-118">要在何時提供的輸入 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db7a3-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db7a3-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db7a3-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="db7a3-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db7a3-121">不要</span><span class="sxs-lookup"><span data-stu-id="db7a3-121">'T</span></span>

<span data-ttu-id="db7a3-122">要有條件地套用之作業的輸入類型 `zeroOp` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="db7a3-123">' U</span><span class="sxs-lookup"><span data-stu-id="db7a3-123">'U</span></span>

<span data-ttu-id="db7a3-124">要有條件地套用之作業的輸入類型 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="db7a3-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="db7a3-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="db7a3-125">See Also</span></span>

- [<span data-ttu-id="db7a3-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="db7a3-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="db7a3-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="db7a3-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="db7a3-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="db7a3-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="db7a3-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="db7a3-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="db7a3-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="db7a3-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)