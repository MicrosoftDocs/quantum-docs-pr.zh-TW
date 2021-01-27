---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3876e2baf1b3ad5bbfa0097d468b1e88adf05db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841724"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="9537c-102">ApplyIfZeroC 操作</span><span class="sxs-lookup"><span data-stu-id="9537c-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="9537c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9537c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9537c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9537c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9537c-105">將以傳統結果值為零的可控作業套用。</span><span class="sxs-lookup"><span data-stu-id="9537c-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="9537c-106">描述</span><span class="sxs-lookup"><span data-stu-id="9537c-106">Description</span></span>

<span data-ttu-id="9537c-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="9537c-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="9537c-108">如果 `One` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="9537c-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="9537c-109">尾碼 `C` 表示要套用的作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="9537c-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="9537c-110">輸入</span><span class="sxs-lookup"><span data-stu-id="9537c-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9537c-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9537c-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="9537c-112">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="9537c-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="9537c-113">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="9537c-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="9537c-114">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="9537c-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="9537c-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="9537c-115">target : 'T</span></span>

<span data-ttu-id="9537c-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="9537c-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9537c-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9537c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9537c-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="9537c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9537c-119">不要</span><span class="sxs-lookup"><span data-stu-id="9537c-119">'T</span></span>

<span data-ttu-id="9537c-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="9537c-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9537c-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9537c-121">See Also</span></span>

- [<span data-ttu-id="9537c-122">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="9537c-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="9537c-123">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="9537c-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="9537c-124">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="9537c-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)