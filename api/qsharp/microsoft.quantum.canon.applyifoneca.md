---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 8b27a192c66a127fe5a8acfbba7b78314988bf2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844919"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="8f34d-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="8f34d-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="8f34d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f34d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f34d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f34d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f34d-105">針對傳統結果值套用條件為一的單一作業。</span><span class="sxs-lookup"><span data-stu-id="8f34d-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8f34d-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f34d-106">Description</span></span>

<span data-ttu-id="8f34d-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `One` 。</span><span class="sxs-lookup"><span data-stu-id="8f34d-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="8f34d-108">如果 `Zero` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="8f34d-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="8f34d-109">尾碼 `CA` 表示要套用的作業是單一 (可控制和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="8f34d-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="8f34d-110">輸入</span><span class="sxs-lookup"><span data-stu-id="8f34d-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="8f34d-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="8f34d-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="8f34d-112">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="8f34d-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="8f34d-113">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="8f34d-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8f34d-114">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="8f34d-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="8f34d-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="8f34d-115">target : 'T</span></span>

<span data-ttu-id="8f34d-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="8f34d-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f34d-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f34d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f34d-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="8f34d-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f34d-119">不要</span><span class="sxs-lookup"><span data-stu-id="8f34d-119">'T</span></span>

<span data-ttu-id="8f34d-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="8f34d-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f34d-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8f34d-121">See Also</span></span>

- [<span data-ttu-id="8f34d-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="8f34d-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="8f34d-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="8f34d-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="8f34d-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="8f34d-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)