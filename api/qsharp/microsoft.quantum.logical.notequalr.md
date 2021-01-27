---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 39601396a75d8c1b9193d4b8f34fa05466beff06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848507"
---
# <a name="notequalr-function"></a><span data-ttu-id="68cd2-102">NotEqualR 函式</span><span class="sxs-lookup"><span data-stu-id="68cd2-102">NotEqualR function</span></span>

<span data-ttu-id="68cd2-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="68cd2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="68cd2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68cd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68cd2-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="68cd2-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="68cd2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="68cd2-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="68cd2-107">答：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="68cd2-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="68cd2-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="68cd2-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="68cd2-109">b：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="68cd2-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="68cd2-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="68cd2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="68cd2-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="68cd2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="68cd2-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="68cd2-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="68cd2-113">備註</span><span class="sxs-lookup"><span data-stu-id="68cd2-113">Remarks</span></span>

<span data-ttu-id="68cd2-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="68cd2-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualR(a, b);
```