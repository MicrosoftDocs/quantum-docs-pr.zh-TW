---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211384"
---
# <a name="abscomplex-function"></a><span data-ttu-id="9bd74-102">AbsComplex 函式</span><span class="sxs-lookup"><span data-stu-id="9bd74-102">AbsComplex function</span></span>

<span data-ttu-id="9bd74-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9bd74-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9bd74-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9bd74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9bd74-105">傳回型別複數的絕對值 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="9bd74-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="9bd74-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9bd74-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="9bd74-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="9bd74-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="9bd74-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="9bd74-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="9bd74-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9bd74-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9bd74-110">絕對值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="9bd74-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>