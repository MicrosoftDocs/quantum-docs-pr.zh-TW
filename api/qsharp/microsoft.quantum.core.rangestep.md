---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213798"
---
# <a name="rangestep-function"></a><span data-ttu-id="ac660-102">RangeStep 函式</span><span class="sxs-lookup"><span data-stu-id="ac660-102">RangeStep function</span></span>

<span data-ttu-id="ac660-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="ac660-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="ac660-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ac660-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ac660-105">傳回整數，這個整數會指定如何計算範圍的下一個值。</span><span class="sxs-lookup"><span data-stu-id="ac660-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="ac660-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ac660-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="ac660-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ac660-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="ac660-108">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac660-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac660-109">指定範圍的已定義步驟值。</span><span class="sxs-lookup"><span data-stu-id="ac660-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac660-110">備註</span><span class="sxs-lookup"><span data-stu-id="ac660-110">Remarks</span></span>

<span data-ttu-id="ac660-111">範圍運算式的第一個專案是 `start` ，其第二個元素是，第三個元素是， `start+step` `start+step+step` 直到 `end` 傳遞為止。</span><span class="sxs-lookup"><span data-stu-id="ac660-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>