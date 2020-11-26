---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211775"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="772b0-102">InferredLabel 函式</span><span class="sxs-lookup"><span data-stu-id="772b0-102">InferredLabel function</span></span>

<span data-ttu-id="772b0-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="772b0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="772b0-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="772b0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="772b0-105">由於分類機率和偏差的考慮，會傳回從該機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="772b0-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="772b0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="772b0-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="772b0-107">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="772b0-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="772b0-108">兩個類別之間的偏差，通常是將分類器定型的結果。</span><span class="sxs-lookup"><span data-stu-id="772b0-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="772b0-109">機率： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="772b0-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="772b0-110">特定範例的分類機率，通常是因為估計其分類頻率所產生。</span><span class="sxs-lookup"><span data-stu-id="772b0-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="772b0-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="772b0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="772b0-112">從指定分類機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="772b0-112">The label inferred from the given classification probability.</span></span>