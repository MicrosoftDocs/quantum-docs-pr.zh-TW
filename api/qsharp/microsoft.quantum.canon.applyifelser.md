---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841804"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="28297-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="28297-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="28297-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28297-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28297-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28297-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28297-105">根據傳統結果的值，套用兩項作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="28297-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="28297-106">描述</span><span class="sxs-lookup"><span data-stu-id="28297-106">Description</span></span>

<span data-ttu-id="28297-107">因此 `result` ， `zeroOp` `zeroInput` 當等於時，會將作業套用至做為其輸入， `result` `Zero` 並適用 `oneOp(oneInput)` 于 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="28297-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="28297-108">輸入</span><span class="sxs-lookup"><span data-stu-id="28297-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="28297-109">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="28297-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="28297-110">用來判斷是否已套用或的測量結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="28297-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="28297-111">zeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28297-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="28297-112">要在其上套用的作業 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="28297-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="28297-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="28297-113">zeroInput : 'T</span></span>

<span data-ttu-id="28297-114">要在何時提供的輸入 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="28297-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="28297-115">oneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28297-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="28297-116">要在其上套用的作業 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="28297-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="28297-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="28297-117">oneInput : 'U</span></span>

<span data-ttu-id="28297-118">要在何時提供的輸入 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="28297-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28297-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28297-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28297-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="28297-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28297-121">不要</span><span class="sxs-lookup"><span data-stu-id="28297-121">'T</span></span>

<span data-ttu-id="28297-122">要有條件地套用之作業的輸入類型 `zeroOp` 。</span><span class="sxs-lookup"><span data-stu-id="28297-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="28297-123">' U</span><span class="sxs-lookup"><span data-stu-id="28297-123">'U</span></span>

<span data-ttu-id="28297-124">要有條件地套用之作業的輸入類型 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="28297-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="28297-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28297-125">See Also</span></span>

- [<span data-ttu-id="28297-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="28297-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="28297-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="28297-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="28297-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="28297-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="28297-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="28297-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="28297-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="28297-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)