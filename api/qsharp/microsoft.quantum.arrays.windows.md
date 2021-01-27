---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842201"
---
# <a name="windows-function"></a><span data-ttu-id="7944e-102">Windows 函數</span><span class="sxs-lookup"><span data-stu-id="7944e-102">Windows function</span></span>

<span data-ttu-id="7944e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7944e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7944e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7944e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7944e-105">傳回長度的所有連續 subarrays `size` 。</span><span class="sxs-lookup"><span data-stu-id="7944e-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="7944e-106">描述</span><span class="sxs-lookup"><span data-stu-id="7944e-106">Description</span></span>

<span data-ttu-id="7944e-107">此函數會依 `n - size + 1` 序傳回所有長度的 subarrays `size` ，其中 `n` 是的長度 `arr` 。</span><span class="sxs-lookup"><span data-stu-id="7944e-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="7944e-108">第一個 subarrays 會 `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 一直到最後一個子陣列為止 `arr[n - size..n - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="7944e-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="7944e-109">如果為 `size <= 0` 或 `size > n` ，則會傳回空陣列。</span><span class="sxs-lookup"><span data-stu-id="7944e-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="7944e-110">輸入</span><span class="sxs-lookup"><span data-stu-id="7944e-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="7944e-111">大小： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7944e-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7944e-112">Subarrays 的長度。</span><span class="sxs-lookup"><span data-stu-id="7944e-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="7944e-113">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="7944e-113">array : 'T[]</span></span>

<span data-ttu-id="7944e-114">元素的陣列。</span><span class="sxs-lookup"><span data-stu-id="7944e-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="7944e-115">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="7944e-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7944e-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="7944e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7944e-117">不要</span><span class="sxs-lookup"><span data-stu-id="7944e-117">'T</span></span>

<span data-ttu-id="7944e-118">元素的類型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7944e-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="7944e-119">範例</span><span class="sxs-lookup"><span data-stu-id="7944e-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```