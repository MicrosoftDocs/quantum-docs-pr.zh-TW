---
uid: Microsoft.Quantum.Math.AbsComplexPolar
title: AbsComplexPolar 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplexPolar
qsharp.summary: Returns the absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: c2b60cbdf69723dfc1470535dbc5beb060e68b86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856406"
---
# <a name="abscomplexpolar-function"></a><span data-ttu-id="12edf-102">AbsComplexPolar 函式</span><span class="sxs-lookup"><span data-stu-id="12edf-102">AbsComplexPolar function</span></span>

<span data-ttu-id="12edf-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="12edf-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="12edf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12edf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12edf-105">傳回型別複數的絕對值 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="12edf-105">Returns the absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="12edf-106">輸入</span><span class="sxs-lookup"><span data-stu-id="12edf-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="12edf-107">輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="12edf-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="12edf-108">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="12edf-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="12edf-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="12edf-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="12edf-110">絕對值 $ | c |= r $。</span><span class="sxs-lookup"><span data-stu-id="12edf-110">Absolute value $|c| = r$.</span></span>