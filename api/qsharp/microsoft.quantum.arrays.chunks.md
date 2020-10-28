---
uid: Microsoft.Quantum.Arrays.Chunks
title: 區塊函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699521"
---
# <a name="chunks-function"></a><span data-ttu-id="d8f39-102">區塊函數</span><span class="sxs-lookup"><span data-stu-id="d8f39-102">Chunks function</span></span>

<span data-ttu-id="d8f39-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d8f39-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d8f39-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8f39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8f39-105">將陣列分割為相等長度的多個部分。</span><span class="sxs-lookup"><span data-stu-id="d8f39-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="d8f39-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d8f39-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="d8f39-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8f39-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8f39-108">每個區塊的長度。</span><span class="sxs-lookup"><span data-stu-id="d8f39-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="d8f39-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="d8f39-109">arr : 'T[]</span></span>

<span data-ttu-id="d8f39-110">要分割的陣列。</span><span class="sxs-lookup"><span data-stu-id="d8f39-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="d8f39-111">Output： t [] []</span><span class="sxs-lookup"><span data-stu-id="d8f39-111">Output : 'T[][]</span></span>

<span data-ttu-id="d8f39-112">陣列，其中包含原始陣列的每個區塊。</span><span class="sxs-lookup"><span data-stu-id="d8f39-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d8f39-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="d8f39-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8f39-114">不要</span><span class="sxs-lookup"><span data-stu-id="d8f39-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d8f39-115">備註</span><span class="sxs-lookup"><span data-stu-id="d8f39-115">Remarks</span></span>

<span data-ttu-id="d8f39-116">請注意，輸出的最後一個元素可能會比無法整除的還短 `nElements` `Length(arr)` `nElements` 。</span><span class="sxs-lookup"><span data-stu-id="d8f39-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>