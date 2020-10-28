---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700714"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="d20ae-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="d20ae-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="d20ae-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="d20ae-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="d20ae-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d20ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d20ae-105">以指定的內含間隔繪製隨機實數。</span><span class="sxs-lookup"><span data-stu-id="d20ae-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="d20ae-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d20ae-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="d20ae-107">最小值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d20ae-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d20ae-108">要繪製的最小實數。</span><span class="sxs-lookup"><span data-stu-id="d20ae-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="d20ae-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d20ae-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d20ae-110">要繪製的最大實數數目。</span><span class="sxs-lookup"><span data-stu-id="d20ae-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="d20ae-111">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d20ae-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d20ae-112">的內含間隔中的隨機實數， `min` `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="d20ae-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="d20ae-113">備註</span><span class="sxs-lookup"><span data-stu-id="d20ae-113">Remarks</span></span>

<span data-ttu-id="d20ae-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="d20ae-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d20ae-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d20ae-115">See Also</span></span>

- [<span data-ttu-id="d20ae-116">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="d20ae-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)