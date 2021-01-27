---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815989"
---
# <a name="equalr-function"></a><span data-ttu-id="a636d-102">EqualR 函式</span><span class="sxs-lookup"><span data-stu-id="a636d-102">EqualR function</span></span>

<span data-ttu-id="a636d-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a636d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a636d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a636d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a636d-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="a636d-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="a636d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a636d-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="a636d-107">答：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a636d-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="a636d-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="a636d-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="a636d-109">b：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a636d-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="a636d-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="a636d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a636d-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a636d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a636d-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="a636d-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a636d-113">備註</span><span class="sxs-lookup"><span data-stu-id="a636d-113">Remarks</span></span>

<span data-ttu-id="a636d-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="a636d-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```