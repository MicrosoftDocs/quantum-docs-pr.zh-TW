---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217997"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="e1eb1-102">ApplySeriesOfOps 操作</span><span class="sxs-lookup"><span data-stu-id="e1eb1-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="e1eb1-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1eb1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1eb1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1eb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1eb1-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="e1eb1-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e1eb1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e1eb1-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="e1eb1-107">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="e1eb1-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="e1eb1-108">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="e1eb1-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="e1eb1-109">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="e1eb1-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="e1eb1-110">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="e1eb1-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="e1eb1-111">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="e1eb1-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="e1eb1-112">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="e1eb1-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="e1eb1-113">register： t []</span><span class="sxs-lookup"><span data-stu-id="e1eb1-113">register : 'T[]</span></span>

<span data-ttu-id="e1eb1-114">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="e1eb1-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1eb1-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1eb1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e1eb1-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="e1eb1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1eb1-117">不要</span><span class="sxs-lookup"><span data-stu-id="e1eb1-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="e1eb1-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1eb1-118">See Also</span></span>

- [<span data-ttu-id="e1eb1-119">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="e1eb1-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)