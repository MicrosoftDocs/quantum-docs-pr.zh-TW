---
uid: Microsoft.Quantum.Arrays.Sorted
title: 已排序函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845435"
---
# <a name="sorted-function"></a><span data-ttu-id="62a30-102">已排序函數</span><span class="sxs-lookup"><span data-stu-id="62a30-102">Sorted function</span></span>

<span data-ttu-id="62a30-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="62a30-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="62a30-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62a30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62a30-105">指定陣列時，會傳回該陣列的元素，並依指定的比較函式排序。</span><span class="sxs-lookup"><span data-stu-id="62a30-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="62a30-106">輸入</span><span class="sxs-lookup"><span data-stu-id="62a30-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="62a30-107">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="62a30-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="62a30-108">比較兩個元素的函式，如果是，則會將其 `a` 視為小於或等於 `b` `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="62a30-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="62a30-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="62a30-109">array : 'T[]</span></span>

<span data-ttu-id="62a30-110">要排序的陣列。</span><span class="sxs-lookup"><span data-stu-id="62a30-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="62a30-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="62a30-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="62a30-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="62a30-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="62a30-113">不要</span><span class="sxs-lookup"><span data-stu-id="62a30-113">'T</span></span>

<span data-ttu-id="62a30-114">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="62a30-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="62a30-115">範例</span><span class="sxs-lookup"><span data-stu-id="62a30-115">Example</span></span>

<span data-ttu-id="62a30-116">下列程式碼片段會以遞增順序排序要進行的整數陣列：</span><span class="sxs-lookup"><span data-stu-id="62a30-116">The following snippet sorts an array of integers to occur in ascending order:</span></span>

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a><span data-ttu-id="62a30-117">備註</span><span class="sxs-lookup"><span data-stu-id="62a30-117">Remarks</span></span>

<span data-ttu-id="62a30-118">函式 `comparison` 假設為可轉移，因此，如果 `comparison(a, b)` 和 `comparison(b, c)` ，則 `comparison(a, c)` 會假設為。</span><span class="sxs-lookup"><span data-stu-id="62a30-118">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="62a30-119">如果這個屬性不存在，則此函式的輸出可能會不正確。</span><span class="sxs-lookup"><span data-stu-id="62a30-119">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="62a30-120">因為這是函式，所以即使兩個元素被視為相等，也會完全 determinstic 結果，也 `comparison` 就是當 `comparison(a, b)` 和 `comparison(b, a)` 都是時 `true` 。</span><span class="sxs-lookup"><span data-stu-id="62a30-120">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="62a30-121">尤其是，此函式所執行的排序保證是穩定的，因此，如果在 `a` `b` 和內的兩個專案都是以相同的順序出現在中，則也會在 `array` `comparison` `a` `b` 輸出中顯示。</span><span class="sxs-lookup"><span data-stu-id="62a30-121">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="62a30-122">例如：</span><span class="sxs-lookup"><span data-stu-id="62a30-122">For example:</span></span>

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```