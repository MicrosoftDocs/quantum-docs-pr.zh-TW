---
uid: Microsoft.Quantum.Arrays.Filtered
title: 篩選函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847152"
---
# <a name="filtered-function"></a><span data-ttu-id="ca969-102">篩選函數</span><span class="sxs-lookup"><span data-stu-id="ca969-102">Filtered function</span></span>

<span data-ttu-id="ca969-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ca969-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ca969-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca969-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca969-105">指定陣列和定義給陣列元素的述詞時，會傳回陣列，其中包含符合述詞的元素。</span><span class="sxs-lookup"><span data-stu-id="ca969-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ca969-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ca969-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ca969-107">述詞： t-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ca969-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ca969-108">從 `'T` 到布林值的函式，用來篩選元素。</span><span class="sxs-lookup"><span data-stu-id="ca969-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ca969-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="ca969-109">array : 'T[]</span></span>

<span data-ttu-id="ca969-110">的元素陣列 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="ca969-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="ca969-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="ca969-111">Output : 'T[]</span></span>

<span data-ttu-id="ca969-112">滿足述詞的 `'T[]` 元素陣列。</span><span class="sxs-lookup"><span data-stu-id="ca969-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ca969-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="ca969-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca969-114">不要</span><span class="sxs-lookup"><span data-stu-id="ca969-114">'T</span></span>

<span data-ttu-id="ca969-115">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="ca969-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="ca969-116">範例</span><span class="sxs-lookup"><span data-stu-id="ca969-116">Example</span></span>

<span data-ttu-id="ca969-117">下列程式碼示範「篩選」函數。</span><span class="sxs-lookup"><span data-stu-id="ca969-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="ca969-118">使用函式定義述詞 @"microsoft.quantum.logical.greaterthani" ：</span><span class="sxs-lookup"><span data-stu-id="ca969-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="ca969-119">此範例預期的結果會是大於5的數位陣列。</span><span class="sxs-lookup"><span data-stu-id="ca969-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca969-120">備註</span><span class="sxs-lookup"><span data-stu-id="ca969-120">Remarks</span></span>

<span data-ttu-id="ca969-121">函式是針對泛型型別定義的，也就是說，每當我們有陣列和述詞時，就 `'T[]` `'T -> Bool` 可以篩選元素。</span><span class="sxs-lookup"><span data-stu-id="ca969-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>