---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a8606cde976882bba0eb23467932b9ee0ed36696
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840610"
---
# <a name="delayca-operation"></a><span data-ttu-id="ee6ca-102">DelayCA 操作</span><span class="sxs-lookup"><span data-stu-id="ee6ca-102">DelayCA operation</span></span>

<span data-ttu-id="ee6ca-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee6ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee6ca-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee6ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee6ca-105">套用具有延遲的指定作業。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ee6ca-106">描述</span><span class="sxs-lookup"><span data-stu-id="ee6ca-106">Description</span></span>

<span data-ttu-id="ee6ca-107">如果有作業和該作業的輸入，則會在提供額外的輸入之後套用作業。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="ee6ca-108">尤其是，運算式 `Delay(op, arg, _)` 是 `op` 在呼叫時套用的作業 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="ee6ca-109">運算式 `Delay(op,arg,_)` 允許延遲的應用程式 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="ee6ca-110">輸入</span><span class="sxs-lookup"><span data-stu-id="ee6ca-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ee6ca-111">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ee6ca-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ee6ca-112">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="ee6ca-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="ee6ca-113">arg : 'T</span></span>

<span data-ttu-id="ee6ca-114">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="ee6ca-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee6ca-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="ee6ca-116">使用部分應用程式來延遲作業應用程式的引數。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee6ca-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee6ca-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee6ca-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="ee6ca-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee6ca-119">不要</span><span class="sxs-lookup"><span data-stu-id="ee6ca-119">'T</span></span>

<span data-ttu-id="ee6ca-120">要延遲之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="ee6ca-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee6ca-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee6ca-121">See Also</span></span>

- [<span data-ttu-id="ee6ca-122">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="ee6ca-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="ee6ca-123">Canon. 延遲</span><span class="sxs-lookup"><span data-stu-id="ee6ca-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)