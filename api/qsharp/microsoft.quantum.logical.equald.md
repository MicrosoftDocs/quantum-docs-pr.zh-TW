---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198141"
---
# <a name="equald-function"></a><span data-ttu-id="91b91-102">EqualD 函式</span><span class="sxs-lookup"><span data-stu-id="91b91-102">EqualD function</span></span>

<span data-ttu-id="91b91-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="91b91-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="91b91-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91b91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91b91-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="91b91-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="91b91-106">輸入</span><span class="sxs-lookup"><span data-stu-id="91b91-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="91b91-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="91b91-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="91b91-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="91b91-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="91b91-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="91b91-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="91b91-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="91b91-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="91b91-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="91b91-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="91b91-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="91b91-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="91b91-113">備註</span><span class="sxs-lookup"><span data-stu-id="91b91-113">Remarks</span></span>

<span data-ttu-id="91b91-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="91b91-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```