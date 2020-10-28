---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700294"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="ae9d3-102">InferredLabel 函式</span><span class="sxs-lookup"><span data-stu-id="ae9d3-102">InferredLabel function</span></span>

<span data-ttu-id="ae9d3-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ae9d3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae9d3-105">由於分類機率和偏差的考慮，會傳回從該機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="ae9d3-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="ae9d3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ae9d3-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="ae9d3-107">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae9d3-108">兩個類別之間的偏差，通常是將分類器定型的結果。</span><span class="sxs-lookup"><span data-stu-id="ae9d3-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="ae9d3-109">機率： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae9d3-110">特定範例的分類機率，通常是因為估計其分類頻率所產生。</span><span class="sxs-lookup"><span data-stu-id="ae9d3-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="ae9d3-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae9d3-112">從指定分類機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="ae9d3-112">The label inferred from the given classification probability.</span></span>