---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 176e15139a27d375fb047c07fa1ee778dc8cc2ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221363"
---
# <a name="equala-function"></a><span data-ttu-id="7df02-102">EqualA 函式</span><span class="sxs-lookup"><span data-stu-id="7df02-102">EqualA function</span></span>

<span data-ttu-id="7df02-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7df02-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7df02-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7df02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7df02-105">如果有兩個相同類型的陣列和針對陣列的元素配對所定義的述詞，就會檢查陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="7df02-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="7df02-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7df02-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="7df02-107">等於： ( 否，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7df02-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7df02-108">來自元組的函式， `('T, 'T)` `Bool` 用來檢查陣列的兩個元素是否相等。</span><span class="sxs-lookup"><span data-stu-id="7df02-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="7df02-109">array1： t []</span><span class="sxs-lookup"><span data-stu-id="7df02-109">array1 : 'T[]</span></span>

<span data-ttu-id="7df02-110">要比較的第一個陣列。</span><span class="sxs-lookup"><span data-stu-id="7df02-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="7df02-111">array2： t []</span><span class="sxs-lookup"><span data-stu-id="7df02-111">array2 : 'T[]</span></span>

<span data-ttu-id="7df02-112">要比較的第二個數組。</span><span class="sxs-lookup"><span data-stu-id="7df02-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7df02-113">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7df02-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7df02-114">如果和相等，則值為 `true` `array1` `array2` 。</span><span class="sxs-lookup"><span data-stu-id="7df02-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="7df02-115">也就是說，如果兩個數組都有相同的長度，而且所有元素都等於所定義的 `equal` 。</span><span class="sxs-lookup"><span data-stu-id="7df02-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7df02-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="7df02-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7df02-117">不要</span><span class="sxs-lookup"><span data-stu-id="7df02-117">'T</span></span>

<span data-ttu-id="7df02-118">每個陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="7df02-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="7df02-119">備註</span><span class="sxs-lookup"><span data-stu-id="7df02-119">Remarks</span></span>

<span data-ttu-id="7df02-120">這個函式是針對泛型型別所定義;也就是說，只要有兩個數組和一個函式，此函式就 `'T[]` 會傳回 `equal: ('T, 'T) -> Bool` 一個 `Bool` 值，指出陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="7df02-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="7df02-121">針對兩個被視為相等的陣列，它們必須有相等的長度，而且陣列中相同位置的元素必須相等。</span><span class="sxs-lookup"><span data-stu-id="7df02-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>