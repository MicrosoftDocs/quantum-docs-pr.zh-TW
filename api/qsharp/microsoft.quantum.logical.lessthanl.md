---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: d5753f9e1447fc1bd433703037fe44c86aaa659c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849157"
---
# <a name="lessthanl-function"></a><span data-ttu-id="9cb82-102">LessThanL 函式</span><span class="sxs-lookup"><span data-stu-id="9cb82-102">LessThanL function</span></span>

<span data-ttu-id="9cb82-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9cb82-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9cb82-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9cb82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9cb82-105">只有當數位小於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="9cb82-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="9cb82-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9cb82-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9cb82-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9cb82-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9cb82-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="9cb82-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="9cb82-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9cb82-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9cb82-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="9cb82-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9cb82-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9cb82-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9cb82-112">`true` 只有在 `a` 嚴格小於時才會 `b` 。</span><span class="sxs-lookup"><span data-stu-id="9cb82-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9cb82-113">備註</span><span class="sxs-lookup"><span data-stu-id="9cb82-113">Remarks</span></span>

<span data-ttu-id="9cb82-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="9cb82-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanL(a, b);
```