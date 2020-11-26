---
uid: Microsoft.Quantum.Logical.EqualL
title: EqualL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198107"
---
# <a name="equall-function"></a><span data-ttu-id="5db84-102">EqualL 函式</span><span class="sxs-lookup"><span data-stu-id="5db84-102">EqualL function</span></span>

<span data-ttu-id="5db84-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5db84-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5db84-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5db84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5db84-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="5db84-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5db84-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5db84-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5db84-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5db84-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5db84-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="5db84-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5db84-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5db84-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5db84-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="5db84-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5db84-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5db84-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5db84-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="5db84-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5db84-113">備註</span><span class="sxs-lookup"><span data-stu-id="5db84-113">Remarks</span></span>

<span data-ttu-id="5db84-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="5db84-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```