---
uid: Microsoft.Quantum.Math.AbsSquaredComplex
title: AbsSquaredComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsSquaredComplex
qsharp.summary: Returns the squared absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d48212d7f861b3ff9e37d078742f53f0cd8c71ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195897"
---
# <a name="abssquaredcomplex-function"></a><span data-ttu-id="b940d-102">AbsSquaredComplex 函式</span><span class="sxs-lookup"><span data-stu-id="b940d-102">AbsSquaredComplex function</span></span>

<span data-ttu-id="b940d-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b940d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b940d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b940d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b940d-105">傳回復數類型的平方絕對值 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="b940d-105">Returns the squared absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsSquaredComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="b940d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b940d-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="b940d-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b940d-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b940d-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="b940d-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="b940d-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b940d-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b940d-110">平方絕對值 $ | c | ^ 2 = x ^ 2 + y ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="b940d-110">Squared absolute value $|c|^2 = x^2 + y^2$.</span></span>