---
uid: Microsoft.Quantum.Logical.EqualD
title: EqualD 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816875"
---
# <a name="equald-function"></a><span data-ttu-id="e9297-102">EqualD 函式</span><span class="sxs-lookup"><span data-stu-id="e9297-102">EqualD function</span></span>

<span data-ttu-id="e9297-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e9297-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e9297-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9297-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9297-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="e9297-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e9297-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e9297-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="e9297-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9297-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9297-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="e9297-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="e9297-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9297-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9297-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="e9297-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e9297-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9297-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9297-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="e9297-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9297-113">備註</span><span class="sxs-lookup"><span data-stu-id="e9297-113">Remarks</span></span>

<span data-ttu-id="e9297-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="e9297-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```