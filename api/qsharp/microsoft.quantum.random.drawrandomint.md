---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192905"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="dfd79-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="dfd79-102">DrawRandomInt operation</span></span>

<span data-ttu-id="dfd79-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="dfd79-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="dfd79-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dfd79-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dfd79-105">在指定的內含範圍內繪製隨機整數。</span><span class="sxs-lookup"><span data-stu-id="dfd79-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="dfd79-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dfd79-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="dfd79-107">最小值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfd79-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfd79-108">要繪製的最小整數。</span><span class="sxs-lookup"><span data-stu-id="dfd79-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="dfd79-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfd79-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfd79-110">要繪製的最大整數。</span><span class="sxs-lookup"><span data-stu-id="dfd79-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="dfd79-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfd79-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfd79-112">中包含範圍內的整數， `min` `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="dfd79-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfd79-113">備註</span><span class="sxs-lookup"><span data-stu-id="dfd79-113">Remarks</span></span>

<span data-ttu-id="dfd79-114">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="dfd79-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfd79-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dfd79-115">See Also</span></span>

- [<span data-ttu-id="dfd79-116">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="dfd79-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)