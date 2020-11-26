---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214002"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="456a6-102">RangeAsIntArray 函式</span><span class="sxs-lookup"><span data-stu-id="456a6-102">RangeAsIntArray function</span></span>

<span data-ttu-id="456a6-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="456a6-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="456a6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="456a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="456a6-105">建立 `arr` 由 start 列舉的整數陣列。步。。結束。</span><span class="sxs-lookup"><span data-stu-id="456a6-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="456a6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="456a6-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="456a6-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="456a6-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="456a6-108">`Range` `start..step..end` 要轉換為數組的值的。</span><span class="sxs-lookup"><span data-stu-id="456a6-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="456a6-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="456a6-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="456a6-110">新的整數陣列，對應至逐一查看的值 `range` 。</span><span class="sxs-lookup"><span data-stu-id="456a6-110">A new array of integers corresponding to values iterated over by `range`.</span></span>