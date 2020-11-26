---
uid: Microsoft.Quantum.Arrays.Mapped
title: 對應函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 9632b9f53ffad8ece958ab1dc9ad446c7dcb9e13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220734"
---
# <a name="mapped-function"></a><span data-ttu-id="daefa-102">對應函數</span><span class="sxs-lookup"><span data-stu-id="daefa-102">Mapped function</span></span>

<span data-ttu-id="daefa-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="daefa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="daefa-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="daefa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="daefa-105">指定陣列和針對陣列元素定義的函式時，會傳回新的陣列，其中包含函式下原始陣列的影像。</span><span class="sxs-lookup"><span data-stu-id="daefa-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="daefa-106">輸入</span><span class="sxs-lookup"><span data-stu-id="daefa-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="daefa-107">對應工具： t-> ' U</span><span class="sxs-lookup"><span data-stu-id="daefa-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="daefa-108">從至的函式， `'T` `'U` 用來對應元素。</span><span class="sxs-lookup"><span data-stu-id="daefa-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="daefa-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="daefa-109">array : 'T[]</span></span>

<span data-ttu-id="daefa-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="daefa-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="daefa-111">輸出： ' U []</span><span class="sxs-lookup"><span data-stu-id="daefa-111">Output : 'U[]</span></span>

<span data-ttu-id="daefa-112">由函式 `'U[]` 所對應的元素陣列 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="daefa-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="daefa-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="daefa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="daefa-114">不要</span><span class="sxs-lookup"><span data-stu-id="daefa-114">'T</span></span>

<span data-ttu-id="daefa-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="daefa-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="daefa-116">' U</span><span class="sxs-lookup"><span data-stu-id="daefa-116">'U</span></span>

<span data-ttu-id="daefa-117">函數的結果型別 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="daefa-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="daefa-118">備註</span><span class="sxs-lookup"><span data-stu-id="daefa-118">Remarks</span></span>

<span data-ttu-id="daefa-119">函式是針對泛型型別定義的，也就是說，每當我們有陣列和函式時， `'T[]` `mapper: 'T -> 'U` 我們可以對應陣列的元素，並產生型別的新陣列 `'U[]` 。</span><span class="sxs-lookup"><span data-stu-id="daefa-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>