---
uid: Microsoft.Quantum.Logical.EqualL
title: EqualL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697314"
---
# <a name="equall-function"></a><span data-ttu-id="0f5dc-102">EqualL 函式</span><span class="sxs-lookup"><span data-stu-id="0f5dc-102">EqualL function</span></span>

<span data-ttu-id="0f5dc-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0f5dc-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0f5dc-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f5dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f5dc-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="0f5dc-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="0f5dc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0f5dc-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0f5dc-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0f5dc-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0f5dc-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="0f5dc-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="0f5dc-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0f5dc-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0f5dc-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="0f5dc-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0f5dc-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0f5dc-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0f5dc-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0f5dc-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f5dc-113">備註</span><span class="sxs-lookup"><span data-stu-id="0f5dc-113">Remarks</span></span>

<span data-ttu-id="0f5dc-114">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="0f5dc-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```