---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197461"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="c06aa-102">NearlyEqualD 函式</span><span class="sxs-lookup"><span data-stu-id="c06aa-102">NearlyEqualD function</span></span>

<span data-ttu-id="c06aa-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c06aa-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c06aa-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c06aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c06aa-105">只有在兩個輸入幾乎相等 (（也就是在 1e-12) 的容錯內）時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="c06aa-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c06aa-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c06aa-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c06aa-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06aa-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06aa-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="c06aa-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c06aa-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c06aa-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c06aa-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="c06aa-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c06aa-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c06aa-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c06aa-112">`true` 如果與 `a` 幾乎相等，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="c06aa-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c06aa-113">備註</span><span class="sxs-lookup"><span data-stu-id="c06aa-113">Remarks</span></span>

<span data-ttu-id="c06aa-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="c06aa-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```