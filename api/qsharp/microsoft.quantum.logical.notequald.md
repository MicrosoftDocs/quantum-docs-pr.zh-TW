---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 38f30309a4c27a5ef7e112a09a0efe3b5512d4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849039"
---
# <a name="notequald-function"></a><span data-ttu-id="b5ca9-102">NotEqualD 函式</span><span class="sxs-lookup"><span data-stu-id="b5ca9-102">NotEqualD function</span></span>

<span data-ttu-id="b5ca9-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b5ca9-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b5ca9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5ca9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5ca9-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="b5ca9-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b5ca9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b5ca9-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="b5ca9-107">a： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5ca9-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5ca9-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="b5ca9-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="b5ca9-109">b： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5ca9-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5ca9-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="b5ca9-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b5ca9-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b5ca9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b5ca9-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="b5ca9-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5ca9-113">備註</span><span class="sxs-lookup"><span data-stu-id="b5ca9-113">Remarks</span></span>

<span data-ttu-id="b5ca9-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="b5ca9-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualD(a, b);
```