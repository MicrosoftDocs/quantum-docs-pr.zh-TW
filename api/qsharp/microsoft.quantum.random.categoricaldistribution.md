---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842354"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="ab13e-102">CategoricalDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="ab13e-102">CategoricalDistribution function</span></span>

<span data-ttu-id="ab13e-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ab13e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ab13e-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ab13e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ab13e-105">傳回離散類別分佈，其中會明確指定指定結果的每個有限清單的機率。</span><span class="sxs-lookup"><span data-stu-id="ab13e-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="ab13e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ab13e-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="ab13e-107">probs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ab13e-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ab13e-108">類別散發的每個結果的機率。</span><span class="sxs-lookup"><span data-stu-id="ab13e-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="ab13e-109">這些機率可能不會正規化，但全部都不能為負數。</span><span class="sxs-lookup"><span data-stu-id="ab13e-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="ab13e-110">輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="ab13e-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="ab13e-111">具有機率的索引 `i` `probs[i] / sum` ，其中 `sum` 是指定的總和 `probs` `Fold(PlusD, 0.0, probs)` 。</span><span class="sxs-lookup"><span data-stu-id="ab13e-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="ab13e-112">範例</span><span class="sxs-lookup"><span data-stu-id="ab13e-112">Example</span></span>

<span data-ttu-id="ab13e-113">下列 Q # 程式碼會顯示0，機率為30%，而1的機率為70%：</span><span class="sxs-lookup"><span data-stu-id="ab13e-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```