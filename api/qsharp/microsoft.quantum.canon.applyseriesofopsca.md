---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217878"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="7b735-102">ApplySeriesOfOpsCA 操作</span><span class="sxs-lookup"><span data-stu-id="7b735-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="7b735-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b735-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b735-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b735-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b735-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="7b735-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="7b735-106"> (Adjoint + 控制) </span><span class="sxs-lookup"><span data-stu-id="7b735-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7b735-107">輸入</span><span class="sxs-lookup"><span data-stu-id="7b735-107">Input</span></span>

### <a name="listofops--t--unit--is-adj--ctl"></a><span data-ttu-id="7b735-108">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="7b735-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="7b735-109">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="7b735-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="7b735-110">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="7b735-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="7b735-111">每個都必須同時具有 Adjoint 和控制仿函數。</span><span class="sxs-lookup"><span data-stu-id="7b735-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="7b735-112">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="7b735-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="7b735-113">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="7b735-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="7b735-114">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="7b735-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="7b735-115">register： t []</span><span class="sxs-lookup"><span data-stu-id="7b735-115">register : 'T[]</span></span>

<span data-ttu-id="7b735-116">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="7b735-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b735-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b735-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b735-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="7b735-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b735-119">不要</span><span class="sxs-lookup"><span data-stu-id="7b735-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="7b735-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b735-120">See Also</span></span>

- [<span data-ttu-id="7b735-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="7b735-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)