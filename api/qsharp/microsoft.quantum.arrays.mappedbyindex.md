---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699452"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="f49a4-102">MappedByIndex 函式</span><span class="sxs-lookup"><span data-stu-id="f49a4-102">MappedByIndex function</span></span>

<span data-ttu-id="f49a4-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f49a4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f49a4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f49a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f49a4-105">如果陣列和函式是針對陣列的索引元素所定義，則會傳回新的陣列，此陣列是由函式下原始陣列的影像所組成。</span><span class="sxs-lookup"><span data-stu-id="f49a4-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="f49a4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f49a4-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="f49a4-107">對應工具： ([Int](xref:microsoft.quantum.lang-ref.int)，t) -> ' U</span><span class="sxs-lookup"><span data-stu-id="f49a4-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="f49a4-108">從到的函式， `(Int, 'T)` `'U` 用來對應元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="f49a4-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="f49a4-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="f49a4-109">array : 'T[]</span></span>

<span data-ttu-id="f49a4-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="f49a4-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="f49a4-111">輸出： ' U []</span><span class="sxs-lookup"><span data-stu-id="f49a4-111">Output : 'U[]</span></span>

<span data-ttu-id="f49a4-112">由函式 `'U[]` 所對應的元素陣列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="f49a4-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f49a4-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="f49a4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f49a4-114">不要</span><span class="sxs-lookup"><span data-stu-id="f49a4-114">'T</span></span>

<span data-ttu-id="f49a4-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="f49a4-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="f49a4-116">' U</span><span class="sxs-lookup"><span data-stu-id="f49a4-116">'U</span></span>

<span data-ttu-id="f49a4-117">函數的結果型別 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="f49a4-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="f49a4-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f49a4-118">See Also</span></span>

- [<span data-ttu-id="f49a4-119">。對應的</span><span class="sxs-lookup"><span data-stu-id="f49a4-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)