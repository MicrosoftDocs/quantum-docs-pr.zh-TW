---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d47e04616d4bcf49273bec31fc22990a8244962b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700686"
---
# <a name="abscomplex-function"></a><span data-ttu-id="9e3a3-102">AbsComplex 函式</span><span class="sxs-lookup"><span data-stu-id="9e3a3-102">AbsComplex function</span></span>

<span data-ttu-id="9e3a3-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9e3a3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9e3a3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e3a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e3a3-105">傳回型別複數的絕對值 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="9e3a3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9e3a3-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="9e3a3-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="9e3a3-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="9e3a3-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="9e3a3-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9e3a3-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9e3a3-110">絕對值 $ | c |= \sqrt{x ^ 2 + y ^ 2} $。</span><span class="sxs-lookup"><span data-stu-id="9e3a3-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>