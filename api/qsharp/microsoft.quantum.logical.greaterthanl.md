---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 5e1b2adab36b7937c83ea912b8a9cb148b626ee5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197971"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="30945-102">GreaterThanL 函式</span><span class="sxs-lookup"><span data-stu-id="30945-102">GreaterThanL function</span></span>

<span data-ttu-id="30945-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="30945-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="30945-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30945-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30945-105">只有當數位大於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="30945-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="30945-106">輸入</span><span class="sxs-lookup"><span data-stu-id="30945-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="30945-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="30945-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="30945-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="30945-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="30945-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="30945-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="30945-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="30945-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="30945-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30945-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30945-112">`true` 只有在 `a` 完全大於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="30945-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="30945-113">備註</span><span class="sxs-lookup"><span data-stu-id="30945-113">Remarks</span></span>

<span data-ttu-id="30945-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="30945-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```