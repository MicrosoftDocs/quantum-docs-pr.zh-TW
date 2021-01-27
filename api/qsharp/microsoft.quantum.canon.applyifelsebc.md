---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841828"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="e2842-102">ApplyIfElseBC 操作</span><span class="sxs-lookup"><span data-stu-id="e2842-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="e2842-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2842-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2842-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2842-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2842-105">根據傳統位的值，套用兩個可控作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="e2842-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="e2842-106">描述</span><span class="sxs-lookup"><span data-stu-id="e2842-106">Description</span></span>

<span data-ttu-id="e2842-107">有一點 `bit` ，會在為時套用作業 `trueOp` `trueInput` 做為其 `bit` 輸入 `true` ，並 `falseOp(falseInput)` 在為時套用 `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="e2842-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e2842-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="e2842-109">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e2842-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e2842-110">用來判斷是否已套用或的布林值 `trueOp` `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-ctl"></a><span data-ttu-id="e2842-111">trueOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="e2842-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e2842-112">當為時要套用的可控制作業 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="e2842-113">trueInput： t</span><span class="sxs-lookup"><span data-stu-id="e2842-113">trueInput : 'T</span></span>

<span data-ttu-id="e2842-114">當為時，所要提供的輸入 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-ctl"></a><span data-ttu-id="e2842-115">falseOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="e2842-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e2842-116">當為時要套用的可控制作業 `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="e2842-117">falseInput： ' U</span><span class="sxs-lookup"><span data-stu-id="e2842-117">falseInput : 'U</span></span>

<span data-ttu-id="e2842-118">當為時，所要提供的輸入 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2842-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2842-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e2842-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="e2842-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e2842-121">不要</span><span class="sxs-lookup"><span data-stu-id="e2842-121">'T</span></span>

<span data-ttu-id="e2842-122">要有條件地套用之作業的輸入類型 `trueOp` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="e2842-123">' U</span><span class="sxs-lookup"><span data-stu-id="e2842-123">'U</span></span>

<span data-ttu-id="e2842-124">要有條件地套用之作業的輸入類型 `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="e2842-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2842-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e2842-125">See Also</span></span>

- [<span data-ttu-id="e2842-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="e2842-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="e2842-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="e2842-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="e2842-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="e2842-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="e2842-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="e2842-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="e2842-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="e2842-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)