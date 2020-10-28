---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699407"
---
# <a name="unique-function"></a><span data-ttu-id="b4be3-102">Unique 函數</span><span class="sxs-lookup"><span data-stu-id="b4be3-102">Unique function</span></span>

<span data-ttu-id="b4be3-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b4be3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b4be3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4be3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4be3-105">傳回不等於相鄰元素的新陣列。</span><span class="sxs-lookup"><span data-stu-id="b4be3-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b4be3-106">描述</span><span class="sxs-lookup"><span data-stu-id="b4be3-106">Description</span></span>

<span data-ttu-id="b4be3-107">假設有一些元素陣列和函式測試是否相等，此函式會傳回新的陣列，其中會保留專案的相對順序，但是所有相等的相鄰元素都會篩選成隻有一個專案。</span><span class="sxs-lookup"><span data-stu-id="b4be3-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="b4be3-108">輸入</span><span class="sxs-lookup"><span data-stu-id="b4be3-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="b4be3-109">等於： ( 否，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b4be3-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b4be3-110">比較兩個元素的函式， `a` 如果是，則視為等於 `b` `equal(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="b4be3-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="b4be3-111">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="b4be3-111">array : 'T[]</span></span>

<span data-ttu-id="b4be3-112">要針對唯一元素篩選的陣列。</span><span class="sxs-lookup"><span data-stu-id="b4be3-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b4be3-113">Output： t []</span><span class="sxs-lookup"><span data-stu-id="b4be3-113">Output : 'T[]</span></span>

<span data-ttu-id="b4be3-114">不等於相鄰元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="b4be3-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b4be3-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="b4be3-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b4be3-116">不要</span><span class="sxs-lookup"><span data-stu-id="b4be3-116">'T</span></span>

<span data-ttu-id="b4be3-117">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="b4be3-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4be3-118">備註</span><span class="sxs-lookup"><span data-stu-id="b4be3-118">Remarks</span></span>

<span data-ttu-id="b4be3-119">如果有多個元素相等，但彼此不同，則輸出陣列中會出現多個專案。</span><span class="sxs-lookup"><span data-stu-id="b4be3-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="b4be3-120">使用此函式搭配 `Sorted` 來取得具有整體唯一元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="b4be3-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>