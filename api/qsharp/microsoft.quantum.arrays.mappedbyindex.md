---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845657"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="67f1e-102">MappedByIndex 函式</span><span class="sxs-lookup"><span data-stu-id="67f1e-102">MappedByIndex function</span></span>

<span data-ttu-id="67f1e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="67f1e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="67f1e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67f1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67f1e-105">如果陣列和函式是針對陣列的索引元素所定義，則會傳回新的陣列，此陣列是由函式下原始陣列的影像所組成。</span><span class="sxs-lookup"><span data-stu-id="67f1e-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="67f1e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="67f1e-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="67f1e-107">對應工具： ([Int](xref:microsoft.quantum.lang-ref.int)，t) -> ' U</span><span class="sxs-lookup"><span data-stu-id="67f1e-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="67f1e-108">從到的函式， `(Int, 'T)` `'U` 用來對應元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="67f1e-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="67f1e-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="67f1e-109">array : 'T[]</span></span>

<span data-ttu-id="67f1e-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="67f1e-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="67f1e-111">輸出： ' U []</span><span class="sxs-lookup"><span data-stu-id="67f1e-111">Output : 'U[]</span></span>

<span data-ttu-id="67f1e-112">由函式 `'U[]` 所對應的元素陣列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="67f1e-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="67f1e-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="67f1e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67f1e-114">不要</span><span class="sxs-lookup"><span data-stu-id="67f1e-114">'T</span></span>

<span data-ttu-id="67f1e-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="67f1e-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="67f1e-116">' U</span><span class="sxs-lookup"><span data-stu-id="67f1e-116">'U</span></span>

<span data-ttu-id="67f1e-117">函數的結果型別 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="67f1e-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="67f1e-118">範例</span><span class="sxs-lookup"><span data-stu-id="67f1e-118">Example</span></span>

<span data-ttu-id="67f1e-119">下列兩行是相等的：</span><span class="sxs-lookup"><span data-stu-id="67f1e-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="67f1e-120">及</span><span class="sxs-lookup"><span data-stu-id="67f1e-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="67f1e-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="67f1e-121">See Also</span></span>

- [<span data-ttu-id="67f1e-122">。對應的</span><span class="sxs-lookup"><span data-stu-id="67f1e-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)