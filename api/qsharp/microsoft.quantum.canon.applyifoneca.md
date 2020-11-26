---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218575"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="b8ab1-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="b8ab1-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="b8ab1-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b8ab1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b8ab1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8ab1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8ab1-105">針對傳統結果值套用條件為一的單一作業。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b8ab1-106">描述</span><span class="sxs-lookup"><span data-stu-id="b8ab1-106">Description</span></span>

<span data-ttu-id="b8ab1-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `One` 。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="b8ab1-108">如果 `Zero` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="b8ab1-109">尾碼 `CA` 表示要套用的作業是單一 (可控制和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="b8ab1-110">輸入</span><span class="sxs-lookup"><span data-stu-id="b8ab1-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b8ab1-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b8ab1-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="b8ab1-112">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b8ab1-113">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b8ab1-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b8ab1-114">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="b8ab1-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="b8ab1-115">target : 'T</span></span>

<span data-ttu-id="b8ab1-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8ab1-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8ab1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b8ab1-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="b8ab1-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b8ab1-119">不要</span><span class="sxs-lookup"><span data-stu-id="b8ab1-119">'T</span></span>

<span data-ttu-id="b8ab1-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="b8ab1-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8ab1-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b8ab1-121">See Also</span></span>

- [<span data-ttu-id="b8ab1-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="b8ab1-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="b8ab1-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="b8ab1-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="b8ab1-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="b8ab1-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)