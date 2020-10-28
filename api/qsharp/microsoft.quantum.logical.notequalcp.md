---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699739"
---
# <a name="notequalcp-function"></a><span data-ttu-id="0a5e0-102">NotEqualCP 函式</span><span class="sxs-lookup"><span data-stu-id="0a5e0-102">NotEqualCP function</span></span>

<span data-ttu-id="0a5e0-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0a5e0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0a5e0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a5e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a5e0-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="0a5e0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0a5e0-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="0a5e0-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="0a5e0-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="0a5e0-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="0a5e0-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="0a5e0-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="0a5e0-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0a5e0-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0a5e0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0a5e0-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-112">`true` if and only if `a` is not equal to `b`.</span></span>