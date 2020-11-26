---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213832"
---
# <a name="rangereverse-function"></a><span data-ttu-id="da7d8-102">RangeReverse 函式</span><span class="sxs-lookup"><span data-stu-id="da7d8-102">RangeReverse function</span></span>

<span data-ttu-id="da7d8-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="da7d8-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="da7d8-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="da7d8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="da7d8-105">傳回新的範圍，這是輸入範圍的反向。</span><span class="sxs-lookup"><span data-stu-id="da7d8-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="da7d8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="da7d8-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="da7d8-107">r： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="da7d8-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="da7d8-108">輸入範圍。</span><span class="sxs-lookup"><span data-stu-id="da7d8-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="da7d8-109">輸出： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="da7d8-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="da7d8-110">指定範圍反轉的新範圍。</span><span class="sxs-lookup"><span data-stu-id="da7d8-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="da7d8-111">備註</span><span class="sxs-lookup"><span data-stu-id="da7d8-111">Remarks</span></span>

<span data-ttu-id="da7d8-112">請注意，範圍的反向不只是 `end` ... `-step` `start` ，因為範圍的實際最後一個元素可能不 `end` 會與相同。</span><span class="sxs-lookup"><span data-stu-id="da7d8-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>