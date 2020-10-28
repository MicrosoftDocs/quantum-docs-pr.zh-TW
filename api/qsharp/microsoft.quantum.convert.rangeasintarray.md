---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698263"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="e07c3-102">RangeAsIntArray 函式</span><span class="sxs-lookup"><span data-stu-id="e07c3-102">RangeAsIntArray function</span></span>

<span data-ttu-id="e07c3-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e07c3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e07c3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e07c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e07c3-105">建立 `arr` 由 start 列舉的整數陣列。步。。結束。</span><span class="sxs-lookup"><span data-stu-id="e07c3-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="e07c3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e07c3-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e07c3-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e07c3-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e07c3-108">`Range` `start..step..end` 要轉換為數組的值的。</span><span class="sxs-lookup"><span data-stu-id="e07c3-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="e07c3-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e07c3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e07c3-110">新的整數陣列，對應至逐一查看的值 `range` 。</span><span class="sxs-lookup"><span data-stu-id="e07c3-110">A new array of integers corresponding to values iterated over by `range`.</span></span>