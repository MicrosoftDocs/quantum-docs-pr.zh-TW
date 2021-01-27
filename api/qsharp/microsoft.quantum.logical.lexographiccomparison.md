---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814391"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="e9fb1-102">LexographicComparison 函式</span><span class="sxs-lookup"><span data-stu-id="e9fb1-102">LexographicComparison function</span></span>

<span data-ttu-id="e9fb1-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e9fb1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e9fb1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9fb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9fb1-105">指定比較函式時，會傳回 lexographically 比較兩個數組的新函數。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="e9fb1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e9fb1-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="e9fb1-107">elementComparison： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9fb1-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9fb1-108">比較兩個元素的函式， `x` `y` 如果 `x` 小於或等於，則傳回 `y` 。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="e9fb1-109">Output： ( t []，t [] ) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9fb1-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9fb1-110">比較兩個數組的函式， `xs` `ys` 如果 `xs` 發生在 lexographical 順序之前或等於，則會傳回 `ys` 。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e9fb1-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="e9fb1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e9fb1-112">不要</span><span class="sxs-lookup"><span data-stu-id="e9fb1-112">'T</span></span>

<span data-ttu-id="e9fb1-113">要比較之陣列的元素類型。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9fb1-114">備註</span><span class="sxs-lookup"><span data-stu-id="e9fb1-114">Remarks</span></span>

<span data-ttu-id="e9fb1-115">兩個數組之間的 lexographic `xs` 比較 `ys` 會由下列程式定義。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="e9fb1-116">`x` `y` 如果 `elementComparison(x, y)` 和 `elementComparison(y, x)` 都是 true，就表示兩個元素和相等。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="e9fb1-117">這兩個數組都是依元素進行比較，直到第一對不相等的元素為止。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="e9fb1-118">在 lexographical 順序中，第一個會根據所發生的元素，包含最先發生的專案 `elementComparison` 。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="e9fb1-119">如果找不到任何 inequivalent 元素，且其中一個陣列的長度超過另一個陣列，則會先將較短的陣列視為發生。</span><span class="sxs-lookup"><span data-stu-id="e9fb1-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9fb1-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e9fb1-120">See Also</span></span>

- [<span data-ttu-id="e9fb1-121">依序排序的</span><span class="sxs-lookup"><span data-stu-id="e9fb1-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)