---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 78c1cf23614fbb7c27122548de487c7350467948
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699304"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="31283-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="31283-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="31283-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="31283-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="31283-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31283-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31283-105">根據傳統結果的值，套用兩項作業的其中一個。</span><span class="sxs-lookup"><span data-stu-id="31283-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="31283-106">描述</span><span class="sxs-lookup"><span data-stu-id="31283-106">Description</span></span>

<span data-ttu-id="31283-107">因此 `result` ， `zeroOp` `zeroInput` 當等於時，會將作業套用至做為其輸入， `result` `Zero` 並適用 `oneOp(oneInput)` 于 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="31283-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="31283-108">輸入</span><span class="sxs-lookup"><span data-stu-id="31283-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="31283-109">結果： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="31283-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="31283-110">用來判斷是否已套用或的測量結果 `zeroOp` `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="31283-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="31283-111">zeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31283-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="31283-112">要在其上套用的作業 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="31283-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="31283-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="31283-113">zeroInput : 'T</span></span>

<span data-ttu-id="31283-114">要在何時提供的輸入 `zeroOp` `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="31283-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="31283-115">oneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31283-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="31283-116">要在其上套用的作業 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="31283-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="31283-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="31283-117">oneInput : 'U</span></span>

<span data-ttu-id="31283-118">要在何時提供的輸入 `oneOp` `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="31283-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31283-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31283-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="31283-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="31283-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31283-121">不要</span><span class="sxs-lookup"><span data-stu-id="31283-121">'T</span></span>

<span data-ttu-id="31283-122">要有條件地套用之作業的輸入類型 `zeroOp` 。</span><span class="sxs-lookup"><span data-stu-id="31283-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="31283-123">' U</span><span class="sxs-lookup"><span data-stu-id="31283-123">'U</span></span>

<span data-ttu-id="31283-124">要有條件地套用之作業的輸入類型 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="31283-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="31283-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="31283-125">See Also</span></span>

- [<span data-ttu-id="31283-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="31283-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="31283-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="31283-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="31283-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="31283-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="31283-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="31283-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="31283-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="31283-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)