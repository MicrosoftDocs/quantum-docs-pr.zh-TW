---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848592"
---
# <a name="foreach-operation"></a><span data-ttu-id="5e0ae-102">ForEach 操作</span><span class="sxs-lookup"><span data-stu-id="5e0ae-102">ForEach operation</span></span>

<span data-ttu-id="5e0ae-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5e0ae-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5e0ae-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e0ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e0ae-105">指定陣列和定義給陣列元素的作業時，會傳回新的陣列，其中包含作業下原始陣列的影像。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="5e0ae-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5e0ae-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="5e0ae-107">action： t => ' U</span><span class="sxs-lookup"><span data-stu-id="5e0ae-107">action : 'T => 'U</span></span> 

<span data-ttu-id="5e0ae-108">從 `'T` 到的作業 `'U` 會套用至每個元素。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="5e0ae-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="5e0ae-109">array : 'T[]</span></span>

<span data-ttu-id="5e0ae-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="5e0ae-111">輸出： ' U []</span><span class="sxs-lookup"><span data-stu-id="5e0ae-111">Output : 'U[]</span></span>

<span data-ttu-id="5e0ae-112">作業所 `'U[]` 對應的元素陣列 `action` 。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5e0ae-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="5e0ae-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e0ae-114">不要</span><span class="sxs-lookup"><span data-stu-id="5e0ae-114">'T</span></span>

<span data-ttu-id="5e0ae-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="5e0ae-116">' U</span><span class="sxs-lookup"><span data-stu-id="5e0ae-116">'U</span></span>

<span data-ttu-id="5e0ae-117">運算的結果類型 `action` 。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e0ae-118">備註</span><span class="sxs-lookup"><span data-stu-id="5e0ae-118">Remarks</span></span>

<span data-ttu-id="5e0ae-119">作業是針對泛型型別定義的，也就是說，每當我們有陣列和作業時， `'T[]` `action : 'T -> 'U` 我們可以對應陣列的元素，並產生型別的新陣列 `'U[]` 。</span><span class="sxs-lookup"><span data-stu-id="5e0ae-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>