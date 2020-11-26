---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221703"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="e27a9-102">_SwapOrderToPermuteArray 函式</span><span class="sxs-lookup"><span data-stu-id="e27a9-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="e27a9-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e27a9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e27a9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e27a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e27a9-105">傳回陣列中的順序元素需要交換以產生已排序的陣列。</span><span class="sxs-lookup"><span data-stu-id="e27a9-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="e27a9-106">假設進行交換。</span><span class="sxs-lookup"><span data-stu-id="e27a9-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="e27a9-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e27a9-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="e27a9-108">newOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e27a9-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e27a9-109">陣列，其中包含新陣列的索引排列。</span><span class="sxs-lookup"><span data-stu-id="e27a9-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="e27a9-110">應該有 $n $ 元素，每一個都是從 $0 $ 到 $n-$1 的唯一整數。</span><span class="sxs-lookup"><span data-stu-id="e27a9-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="e27a9-111">輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e27a9-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="e27a9-112">元組代表要交換的兩個索引。</span><span class="sxs-lookup"><span data-stu-id="e27a9-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="e27a9-113">交換會從最小的索引開始。</span><span class="sxs-lookup"><span data-stu-id="e27a9-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="e27a9-114">備註</span><span class="sxs-lookup"><span data-stu-id="e27a9-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="e27a9-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="e27a9-115">Psuedocode</span></span>

<span data-ttu-id="e27a9-116">針對 (index in 0.. Length (newOrder) -1) {while newOrder [index]！ = index {Switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="e27a9-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>