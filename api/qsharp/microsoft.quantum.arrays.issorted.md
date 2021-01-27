---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845727"
---
# <a name="issorted-function"></a><span data-ttu-id="9143b-102">IsSorted 函式</span><span class="sxs-lookup"><span data-stu-id="9143b-102">IsSorted function</span></span>

<span data-ttu-id="9143b-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9143b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9143b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9143b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9143b-105">指定陣列時，會傳回該陣列是否依照指定的比較函式的定義排序。</span><span class="sxs-lookup"><span data-stu-id="9143b-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="9143b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9143b-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="9143b-107">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9143b-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9143b-108">比較兩個元素的函式，如果是，則會將其 `a` 視為小於或等於 `b` `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="9143b-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="9143b-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="9143b-109">array : 'T[]</span></span>

<span data-ttu-id="9143b-110">要檢查的陣列。</span><span class="sxs-lookup"><span data-stu-id="9143b-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9143b-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9143b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9143b-112">`true` 只有在針對每對元素進行，以及 `a` `b` 該順序發生時，才 `array` `comparison(a, b)` 會是 `true` 。</span><span class="sxs-lookup"><span data-stu-id="9143b-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9143b-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="9143b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9143b-114">不要</span><span class="sxs-lookup"><span data-stu-id="9143b-114">'T</span></span>

<span data-ttu-id="9143b-115">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="9143b-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9143b-116">備註</span><span class="sxs-lookup"><span data-stu-id="9143b-116">Remarks</span></span>

<span data-ttu-id="9143b-117">函式 `comparison` 假設為可轉移，因此，如果 `comparison(a, b)` 和 `comparison(b, c)` ，則 `comparison(a, c)` 會假設為。</span><span class="sxs-lookup"><span data-stu-id="9143b-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="9143b-118">如果這個屬性不存在，則此函式的輸出可能會不正確。</span><span class="sxs-lookup"><span data-stu-id="9143b-118">If this property does not hold, then the output of this function may be incorrect.</span></span>