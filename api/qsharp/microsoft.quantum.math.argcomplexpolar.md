---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852908"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="34768-102">ArgComplexPolar 函式</span><span class="sxs-lookup"><span data-stu-id="34768-102">ArgComplexPolar function</span></span>

<span data-ttu-id="34768-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="34768-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="34768-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34768-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34768-105">傳回型別複數的階段 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="34768-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="34768-106">輸入</span><span class="sxs-lookup"><span data-stu-id="34768-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="34768-107">輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="34768-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="34768-108">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="34768-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="34768-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="34768-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="34768-110">階段 $ \text{Arg} [c] = t $。</span><span class="sxs-lookup"><span data-stu-id="34768-110">Phase $\text{Arg}[c] = t$.</span></span>