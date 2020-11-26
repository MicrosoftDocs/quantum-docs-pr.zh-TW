---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192990"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="4f7b8-102">DrawCategorical 操作</span><span class="sxs-lookup"><span data-stu-id="4f7b8-102">DrawCategorical operation</span></span>

<span data-ttu-id="4f7b8-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4f7b8-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4f7b8-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4f7b8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4f7b8-105">從 probablities 清單所指定的類別散發中，繪製隨機樣本。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="4f7b8-106">描述</span><span class="sxs-lookup"><span data-stu-id="4f7b8-106">Description</span></span>

<span data-ttu-id="4f7b8-107">選取特定索引的機率與該索引的陣列元素值成正比。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="4f7b8-108">會忽略等於零的陣列元素，而且永遠不會傳回其索引。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="4f7b8-109">如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="4f7b8-110">輸入</span><span class="sxs-lookup"><span data-stu-id="4f7b8-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="4f7b8-111">probs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4f7b8-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4f7b8-112">浮點數的陣列，與選取每個索引的機率成正比。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="4f7b8-113">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f7b8-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f7b8-114">整數 $i $ 具有機率 $ \Pr (i) = p_i/\ sum_i p_i $，其中 $p _i $ 是的 $i $ 第一個元素 `probs` 。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f7b8-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4f7b8-115">See Also</span></span>

- [<span data-ttu-id="4f7b8-116">CategoricalDistribution。</span><span class="sxs-lookup"><span data-stu-id="4f7b8-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)