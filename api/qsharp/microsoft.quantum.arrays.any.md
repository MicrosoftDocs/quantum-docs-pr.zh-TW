---
uid: Microsoft.Quantum.Arrays.Any
title: 任何函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221652"
---
# <a name="any-function"></a><span data-ttu-id="21153-102">任何函式</span><span class="sxs-lookup"><span data-stu-id="21153-102">Any function</span></span>

<span data-ttu-id="21153-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="21153-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="21153-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21153-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21153-105">針對陣列的元素定義陣列和述詞，會檢查陣列中至少有一個元素是否滿足述詞。</span><span class="sxs-lookup"><span data-stu-id="21153-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="21153-106">輸入</span><span class="sxs-lookup"><span data-stu-id="21153-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="21153-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21153-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21153-108">中 `'T` `Bool` 用來檢查元素的函式。</span><span class="sxs-lookup"><span data-stu-id="21153-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="21153-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="21153-109">array : 'T[]</span></span>

<span data-ttu-id="21153-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="21153-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="21153-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21153-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21153-112">套用至所有元素的述詞或函式的 `Bool` 值。</span><span class="sxs-lookup"><span data-stu-id="21153-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="21153-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="21153-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="21153-114">不要</span><span class="sxs-lookup"><span data-stu-id="21153-114">'T</span></span>

<span data-ttu-id="21153-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="21153-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="21153-116">備註</span><span class="sxs-lookup"><span data-stu-id="21153-116">Remarks</span></span>

<span data-ttu-id="21153-117">函式是針對泛型型別定義的，也就是說，每當我們有陣列和函式時， `'T[]` `predicate: 'T -> Bool` 我們就可以產生一個 `Bool` 值，指出某個專案是否符合 `predicate` 。</span><span class="sxs-lookup"><span data-stu-id="21153-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>