---
uid: Microsoft.Quantum.Arrays.Zipped
title: 壓縮函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845340"
---
# <a name="zipped-function"></a><span data-ttu-id="39d31-102">壓縮函數</span><span class="sxs-lookup"><span data-stu-id="39d31-102">Zipped function</span></span>

<span data-ttu-id="39d31-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39d31-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39d31-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39d31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39d31-105">假設有兩個數組，會傳回一組新的陣列，讓每一組都包含每個原始陣列中的元素。</span><span class="sxs-lookup"><span data-stu-id="39d31-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="39d31-106">輸入</span><span class="sxs-lookup"><span data-stu-id="39d31-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="39d31-107">左方： t []</span><span class="sxs-lookup"><span data-stu-id="39d31-107">left : 'T[]</span></span>

<span data-ttu-id="39d31-108">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="39d31-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="39d31-109">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="39d31-109">right : 'U[]</span></span>

<span data-ttu-id="39d31-110">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="39d31-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="39d31-111">Output： ( t，' U) []</span><span class="sxs-lookup"><span data-stu-id="39d31-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="39d31-112">陣列，其中包含每個的表單配對 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="39d31-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="39d31-113">如果兩個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="39d31-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39d31-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="39d31-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39d31-115">不要</span><span class="sxs-lookup"><span data-stu-id="39d31-115">'T</span></span>

<span data-ttu-id="39d31-116">左方陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="39d31-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="39d31-117">' U</span><span class="sxs-lookup"><span data-stu-id="39d31-117">'U</span></span>

<span data-ttu-id="39d31-118">右陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="39d31-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="39d31-119">範例</span><span class="sxs-lookup"><span data-stu-id="39d31-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="39d31-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39d31-120">See Also</span></span>

- [<span data-ttu-id="39d31-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="39d31-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="39d31-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="39d31-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="39d31-123">。已解壓縮</span><span class="sxs-lookup"><span data-stu-id="39d31-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)