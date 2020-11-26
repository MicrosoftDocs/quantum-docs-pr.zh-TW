---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: ApplyIfZeroA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: ab5b05791213da7c8bee5915764c342cb0bed851
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218490"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="e1691-102">ApplyIfZeroA 操作</span><span class="sxs-lookup"><span data-stu-id="e1691-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="e1691-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1691-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1691-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1691-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1691-105">將以傳統結果值為零的 adjointable 運算套用。</span><span class="sxs-lookup"><span data-stu-id="e1691-105">Applies an adjointable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e1691-106">描述</span><span class="sxs-lookup"><span data-stu-id="e1691-106">Description</span></span>

<span data-ttu-id="e1691-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="e1691-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="e1691-108">如果 `One` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="e1691-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="e1691-109">尾碼 `A` 表示要套用的作業是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="e1691-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="e1691-110">輸入</span><span class="sxs-lookup"><span data-stu-id="e1691-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="e1691-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="e1691-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="e1691-112">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="e1691-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="e1691-113">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="e1691-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e1691-114">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="e1691-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="e1691-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="e1691-115">target : 'T</span></span>

<span data-ttu-id="e1691-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="e1691-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1691-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1691-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e1691-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="e1691-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1691-119">不要</span><span class="sxs-lookup"><span data-stu-id="e1691-119">'T</span></span>

<span data-ttu-id="e1691-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="e1691-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1691-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1691-121">See Also</span></span>

- [<span data-ttu-id="e1691-122">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="e1691-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="e1691-123">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="e1691-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="e1691-124">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="e1691-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)