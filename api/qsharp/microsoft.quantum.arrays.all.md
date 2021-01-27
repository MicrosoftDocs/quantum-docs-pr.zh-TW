---
uid: Microsoft.Quantum.Arrays.All
title: All 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842888"
---
# <a name="all-function"></a><span data-ttu-id="91c19-102">All 函數</span><span class="sxs-lookup"><span data-stu-id="91c19-102">All function</span></span>

<span data-ttu-id="91c19-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="91c19-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="91c19-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91c19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91c19-105">針對陣列的元素定義了陣列和述詞，並檢查陣列的所有元素是否滿足述詞。</span><span class="sxs-lookup"><span data-stu-id="91c19-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="91c19-106">輸入</span><span class="sxs-lookup"><span data-stu-id="91c19-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="91c19-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="91c19-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="91c19-108">中 `'T` `Bool` 用來檢查元素的函式。</span><span class="sxs-lookup"><span data-stu-id="91c19-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="91c19-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="91c19-109">array : 'T[]</span></span>

<span data-ttu-id="91c19-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="91c19-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="91c19-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="91c19-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="91c19-112">套用至所有專案的述詞之 AND 函式的 `Bool` 值。</span><span class="sxs-lookup"><span data-stu-id="91c19-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91c19-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="91c19-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91c19-114">不要</span><span class="sxs-lookup"><span data-stu-id="91c19-114">'T</span></span>

<span data-ttu-id="91c19-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="91c19-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="91c19-116">範例</span><span class="sxs-lookup"><span data-stu-id="91c19-116">Example</span></span>

<span data-ttu-id="91c19-117">下列程式碼會檢查陣列的所有元素是否為非零：</span><span class="sxs-lookup"><span data-stu-id="91c19-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="91c19-118">備註</span><span class="sxs-lookup"><span data-stu-id="91c19-118">Remarks</span></span>

<span data-ttu-id="91c19-119">函式是針對泛型型別定義的，也就是說，只要有陣列和函式， `'T[]` `predicate: 'T -> Bool` 我們就可以產生一個 `Bool` 值，指出所有元素是否都符合 `predicate` 。</span><span class="sxs-lookup"><span data-stu-id="91c19-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>