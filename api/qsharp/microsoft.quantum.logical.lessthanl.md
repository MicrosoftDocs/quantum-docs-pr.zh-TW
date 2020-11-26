---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 9a0678569596ac188c87c3944f3759783fcc77ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197716"
---
# <a name="lessthanl-function"></a><span data-ttu-id="d00a4-102">LessThanL 函式</span><span class="sxs-lookup"><span data-stu-id="d00a4-102">LessThanL function</span></span>

<span data-ttu-id="d00a4-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d00a4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d00a4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d00a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d00a4-105">只有當數位小於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="d00a4-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d00a4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d00a4-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d00a4-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d00a4-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d00a4-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="d00a4-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d00a4-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d00a4-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d00a4-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="d00a4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d00a4-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d00a4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d00a4-112">`true` 只有在 `a` 嚴格小於時才會 `b` 。</span><span class="sxs-lookup"><span data-stu-id="d00a4-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d00a4-113">備註</span><span class="sxs-lookup"><span data-stu-id="d00a4-113">Remarks</span></span>

<span data-ttu-id="d00a4-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="d00a4-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```