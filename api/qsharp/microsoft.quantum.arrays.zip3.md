---
uid: Microsoft.Quantum.Arrays.Zip3
title: Array.zip3 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699397"
---
# <a name="zip3-function"></a><span data-ttu-id="d0213-102">Array.zip3 函式</span><span class="sxs-lookup"><span data-stu-id="d0213-102">Zip3 function</span></span>

<span data-ttu-id="d0213-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0213-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0213-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0213-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="d0213-105">Array.zip3 已被取代。</span><span class="sxs-lookup"><span data-stu-id="d0213-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="d0213-106">請改用 <xref:Microsoft.Quantum.Arrays.Zipped3>。</span><span class="sxs-lookup"><span data-stu-id="d0213-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="d0213-107">假設有三個數組，則會傳回3個元組的新陣列，讓每個3元組包含每個原始陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="d0213-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="d0213-108">輸入</span><span class="sxs-lookup"><span data-stu-id="d0213-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="d0213-109">first： t 1 []</span><span class="sxs-lookup"><span data-stu-id="d0213-109">first : 'T1[]</span></span>

<span data-ttu-id="d0213-110">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="d0213-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="d0213-111">第二： t 2 []</span><span class="sxs-lookup"><span data-stu-id="d0213-111">second : 'T2[]</span></span>

<span data-ttu-id="d0213-112">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="d0213-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="d0213-113">第三： t 3 []</span><span class="sxs-lookup"><span data-stu-id="d0213-113">third : 'T3[]</span></span>

<span data-ttu-id="d0213-114">陣列，其中包含每個元組第三個元素的值。</span><span class="sxs-lookup"><span data-stu-id="d0213-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="d0213-115">輸出： ( t 1，t 2，t 3) []</span><span class="sxs-lookup"><span data-stu-id="d0213-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="d0213-116">陣列，其中包含每個的表單3個元組 `(first[idx], second[idx], third[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="d0213-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="d0213-117">如果三個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d0213-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0213-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="d0213-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="d0213-119">T 1</span><span class="sxs-lookup"><span data-stu-id="d0213-119">'T1</span></span>

<span data-ttu-id="d0213-120">第一個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d0213-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="d0213-121">T 2</span><span class="sxs-lookup"><span data-stu-id="d0213-121">'T2</span></span>

<span data-ttu-id="d0213-122">第二個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d0213-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="d0213-123">T 3</span><span class="sxs-lookup"><span data-stu-id="d0213-123">'T3</span></span>

<span data-ttu-id="d0213-124">第三個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d0213-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0213-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d0213-125">See Also</span></span>

- [<span data-ttu-id="d0213-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="d0213-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="d0213-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="d0213-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)