---
uid: Microsoft.Quantum.Arrays.Zipped
title: 壓縮函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219748"
---
# <a name="zipped-function"></a><span data-ttu-id="7b109-102">壓縮函數</span><span class="sxs-lookup"><span data-stu-id="7b109-102">Zipped function</span></span>

<span data-ttu-id="7b109-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7b109-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7b109-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b109-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b109-105">假設有兩個數組，會傳回一組新的陣列，讓每一組都包含每個原始陣列中的元素。</span><span class="sxs-lookup"><span data-stu-id="7b109-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="7b109-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7b109-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="7b109-107">左方： t []</span><span class="sxs-lookup"><span data-stu-id="7b109-107">left : 'T[]</span></span>

<span data-ttu-id="7b109-108">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="7b109-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="7b109-109">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="7b109-109">right : 'U[]</span></span>

<span data-ttu-id="7b109-110">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="7b109-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="7b109-111">Output： ( t，' U) []</span><span class="sxs-lookup"><span data-stu-id="7b109-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="7b109-112">陣列，其中包含每個的表單配對 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="7b109-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="7b109-113">如果兩個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="7b109-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7b109-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="7b109-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b109-115">不要</span><span class="sxs-lookup"><span data-stu-id="7b109-115">'T</span></span>

<span data-ttu-id="7b109-116">左方陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="7b109-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="7b109-117">' U</span><span class="sxs-lookup"><span data-stu-id="7b109-117">'U</span></span>

<span data-ttu-id="7b109-118">右陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="7b109-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b109-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7b109-119">See Also</span></span>

- [<span data-ttu-id="7b109-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="7b109-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="7b109-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="7b109-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="7b109-122">。已解壓縮</span><span class="sxs-lookup"><span data-stu-id="7b109-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)