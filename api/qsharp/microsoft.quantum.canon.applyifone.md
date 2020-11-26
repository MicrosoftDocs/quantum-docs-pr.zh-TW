---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209395"
---
# <a name="applyifone-operation"></a><span data-ttu-id="3db75-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="3db75-102">ApplyIfOne operation</span></span>

<span data-ttu-id="3db75-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3db75-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3db75-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3db75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3db75-105">套用以傳統結果值為一個的運算。</span><span class="sxs-lookup"><span data-stu-id="3db75-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="3db75-106">描述</span><span class="sxs-lookup"><span data-stu-id="3db75-106">Description</span></span>

<span data-ttu-id="3db75-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `One` 。</span><span class="sxs-lookup"><span data-stu-id="3db75-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="3db75-108">如果 `Zero` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="3db75-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="3db75-109">輸入</span><span class="sxs-lookup"><span data-stu-id="3db75-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3db75-110">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3db75-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="3db75-111">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="3db75-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="3db75-112">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3db75-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3db75-113">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="3db75-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3db75-114">目標： t</span><span class="sxs-lookup"><span data-stu-id="3db75-114">target : 'T</span></span>

<span data-ttu-id="3db75-115">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="3db75-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3db75-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3db75-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3db75-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="3db75-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3db75-118">不要</span><span class="sxs-lookup"><span data-stu-id="3db75-118">'T</span></span>

<span data-ttu-id="3db75-119">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="3db75-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3db75-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3db75-120">See Also</span></span>

- [<span data-ttu-id="3db75-121">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="3db75-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="3db75-122">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="3db75-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="3db75-123">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="3db75-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)