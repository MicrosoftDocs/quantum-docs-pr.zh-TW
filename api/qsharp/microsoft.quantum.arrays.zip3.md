---
uid: Microsoft.Quantum.Arrays.Zip3
title: Array.zip3 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845360"
---
# <a name="zip3-function"></a><span data-ttu-id="5c154-102">Array.zip3 函式</span><span class="sxs-lookup"><span data-stu-id="5c154-102">Zip3 function</span></span>

<span data-ttu-id="5c154-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5c154-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5c154-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c154-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="5c154-105">Array.zip3 已被取代。</span><span class="sxs-lookup"><span data-stu-id="5c154-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="5c154-106">請改用 <xref:Microsoft.Quantum.Arrays.Zipped3>。</span><span class="sxs-lookup"><span data-stu-id="5c154-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="5c154-107">假設有三個數組，則會傳回3個元組的新陣列，讓每個3元組包含每個原始陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="5c154-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="5c154-108">輸入</span><span class="sxs-lookup"><span data-stu-id="5c154-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="5c154-109">first： t 1 []</span><span class="sxs-lookup"><span data-stu-id="5c154-109">first : 'T1[]</span></span>

<span data-ttu-id="5c154-110">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="5c154-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="5c154-111">第二： t 2 []</span><span class="sxs-lookup"><span data-stu-id="5c154-111">second : 'T2[]</span></span>

<span data-ttu-id="5c154-112">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="5c154-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="5c154-113">第三： t 3 []</span><span class="sxs-lookup"><span data-stu-id="5c154-113">third : 'T3[]</span></span>

<span data-ttu-id="5c154-114">陣列，其中包含每個元組第三個元素的值。</span><span class="sxs-lookup"><span data-stu-id="5c154-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="5c154-115">輸出： ( t 1，t 2，t 3) []</span><span class="sxs-lookup"><span data-stu-id="5c154-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="5c154-116">陣列，其中包含每個的表單3個元組 `(first[idx], second[idx], third[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="5c154-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="5c154-117">如果三個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="5c154-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5c154-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="5c154-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="5c154-119">T 1</span><span class="sxs-lookup"><span data-stu-id="5c154-119">'T1</span></span>

<span data-ttu-id="5c154-120">第一個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="5c154-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="5c154-121">T 2</span><span class="sxs-lookup"><span data-stu-id="5c154-121">'T2</span></span>

<span data-ttu-id="5c154-122">第二個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="5c154-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="5c154-123">T 3</span><span class="sxs-lookup"><span data-stu-id="5c154-123">'T3</span></span>

<span data-ttu-id="5c154-124">第三個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="5c154-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c154-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5c154-125">See Also</span></span>

- [<span data-ttu-id="5c154-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="5c154-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="5c154-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="5c154-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)