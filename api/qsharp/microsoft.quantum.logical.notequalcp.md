---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 85225109a3822a9b63a231631f3d7265143418b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814405"
---
# <a name="notequalcp-function"></a><span data-ttu-id="2209d-102">NotEqualCP 函式</span><span class="sxs-lookup"><span data-stu-id="2209d-102">NotEqualCP function</span></span>

<span data-ttu-id="2209d-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2209d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2209d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2209d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2209d-105">只有在兩個輸入不相等時，才會傳回 true。</span><span class="sxs-lookup"><span data-stu-id="2209d-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="2209d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2209d-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="2209d-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2209d-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2209d-108">要比較的第一個值。</span><span class="sxs-lookup"><span data-stu-id="2209d-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="2209d-109">b： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2209d-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2209d-110">要比較的第二個值。</span><span class="sxs-lookup"><span data-stu-id="2209d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2209d-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2209d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2209d-112">`true` 如果和 `a` 不等於，則為 `b` 。</span><span class="sxs-lookup"><span data-stu-id="2209d-112">`true` if and only if `a` is not equal to `b`.</span></span>