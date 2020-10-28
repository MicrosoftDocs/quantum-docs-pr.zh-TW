---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699296"
---
# <a name="applyifone-operation"></a><span data-ttu-id="0e9e3-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="0e9e3-102">ApplyIfOne operation</span></span>

<span data-ttu-id="0e9e3-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e9e3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e9e3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e9e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e9e3-105">套用以傳統結果值為一個的運算。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="0e9e3-106">描述</span><span class="sxs-lookup"><span data-stu-id="0e9e3-106">Description</span></span>

<span data-ttu-id="0e9e3-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `One` 。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="0e9e3-108">如果 `Zero` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="0e9e3-109">輸入</span><span class="sxs-lookup"><span data-stu-id="0e9e3-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="0e9e3-110">結果： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0e9e3-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="0e9e3-111">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="0e9e3-112">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e9e3-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0e9e3-113">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="0e9e3-114">目標： t</span><span class="sxs-lookup"><span data-stu-id="0e9e3-114">target : 'T</span></span>

<span data-ttu-id="0e9e3-115">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e9e3-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e9e3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0e9e3-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="0e9e3-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e9e3-118">不要</span><span class="sxs-lookup"><span data-stu-id="0e9e3-118">'T</span></span>

<span data-ttu-id="0e9e3-119">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="0e9e3-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e9e3-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e9e3-120">See Also</span></span>

- [<span data-ttu-id="0e9e3-121">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="0e9e3-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="0e9e3-122">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="0e9e3-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="0e9e3-123">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="0e9e3-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)