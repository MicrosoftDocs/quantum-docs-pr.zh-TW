---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700379"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="7a558-102">CategoricalDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="7a558-102">CategoricalDistribution function</span></span>

<span data-ttu-id="7a558-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="7a558-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="7a558-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a558-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a558-105">傳回離散類別分佈，其中會明確指定指定結果的每個有限清單的機率。</span><span class="sxs-lookup"><span data-stu-id="7a558-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="7a558-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7a558-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="7a558-107">probs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7a558-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7a558-108">類別散發的每個結果的機率。</span><span class="sxs-lookup"><span data-stu-id="7a558-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="7a558-109">這些機率可能不會正規化，但全部都不能為負數。</span><span class="sxs-lookup"><span data-stu-id="7a558-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="7a558-110">輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="7a558-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="7a558-111">具有機率的索引 `i` `probs[i] / sum` ，其中 `sum` 是指定的總和 `probs` `Fold(PlusD, 0.0, probs)` 。</span><span class="sxs-lookup"><span data-stu-id="7a558-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>