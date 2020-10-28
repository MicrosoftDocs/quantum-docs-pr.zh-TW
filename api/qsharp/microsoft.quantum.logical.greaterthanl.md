---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697698"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="00bae-102">GreaterThanL 函式</span><span class="sxs-lookup"><span data-stu-id="00bae-102">GreaterThanL function</span></span>

<span data-ttu-id="00bae-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="00bae-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="00bae-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00bae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00bae-105">只有當數位大於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="00bae-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="00bae-106">輸入</span><span class="sxs-lookup"><span data-stu-id="00bae-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="00bae-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="00bae-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="00bae-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="00bae-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="00bae-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="00bae-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="00bae-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="00bae-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="00bae-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00bae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00bae-112">`true` 只有在 `a` 完全大於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="00bae-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="00bae-113">備註</span><span class="sxs-lookup"><span data-stu-id="00bae-113">Remarks</span></span>

<span data-ttu-id="00bae-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="00bae-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```