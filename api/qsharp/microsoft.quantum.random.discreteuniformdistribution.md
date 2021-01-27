---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853730"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="f5b9e-102">DiscreteUniformDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="f5b9e-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="f5b9e-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f5b9e-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f5b9e-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f5b9e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f5b9e-105">傳回指定內含範圍的統一散發。</span><span class="sxs-lookup"><span data-stu-id="f5b9e-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="f5b9e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f5b9e-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="f5b9e-107">最小值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5b9e-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5b9e-108">要繪製的最小整數。</span><span class="sxs-lookup"><span data-stu-id="f5b9e-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="f5b9e-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5b9e-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5b9e-110">要繪製的最大整數。</span><span class="sxs-lookup"><span data-stu-id="f5b9e-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="f5b9e-111">輸出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="f5b9e-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="f5b9e-112">隨機 variates 是中包含範圍內之整數的分佈， `min` 其 `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="f5b9e-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="f5b9e-113">範例</span><span class="sxs-lookup"><span data-stu-id="f5b9e-113">Example</span></span>

<span data-ttu-id="f5b9e-114">下列 Q # 程式碼片段會隨機擲出六側的骰子：</span><span class="sxs-lookup"><span data-stu-id="f5b9e-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="f5b9e-115">備註</span><span class="sxs-lookup"><span data-stu-id="f5b9e-115">Remarks</span></span>

<span data-ttu-id="f5b9e-116">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="f5b9e-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5b9e-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5b9e-117">See Also</span></span>

- [<span data-ttu-id="f5b9e-118">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="f5b9e-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)