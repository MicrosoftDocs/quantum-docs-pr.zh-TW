---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 3f4ccb0888e7df7c43ff73be8a3140e3fa84d4dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197631"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="ff61e-102">LessThanOrEqualD 函式</span><span class="sxs-lookup"><span data-stu-id="ff61e-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="ff61e-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ff61e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ff61e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff61e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff61e-105">只有當數位小於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="ff61e-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ff61e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ff61e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ff61e-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff61e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff61e-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="ff61e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ff61e-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff61e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff61e-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="ff61e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ff61e-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ff61e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ff61e-112">`true` 如果 `a` 小於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="ff61e-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff61e-113">備註</span><span class="sxs-lookup"><span data-stu-id="ff61e-113">Remarks</span></span>

<span data-ttu-id="ff61e-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="ff61e-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```