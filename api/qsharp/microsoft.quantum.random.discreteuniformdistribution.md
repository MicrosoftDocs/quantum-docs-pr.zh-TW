---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699659"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="c5fcf-102">DiscreteUniformDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="c5fcf-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="c5fcf-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c5fcf-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c5fcf-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5fcf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5fcf-105">傳回指定內含範圍的統一散發。</span><span class="sxs-lookup"><span data-stu-id="c5fcf-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="c5fcf-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c5fcf-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="c5fcf-107">最小值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5fcf-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5fcf-108">要繪製的最小整數。</span><span class="sxs-lookup"><span data-stu-id="c5fcf-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="c5fcf-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5fcf-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5fcf-110">要繪製的最大整數。</span><span class="sxs-lookup"><span data-stu-id="c5fcf-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="c5fcf-111">輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="c5fcf-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="c5fcf-112">隨機 variates 是中包含範圍內之整數的分佈， `min` 其 `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="c5fcf-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5fcf-113">備註</span><span class="sxs-lookup"><span data-stu-id="c5fcf-113">Remarks</span></span>

<span data-ttu-id="c5fcf-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="c5fcf-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5fcf-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c5fcf-115">See Also</span></span>

- [<span data-ttu-id="c5fcf-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="c5fcf-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)