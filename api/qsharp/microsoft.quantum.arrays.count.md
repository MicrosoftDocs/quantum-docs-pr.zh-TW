---
uid: Microsoft.Quantum.Arrays.Count
title: Count 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699510"
---
# <a name="count-function"></a><span data-ttu-id="d5395-102">Count 函數</span><span class="sxs-lookup"><span data-stu-id="d5395-102">Count function</span></span>

<span data-ttu-id="d5395-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d5395-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d5395-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5395-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5395-105">針對陣列的元素定義陣列和述詞，會傳回陣列中的元素數目，這些專案是由滿足述詞的元素所組成。</span><span class="sxs-lookup"><span data-stu-id="d5395-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="d5395-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d5395-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="d5395-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d5395-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d5395-108">從 `'T` 到布林值的函式，用來篩選元素。</span><span class="sxs-lookup"><span data-stu-id="d5395-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="d5395-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="d5395-109">array : 'T[]</span></span>

<span data-ttu-id="d5395-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="d5395-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="d5395-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5395-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5395-112">中符合述詞的元素數目 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d5395-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d5395-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="d5395-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5395-114">不要</span><span class="sxs-lookup"><span data-stu-id="d5395-114">'T</span></span>

<span data-ttu-id="d5395-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d5395-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5395-116">備註</span><span class="sxs-lookup"><span data-stu-id="d5395-116">Remarks</span></span>

<span data-ttu-id="d5395-117">函式是針對泛型型別定義的，也就是說，每當我們有陣列和述詞時，就 `'T[]` `'T -> Bool` 可以篩選元素。</span><span class="sxs-lookup"><span data-stu-id="d5395-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>