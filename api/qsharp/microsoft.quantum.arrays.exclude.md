---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221346"
---
# <a name="exclude-function"></a><span data-ttu-id="d78cb-102">Exclude 函數</span><span class="sxs-lookup"><span data-stu-id="d78cb-102">Exclude function</span></span>

<span data-ttu-id="d78cb-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d78cb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d78cb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d78cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d78cb-105">傳回陣列，其中包含另一個陣列的元素，但不包括指定之索引清單中的元素。</span><span class="sxs-lookup"><span data-stu-id="d78cb-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="d78cb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d78cb-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="d78cb-107">remove： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d78cb-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d78cb-108">索引的陣列，表示應從輸出中排除的元素。</span><span class="sxs-lookup"><span data-stu-id="d78cb-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="d78cb-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="d78cb-109">array : 'T[]</span></span>

<span data-ttu-id="d78cb-110">輸出陣列中的值所採用的陣列。</span><span class="sxs-lookup"><span data-stu-id="d78cb-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="d78cb-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="d78cb-111">Output : 'T[]</span></span>

<span data-ttu-id="d78cb-112">陣列 `output` `output[0]` ，這是 `array` 其索引不會出現在中的第一個專案 `remove` ，例如 `output[1]` 第二個這類元素等等。</span><span class="sxs-lookup"><span data-stu-id="d78cb-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d78cb-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="d78cb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d78cb-114">不要</span><span class="sxs-lookup"><span data-stu-id="d78cb-114">'T</span></span>

<span data-ttu-id="d78cb-115">陣列元素的類型。</span><span class="sxs-lookup"><span data-stu-id="d78cb-115">The type of the array elements.</span></span>