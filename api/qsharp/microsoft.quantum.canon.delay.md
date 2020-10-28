---
uid: Microsoft.Quantum.Canon.Delay
title: 延遲操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699041"
---
# <a name="delay-operation"></a><span data-ttu-id="06eb8-102">延遲操作</span><span class="sxs-lookup"><span data-stu-id="06eb8-102">Delay operation</span></span>

<span data-ttu-id="06eb8-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06eb8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06eb8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06eb8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06eb8-105">套用具有延遲的指定作業。</span><span class="sxs-lookup"><span data-stu-id="06eb8-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="06eb8-106">描述</span><span class="sxs-lookup"><span data-stu-id="06eb8-106">Description</span></span>

<span data-ttu-id="06eb8-107">如果有作業和該作業的輸入，則會在提供額外的輸入之後套用作業。</span><span class="sxs-lookup"><span data-stu-id="06eb8-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="06eb8-108">尤其是，運算式 `Delay(op, arg, _)` 是 `op` 在呼叫時套用的作業 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="06eb8-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="06eb8-109">運算式 `Delay(op,arg,_)` 允許延遲的應用程式 `op` 。</span><span class="sxs-lookup"><span data-stu-id="06eb8-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="06eb8-110">輸入</span><span class="sxs-lookup"><span data-stu-id="06eb8-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="06eb8-111">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="06eb8-111">op : 'T => 'U</span></span> 

<span data-ttu-id="06eb8-112">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="06eb8-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="06eb8-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="06eb8-113">arg : 'T</span></span>

<span data-ttu-id="06eb8-114">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="06eb8-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="06eb8-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06eb8-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="06eb8-116">使用部分應用程式來延遲作業應用程式的引數。</span><span class="sxs-lookup"><span data-stu-id="06eb8-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="06eb8-117">輸出： ' U</span><span class="sxs-lookup"><span data-stu-id="06eb8-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="06eb8-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="06eb8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="06eb8-119">不要</span><span class="sxs-lookup"><span data-stu-id="06eb8-119">'T</span></span>

<span data-ttu-id="06eb8-120">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="06eb8-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="06eb8-121">' U</span><span class="sxs-lookup"><span data-stu-id="06eb8-121">'U</span></span>

<span data-ttu-id="06eb8-122">要延遲之作業的傳回型別。</span><span class="sxs-lookup"><span data-stu-id="06eb8-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="06eb8-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="06eb8-123">See Also</span></span>

- [<span data-ttu-id="06eb8-124">Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="06eb8-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="06eb8-125">Canon. DelayA</span><span class="sxs-lookup"><span data-stu-id="06eb8-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="06eb8-126">Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="06eb8-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="06eb8-127">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="06eb8-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)