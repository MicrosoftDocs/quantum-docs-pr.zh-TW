---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分割函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220496"
---
# <a name="partitioned-function"></a><span data-ttu-id="891b7-102">分割函數</span><span class="sxs-lookup"><span data-stu-id="891b7-102">Partitioned function</span></span>

<span data-ttu-id="891b7-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="891b7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="891b7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="891b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="891b7-105">將陣列分割成多個部分。</span><span class="sxs-lookup"><span data-stu-id="891b7-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="891b7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="891b7-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="891b7-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="891b7-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="891b7-108">陣列中每個部分的元素數目</span><span class="sxs-lookup"><span data-stu-id="891b7-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="891b7-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="891b7-109">arr : 'T[]</span></span>

<span data-ttu-id="891b7-110">要分割的輸入陣列。</span><span class="sxs-lookup"><span data-stu-id="891b7-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="891b7-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="891b7-111">Output : 'T[][]</span></span>

<span data-ttu-id="891b7-112">多個陣列，其中第一個陣列是第一個陣列 `nElements[0]` `arr` ，而第二個數組是下一個陣列 `nElements[1]` `arr` 。最後一個陣列將包含所有剩餘的元素。</span><span class="sxs-lookup"><span data-stu-id="891b7-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="891b7-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="891b7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="891b7-114">不要</span><span class="sxs-lookup"><span data-stu-id="891b7-114">'T</span></span>

