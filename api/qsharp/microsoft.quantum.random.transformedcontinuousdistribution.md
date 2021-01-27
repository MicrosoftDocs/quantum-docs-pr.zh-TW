---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857762"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="868ca-102">TransformedContinuousDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="868ca-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="868ca-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="868ca-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="868ca-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="868ca-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="868ca-105">指定連續散發時，會傳回由指定函式轉換原始的新散發。</span><span class="sxs-lookup"><span data-stu-id="868ca-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="868ca-106">輸入</span><span class="sxs-lookup"><span data-stu-id="868ca-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="868ca-107">轉換： [雙](xref:microsoft.quantum.lang-ref.double) -> [精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="868ca-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="868ca-108">將原始分佈的 variates 轉換成已轉換之分佈的函式。</span><span class="sxs-lookup"><span data-stu-id="868ca-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="868ca-109">散發： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="868ca-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="868ca-110">要轉換的原始散發。</span><span class="sxs-lookup"><span data-stu-id="868ca-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="868ca-111">輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="868ca-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="868ca-112">由指定的轉換相關的新散發 `distribution` `transform` 。</span><span class="sxs-lookup"><span data-stu-id="868ca-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="868ca-113">範例</span><span class="sxs-lookup"><span data-stu-id="868ca-113">Example</span></span>

<span data-ttu-id="868ca-114">下列兩個散發相同：</span><span class="sxs-lookup"><span data-stu-id="868ca-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```