---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814412"
---
# <a name="notequalb-function"></a><span data-ttu-id="fc81e-102">NotEqualB 函式</span><span class="sxs-lookup"><span data-stu-id="fc81e-102">NotEqualB function</span></span>

<span data-ttu-id="fc81e-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fc81e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fc81e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc81e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc81e-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="fc81e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fc81e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fc81e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fc81e-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc81e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc81e-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="fc81e-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fc81e-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc81e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc81e-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="fc81e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fc81e-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fc81e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fc81e-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="fc81e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc81e-113">備註</span><span class="sxs-lookup"><span data-stu-id="fc81e-113">Remarks</span></span>

<span data-ttu-id="fc81e-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="fc81e-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```