---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847615"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="7c482-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="7c482-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="7c482-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="7c482-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="7c482-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7c482-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7c482-105">以指定的內含間隔繪製隨機實數。</span><span class="sxs-lookup"><span data-stu-id="7c482-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="7c482-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7c482-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="7c482-107">最小值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c482-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c482-108">要繪製的最小實數。</span><span class="sxs-lookup"><span data-stu-id="7c482-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="7c482-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c482-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c482-110">要繪製的最大實數數目。</span><span class="sxs-lookup"><span data-stu-id="7c482-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="7c482-111">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7c482-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7c482-112">的內含間隔中的隨機實數， `min` `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="7c482-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="7c482-113">範例</span><span class="sxs-lookup"><span data-stu-id="7c482-113">Example</span></span>

<span data-ttu-id="7c482-114">下列 Q # 程式碼片段會在 $0 $ 和 $2 \pi $ 之間隨機繪製角度：</span><span class="sxs-lookup"><span data-stu-id="7c482-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="7c482-115">備註</span><span class="sxs-lookup"><span data-stu-id="7c482-115">Remarks</span></span>

<span data-ttu-id="7c482-116">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="7c482-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c482-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7c482-117">See Also</span></span>

- [<span data-ttu-id="7c482-118">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="7c482-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)