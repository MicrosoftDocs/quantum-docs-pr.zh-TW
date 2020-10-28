---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700330"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="09a54-102">GreaterThanOrEqualL 函式</span><span class="sxs-lookup"><span data-stu-id="09a54-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="09a54-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="09a54-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="09a54-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09a54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09a54-105">只有當數位大於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="09a54-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="09a54-106">輸入</span><span class="sxs-lookup"><span data-stu-id="09a54-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="09a54-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="09a54-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="09a54-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="09a54-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="09a54-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="09a54-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="09a54-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="09a54-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="09a54-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="09a54-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="09a54-112">`true` 如果 `a` 大於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="09a54-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="09a54-113">備註</span><span class="sxs-lookup"><span data-stu-id="09a54-113">Remarks</span></span>

<span data-ttu-id="09a54-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="09a54-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```