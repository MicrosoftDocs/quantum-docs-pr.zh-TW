---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 1de3fdb0fa53fef9cbf4b9ee9b6a1c54865bd093
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849122"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="660d7-102">LessThanOrEqualL 函式</span><span class="sxs-lookup"><span data-stu-id="660d7-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="660d7-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="660d7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="660d7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="660d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="660d7-105">只有當數位小於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="660d7-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="660d7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="660d7-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="660d7-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="660d7-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="660d7-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="660d7-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="660d7-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="660d7-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="660d7-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="660d7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="660d7-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="660d7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="660d7-112">`true` 如果 `a` 小於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="660d7-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="660d7-113">備註</span><span class="sxs-lookup"><span data-stu-id="660d7-113">Remarks</span></span>

<span data-ttu-id="660d7-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="660d7-114">The following are equivalent:</span></span>

```qsharp
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```