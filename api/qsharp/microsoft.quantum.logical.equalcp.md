---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699746"
---
# <a name="equalcp-function"></a><span data-ttu-id="f257d-102">EqualCP 函式</span><span class="sxs-lookup"><span data-stu-id="f257d-102">EqualCP function</span></span>

<span data-ttu-id="f257d-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f257d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f257d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f257d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f257d-105">只有當兩個輸入相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="f257d-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="f257d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f257d-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="f257d-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f257d-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f257d-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="f257d-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="f257d-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f257d-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="f257d-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="f257d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f257d-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f257d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f257d-112">`true` 只有當 `a` 等於時，才為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="f257d-112">`true` if and only if `a` is equal to `b`.</span></span>