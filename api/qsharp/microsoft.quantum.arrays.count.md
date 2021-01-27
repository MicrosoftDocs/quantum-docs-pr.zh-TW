---
uid: Microsoft.Quantum.Arrays.Count
title: Count 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842842"
---
# <a name="count-function"></a><span data-ttu-id="dd9cb-102">Count 函數</span><span class="sxs-lookup"><span data-stu-id="dd9cb-102">Count function</span></span>

<span data-ttu-id="dd9cb-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dd9cb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dd9cb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd9cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd9cb-105">針對陣列的元素定義陣列和述詞，會傳回陣列中的元素數目，這些專案是由滿足述詞的元素所組成。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="dd9cb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dd9cb-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="dd9cb-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dd9cb-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dd9cb-108">從 `'T` 到布林值的函式，用來篩選元素。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="dd9cb-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="dd9cb-109">array : 'T[]</span></span>

<span data-ttu-id="dd9cb-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="dd9cb-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd9cb-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd9cb-112">中符合述詞的元素數目 `array` 。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dd9cb-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="dd9cb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dd9cb-114">不要</span><span class="sxs-lookup"><span data-stu-id="dd9cb-114">'T</span></span>

<span data-ttu-id="dd9cb-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="dd9cb-116">範例</span><span class="sxs-lookup"><span data-stu-id="dd9cb-116">Example</span></span>

<span data-ttu-id="dd9cb-117">下列程式碼示範 "Count" 函式。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-117">The following code demonstrates the "Count" function.</span></span>
<span data-ttu-id="dd9cb-118">使用函式定義述詞 @"microsoft.quantum.logical.greaterthani" ：</span><span class="sxs-lookup"><span data-stu-id="dd9cb-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a><span data-ttu-id="dd9cb-119">備註</span><span class="sxs-lookup"><span data-stu-id="dd9cb-119">Remarks</span></span>

<span data-ttu-id="dd9cb-120">函式是針對泛型型別定義的，也就是說，每當我們有陣列和述詞時，就 `'T[]` `'T -> Bool` 可以篩選元素。</span><span class="sxs-lookup"><span data-stu-id="dd9cb-120">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>