---
uid: Microsoft.Quantum.Logical.Or
title: Or 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 98a416229386461b241d087b7ae95f078f8be70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699606"
---
# <a name="or-function"></a><span data-ttu-id="baa8e-102">Or 函式</span><span class="sxs-lookup"><span data-stu-id="baa8e-102">Or function</span></span>

<span data-ttu-id="baa8e-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="baa8e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="baa8e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="baa8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="baa8e-105">傳回兩個值的布林分離。</span><span class="sxs-lookup"><span data-stu-id="baa8e-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="baa8e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="baa8e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="baa8e-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="baa8e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="baa8e-108">要考慮的第一個值。</span><span class="sxs-lookup"><span data-stu-id="baa8e-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="baa8e-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="baa8e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="baa8e-110">要考慮的第二個值。</span><span class="sxs-lookup"><span data-stu-id="baa8e-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="baa8e-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="baa8e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="baa8e-112">`true` 如果或為，則 `a` 為，否則 `b` 為 `true` 。</span><span class="sxs-lookup"><span data-stu-id="baa8e-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="baa8e-113">備註</span><span class="sxs-lookup"><span data-stu-id="baa8e-113">Remarks</span></span>

<span data-ttu-id="baa8e-114">與運算子不同的 `or` 是，此函式不會進行較短的運算，因此會完全評估這兩個輸入。</span><span class="sxs-lookup"><span data-stu-id="baa8e-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="baa8e-115">最高的最小運算行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="baa8e-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a or b;
let x = Or(a, b);
```