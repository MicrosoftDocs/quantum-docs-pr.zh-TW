---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192939"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="6b345-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="6b345-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="6b345-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6b345-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6b345-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6b345-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6b345-105">以指定的內含間隔繪製隨機實數。</span><span class="sxs-lookup"><span data-stu-id="6b345-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="6b345-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6b345-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="6b345-107">最小值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6b345-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6b345-108">要繪製的最小實數。</span><span class="sxs-lookup"><span data-stu-id="6b345-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="6b345-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6b345-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6b345-110">要繪製的最大實數數目。</span><span class="sxs-lookup"><span data-stu-id="6b345-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="6b345-111">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6b345-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6b345-112">的內含間隔中的隨機實數， `min` `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="6b345-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b345-113">備註</span><span class="sxs-lookup"><span data-stu-id="6b345-113">Remarks</span></span>

<span data-ttu-id="6b345-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="6b345-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b345-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6b345-115">See Also</span></span>

- [<span data-ttu-id="6b345-116">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="6b345-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)