---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209480"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="9c977-102">ApplyIfElseRC 操作</span><span class="sxs-lookup"><span data-stu-id="9c977-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="9c977-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c977-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c977-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c977-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c977-105">根據傳統結果的值，套用兩個可控作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="9c977-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="9c977-106">描述</span><span class="sxs-lookup"><span data-stu-id="9c977-106">Description</span></span>

<span data-ttu-id="9c977-107">因此 `result` ， `zeroOp` `zeroInput` 當等於時，會將作業套用至做為其輸入， `result` `Zero` 並適用 `oneOp(oneInput)` 于 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="9c977-108">輸入</span><span class="sxs-lookup"><span data-stu-id="9c977-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9c977-109">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9c977-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="9c977-110">用來判斷是否已套用或的測量結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="9c977-111">zeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="9c977-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9c977-112">要在其上套用的可控制作業 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="9c977-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="9c977-113">zeroInput : 'T</span></span>

<span data-ttu-id="9c977-114">要在何時提供的輸入 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="9c977-115">oneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="9c977-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9c977-116">要在其上套用的可控制作業 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="9c977-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="9c977-117">oneInput : 'U</span></span>

<span data-ttu-id="9c977-118">要在何時提供的輸入 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c977-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c977-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c977-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="9c977-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c977-121">不要</span><span class="sxs-lookup"><span data-stu-id="9c977-121">'T</span></span>

<span data-ttu-id="9c977-122">要有條件地套用之作業的輸入類型 `zeroOp` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="9c977-123">' U</span><span class="sxs-lookup"><span data-stu-id="9c977-123">'U</span></span>

<span data-ttu-id="9c977-124">要有條件地套用之作業的輸入類型 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="9c977-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c977-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9c977-125">See Also</span></span>

- [<span data-ttu-id="9c977-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="9c977-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="9c977-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="9c977-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="9c977-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="9c977-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="9c977-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="9c977-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="9c977-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="9c977-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)