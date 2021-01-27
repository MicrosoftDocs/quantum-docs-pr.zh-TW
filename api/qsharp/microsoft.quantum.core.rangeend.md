---
uid: Microsoft.Quantum.Core.RangeEnd
title: 到 rangeend 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831373"
---
# <a name="rangeend-function"></a><span data-ttu-id="db236-102">到 rangeend 函式</span><span class="sxs-lookup"><span data-stu-id="db236-102">RangeEnd function</span></span>

<span data-ttu-id="db236-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="db236-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="db236-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="db236-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="db236-105">傳回指定範圍的定義結束值，這不一定是序列中的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="db236-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="db236-106">輸入</span><span class="sxs-lookup"><span data-stu-id="db236-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="db236-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="db236-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="db236-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="db236-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="db236-109">指定範圍的定義結束值。</span><span class="sxs-lookup"><span data-stu-id="db236-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="db236-110">備註</span><span class="sxs-lookup"><span data-stu-id="db236-110">Remarks</span></span>

<span data-ttu-id="db236-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="db236-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="db236-112">請注意，定義的範圍結束值可能會與範圍所指定之序列中的最後一個元素不同;例如，在範圍0中。</span><span class="sxs-lookup"><span data-stu-id="db236-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="db236-113">2。</span><span class="sxs-lookup"><span data-stu-id="db236-113">2 ..</span></span> <span data-ttu-id="db236-114">5最後一個元素是4，但結束值為5。</span><span class="sxs-lookup"><span data-stu-id="db236-114">5 the last element is 4 but the end value is 5.</span></span>