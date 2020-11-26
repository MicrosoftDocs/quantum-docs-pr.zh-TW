---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: c9dd07ddc63f1d75952d3841997eed0f78e054b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219782"
---
# <a name="zip4-function"></a><span data-ttu-id="9d69f-102">Zip4 函式</span><span class="sxs-lookup"><span data-stu-id="9d69f-102">Zip4 function</span></span>

<span data-ttu-id="9d69f-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9d69f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9d69f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d69f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="9d69f-105">Zip4 已被取代。</span><span class="sxs-lookup"><span data-stu-id="9d69f-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="9d69f-106">請改用 <xref:Microsoft.Quantum.Arrays.Zipped4>。</span><span class="sxs-lookup"><span data-stu-id="9d69f-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="9d69f-107">假設有四個數組，會傳回4個元組的新陣列，讓每個4元組包含每個原始陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="9d69f-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="9d69f-108">輸入</span><span class="sxs-lookup"><span data-stu-id="9d69f-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="9d69f-109">first： t 1 []</span><span class="sxs-lookup"><span data-stu-id="9d69f-109">first : 'T1[]</span></span>

<span data-ttu-id="9d69f-110">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="9d69f-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="9d69f-111">第二： t 2 []</span><span class="sxs-lookup"><span data-stu-id="9d69f-111">second : 'T2[]</span></span>

<span data-ttu-id="9d69f-112">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="9d69f-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="9d69f-113">第三： t 3 []</span><span class="sxs-lookup"><span data-stu-id="9d69f-113">third : 'T3[]</span></span>

<span data-ttu-id="9d69f-114">陣列，其中包含每個元組第三個元素的值。</span><span class="sxs-lookup"><span data-stu-id="9d69f-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="9d69f-115">第四個：不是 4 []</span><span class="sxs-lookup"><span data-stu-id="9d69f-115">fourth : 'T4[]</span></span>

<span data-ttu-id="9d69f-116">陣列，其中包含每個元組第四個元素的值。</span><span class="sxs-lookup"><span data-stu-id="9d69f-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="9d69f-117">輸出： ( t 1，t 2，t 3，t 4) []</span><span class="sxs-lookup"><span data-stu-id="9d69f-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="9d69f-118">陣列，其中包含每個的表單4元組 `(first[idx], second[idx], third[idx], fourth[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="9d69f-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="9d69f-119">如果四個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="9d69f-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9d69f-120">類型參數</span><span class="sxs-lookup"><span data-stu-id="9d69f-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="9d69f-121">T 1</span><span class="sxs-lookup"><span data-stu-id="9d69f-121">'T1</span></span>

<span data-ttu-id="9d69f-122">第一個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="9d69f-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="9d69f-123">T 2</span><span class="sxs-lookup"><span data-stu-id="9d69f-123">'T2</span></span>

<span data-ttu-id="9d69f-124">第二個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="9d69f-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="9d69f-125">T 3</span><span class="sxs-lookup"><span data-stu-id="9d69f-125">'T3</span></span>

<span data-ttu-id="9d69f-126">第三個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="9d69f-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="9d69f-127">T 4</span><span class="sxs-lookup"><span data-stu-id="9d69f-127">'T4</span></span>

<span data-ttu-id="9d69f-128">第四個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="9d69f-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d69f-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d69f-129">See Also</span></span>

- [<span data-ttu-id="9d69f-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="9d69f-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="9d69f-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="9d69f-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)