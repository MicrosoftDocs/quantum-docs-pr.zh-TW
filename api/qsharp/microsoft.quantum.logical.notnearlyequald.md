---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699735"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="0e456-102">NotNearlyEqualD 函式</span><span class="sxs-lookup"><span data-stu-id="0e456-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="0e456-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0e456-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0e456-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e456-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e456-105">只有在兩個輸入不是幾乎相等 (也就是不在 1e-12) 的容錯內時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="0e456-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0e456-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0e456-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="0e456-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0e456-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0e456-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="0e456-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="0e456-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0e456-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0e456-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="0e456-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0e456-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0e456-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0e456-112">`true` 如果與 `a` 不是幾乎相等，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0e456-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e456-113">備註</span><span class="sxs-lookup"><span data-stu-id="0e456-113">Remarks</span></span>

<span data-ttu-id="0e456-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="0e456-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```