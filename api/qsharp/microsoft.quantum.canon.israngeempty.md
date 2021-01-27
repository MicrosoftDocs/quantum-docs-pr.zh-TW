---
uid: Microsoft.Quantum.Canon.IsRangeEmpty
title: IsRangeEmpty 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsRangeEmpty
qsharp.summary: Returns true if and only if input range is empty.
ms.openlocfilehash: a36d174bd0e89df0f546290fc469214fd820aa5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840343"
---
# <a name="israngeempty-function"></a><span data-ttu-id="4bab9-102">IsRangeEmpty 函式</span><span class="sxs-lookup"><span data-stu-id="4bab9-102">IsRangeEmpty function</span></span>

<span data-ttu-id="4bab9-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4bab9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4bab9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4bab9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4bab9-105">只有當輸入範圍是空的時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="4bab9-105">Returns true if and only if input range is empty.</span></span>

```qsharp
function IsRangeEmpty (rng : Range) : Bool
```


## <a name="input"></a><span data-ttu-id="4bab9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4bab9-106">Input</span></span>

### <a name="rng--range"></a><span data-ttu-id="4bab9-107">rng： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4bab9-107">rng : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="4bab9-108">任何範圍</span><span class="sxs-lookup"><span data-stu-id="4bab9-108">Any range</span></span>



## <a name="output--bool"></a><span data-ttu-id="4bab9-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4bab9-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4bab9-110">若為 True，則為 True，如果是空的則為 True `rng`</span><span class="sxs-lookup"><span data-stu-id="4bab9-110">True, if and only if `rng` is empty</span></span>