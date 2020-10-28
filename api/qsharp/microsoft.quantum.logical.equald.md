---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697702"
---
# <a name="equald-function"></a><span data-ttu-id="ef1c6-102">EqualD 函式</span><span class="sxs-lookup"><span data-stu-id="ef1c6-102">EqualD function</span></span>

<span data-ttu-id="ef1c6-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ef1c6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ef1c6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef1c6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef1c6-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ef1c6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ef1c6-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ef1c6-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ef1c6-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ef1c6-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ef1c6-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ef1c6-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ef1c6-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ef1c6-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ef1c6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ef1c6-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="ef1c6-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef1c6-113">備註</span><span class="sxs-lookup"><span data-stu-id="ef1c6-113">Remarks</span></span>

<span data-ttu-id="ef1c6-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="ef1c6-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```