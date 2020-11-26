---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220683"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="48423-102">MappedOverRange 函式</span><span class="sxs-lookup"><span data-stu-id="48423-102">MappedOverRange function</span></span>

<span data-ttu-id="48423-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="48423-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="48423-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="48423-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="48423-105">假設範圍和採用整數做為輸入的函式，則會傳回新的陣列，其中包含函式下範圍值的影像。</span><span class="sxs-lookup"><span data-stu-id="48423-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="48423-106">輸入</span><span class="sxs-lookup"><span data-stu-id="48423-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="48423-107">對應工具： [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="48423-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="48423-108">中 `Int` `'T` 用來對應範圍值的函式。</span><span class="sxs-lookup"><span data-stu-id="48423-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="48423-109">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="48423-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="48423-110">整數的範圍。</span><span class="sxs-lookup"><span data-stu-id="48423-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="48423-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="48423-111">Output : 'T[]</span></span>

<span data-ttu-id="48423-112">由函式 `'T[]` 所對應的元素陣列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="48423-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48423-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="48423-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48423-114">不要</span><span class="sxs-lookup"><span data-stu-id="48423-114">'T</span></span>

<span data-ttu-id="48423-115">函數的結果型別 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="48423-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="48423-116">備註</span><span class="sxs-lookup"><span data-stu-id="48423-116">Remarks</span></span>

<span data-ttu-id="48423-117">函數是針對泛型型別定義的，也就是說，每當我們有函式時， `mapper: Int -> 'T` 我們可以對應範圍的值，並產生型別的陣列 `'T[]` 。</span><span class="sxs-lookup"><span data-stu-id="48423-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="48423-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="48423-118">See Also</span></span>

- [<span data-ttu-id="48423-119">。對應的</span><span class="sxs-lookup"><span data-stu-id="48423-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)