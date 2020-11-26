---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217929"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="25de0-102">ApplySeriesOfOpsC 操作</span><span class="sxs-lookup"><span data-stu-id="25de0-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="25de0-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25de0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25de0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25de0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25de0-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="25de0-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="25de0-106"> (控制) </span><span class="sxs-lookup"><span data-stu-id="25de0-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="25de0-107">輸入</span><span class="sxs-lookup"><span data-stu-id="25de0-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="25de0-108">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl []</span><span class="sxs-lookup"><span data-stu-id="25de0-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="25de0-109">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="25de0-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="25de0-110">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="25de0-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="25de0-111">每個都必須有控制的仿函數</span><span class="sxs-lookup"><span data-stu-id="25de0-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="25de0-112">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="25de0-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="25de0-113">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="25de0-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="25de0-114">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="25de0-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="25de0-115">register： t []</span><span class="sxs-lookup"><span data-stu-id="25de0-115">register : 'T[]</span></span>

<span data-ttu-id="25de0-116">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="25de0-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25de0-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25de0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="25de0-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="25de0-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25de0-119">不要</span><span class="sxs-lookup"><span data-stu-id="25de0-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="25de0-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="25de0-120">See Also</span></span>

- [<span data-ttu-id="25de0-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="25de0-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)