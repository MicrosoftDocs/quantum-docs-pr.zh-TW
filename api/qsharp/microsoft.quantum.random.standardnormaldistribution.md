---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857804"
---
# <a name="standardnormaldistribution-function"></a><span data-ttu-id="3df55-102">StandardNormalDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="3df55-102">StandardNormalDistribution function</span></span>

<span data-ttu-id="3df55-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3df55-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3df55-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3df55-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3df55-105">傳回具有 mean 0 和變異數1的一般分佈。</span><span class="sxs-lookup"><span data-stu-id="3df55-105">Returns a normal distribution with mean 0 and variance 1.</span></span>

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a><span data-ttu-id="3df55-106">輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="3df55-106">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="3df55-107">範例</span><span class="sxs-lookup"><span data-stu-id="3df55-107">Example</span></span>

<span data-ttu-id="3df55-108">下列範例會從標準一般分佈中繪製10個樣本：</span><span class="sxs-lookup"><span data-stu-id="3df55-108">The following draws 10 samples from the standard normal distribution:</span></span>

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a><span data-ttu-id="3df55-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3df55-109">See Also</span></span>

- [<span data-ttu-id="3df55-110">NormalDistribution。</span><span class="sxs-lookup"><span data-stu-id="3df55-110">Microsoft.Quantum.Random.NormalDistribution</span></span>](xref:Microsoft.Quantum.Random.NormalDistribution)