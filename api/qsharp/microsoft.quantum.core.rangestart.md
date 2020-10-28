---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698207"
---
# <a name="rangestart-function"></a><span data-ttu-id="e124d-102">RangeStart 函式</span><span class="sxs-lookup"><span data-stu-id="e124d-102">RangeStart function</span></span>

<span data-ttu-id="e124d-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e124d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e124d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e124d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e124d-105">傳回指定範圍的已定義開始值。</span><span class="sxs-lookup"><span data-stu-id="e124d-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="e124d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e124d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e124d-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e124d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="e124d-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e124d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e124d-109">指定範圍的已定義開始值。</span><span class="sxs-lookup"><span data-stu-id="e124d-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="e124d-110">備註</span><span class="sxs-lookup"><span data-stu-id="e124d-110">Remarks</span></span>

<span data-ttu-id="e124d-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="e124d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="e124d-112">請注意，範圍的定義開始值與序列的第一個元素相同，除非範圍指定空的序列 (例如，2。</span><span class="sxs-lookup"><span data-stu-id="e124d-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="e124d-113">1)。</span><span class="sxs-lookup"><span data-stu-id="e124d-113">1).</span></span>