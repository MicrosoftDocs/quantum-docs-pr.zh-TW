---
uid: Microsoft.Quantum.Math.ComplexAsComplexPolar
title: ComplexAsComplexPolar 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexAsComplexPolar
qsharp.summary: Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5155583291e69a78df66f3b77d758fc1708d9146
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195625"
---
# <a name="complexascomplexpolar-function"></a><span data-ttu-id="3fa2e-102">ComplexAsComplexPolar 函式</span><span class="sxs-lookup"><span data-stu-id="3fa2e-102">ComplexAsComplexPolar function</span></span>

<span data-ttu-id="3fa2e-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3fa2e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3fa2e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fa2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fa2e-105">將複數類型的複數轉換 `Complex` 成類型的複數 `ComplexPolar` 。</span><span class="sxs-lookup"><span data-stu-id="3fa2e-105">Converts a complex number of type `Complex` to a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ComplexAsComplexPolar (input : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="3fa2e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3fa2e-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="3fa2e-107">輸入： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="3fa2e-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="3fa2e-108">複數 $c = x + i y $。</span><span class="sxs-lookup"><span data-stu-id="3fa2e-108">Complex number $c = x + i y$.</span></span>



## <a name="output--complexpolar"></a><span data-ttu-id="3fa2e-109">輸出： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="3fa2e-109">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="3fa2e-110">複數 $c = r e ^ {i t} $。</span><span class="sxs-lookup"><span data-stu-id="3fa2e-110">Complex number $c = r e^{i t}$.</span></span>