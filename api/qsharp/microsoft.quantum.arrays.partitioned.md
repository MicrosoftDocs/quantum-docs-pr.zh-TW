---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分割函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699439"
---
# <a name="partitioned-function"></a><span data-ttu-id="5547d-102">分割函數</span><span class="sxs-lookup"><span data-stu-id="5547d-102">Partitioned function</span></span>

<span data-ttu-id="5547d-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5547d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5547d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5547d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5547d-105">將陣列分割成多個部分。</span><span class="sxs-lookup"><span data-stu-id="5547d-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="5547d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5547d-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="5547d-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5547d-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5547d-108">陣列中每個部分的元素數目</span><span class="sxs-lookup"><span data-stu-id="5547d-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="5547d-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="5547d-109">arr : 'T[]</span></span>

<span data-ttu-id="5547d-110">要分割的輸入陣列。</span><span class="sxs-lookup"><span data-stu-id="5547d-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="5547d-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="5547d-111">Output : 'T[][]</span></span>

<span data-ttu-id="5547d-112">多個陣列，其中第一個陣列是第一個陣列 `nElements[0]` `arr` ，而第二個數組是下一個陣列 `nElements[1]` `arr` 。最後一個陣列將包含所有剩餘的元素。</span><span class="sxs-lookup"><span data-stu-id="5547d-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5547d-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="5547d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5547d-114">不要</span><span class="sxs-lookup"><span data-stu-id="5547d-114">'T</span></span>

