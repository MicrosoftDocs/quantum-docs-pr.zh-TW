---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: f28cff599e06090145fac860dbaf8274c966f80a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208545"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="5b963-102">ApplyToHeadCA 操作</span><span class="sxs-lookup"><span data-stu-id="5b963-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="5b963-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5b963-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5b963-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b963-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b963-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="5b963-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5b963-106">描述</span><span class="sxs-lookup"><span data-stu-id="5b963-106">Description</span></span>

<span data-ttu-id="5b963-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="5b963-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5b963-108">輸入</span><span class="sxs-lookup"><span data-stu-id="5b963-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="5b963-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5b963-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="5b963-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="5b963-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5b963-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="5b963-111">targets : 'T[]</span></span>

<span data-ttu-id="5b963-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="5b963-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5b963-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b963-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5b963-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="5b963-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5b963-115">不要</span><span class="sxs-lookup"><span data-stu-id="5b963-115">'T</span></span>

<span data-ttu-id="5b963-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="5b963-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b963-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b963-117">See Also</span></span>

- [<span data-ttu-id="5b963-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="5b963-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="5b963-119">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="5b963-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="5b963-120">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="5b963-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)