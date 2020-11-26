---
uid: Microsoft.Quantum.Math.ComplexPolarAsComplex
title: ComplexPolarAsComplex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolarAsComplex
qsharp.summary: Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.
ms.openlocfilehash: ace458ec168b70a873fae2a4990b9a427efac7cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228605"
---
# <a name="complexpolarascomplex-function"></a><span data-ttu-id="cb67e-102">ComplexPolarAsComplex 函式</span><span class="sxs-lookup"><span data-stu-id="cb67e-102">ComplexPolarAsComplex function</span></span>

<span data-ttu-id="cb67e-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="cb67e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="cb67e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb67e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb67e-105">將複數類型的複數轉換 `ComplexPolar` 成類型的複數 `Complex` 。</span><span class="sxs-lookup"><span data-stu-id="cb67e-105">Converts a complex number of type `ComplexPolar` to a complex number of type `Complex`.</span></span>

```qsharp
function ComplexPolarAsComplex (input : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.Complex
```


## <a name="input"></a><span data-ttu-id="cb67e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="cb67e-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="cb67e-107">輸入： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="cb67e-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="cb67e-108">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="cb67e-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--complex"></a><span data-ttu-id="cb67e-109">輸出： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="cb67e-109">Output : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="cb67e-110">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="cb67e-110">Complex number $c = x + i y$.</span></span>