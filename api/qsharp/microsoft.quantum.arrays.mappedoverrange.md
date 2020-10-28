---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699450"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="f9460-102">MappedOverRange 函式</span><span class="sxs-lookup"><span data-stu-id="f9460-102">MappedOverRange function</span></span>

<span data-ttu-id="f9460-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9460-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9460-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9460-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9460-105">假設範圍和採用整數做為輸入的函式，則會傳回新的陣列，其中包含函式下範圍值的影像。</span><span class="sxs-lookup"><span data-stu-id="f9460-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f9460-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f9460-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="f9460-107">對應工具： [Int](xref:microsoft.quantum.lang-ref.int) -> t</span><span class="sxs-lookup"><span data-stu-id="f9460-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="f9460-108">中 `Int` `'T` 用來對應範圍值的函式。</span><span class="sxs-lookup"><span data-stu-id="f9460-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="f9460-109">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f9460-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f9460-110">整數的範圍。</span><span class="sxs-lookup"><span data-stu-id="f9460-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="f9460-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="f9460-111">Output : 'T[]</span></span>

<span data-ttu-id="f9460-112">由函式 `'T[]` 所對應的元素陣列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="f9460-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f9460-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="f9460-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9460-114">不要</span><span class="sxs-lookup"><span data-stu-id="f9460-114">'T</span></span>

<span data-ttu-id="f9460-115">函數的結果型別 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="f9460-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9460-116">備註</span><span class="sxs-lookup"><span data-stu-id="f9460-116">Remarks</span></span>

<span data-ttu-id="f9460-117">函數是針對泛型型別定義的，也就是說，每當我們有函式時， `mapper: Int -> 'T` 我們可以對應範圍的值，並產生型別的陣列 `'T[]` 。</span><span class="sxs-lookup"><span data-stu-id="f9460-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9460-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f9460-118">See Also</span></span>

- [<span data-ttu-id="f9460-119">。對應的</span><span class="sxs-lookup"><span data-stu-id="f9460-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)