---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853650"
---
# <a name="rangereverse-function"></a><span data-ttu-id="1301f-102">RangeReverse 函式</span><span class="sxs-lookup"><span data-stu-id="1301f-102">RangeReverse function</span></span>

<span data-ttu-id="1301f-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="1301f-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="1301f-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1301f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1301f-105">傳回新的範圍，這是輸入範圍的反向。</span><span class="sxs-lookup"><span data-stu-id="1301f-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="1301f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1301f-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="1301f-107">r： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="1301f-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="1301f-108">輸入範圍。</span><span class="sxs-lookup"><span data-stu-id="1301f-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="1301f-109">輸出： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="1301f-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="1301f-110">指定範圍反轉的新範圍。</span><span class="sxs-lookup"><span data-stu-id="1301f-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="1301f-111">備註</span><span class="sxs-lookup"><span data-stu-id="1301f-111">Remarks</span></span>

<span data-ttu-id="1301f-112">請注意，範圍的反向不只是 `end` ... `-step` `start` ，因為範圍的實際最後一個元素可能不 `end` 會與相同。</span><span class="sxs-lookup"><span data-stu-id="1301f-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>