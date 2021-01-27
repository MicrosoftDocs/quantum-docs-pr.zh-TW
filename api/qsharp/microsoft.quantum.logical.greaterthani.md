---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 86fc8e927c292a2ea814ed80a33de42bffdb96b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815946"
---
# <a name="greaterthani-function"></a><span data-ttu-id="7a655-102">GreaterThanI 函式</span><span class="sxs-lookup"><span data-stu-id="7a655-102">GreaterThanI function</span></span>

<span data-ttu-id="7a655-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7a655-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7a655-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a655-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a655-105">只有當數位大於另一個數位時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="7a655-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="7a655-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7a655-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="7a655-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a655-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a655-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="7a655-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="7a655-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a655-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a655-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="7a655-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7a655-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7a655-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7a655-112">`true` 只有在 `a` 完全大於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="7a655-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7a655-113">備註</span><span class="sxs-lookup"><span data-stu-id="7a655-113">Remarks</span></span>

<span data-ttu-id="7a655-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="7a655-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanI(a, b);
```