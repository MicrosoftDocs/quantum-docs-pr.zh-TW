---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: d37bf1c10899d06e798d29c68f88b06f2d5918a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195557"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="44f31-102">ContinuedFractionConvergentI 函式</span><span class="sxs-lookup"><span data-stu-id="44f31-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="44f31-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="44f31-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="44f31-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44f31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44f31-105">找出最接近 `fraction` 分母小於或等於分母的接續分數 convergent `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="44f31-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="44f31-106">輸入</span><span class="sxs-lookup"><span data-stu-id="44f31-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="44f31-107">分數： [分數](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="44f31-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="44f31-108">denominatorBound： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44f31-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="44f31-109">輸出： [分數](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="44f31-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="44f31-110">最接近 `fraction` 小於分母或等於分母的最小分數 `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="44f31-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>