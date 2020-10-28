---
uid: Microsoft.Quantum.Arrays.All
title: All 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699523"
---
# <a name="all-function"></a><span data-ttu-id="890f9-102">All 函數</span><span class="sxs-lookup"><span data-stu-id="890f9-102">All function</span></span>

<span data-ttu-id="890f9-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="890f9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="890f9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="890f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="890f9-105">針對陣列的元素定義了陣列和述詞，並檢查陣列的所有元素是否滿足述詞。</span><span class="sxs-lookup"><span data-stu-id="890f9-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="890f9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="890f9-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="890f9-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="890f9-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="890f9-108">中 `'T` `Bool` 用來檢查元素的函式。</span><span class="sxs-lookup"><span data-stu-id="890f9-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="890f9-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="890f9-109">array : 'T[]</span></span>

<span data-ttu-id="890f9-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="890f9-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="890f9-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="890f9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="890f9-112">套用至所有專案的述詞之 AND 函式的 `Bool` 值。</span><span class="sxs-lookup"><span data-stu-id="890f9-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="890f9-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="890f9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="890f9-114">不要</span><span class="sxs-lookup"><span data-stu-id="890f9-114">'T</span></span>

<span data-ttu-id="890f9-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="890f9-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="890f9-116">備註</span><span class="sxs-lookup"><span data-stu-id="890f9-116">Remarks</span></span>

<span data-ttu-id="890f9-117">函式是針對泛型型別定義的，也就是說，只要有陣列和函式， `'T[]` `predicate: 'T -> Bool` 我們就可以產生一個 `Bool` 值，指出所有元素是否都符合 `predicate` 。</span><span class="sxs-lookup"><span data-stu-id="890f9-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>