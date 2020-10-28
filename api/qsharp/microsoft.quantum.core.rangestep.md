---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698206"
---
# <a name="rangestep-function"></a><span data-ttu-id="a8324-102">RangeStep 函式</span><span class="sxs-lookup"><span data-stu-id="a8324-102">RangeStep function</span></span>

<span data-ttu-id="a8324-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a8324-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a8324-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8324-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8324-105">傳回整數，這個整數會指定如何計算範圍的下一個值。</span><span class="sxs-lookup"><span data-stu-id="a8324-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="a8324-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a8324-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="a8324-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a8324-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="a8324-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a8324-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a8324-109">指定範圍的已定義步驟值。</span><span class="sxs-lookup"><span data-stu-id="a8324-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8324-110">備註</span><span class="sxs-lookup"><span data-stu-id="a8324-110">Remarks</span></span>

<span data-ttu-id="a8324-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="a8324-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>