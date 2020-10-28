---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699398"
---
# <a name="zip-function"></a><span data-ttu-id="524df-102">Zip 函數</span><span class="sxs-lookup"><span data-stu-id="524df-102">Zip function</span></span>

<span data-ttu-id="524df-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="524df-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="524df-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="524df-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="524df-105">Zip 已淘汰。</span><span class="sxs-lookup"><span data-stu-id="524df-105">Zip has been deprecated.</span></span> <span data-ttu-id="524df-106">請改用 <xref:Microsoft.Quantum.Arrays.Zipped>。</span><span class="sxs-lookup"><span data-stu-id="524df-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="524df-107">假設有兩個數組，會傳回一組新的陣列，讓每一組都包含每個原始陣列中的元素。</span><span class="sxs-lookup"><span data-stu-id="524df-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="524df-108">輸入</span><span class="sxs-lookup"><span data-stu-id="524df-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="524df-109">左方： t []</span><span class="sxs-lookup"><span data-stu-id="524df-109">left : 'T[]</span></span>

<span data-ttu-id="524df-110">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="524df-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="524df-111">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="524df-111">right : 'U[]</span></span>

<span data-ttu-id="524df-112">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="524df-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="524df-113">Output： ( t，' U) []</span><span class="sxs-lookup"><span data-stu-id="524df-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="524df-114">陣列，其中包含每個的表單配對 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="524df-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="524df-115">如果兩個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="524df-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="524df-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="524df-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="524df-117">不要</span><span class="sxs-lookup"><span data-stu-id="524df-117">'T</span></span>

<span data-ttu-id="524df-118">左方陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="524df-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="524df-119">' U</span><span class="sxs-lookup"><span data-stu-id="524df-119">'U</span></span>

<span data-ttu-id="524df-120">右陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="524df-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="524df-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="524df-121">See Also</span></span>

- [<span data-ttu-id="524df-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="524df-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="524df-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="524df-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="524df-124">。已解壓縮</span><span class="sxs-lookup"><span data-stu-id="524df-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)