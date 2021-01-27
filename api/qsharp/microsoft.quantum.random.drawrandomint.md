---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851131"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="ccd69-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="ccd69-102">DrawRandomInt operation</span></span>

<span data-ttu-id="ccd69-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ccd69-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ccd69-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ccd69-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ccd69-105">在指定的內含範圍內繪製隨機整數。</span><span class="sxs-lookup"><span data-stu-id="ccd69-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ccd69-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ccd69-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="ccd69-107">最小值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ccd69-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ccd69-108">要繪製的最小整數。</span><span class="sxs-lookup"><span data-stu-id="ccd69-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="ccd69-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ccd69-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ccd69-110">要繪製的最大整數。</span><span class="sxs-lookup"><span data-stu-id="ccd69-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="ccd69-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ccd69-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ccd69-112">中包含範圍內的整數， `min` `max` 具有統一機率。</span><span class="sxs-lookup"><span data-stu-id="ccd69-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="ccd69-113">範例</span><span class="sxs-lookup"><span data-stu-id="ccd69-113">Example</span></span>

<span data-ttu-id="ccd69-114">下列 Q # 程式碼片段會隨機擲出六側的骰子：</span><span class="sxs-lookup"><span data-stu-id="ccd69-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="ccd69-115">備註</span><span class="sxs-lookup"><span data-stu-id="ccd69-115">Remarks</span></span>

<span data-ttu-id="ccd69-116">如果為 `max <= min` ，則失敗。</span><span class="sxs-lookup"><span data-stu-id="ccd69-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccd69-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ccd69-117">See Also</span></span>

- [<span data-ttu-id="ccd69-118">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ccd69-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)