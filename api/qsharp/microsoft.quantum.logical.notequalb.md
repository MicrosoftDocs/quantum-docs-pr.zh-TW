---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697255"
---
# <a name="notequalb-function"></a><span data-ttu-id="90716-102">NotEqualB 函式</span><span class="sxs-lookup"><span data-stu-id="90716-102">NotEqualB function</span></span>

<span data-ttu-id="90716-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="90716-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="90716-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90716-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90716-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="90716-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="90716-106">輸入</span><span class="sxs-lookup"><span data-stu-id="90716-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="90716-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90716-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90716-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="90716-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="90716-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90716-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90716-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="90716-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="90716-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90716-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90716-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="90716-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="90716-113">備註</span><span class="sxs-lookup"><span data-stu-id="90716-113">Remarks</span></span>

<span data-ttu-id="90716-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="90716-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```