---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: e3175b9b6fd2890963de0452102e2f0de1026b91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198226"
---
# <a name="equalcp-function"></a><span data-ttu-id="1fbd4-102">EqualCP 函式</span><span class="sxs-lookup"><span data-stu-id="1fbd4-102">EqualCP function</span></span>

<span data-ttu-id="1fbd4-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1fbd4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1fbd4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1fbd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1fbd4-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="1fbd4-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="1fbd4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1fbd4-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="1fbd4-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1fbd4-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1fbd4-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="1fbd4-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="1fbd4-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1fbd4-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1fbd4-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="1fbd4-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1fbd4-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1fbd4-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1fbd4-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="1fbd4-112">`true` if and only if `a` is equal to `b`.</span></span>