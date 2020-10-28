---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697571"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="62df6-102">TransformedContinuousDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="62df6-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="62df6-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="62df6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="62df6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62df6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62df6-105">指定連續散發時，會傳回由指定函式轉換原始的新散發。</span><span class="sxs-lookup"><span data-stu-id="62df6-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="62df6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="62df6-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="62df6-107">轉換： [雙](xref:microsoft.quantum.lang-ref.double) -> [精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="62df6-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="62df6-108">將原始分佈的 variates 轉換成已轉換之分佈的函式。</span><span class="sxs-lookup"><span data-stu-id="62df6-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="62df6-109">散發： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="62df6-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="62df6-110">要轉換的原始散發。</span><span class="sxs-lookup"><span data-stu-id="62df6-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="62df6-111">輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="62df6-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="62df6-112">由指定的轉換相關的新散發 `distribution` `transform` 。</span><span class="sxs-lookup"><span data-stu-id="62df6-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>