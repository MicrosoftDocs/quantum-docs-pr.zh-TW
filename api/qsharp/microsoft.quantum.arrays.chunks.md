---
uid: Microsoft.Quantum.Arrays.Chunks
title: 區塊函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842882"
---
# <a name="chunks-function"></a><span data-ttu-id="13410-102">區塊函數</span><span class="sxs-lookup"><span data-stu-id="13410-102">Chunks function</span></span>

<span data-ttu-id="13410-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="13410-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="13410-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13410-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13410-105">將陣列分割為相等長度的多個部分。</span><span class="sxs-lookup"><span data-stu-id="13410-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="13410-106">輸入</span><span class="sxs-lookup"><span data-stu-id="13410-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="13410-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13410-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13410-108">每個區塊的長度。</span><span class="sxs-lookup"><span data-stu-id="13410-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="13410-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="13410-109">arr : 'T[]</span></span>

<span data-ttu-id="13410-110">要分割的陣列。</span><span class="sxs-lookup"><span data-stu-id="13410-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="13410-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="13410-111">Output : 'T[][]</span></span>

<span data-ttu-id="13410-112">陣列，其中包含原始陣列的每個區塊。</span><span class="sxs-lookup"><span data-stu-id="13410-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="13410-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="13410-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13410-114">不要</span><span class="sxs-lookup"><span data-stu-id="13410-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="13410-115">備註</span><span class="sxs-lookup"><span data-stu-id="13410-115">Remarks</span></span>

<span data-ttu-id="13410-116">請注意，輸出的最後一個元素可能會比無法整除的還短 `nElements` `Length(arr)` `nElements` 。</span><span class="sxs-lookup"><span data-stu-id="13410-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>