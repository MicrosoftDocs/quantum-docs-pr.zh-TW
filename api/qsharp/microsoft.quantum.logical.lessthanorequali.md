---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197561"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="0825c-102">LessThanOrEqualI 函式</span><span class="sxs-lookup"><span data-stu-id="0825c-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="0825c-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0825c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0825c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0825c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0825c-105">只有當數位小於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="0825c-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="0825c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0825c-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0825c-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0825c-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0825c-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="0825c-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="0825c-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0825c-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0825c-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="0825c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0825c-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0825c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0825c-112">`true` 如果 `a` 小於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0825c-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0825c-113">備註</span><span class="sxs-lookup"><span data-stu-id="0825c-113">Remarks</span></span>

<span data-ttu-id="0825c-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="0825c-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```