---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698226"
---
# <a name="rangereverse-function"></a><span data-ttu-id="37431-102">RangeReverse 函式</span><span class="sxs-lookup"><span data-stu-id="37431-102">RangeReverse function</span></span>

<span data-ttu-id="37431-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="37431-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="37431-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37431-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37431-105">傳回新的範圍，這是輸入範圍的反向。</span><span class="sxs-lookup"><span data-stu-id="37431-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="37431-106">輸入</span><span class="sxs-lookup"><span data-stu-id="37431-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="37431-107">r： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="37431-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="37431-108">輸入範圍。</span><span class="sxs-lookup"><span data-stu-id="37431-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="37431-109">輸出： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="37431-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="37431-110">指定範圍反轉的新範圍。</span><span class="sxs-lookup"><span data-stu-id="37431-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="37431-111">備註</span><span class="sxs-lookup"><span data-stu-id="37431-111">Remarks</span></span>

<span data-ttu-id="37431-112">請注意，範圍的反向不只是 `end` ... `-step` `start` ，因為範圍的實際最後一個元素可能不 `end` 會與相同。</span><span class="sxs-lookup"><span data-stu-id="37431-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>