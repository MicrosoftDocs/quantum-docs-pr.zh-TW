---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699232"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="31d85-102">ApplySeriesOfOpsA 操作</span><span class="sxs-lookup"><span data-stu-id="31d85-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="31d85-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="31d85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="31d85-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31d85-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31d85-105">依序在陣列上套用 ops 清單和其目標。</span><span class="sxs-lookup"><span data-stu-id="31d85-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="31d85-106"> (Adjoint) </span><span class="sxs-lookup"><span data-stu-id="31d85-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="31d85-107">輸入</span><span class="sxs-lookup"><span data-stu-id="31d85-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="31d85-108">listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 []</span><span class="sxs-lookup"><span data-stu-id="31d85-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="31d85-109">要套用的 ops 清單（每個都有一個 t 陣列）。</span><span class="sxs-lookup"><span data-stu-id="31d85-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="31d85-110">它們會依序套用，最小的索引優先。</span><span class="sxs-lookup"><span data-stu-id="31d85-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="31d85-111">每個都必須有 adjoint 仿函數</span><span class="sxs-lookup"><span data-stu-id="31d85-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="31d85-112">目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="31d85-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="31d85-113">描述 op 目標的嵌套陣列。</span><span class="sxs-lookup"><span data-stu-id="31d85-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="31d85-114">每個陣列都應該包含描述要使用之索引的整數清單。</span><span class="sxs-lookup"><span data-stu-id="31d85-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="31d85-115">register： t []</span><span class="sxs-lookup"><span data-stu-id="31d85-115">register : 'T[]</span></span>

<span data-ttu-id="31d85-116">要處理的量子位 register。</span><span class="sxs-lookup"><span data-stu-id="31d85-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31d85-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31d85-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="31d85-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="31d85-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31d85-119">不要</span><span class="sxs-lookup"><span data-stu-id="31d85-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="31d85-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="31d85-120">See Also</span></span>

- [<span data-ttu-id="31d85-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="31d85-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)