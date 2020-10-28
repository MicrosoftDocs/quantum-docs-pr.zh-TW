---
uid: Microsoft.Quantum.Logical.LessThanL
title: LessThanL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanL
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: fde57bcd9960056461bddac54300c298def8f7d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697290"
---
# <a name="lessthanl-function"></a><span data-ttu-id="cb05f-102">LessThanL 函式</span><span class="sxs-lookup"><span data-stu-id="cb05f-102">LessThanL function</span></span>

<span data-ttu-id="cb05f-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cb05f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cb05f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb05f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb05f-105">只有當數位小於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="cb05f-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cb05f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cb05f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cb05f-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cb05f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cb05f-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="cb05f-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cb05f-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cb05f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cb05f-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="cb05f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cb05f-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cb05f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cb05f-112">`true` 只有在 `a` 嚴格小於時才會 `b` 。</span><span class="sxs-lookup"><span data-stu-id="cb05f-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb05f-113">備註</span><span class="sxs-lookup"><span data-stu-id="cb05f-113">Remarks</span></span>

<span data-ttu-id="cb05f-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="cb05f-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanL(a, b);
```