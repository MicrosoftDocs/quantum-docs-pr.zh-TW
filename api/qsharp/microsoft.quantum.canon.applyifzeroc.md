---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: cfc2a659f4da011baadff1a0d6a20a2a36d0a285
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699283"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="2f76c-102">ApplyIfZeroC 操作</span><span class="sxs-lookup"><span data-stu-id="2f76c-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="2f76c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f76c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f76c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f76c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f76c-105">將以傳統結果值為零的可控作業套用。</span><span class="sxs-lookup"><span data-stu-id="2f76c-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="2f76c-106">描述</span><span class="sxs-lookup"><span data-stu-id="2f76c-106">Description</span></span>

<span data-ttu-id="2f76c-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="2f76c-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="2f76c-108">如果 `One` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="2f76c-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="2f76c-109">尾碼 `C` 表示要套用的作業是可控制的。</span><span class="sxs-lookup"><span data-stu-id="2f76c-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="2f76c-110">輸入</span><span class="sxs-lookup"><span data-stu-id="2f76c-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="2f76c-111">結果： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="2f76c-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="2f76c-112">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="2f76c-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="2f76c-113">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="2f76c-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="2f76c-114">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="2f76c-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="2f76c-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="2f76c-115">target : 'T</span></span>

<span data-ttu-id="2f76c-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="2f76c-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f76c-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f76c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f76c-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="2f76c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f76c-119">不要</span><span class="sxs-lookup"><span data-stu-id="2f76c-119">'T</span></span>

<span data-ttu-id="2f76c-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="2f76c-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f76c-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2f76c-121">See Also</span></span>

- [<span data-ttu-id="2f76c-122">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="2f76c-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="2f76c-123">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="2f76c-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="2f76c-124">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="2f76c-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)