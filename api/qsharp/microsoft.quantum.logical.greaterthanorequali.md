---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: c1a513500c8a70bd7628976974387cba48162e80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849189"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="437e2-102">GreaterThanOrEqualI 函式</span><span class="sxs-lookup"><span data-stu-id="437e2-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="437e2-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="437e2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="437e2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="437e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="437e2-105">只有當數位大於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="437e2-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="437e2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="437e2-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="437e2-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="437e2-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="437e2-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="437e2-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="437e2-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="437e2-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="437e2-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="437e2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="437e2-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="437e2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="437e2-112">`true` 如果 `a` 大於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="437e2-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="437e2-113">備註</span><span class="sxs-lookup"><span data-stu-id="437e2-113">Remarks</span></span>

<span data-ttu-id="437e2-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="437e2-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```