---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700507"
---
# <a name="argcomplex-function"></a><span data-ttu-id="17e0e-102">ArgComplex 函式</span><span class="sxs-lookup"><span data-stu-id="17e0e-102">ArgComplex function</span></span>

<span data-ttu-id="17e0e-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="17e0e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="17e0e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17e0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17e0e-105">傳回型別複數的階段 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="17e0e-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="17e0e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="17e0e-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="17e0e-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="17e0e-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="17e0e-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="17e0e-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="17e0e-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17e0e-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17e0e-110">階段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="17e0e-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>