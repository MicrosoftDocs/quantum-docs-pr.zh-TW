---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850891"
---
# <a name="zip4-function"></a><span data-ttu-id="d9248-102">Zip4 函式</span><span class="sxs-lookup"><span data-stu-id="d9248-102">Zip4 function</span></span>

<span data-ttu-id="d9248-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d9248-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d9248-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9248-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="d9248-105">Zip4 已被取代。</span><span class="sxs-lookup"><span data-stu-id="d9248-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="d9248-106">請改用 <xref:Microsoft.Quantum.Arrays.Zipped4>。</span><span class="sxs-lookup"><span data-stu-id="d9248-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="d9248-107">假設有四個數組，會傳回4個元組的新陣列，讓每個4元組包含每個原始陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="d9248-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="d9248-108">輸入</span><span class="sxs-lookup"><span data-stu-id="d9248-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="d9248-109">first： t 1 []</span><span class="sxs-lookup"><span data-stu-id="d9248-109">first : 'T1[]</span></span>

<span data-ttu-id="d9248-110">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="d9248-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="d9248-111">第二： t 2 []</span><span class="sxs-lookup"><span data-stu-id="d9248-111">second : 'T2[]</span></span>

<span data-ttu-id="d9248-112">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="d9248-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="d9248-113">第三： t 3 []</span><span class="sxs-lookup"><span data-stu-id="d9248-113">third : 'T3[]</span></span>

<span data-ttu-id="d9248-114">陣列，其中包含每個元組第三個元素的值。</span><span class="sxs-lookup"><span data-stu-id="d9248-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="d9248-115">第四個：不是 4 []</span><span class="sxs-lookup"><span data-stu-id="d9248-115">fourth : 'T4[]</span></span>

<span data-ttu-id="d9248-116">陣列，其中包含每個元組第四個元素的值。</span><span class="sxs-lookup"><span data-stu-id="d9248-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="d9248-117">輸出： ( t 1，t 2，t 3，t 4) []</span><span class="sxs-lookup"><span data-stu-id="d9248-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="d9248-118">陣列，其中包含每個的表單4元組 `(first[idx], second[idx], third[idx], fourth[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="d9248-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="d9248-119">如果四個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="d9248-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d9248-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="d9248-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="d9248-121">T 1</span><span class="sxs-lookup"><span data-stu-id="d9248-121">'T1</span></span>

<span data-ttu-id="d9248-122">第一個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d9248-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="d9248-123">T 2</span><span class="sxs-lookup"><span data-stu-id="d9248-123">'T2</span></span>

<span data-ttu-id="d9248-124">第二個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d9248-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="d9248-125">T 3</span><span class="sxs-lookup"><span data-stu-id="d9248-125">'T3</span></span>

<span data-ttu-id="d9248-126">第三個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d9248-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="d9248-127">T 4</span><span class="sxs-lookup"><span data-stu-id="d9248-127">'T4</span></span>

<span data-ttu-id="d9248-128">第四個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="d9248-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9248-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d9248-129">See Also</span></span>

- [<span data-ttu-id="d9248-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="d9248-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="d9248-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="d9248-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)