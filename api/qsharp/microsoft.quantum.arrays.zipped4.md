---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845321"
---
# <a name="zipped4-function"></a><span data-ttu-id="2c2f7-102">Zipped4 函式</span><span class="sxs-lookup"><span data-stu-id="2c2f7-102">Zipped4 function</span></span>

<span data-ttu-id="2c2f7-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2c2f7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2c2f7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c2f7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c2f7-105">假設有四個數組，會傳回4個元組的新陣列，讓每個4元組包含每個原始陣列的元素。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="2c2f7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2c2f7-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="2c2f7-107">first： t 1 []</span><span class="sxs-lookup"><span data-stu-id="2c2f7-107">first : 'T1[]</span></span>

<span data-ttu-id="2c2f7-108">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="2c2f7-109">第二： t 2 []</span><span class="sxs-lookup"><span data-stu-id="2c2f7-109">second : 'T2[]</span></span>

<span data-ttu-id="2c2f7-110">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="2c2f7-111">第三： t 3 []</span><span class="sxs-lookup"><span data-stu-id="2c2f7-111">third : 'T3[]</span></span>

<span data-ttu-id="2c2f7-112">陣列，其中包含每個元組第三個元素的值。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="2c2f7-113">第四個：不是 4 []</span><span class="sxs-lookup"><span data-stu-id="2c2f7-113">fourth : 'T4[]</span></span>

<span data-ttu-id="2c2f7-114">陣列，其中包含每個元組第四個元素的值。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="2c2f7-115">輸出： ( t 1，t 2，t 3，t 4) []</span><span class="sxs-lookup"><span data-stu-id="2c2f7-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="2c2f7-116">陣列，其中包含每個的表單4元組 `(first[idx], second[idx], third[idx], fourth[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="2c2f7-117">如果四個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2c2f7-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="2c2f7-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="2c2f7-119">T 1</span><span class="sxs-lookup"><span data-stu-id="2c2f7-119">'T1</span></span>

<span data-ttu-id="2c2f7-120">第一個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="2c2f7-121">T 2</span><span class="sxs-lookup"><span data-stu-id="2c2f7-121">'T2</span></span>

<span data-ttu-id="2c2f7-122">第二個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="2c2f7-123">T 3</span><span class="sxs-lookup"><span data-stu-id="2c2f7-123">'T3</span></span>

<span data-ttu-id="2c2f7-124">第三個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="2c2f7-125">T 4</span><span class="sxs-lookup"><span data-stu-id="2c2f7-125">'T4</span></span>

<span data-ttu-id="2c2f7-126">第四個陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="2c2f7-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c2f7-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c2f7-127">See Also</span></span>

- [<span data-ttu-id="2c2f7-128">Microsoft.Quantum.Arrays.Ziped</span><span class="sxs-lookup"><span data-stu-id="2c2f7-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="2c2f7-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="2c2f7-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)