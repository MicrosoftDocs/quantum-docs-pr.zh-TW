---
uid: Microsoft.Quantum.Arrays.Zipped
title: 壓縮函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699395"
---
# <a name="zipped-function"></a><span data-ttu-id="f49c5-102">壓縮函數</span><span class="sxs-lookup"><span data-stu-id="f49c5-102">Zipped function</span></span>

<span data-ttu-id="f49c5-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f49c5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f49c5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f49c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f49c5-105">假設有兩個數組，會傳回一組新的陣列，讓每一組都包含每個原始陣列中的元素。</span><span class="sxs-lookup"><span data-stu-id="f49c5-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="f49c5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f49c5-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="f49c5-107">左方： t []</span><span class="sxs-lookup"><span data-stu-id="f49c5-107">left : 'T[]</span></span>

<span data-ttu-id="f49c5-108">陣列，其中包含每個元組的第一個元素值。</span><span class="sxs-lookup"><span data-stu-id="f49c5-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="f49c5-109">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="f49c5-109">right : 'U[]</span></span>

<span data-ttu-id="f49c5-110">陣列，其中包含每個元組的第二個元素的值。</span><span class="sxs-lookup"><span data-stu-id="f49c5-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="f49c5-111">Output： ( t，' U) []</span><span class="sxs-lookup"><span data-stu-id="f49c5-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="f49c5-112">陣列，其中包含每個的表單配對 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="f49c5-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="f49c5-113">如果兩個數組的長度不相等，則輸出將會是輸入較短的時間長度。</span><span class="sxs-lookup"><span data-stu-id="f49c5-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f49c5-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="f49c5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f49c5-115">不要</span><span class="sxs-lookup"><span data-stu-id="f49c5-115">'T</span></span>

<span data-ttu-id="f49c5-116">左方陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="f49c5-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="f49c5-117">' U</span><span class="sxs-lookup"><span data-stu-id="f49c5-117">'U</span></span>

<span data-ttu-id="f49c5-118">右陣列元素的型別。</span><span class="sxs-lookup"><span data-stu-id="f49c5-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f49c5-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f49c5-119">See Also</span></span>

- [<span data-ttu-id="f49c5-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="f49c5-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="f49c5-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="f49c5-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="f49c5-122">。已解壓縮</span><span class="sxs-lookup"><span data-stu-id="f49c5-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)