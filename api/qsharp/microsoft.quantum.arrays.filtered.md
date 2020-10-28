---
uid: Microsoft.Quantum.Arrays.Filtered
title: 篩選函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699488"
---
# <a name="filtered-function"></a><span data-ttu-id="a7cb2-102">篩選函數</span><span class="sxs-lookup"><span data-stu-id="a7cb2-102">Filtered function</span></span>

<span data-ttu-id="a7cb2-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a7cb2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a7cb2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7cb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7cb2-105">指定陣列和定義給陣列元素的述詞時，會傳回陣列，其中包含符合述詞的元素。</span><span class="sxs-lookup"><span data-stu-id="a7cb2-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a7cb2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a7cb2-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="a7cb2-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7cb2-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7cb2-108">從 `'T` 到布林值的函式，用來篩選元素。</span><span class="sxs-lookup"><span data-stu-id="a7cb2-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="a7cb2-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="a7cb2-109">array : 'T[]</span></span>

<span data-ttu-id="a7cb2-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="a7cb2-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="a7cb2-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="a7cb2-111">Output : 'T[]</span></span>

<span data-ttu-id="a7cb2-112">滿足述詞的 `'T[]` 元素陣列。</span><span class="sxs-lookup"><span data-stu-id="a7cb2-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7cb2-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="a7cb2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7cb2-114">不要</span><span class="sxs-lookup"><span data-stu-id="a7cb2-114">'T</span></span>

<span data-ttu-id="a7cb2-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a7cb2-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7cb2-116">備註</span><span class="sxs-lookup"><span data-stu-id="a7cb2-116">Remarks</span></span>

<span data-ttu-id="a7cb2-117">函式是針對泛型型別定義的，也就是說，每當我們有陣列和述詞時，就 `'T[]` `'T -> Bool` 可以篩選元素。</span><span class="sxs-lookup"><span data-stu-id="a7cb2-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>