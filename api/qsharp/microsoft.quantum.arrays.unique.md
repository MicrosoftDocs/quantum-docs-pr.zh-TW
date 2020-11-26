---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220003"
---
# <a name="unique-function"></a><span data-ttu-id="7d74e-102">Unique 函數</span><span class="sxs-lookup"><span data-stu-id="7d74e-102">Unique function</span></span>

<span data-ttu-id="7d74e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7d74e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7d74e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d74e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d74e-105">傳回不等於相鄰元素的新陣列。</span><span class="sxs-lookup"><span data-stu-id="7d74e-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="7d74e-106">描述</span><span class="sxs-lookup"><span data-stu-id="7d74e-106">Description</span></span>

<span data-ttu-id="7d74e-107">假設有一些元素陣列和函式測試是否相等，此函式會傳回新的陣列，其中會保留專案的相對順序，但是所有相等的相鄰元素都會篩選成隻有一個專案。</span><span class="sxs-lookup"><span data-stu-id="7d74e-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="7d74e-108">輸入</span><span class="sxs-lookup"><span data-stu-id="7d74e-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="7d74e-109">等於： ( 否，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d74e-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d74e-110">比較兩個元素的函式， `a` 如果是，則視為等於 `b` `equal(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="7d74e-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="7d74e-111">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="7d74e-111">array : 'T[]</span></span>

<span data-ttu-id="7d74e-112">要針對唯一元素篩選的陣列。</span><span class="sxs-lookup"><span data-stu-id="7d74e-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="7d74e-113">Output： t []</span><span class="sxs-lookup"><span data-stu-id="7d74e-113">Output : 'T[]</span></span>

<span data-ttu-id="7d74e-114">不等於相鄰元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="7d74e-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7d74e-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="7d74e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d74e-116">不要</span><span class="sxs-lookup"><span data-stu-id="7d74e-116">'T</span></span>

<span data-ttu-id="7d74e-117">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7d74e-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d74e-118">備註</span><span class="sxs-lookup"><span data-stu-id="7d74e-118">Remarks</span></span>

<span data-ttu-id="7d74e-119">如果有多個元素相等，但彼此不同，則輸出陣列中會出現多個專案。</span><span class="sxs-lookup"><span data-stu-id="7d74e-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="7d74e-120">使用此函式搭配 `Sorted` 來取得具有整體唯一元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="7d74e-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>