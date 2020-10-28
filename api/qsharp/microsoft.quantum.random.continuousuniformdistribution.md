---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697139"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="83af8-102">ContinuousUniformDistribution 函式</span><span class="sxs-lookup"><span data-stu-id="83af8-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="83af8-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="83af8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="83af8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83af8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83af8-105">傳回指定的內含間隔的統一散發。</span><span class="sxs-lookup"><span data-stu-id="83af8-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="83af8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="83af8-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="83af8-107">最小值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83af8-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83af8-108">要繪製的最小實數。</span><span class="sxs-lookup"><span data-stu-id="83af8-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="83af8-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83af8-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83af8-110">要繪製的最大實數數目。</span><span class="sxs-lookup"><span data-stu-id="83af8-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="83af8-111">輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="83af8-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="83af8-112">隨機 variates 的分佈，其隨機是的內含間隔中的實數（ `min` `max` 具有統一機率）。</span><span class="sxs-lookup"><span data-stu-id="83af8-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="83af8-113">備註</span><span class="sxs-lookup"><span data-stu-id="83af8-113">Remarks</span></span>

<span data-ttu-id="83af8-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="83af8-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="83af8-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="83af8-115">See Also</span></span>

- [<span data-ttu-id="83af8-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="83af8-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)