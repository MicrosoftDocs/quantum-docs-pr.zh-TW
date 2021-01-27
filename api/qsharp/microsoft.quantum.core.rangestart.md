---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831106"
---
# <a name="rangestart-function"></a><span data-ttu-id="be46d-102">RangeStart 函式</span><span class="sxs-lookup"><span data-stu-id="be46d-102">RangeStart function</span></span>

<span data-ttu-id="be46d-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="be46d-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="be46d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="be46d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="be46d-105">傳回指定範圍的已定義開始值。</span><span class="sxs-lookup"><span data-stu-id="be46d-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="be46d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="be46d-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="be46d-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="be46d-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="be46d-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be46d-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be46d-109">指定範圍的已定義開始值。</span><span class="sxs-lookup"><span data-stu-id="be46d-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="be46d-110">備註</span><span class="sxs-lookup"><span data-stu-id="be46d-110">Remarks</span></span>

<span data-ttu-id="be46d-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="be46d-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="be46d-112">請注意，範圍的定義開始值與序列的第一個元素相同，除非範圍指定空的序列 (例如，2。</span><span class="sxs-lookup"><span data-stu-id="be46d-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="be46d-113">1)。</span><span class="sxs-lookup"><span data-stu-id="be46d-113">1).</span></span>