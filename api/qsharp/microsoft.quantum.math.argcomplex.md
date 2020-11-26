---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211095"
---
# <a name="argcomplex-function"></a><span data-ttu-id="afa30-102">ArgComplex 函式</span><span class="sxs-lookup"><span data-stu-id="afa30-102">ArgComplex function</span></span>

<span data-ttu-id="afa30-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="afa30-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="afa30-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afa30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afa30-105">傳回型別複數的階段 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="afa30-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="afa30-106">輸入</span><span class="sxs-lookup"><span data-stu-id="afa30-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="afa30-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="afa30-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="afa30-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="afa30-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="afa30-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="afa30-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="afa30-110">階段 $ \text{Arg} [c] = \text{ArcTan} (y，x) \in (-\pi，\pi] $。</span><span class="sxs-lookup"><span data-stu-id="afa30-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>