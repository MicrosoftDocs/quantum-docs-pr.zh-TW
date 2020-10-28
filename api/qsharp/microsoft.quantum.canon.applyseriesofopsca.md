---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699229"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="cc016-102">ApplySeriesOfOpsCA 操作</span><span class="sxs-lookup"><span data-stu-id="cc016-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="cc016-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc016-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc016-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc016-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc016-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="cc016-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="cc016-106"> (Adjoint + 控制) </span><span class="sxs-lookup"><span data-stu-id="cc016-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cc016-107">輸入</span><span class="sxs-lookup"><span data-stu-id="cc016-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="cc016-108">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="cc016-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="cc016-109">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="cc016-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="cc016-110">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="cc016-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="cc016-111">每個都必須同時具有 Adjoint 和控制仿函數。</span><span class="sxs-lookup"><span data-stu-id="cc016-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="cc016-112">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="cc016-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="cc016-113">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="cc016-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="cc016-114">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="cc016-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="cc016-115">register： t []</span><span class="sxs-lookup"><span data-stu-id="cc016-115">register : 'T[]</span></span>

<span data-ttu-id="cc016-116">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="cc016-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc016-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc016-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cc016-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="cc016-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc016-119">不要</span><span class="sxs-lookup"><span data-stu-id="cc016-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="cc016-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cc016-120">See Also</span></span>

- [<span data-ttu-id="cc016-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="cc016-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)