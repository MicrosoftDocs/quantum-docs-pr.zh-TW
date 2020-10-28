---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699309"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="81007-102">ApplyIfElseBCA 操作</span><span class="sxs-lookup"><span data-stu-id="81007-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="81007-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81007-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81007-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81007-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81007-105">根據傳統位的值，套用兩項單一作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="81007-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="81007-106">描述</span><span class="sxs-lookup"><span data-stu-id="81007-106">Description</span></span>

<span data-ttu-id="81007-107">有一點 `bit` ，會在為時套用作業 `trueOp` `trueInput` 做為其 `bit` 輸入 `true` ，並 `falseOp(falseInput)` 在為時套用 `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="81007-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="81007-108">輸入</span><span class="sxs-lookup"><span data-stu-id="81007-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="81007-109">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81007-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="81007-110">用來判斷是否已套用或的布林值 `trueOp` `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="81007-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj--ctl"></a><span data-ttu-id="81007-111">trueOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="81007-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="81007-112">當為時要套用的單一 `bit` 作業 `true` 。</span><span class="sxs-lookup"><span data-stu-id="81007-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="81007-113">trueInput： t</span><span class="sxs-lookup"><span data-stu-id="81007-113">trueInput : 'T</span></span>

<span data-ttu-id="81007-114">當為時，所要提供的輸入 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="81007-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj--ctl"></a><span data-ttu-id="81007-115">falseOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="81007-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="81007-116">當為時要套用的單一 `bit` 作業 `false` 。</span><span class="sxs-lookup"><span data-stu-id="81007-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="81007-117">falseInput： ' U</span><span class="sxs-lookup"><span data-stu-id="81007-117">falseInput : 'U</span></span>

<span data-ttu-id="81007-118">當為時，所要提供的輸入 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="81007-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81007-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81007-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="81007-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="81007-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81007-121">不要</span><span class="sxs-lookup"><span data-stu-id="81007-121">'T</span></span>

<span data-ttu-id="81007-122">要有條件地套用之作業的輸入類型 `trueOp` 。</span><span class="sxs-lookup"><span data-stu-id="81007-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="81007-123">' U</span><span class="sxs-lookup"><span data-stu-id="81007-123">'U</span></span>

<span data-ttu-id="81007-124">要有條件地套用之作業的輸入類型 `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="81007-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="81007-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="81007-125">See Also</span></span>

- [<span data-ttu-id="81007-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="81007-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="81007-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="81007-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="81007-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="81007-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="81007-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="81007-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="81007-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="81007-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)