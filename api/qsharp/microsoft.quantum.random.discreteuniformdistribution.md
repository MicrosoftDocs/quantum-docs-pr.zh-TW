---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193007"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="2eb9f-102">DiscreteUniformDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="2eb9f-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="2eb9f-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2eb9f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2eb9f-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2eb9f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2eb9f-105">傳回指定內含範圍的統一散發。</span><span class="sxs-lookup"><span data-stu-id="2eb9f-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="2eb9f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2eb9f-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="2eb9f-107">最小值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2eb9f-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2eb9f-108">要繪製的最小整數。</span><span class="sxs-lookup"><span data-stu-id="2eb9f-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="2eb9f-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2eb9f-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2eb9f-110">要繪製的最大整數。</span><span class="sxs-lookup"><span data-stu-id="2eb9f-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="2eb9f-111">輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="2eb9f-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="2eb9f-112">隨機 variates 是中包含範圍內之整數的分佈， `min` 其 `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="2eb9f-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="2eb9f-113">備註</span><span class="sxs-lookup"><span data-stu-id="2eb9f-113">Remarks</span></span>

<span data-ttu-id="2eb9f-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="2eb9f-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2eb9f-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2eb9f-115">See Also</span></span>

- [<span data-ttu-id="2eb9f-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="2eb9f-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)