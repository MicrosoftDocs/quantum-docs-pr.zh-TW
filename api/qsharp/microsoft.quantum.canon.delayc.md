---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216484"
---
# <a name="delayc-operation"></a><span data-ttu-id="ad838-102">DelayC 操作</span><span class="sxs-lookup"><span data-stu-id="ad838-102">DelayC operation</span></span>

<span data-ttu-id="ad838-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ad838-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ad838-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad838-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad838-105">套用具有延遲的指定作業。</span><span class="sxs-lookup"><span data-stu-id="ad838-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="ad838-106">描述</span><span class="sxs-lookup"><span data-stu-id="ad838-106">Description</span></span>

<span data-ttu-id="ad838-107">如果有作業和該作業的輸入，則會在提供額外的輸入之後套用作業。</span><span class="sxs-lookup"><span data-stu-id="ad838-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="ad838-108">尤其是，運算式 `Delay(op, arg, _)` 是 `op` 在呼叫時套用的作業 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="ad838-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="ad838-109">運算式 `Delay(op,arg,_)` 允許延遲的應用程式 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ad838-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="ad838-110">輸入</span><span class="sxs-lookup"><span data-stu-id="ad838-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="ad838-111">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="ad838-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ad838-112">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="ad838-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="ad838-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="ad838-113">arg : 'T</span></span>

<span data-ttu-id="ad838-114">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="ad838-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="ad838-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad838-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="ad838-116">使用部分應用程式來延遲作業應用程式的引數。</span><span class="sxs-lookup"><span data-stu-id="ad838-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad838-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad838-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ad838-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="ad838-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ad838-119">不要</span><span class="sxs-lookup"><span data-stu-id="ad838-119">'T</span></span>

<span data-ttu-id="ad838-120">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="ad838-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad838-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ad838-121">See Also</span></span>

- [<span data-ttu-id="ad838-122">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="ad838-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="ad838-123">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="ad838-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)