---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3397c059706c48ff8ca47dd2312cfa9565aacaba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208630"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="e8dee-102">ApplyToHeadA 操作</span><span class="sxs-lookup"><span data-stu-id="e8dee-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="e8dee-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e8dee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e8dee-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8dee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8dee-105">將作業套用至陣列的第一個元素。</span><span class="sxs-lookup"><span data-stu-id="e8dee-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="e8dee-106">描述</span><span class="sxs-lookup"><span data-stu-id="e8dee-106">Description</span></span>

<span data-ttu-id="e8dee-107">假設有作業 `op` 和目標陣列，則 `targets` 適用 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="e8dee-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e8dee-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e8dee-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="e8dee-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="e8dee-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e8dee-110">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="e8dee-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e8dee-111">目標： t []</span><span class="sxs-lookup"><span data-stu-id="e8dee-111">targets : 'T[]</span></span>

<span data-ttu-id="e8dee-112">目標的陣列，其中第一個會套用至 `op` 。</span><span class="sxs-lookup"><span data-stu-id="e8dee-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8dee-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8dee-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e8dee-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="e8dee-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8dee-115">不要</span><span class="sxs-lookup"><span data-stu-id="e8dee-115">'T</span></span>

<span data-ttu-id="e8dee-116">要套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="e8dee-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8dee-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e8dee-117">See Also</span></span>

- [<span data-ttu-id="e8dee-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="e8dee-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="e8dee-119">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="e8dee-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="e8dee-120">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="e8dee-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)