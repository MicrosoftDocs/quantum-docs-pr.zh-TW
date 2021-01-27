---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 215b71a8d2e4f8a22df05b210824bc40a969b6f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841734"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="6f0f8-102">ApplyIfZero 操作</span><span class="sxs-lookup"><span data-stu-id="6f0f8-102">ApplyIfZero operation</span></span>

<span data-ttu-id="6f0f8-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6f0f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6f0f8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f0f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f0f8-105">將以傳統結果值為零的運算套用。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="6f0f8-106">描述</span><span class="sxs-lookup"><span data-stu-id="6f0f8-106">Description</span></span>

<span data-ttu-id="6f0f8-107">指定作業 `op` 和結果值時 `result` ， `op` 如果是，則 `target` 會套用至 `result` `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="6f0f8-108">如果 `One` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="6f0f8-109">輸入</span><span class="sxs-lookup"><span data-stu-id="6f0f8-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="6f0f8-110">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="6f0f8-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="6f0f8-111">控制是否套用 op 的測量結果。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="6f0f8-112">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f0f8-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6f0f8-113">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="6f0f8-114">目標： t</span><span class="sxs-lookup"><span data-stu-id="6f0f8-114">target : 'T</span></span>

<span data-ttu-id="6f0f8-115">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f0f8-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f0f8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6f0f8-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="6f0f8-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f0f8-118">不要</span><span class="sxs-lookup"><span data-stu-id="6f0f8-118">'T</span></span>

<span data-ttu-id="6f0f8-119">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="6f0f8-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f0f8-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6f0f8-120">See Also</span></span>

- [<span data-ttu-id="6f0f8-121">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="6f0f8-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="6f0f8-122">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="6f0f8-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="6f0f8-123">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="6f0f8-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)