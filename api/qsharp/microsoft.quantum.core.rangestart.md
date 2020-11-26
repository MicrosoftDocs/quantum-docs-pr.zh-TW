---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223998"
---
# <a name="rangestart-function"></a><span data-ttu-id="22ad0-102">RangeStart 函式</span><span class="sxs-lookup"><span data-stu-id="22ad0-102">RangeStart function</span></span>

<span data-ttu-id="22ad0-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="22ad0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="22ad0-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="22ad0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="22ad0-105">傳回指定範圍的已定義開始值。</span><span class="sxs-lookup"><span data-stu-id="22ad0-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="22ad0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="22ad0-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="22ad0-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="22ad0-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="22ad0-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22ad0-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22ad0-109">指定範圍的已定義開始值。</span><span class="sxs-lookup"><span data-stu-id="22ad0-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="22ad0-110">備註</span><span class="sxs-lookup"><span data-stu-id="22ad0-110">Remarks</span></span>

<span data-ttu-id="22ad0-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="22ad0-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="22ad0-112">請注意，範圍的定義開始值與序列的第一個元素相同，除非範圍指定空的序列 (例如，2。</span><span class="sxs-lookup"><span data-stu-id="22ad0-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="22ad0-113">1)。</span><span class="sxs-lookup"><span data-stu-id="22ad0-113">1).</span></span>