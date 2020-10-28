---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 292599c18d2aac44cef8f0eecca38eb1fbe22061
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700574"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="1641e-102">GreaterThanOrEqualI 函式</span><span class="sxs-lookup"><span data-stu-id="1641e-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="1641e-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1641e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1641e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1641e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1641e-105">只有當數位大於或等於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="1641e-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="1641e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1641e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="1641e-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1641e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1641e-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="1641e-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="1641e-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1641e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1641e-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="1641e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1641e-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1641e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1641e-112">`true` 如果 `a` 大於或等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="1641e-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1641e-113">備註</span><span class="sxs-lookup"><span data-stu-id="1641e-113">Remarks</span></span>

<span data-ttu-id="1641e-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="1641e-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```