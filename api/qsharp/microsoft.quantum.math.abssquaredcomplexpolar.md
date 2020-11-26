---
uid: Microsoft.Quantum.Math.AbsSquaredComplexPolar
title: AbsSquaredComplexPolar 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsSquaredComplexPolar
qsharp.summary: Returns the squared absolute value of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 51ec302d5120b2af58c00fc20c5c8cf739f189b1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211282"
---
# <a name="abssquaredcomplexpolar-function"></a><span data-ttu-id="10ce1-102">AbsSquaredComplexPolar 函式</span><span class="sxs-lookup"><span data-stu-id="10ce1-102">AbsSquaredComplexPolar function</span></span>

<span data-ttu-id="10ce1-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="10ce1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="10ce1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10ce1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10ce1-105">傳回復數類型的平方絕對值 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="10ce1-105">Returns the squared absolute value of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function AbsSquaredComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="10ce1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="10ce1-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="10ce1-107">輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="10ce1-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="10ce1-108">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="10ce1-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="10ce1-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10ce1-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="10ce1-110">平方絕對值 $ | c | ^ 2 = r ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="10ce1-110">Squared absolute value $|c|^2 = r^2$.</span></span>