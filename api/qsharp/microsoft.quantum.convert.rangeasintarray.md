---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850109"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="01f41-102">RangeAsIntArray 函式</span><span class="sxs-lookup"><span data-stu-id="01f41-102">RangeAsIntArray function</span></span>

<span data-ttu-id="01f41-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="01f41-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="01f41-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01f41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01f41-105">建立 `arr` 由 start 列舉的整數陣列。步。。結束。</span><span class="sxs-lookup"><span data-stu-id="01f41-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="01f41-106">輸入</span><span class="sxs-lookup"><span data-stu-id="01f41-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="01f41-107">範圍： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="01f41-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="01f41-108">`Range` `start..step..end` 要轉換為數組的值的。</span><span class="sxs-lookup"><span data-stu-id="01f41-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="01f41-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="01f41-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="01f41-110">新的整數陣列，對應至逐一查看的值 `range` 。</span><span class="sxs-lookup"><span data-stu-id="01f41-110">A new array of integers corresponding to values iterated over by `range`.</span></span>

## <a name="example"></a><span data-ttu-id="01f41-111">範例</span><span class="sxs-lookup"><span data-stu-id="01f41-111">Example</span></span>

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```