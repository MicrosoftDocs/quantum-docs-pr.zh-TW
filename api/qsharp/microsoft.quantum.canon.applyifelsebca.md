---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844963"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="aa72f-102">ApplyIfElseBCA 操作</span><span class="sxs-lookup"><span data-stu-id="aa72f-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="aa72f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa72f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa72f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa72f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa72f-105">根據傳統位的值，套用兩項單一作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="aa72f-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="aa72f-106">描述</span><span class="sxs-lookup"><span data-stu-id="aa72f-106">Description</span></span>

<span data-ttu-id="aa72f-107">有一點 `bit` ，會在為時套用作業 `trueOp` `trueInput` 做為其 `bit` 輸入 `true` ，並 `falseOp(falseInput)` 在為時套用 `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="aa72f-108">輸入</span><span class="sxs-lookup"><span data-stu-id="aa72f-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="aa72f-109">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aa72f-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aa72f-110">用來判斷是否已套用或的布林值 `trueOp` `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj--ctl"></a><span data-ttu-id="aa72f-111">trueOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="aa72f-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="aa72f-112">當為時要套用的單一 `bit` 作業 `true` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="aa72f-113">trueInput： t</span><span class="sxs-lookup"><span data-stu-id="aa72f-113">trueInput : 'T</span></span>

<span data-ttu-id="aa72f-114">當為時，所要提供的輸入 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj--ctl"></a><span data-ttu-id="aa72f-115">falseOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="aa72f-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="aa72f-116">當為時要套用的單一 `bit` 作業 `false` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="aa72f-117">falseInput： ' U</span><span class="sxs-lookup"><span data-stu-id="aa72f-117">falseInput : 'U</span></span>

<span data-ttu-id="aa72f-118">當為時，所要提供的輸入 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa72f-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa72f-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aa72f-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="aa72f-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa72f-121">不要</span><span class="sxs-lookup"><span data-stu-id="aa72f-121">'T</span></span>

<span data-ttu-id="aa72f-122">要有條件地套用之作業的輸入類型 `trueOp` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="aa72f-123">' U</span><span class="sxs-lookup"><span data-stu-id="aa72f-123">'U</span></span>

<span data-ttu-id="aa72f-124">要有條件地套用之作業的輸入類型 `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="aa72f-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa72f-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aa72f-125">See Also</span></span>

- [<span data-ttu-id="aa72f-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="aa72f-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="aa72f-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="aa72f-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="aa72f-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="aa72f-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="aa72f-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="aa72f-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="aa72f-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="aa72f-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)