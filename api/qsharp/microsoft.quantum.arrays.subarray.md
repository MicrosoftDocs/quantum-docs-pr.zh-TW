---
uid: Microsoft.Quantum.Arrays.Subarray
title: 子陣列函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220156"
---
# <a name="subarray-function"></a><span data-ttu-id="4618f-102">子陣列函數</span><span class="sxs-lookup"><span data-stu-id="4618f-102">Subarray function</span></span>

<span data-ttu-id="4618f-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4618f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4618f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4618f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4618f-105">採用陣列和位置清單，並產生新的陣列，該陣列是從符合指定位置的原始陣列元素組成。</span><span class="sxs-lookup"><span data-stu-id="4618f-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4618f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4618f-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="4618f-107">索引： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4618f-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4618f-108">用來定義子陣列的整數清單。</span><span class="sxs-lookup"><span data-stu-id="4618f-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="4618f-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="4618f-109">array : 'T[]</span></span>

<span data-ttu-id="4618f-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="4618f-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="4618f-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="4618f-111">Output : 'T[]</span></span>

<span data-ttu-id="4618f-112">專案的陣列 `out` ，其索引會對應至子陣列，因此為 `out[idx] == array[indices[idx]]` 。</span><span class="sxs-lookup"><span data-stu-id="4618f-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4618f-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="4618f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4618f-114">不要</span><span class="sxs-lookup"><span data-stu-id="4618f-114">'T</span></span>

<span data-ttu-id="4618f-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="4618f-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="4618f-116">備註</span><span class="sxs-lookup"><span data-stu-id="4618f-116">Remarks</span></span>

<span data-ttu-id="4618f-117">函數是針對泛型型別定義的，也就是，只要有陣列 `'T[]` 和定義子陣列的位置清單 `Int[]` 。</span><span class="sxs-lookup"><span data-stu-id="4618f-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="4618f-118">子陣列的結構是依據產生指定陣列的新深層複本，而不是維護參考。</span><span class="sxs-lookup"><span data-stu-id="4618f-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="4618f-119">如果 `Length(indices) < Length(array)` 為，則此函數會傳回的子集 `array` 。</span><span class="sxs-lookup"><span data-stu-id="4618f-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="4618f-120">另一方面，如果 `indices` 包含重複的元素，則 `array` 會同樣重複的對應元素。</span><span class="sxs-lookup"><span data-stu-id="4618f-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="4618f-121">如果 `indices` 和 `array` 的長度相同，此函數會提供的排列 `array` 。</span><span class="sxs-lookup"><span data-stu-id="4618f-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>