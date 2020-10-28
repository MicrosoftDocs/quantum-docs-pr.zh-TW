---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: b4f2b9a192770f453302b469c80f03a9e57cf891
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700494"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="5680b-102">ArgComplexPolar 函式</span><span class="sxs-lookup"><span data-stu-id="5680b-102">ArgComplexPolar function</span></span>

<span data-ttu-id="5680b-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5680b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5680b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5680b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5680b-105">傳回型別複數的階段 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="5680b-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="5680b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5680b-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="5680b-107">輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="5680b-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="5680b-108">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="5680b-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="5680b-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5680b-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5680b-110">階段 $ \text{Arg} [c] = t $。</span><span class="sxs-lookup"><span data-stu-id="5680b-110">Phase $\text{Arg}[c] = t$.</span></span>