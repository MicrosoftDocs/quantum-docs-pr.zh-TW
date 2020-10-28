---
uid: Microsoft.Quantum.Logical.And
title: And 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699759"
---
# <a name="and-function"></a><span data-ttu-id="f9be5-102">And 函式</span><span class="sxs-lookup"><span data-stu-id="f9be5-102">And function</span></span>

<span data-ttu-id="f9be5-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f9be5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f9be5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9be5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9be5-105">傳回兩個值的布林值結合。</span><span class="sxs-lookup"><span data-stu-id="f9be5-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="f9be5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f9be5-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="f9be5-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f9be5-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f9be5-108">要考慮的第一個值。</span><span class="sxs-lookup"><span data-stu-id="f9be5-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="f9be5-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f9be5-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f9be5-110">要考慮的第二個值。</span><span class="sxs-lookup"><span data-stu-id="f9be5-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f9be5-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f9be5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f9be5-112">`true` 如果和 `a` `b` 都是，則為 `true` 。</span><span class="sxs-lookup"><span data-stu-id="f9be5-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9be5-113">備註</span><span class="sxs-lookup"><span data-stu-id="f9be5-113">Remarks</span></span>

<span data-ttu-id="f9be5-114">與運算子不同的 `and` 是，此函式不會進行較短的運算，因此會完全評估這兩個輸入。</span><span class="sxs-lookup"><span data-stu-id="f9be5-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="f9be5-115">最高的最小運算行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9be5-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```