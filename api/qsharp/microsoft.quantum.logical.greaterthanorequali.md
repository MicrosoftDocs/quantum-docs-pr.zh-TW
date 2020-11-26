---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0435aae4a824bd19d972e9f6b331260bbe21f692
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197784"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="c53a9-102">GreaterThanOrEqualI 函式</span><span class="sxs-lookup"><span data-stu-id="c53a9-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="c53a9-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c53a9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c53a9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c53a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c53a9-105">只有當數位大於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="c53a9-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c53a9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c53a9-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c53a9-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c53a9-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c53a9-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="c53a9-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="c53a9-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c53a9-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c53a9-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="c53a9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c53a9-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c53a9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c53a9-112">`true` 如果 `a` 大於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="c53a9-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c53a9-113">備註</span><span class="sxs-lookup"><span data-stu-id="c53a9-113">Remarks</span></span>

<span data-ttu-id="c53a9-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="c53a9-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```