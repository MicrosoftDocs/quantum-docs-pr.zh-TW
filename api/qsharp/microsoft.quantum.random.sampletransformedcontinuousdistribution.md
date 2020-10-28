---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700710"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="84c97-102">SampleTransformedContinuousDistribution 操作</span><span class="sxs-lookup"><span data-stu-id="84c97-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="84c97-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="84c97-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="84c97-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84c97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84c97-105">從轉換後的發行版本進行取樣的僅限內部操作。</span><span class="sxs-lookup"><span data-stu-id="84c97-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="84c97-106">只能透過部分應用程式使用。</span><span class="sxs-lookup"><span data-stu-id="84c97-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="84c97-107">輸入</span><span class="sxs-lookup"><span data-stu-id="84c97-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="84c97-108">轉換： [雙](xref:microsoft.quantum.lang-ref.double) -> [精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84c97-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="84c97-109">散發： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="84c97-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="84c97-110">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84c97-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

