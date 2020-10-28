---
uid: Microsoft.Quantum.Core.RangeEnd
title: 到 rangeend 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698230"
---
# <a name="rangeend-function"></a><span data-ttu-id="65b84-102">到 rangeend 函式</span><span class="sxs-lookup"><span data-stu-id="65b84-102">RangeEnd function</span></span>

<span data-ttu-id="65b84-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="65b84-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="65b84-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65b84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65b84-105">傳回指定範圍的定義結束值，這不一定是序列中的最後一個元素。</span><span class="sxs-lookup"><span data-stu-id="65b84-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="65b84-106">輸入</span><span class="sxs-lookup"><span data-stu-id="65b84-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="65b84-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="65b84-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="65b84-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="65b84-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="65b84-109">指定範圍的定義結束值。</span><span class="sxs-lookup"><span data-stu-id="65b84-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="65b84-110">備註</span><span class="sxs-lookup"><span data-stu-id="65b84-110">Remarks</span></span>

<span data-ttu-id="65b84-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="65b84-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="65b84-112">請注意，定義的範圍結束值可能會與範圍所指定之序列中的最後一個元素不同;例如，在範圍0中。</span><span class="sxs-lookup"><span data-stu-id="65b84-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="65b84-113">2。</span><span class="sxs-lookup"><span data-stu-id="65b84-113">2 ..</span></span> <span data-ttu-id="65b84-114">5最後一個元素是4，但結束值為5。</span><span class="sxs-lookup"><span data-stu-id="65b84-114">5 the last element is 4 but the end value is 5.</span></span>