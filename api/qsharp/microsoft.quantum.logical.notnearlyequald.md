---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848479"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="e979c-102">NotNearlyEqualD 函式</span><span class="sxs-lookup"><span data-stu-id="e979c-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="e979c-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e979c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e979c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e979c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e979c-105">只有在兩個輸入不是幾乎相等 (也就是不在 1e-12) 的容錯內時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="e979c-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e979c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e979c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e979c-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e979c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e979c-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="e979c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e979c-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e979c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e979c-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="e979c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e979c-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e979c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e979c-112">`true` 如果與 `a` 不是幾乎相等，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="e979c-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e979c-113">備註</span><span class="sxs-lookup"><span data-stu-id="e979c-113">Remarks</span></span>

<span data-ttu-id="e979c-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="e979c-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```