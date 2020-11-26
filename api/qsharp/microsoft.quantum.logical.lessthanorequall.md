---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: LessThanOrEqualL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 2322ae4dd6025108d322d29770f42953213aa025
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197596"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="5a565-102">LessThanOrEqualL 函式</span><span class="sxs-lookup"><span data-stu-id="5a565-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="5a565-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5a565-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5a565-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a565-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a565-105">只有當數位小於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="5a565-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5a565-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5a565-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5a565-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5a565-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5a565-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="5a565-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5a565-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5a565-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5a565-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="5a565-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5a565-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5a565-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5a565-112">`true` 如果 `a` 小於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="5a565-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a565-113">備註</span><span class="sxs-lookup"><span data-stu-id="5a565-113">Remarks</span></span>

<span data-ttu-id="5a565-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="5a565-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```