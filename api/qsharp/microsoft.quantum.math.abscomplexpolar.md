---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: bc74d691e69a4f1be096582e42ec3a88ddcdd3c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700683"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="dacd7-102">AbsComplexPolar 函式</span><span class="sxs-lookup"><span data-stu-id="dacd7-102">AbsComplexPolar function</span></span>

<span data-ttu-id="dacd7-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dacd7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dacd7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dacd7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dacd7-105">傳回型別複數的絕對值 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="dacd7-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="dacd7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dacd7-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="dacd7-107">輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="dacd7-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="dacd7-108">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="dacd7-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="dacd7-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dacd7-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dacd7-110">絕對值 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="dacd7-110">Absolute value $|c| = r$.</span></span>