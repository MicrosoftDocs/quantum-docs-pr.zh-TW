---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 2bb4caa140bef36d893da834eac1c94b8dd8b0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846076"
---
# <a name="abscomplex-function"></a><span data-ttu-id="668c4-102">AbsComplex 函式</span><span class="sxs-lookup"><span data-stu-id="668c4-102">AbsComplex function</span></span>

<span data-ttu-id="668c4-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="668c4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="668c4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="668c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="668c4-105">傳回型別複數的絕對值 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="668c4-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="668c4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="668c4-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="668c4-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="668c4-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="668c4-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="668c4-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="668c4-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="668c4-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="668c4-110">絕對值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="668c4-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>