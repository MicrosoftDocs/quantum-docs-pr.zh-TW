---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 83b5e97085234e8249869f858400cba265d13058
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221448"
---
# <a name="elementsat-function"></a><span data-ttu-id="073b3-102">ElementsAt 函式</span><span class="sxs-lookup"><span data-stu-id="073b3-102">ElementsAt function</span></span>

<span data-ttu-id="073b3-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="073b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="073b3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="073b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="073b3-105">傳回指定之索引範圍的陣列元素。</span><span class="sxs-lookup"><span data-stu-id="073b3-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="073b3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="073b3-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="073b3-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="073b3-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="073b3-108">陣列索引的範圍</span><span class="sxs-lookup"><span data-stu-id="073b3-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="073b3-109">陣列： t []</span><span class="sxs-lookup"><span data-stu-id="073b3-109">array : 'T[]</span></span>

<span data-ttu-id="073b3-110">Array</span><span class="sxs-lookup"><span data-stu-id="073b3-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="073b3-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="073b3-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="073b3-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="073b3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="073b3-113">不要</span><span class="sxs-lookup"><span data-stu-id="073b3-113">'T</span></span>

<span data-ttu-id="073b3-114">之每個專案的型別 `array` 。</span><span class="sxs-lookup"><span data-stu-id="073b3-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="073b3-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="073b3-115">See Also</span></span>

- [<span data-ttu-id="073b3-116">Parameters.alternatefilters.elementat。</span><span class="sxs-lookup"><span data-stu-id="073b3-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="073b3-117">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="073b3-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)