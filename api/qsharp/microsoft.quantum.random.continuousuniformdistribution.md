---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842324"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="b2ffc-102">ContinuousUniformDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="b2ffc-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="b2ffc-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b2ffc-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b2ffc-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b2ffc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b2ffc-105">傳回指定的內含間隔的統一散發。</span><span class="sxs-lookup"><span data-stu-id="b2ffc-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="b2ffc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b2ffc-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="b2ffc-107">最小值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2ffc-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2ffc-108">要繪製的最小實數。</span><span class="sxs-lookup"><span data-stu-id="b2ffc-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="b2ffc-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2ffc-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2ffc-110">要繪製的最大實數數目。</span><span class="sxs-lookup"><span data-stu-id="b2ffc-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="b2ffc-111">輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b2ffc-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b2ffc-112">隨機 variates 的分佈，其隨機是的內含間隔中的實數（ `min` `max` 具有統一機率）。</span><span class="sxs-lookup"><span data-stu-id="b2ffc-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="b2ffc-113">範例</span><span class="sxs-lookup"><span data-stu-id="b2ffc-113">Example</span></span>

<span data-ttu-id="b2ffc-114">下列 Q # 程式碼片段會在 $0 $ 和 $2 \pi $ 之間隨機繪製角度：</span><span class="sxs-lookup"><span data-stu-id="b2ffc-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="b2ffc-115">備註</span><span class="sxs-lookup"><span data-stu-id="b2ffc-115">Remarks</span></span>

<span data-ttu-id="b2ffc-116">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="b2ffc-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2ffc-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b2ffc-117">See Also</span></span>

- [<span data-ttu-id="b2ffc-118">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="b2ffc-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)