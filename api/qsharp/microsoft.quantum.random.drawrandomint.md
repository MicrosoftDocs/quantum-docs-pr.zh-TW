---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700906"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="ee542-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="ee542-102">DrawRandomInt operation</span></span>

<span data-ttu-id="ee542-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ee542-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ee542-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee542-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee542-105">在指定的內含範圍內繪製隨機整數。</span><span class="sxs-lookup"><span data-stu-id="ee542-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ee542-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ee542-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="ee542-107">最小值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee542-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee542-108">要繪製的最小整數。</span><span class="sxs-lookup"><span data-stu-id="ee542-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="ee542-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee542-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee542-110">要繪製的最大整數。</span><span class="sxs-lookup"><span data-stu-id="ee542-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="ee542-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ee542-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ee542-112">中包含範圍內的整數， `min` `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="ee542-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee542-113">備註</span><span class="sxs-lookup"><span data-stu-id="ee542-113">Remarks</span></span>

<span data-ttu-id="ee542-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="ee542-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee542-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ee542-115">See Also</span></span>

- [<span data-ttu-id="ee542-116">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ee542-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)