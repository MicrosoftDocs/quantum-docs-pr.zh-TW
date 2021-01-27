---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850915"
---
# <a name="unique-function"></a><span data-ttu-id="2197c-102">Unique 函數</span><span class="sxs-lookup"><span data-stu-id="2197c-102">Unique function</span></span>

<span data-ttu-id="2197c-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2197c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2197c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2197c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2197c-105">傳回不等於相鄰元素的新陣列。</span><span class="sxs-lookup"><span data-stu-id="2197c-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2197c-106">描述</span><span class="sxs-lookup"><span data-stu-id="2197c-106">Description</span></span>

<span data-ttu-id="2197c-107">假設有一些元素陣列和函式測試是否相等，此函式會傳回新的陣列，其中會保留專案的相對順序，但是所有相等的相鄰元素都會篩選成隻有一個專案。</span><span class="sxs-lookup"><span data-stu-id="2197c-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="2197c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="2197c-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="2197c-109">等於： ( 否，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2197c-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2197c-110">比較兩個元素的函式， `a` 如果是，則視為等於 `b` `equal(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="2197c-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="2197c-111">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="2197c-111">array : 'T[]</span></span>

<span data-ttu-id="2197c-112">要針對唯一元素篩選的陣列。</span><span class="sxs-lookup"><span data-stu-id="2197c-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="2197c-113">Output： t []</span><span class="sxs-lookup"><span data-stu-id="2197c-113">Output : 'T[]</span></span>

<span data-ttu-id="2197c-114">不等於相鄰元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="2197c-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2197c-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="2197c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2197c-116">不要</span><span class="sxs-lookup"><span data-stu-id="2197c-116">'T</span></span>

<span data-ttu-id="2197c-117">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="2197c-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="2197c-118">範例</span><span class="sxs-lookup"><span data-stu-id="2197c-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="2197c-119">備註</span><span class="sxs-lookup"><span data-stu-id="2197c-119">Remarks</span></span>

<span data-ttu-id="2197c-120">如果有多個元素相等，但彼此不同，則輸出陣列中會出現多個專案。</span><span class="sxs-lookup"><span data-stu-id="2197c-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="2197c-121">使用此函式搭配 `Sorted` 來取得具有整體唯一元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="2197c-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>