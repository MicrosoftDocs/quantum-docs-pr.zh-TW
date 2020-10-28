---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 8b0c34915ef392e8a84706f601da71f3848a3134
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699750"
---
# <a name="equalc-function"></a><span data-ttu-id="28bc5-102">EqualC 函式</span><span class="sxs-lookup"><span data-stu-id="28bc5-102">EqualC function</span></span>

<span data-ttu-id="28bc5-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="28bc5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="28bc5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28bc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28bc5-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="28bc5-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="28bc5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="28bc5-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="28bc5-107">a： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="28bc5-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="28bc5-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="28bc5-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="28bc5-109">b： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="28bc5-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="28bc5-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="28bc5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="28bc5-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="28bc5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="28bc5-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="28bc5-112">`true` if and only if `a` is equal to `b`.</span></span>