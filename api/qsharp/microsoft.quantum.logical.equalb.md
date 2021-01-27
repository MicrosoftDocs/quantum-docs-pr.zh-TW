---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817261"
---
# <a name="equalb-function"></a><span data-ttu-id="0685f-102">EqualB 函式</span><span class="sxs-lookup"><span data-stu-id="0685f-102">EqualB function</span></span>

<span data-ttu-id="0685f-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0685f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0685f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0685f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0685f-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="0685f-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="0685f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0685f-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="0685f-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0685f-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0685f-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="0685f-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="0685f-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0685f-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0685f-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="0685f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0685f-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0685f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0685f-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0685f-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0685f-113">備註</span><span class="sxs-lookup"><span data-stu-id="0685f-113">Remarks</span></span>

<span data-ttu-id="0685f-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="0685f-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```