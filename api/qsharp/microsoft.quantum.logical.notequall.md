---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697247"
---
# <a name="notequall-function"></a><span data-ttu-id="cd965-102">NotEqualL 函式</span><span class="sxs-lookup"><span data-stu-id="cd965-102">NotEqualL function</span></span>

<span data-ttu-id="cd965-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cd965-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cd965-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd965-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd965-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="cd965-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="cd965-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cd965-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="cd965-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cd965-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cd965-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="cd965-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="cd965-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cd965-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cd965-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="cd965-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cd965-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd965-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd965-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="cd965-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd965-113">備註</span><span class="sxs-lookup"><span data-stu-id="cd965-113">Remarks</span></span>

<span data-ttu-id="cd965-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="cd965-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```