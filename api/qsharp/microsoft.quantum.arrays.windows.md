---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699401"
---
# <a name="windows-function"></a><span data-ttu-id="205c4-102">Windows 函數</span><span class="sxs-lookup"><span data-stu-id="205c4-102">Windows function</span></span>

<span data-ttu-id="205c4-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="205c4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="205c4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="205c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="205c4-105">傳回長度的所有連續 subarrays `size` 。</span><span class="sxs-lookup"><span data-stu-id="205c4-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="205c4-106">描述</span><span class="sxs-lookup"><span data-stu-id="205c4-106">Description</span></span>

<span data-ttu-id="205c4-107">此函數會依 `n - size + 1` 序傳回所有長度的 subarrays `size` ，其中 `n` 是的長度 `arr` 。</span><span class="sxs-lookup"><span data-stu-id="205c4-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="205c4-108">第一個 subarrays 會 `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 一直到最後一個子陣列為止 `arr[n - size..n - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="205c4-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="205c4-109">如果為 `size <= 0` 或 `size > n` ，則會傳回空陣列。</span><span class="sxs-lookup"><span data-stu-id="205c4-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="205c4-110">輸入</span><span class="sxs-lookup"><span data-stu-id="205c4-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="205c4-111">大小： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="205c4-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="205c4-112">Subarrays 的長度。</span><span class="sxs-lookup"><span data-stu-id="205c4-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="205c4-113">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="205c4-113">array : 'T[]</span></span>

<span data-ttu-id="205c4-114">元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="205c4-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="205c4-115">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="205c4-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="205c4-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="205c4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="205c4-117">不要</span><span class="sxs-lookup"><span data-stu-id="205c4-117">'T</span></span>

<span data-ttu-id="205c4-118">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="205c4-118">The type of `array` elements.</span></span>