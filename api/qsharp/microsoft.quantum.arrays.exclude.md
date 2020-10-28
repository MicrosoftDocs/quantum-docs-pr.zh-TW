---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699490"
---
# <a name="exclude-function"></a><span data-ttu-id="e9c03-102">Exclude 函數</span><span class="sxs-lookup"><span data-stu-id="e9c03-102">Exclude function</span></span>

<span data-ttu-id="e9c03-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e9c03-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e9c03-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9c03-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9c03-105">傳回陣列，其中包含另一個陣列的元素，但不包括指定之索引清單中的元素。</span><span class="sxs-lookup"><span data-stu-id="e9c03-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e9c03-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e9c03-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="e9c03-107">remove： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e9c03-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e9c03-108">索引的陣列，表示應從輸出中排除的元素。</span><span class="sxs-lookup"><span data-stu-id="e9c03-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="e9c03-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="e9c03-109">array : 'T[]</span></span>

<span data-ttu-id="e9c03-110">輸出陣列中的值所採用的陣列。</span><span class="sxs-lookup"><span data-stu-id="e9c03-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="e9c03-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="e9c03-111">Output : 'T[]</span></span>

<span data-ttu-id="e9c03-112">陣列 `output` `output[0]` ，這是 `array` 其索引不會出現在中的第一個專案 `remove` ，例如 `output[1]` 第二個這類元素等等。</span><span class="sxs-lookup"><span data-stu-id="e9c03-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e9c03-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="e9c03-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e9c03-114">不要</span><span class="sxs-lookup"><span data-stu-id="e9c03-114">'T</span></span>

<span data-ttu-id="e9c03-115">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="e9c03-115">The type of the array elements.</span></span>