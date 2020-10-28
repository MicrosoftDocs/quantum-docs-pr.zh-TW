---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 2322e005a5afb73d9719eb65d9ebf50740f1c9fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700483"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="9c27c-102">ContinuedFractionConvergentI 函式</span><span class="sxs-lookup"><span data-stu-id="9c27c-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="9c27c-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9c27c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9c27c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c27c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c27c-105">找出最接近 `fraction` 分母小於或等於分母的接續分數 convergent `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="9c27c-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="9c27c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9c27c-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="9c27c-107">分數： [分數](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="9c27c-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="9c27c-108">denominatorBound： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c27c-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="9c27c-109">輸出： [分數](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="9c27c-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="9c27c-110">最接近 `fraction` 小於分母或等於分母的最小分數 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="9c27c-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>