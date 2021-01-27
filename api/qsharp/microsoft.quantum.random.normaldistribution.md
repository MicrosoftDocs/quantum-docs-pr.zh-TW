---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814174"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="60e3b-102">NormalDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="60e3b-102">NormalDistribution function</span></span>

<span data-ttu-id="60e3b-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="60e3b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="60e3b-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="60e3b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="60e3b-105">傳回具有給定平均值和變異數的一般分佈。</span><span class="sxs-lookup"><span data-stu-id="60e3b-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="60e3b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="60e3b-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="60e3b-107">平均： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60e3b-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="60e3b-108">變異數： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="60e3b-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="60e3b-109">輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="60e3b-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="60e3b-110">範例</span><span class="sxs-lookup"><span data-stu-id="60e3b-110">Example</span></span>

<span data-ttu-id="60e3b-111">下列範例會從一般分佈以平均2和標準差0.1 繪製10個樣本：</span><span class="sxs-lookup"><span data-stu-id="60e3b-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="60e3b-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="60e3b-112">See Also</span></span>

- [<span data-ttu-id="60e3b-113">StandardNormalDistribution。</span><span class="sxs-lookup"><span data-stu-id="60e3b-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)