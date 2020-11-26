---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197750"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="d0ec4-102">GreaterThanOrEqualL 函式</span><span class="sxs-lookup"><span data-stu-id="d0ec4-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="d0ec4-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d0ec4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d0ec4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d0ec4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d0ec4-105">只有當數位大於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="d0ec4-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d0ec4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d0ec4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d0ec4-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d0ec4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d0ec4-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="d0ec4-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d0ec4-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d0ec4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d0ec4-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="d0ec4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d0ec4-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0ec4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d0ec4-112">`true` 如果 `a` 大於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="d0ec4-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0ec4-113">備註</span><span class="sxs-lookup"><span data-stu-id="d0ec4-113">Remarks</span></span>

<span data-ttu-id="d0ec4-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="d0ec4-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```