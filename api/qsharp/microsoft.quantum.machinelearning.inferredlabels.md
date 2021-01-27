---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848400"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="3fcd1-102">InferredLabels 函式</span><span class="sxs-lookup"><span data-stu-id="3fcd1-102">InferredLabels function</span></span>

<span data-ttu-id="3fcd1-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3fcd1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3fcd1-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3fcd1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3fcd1-105">由於分類機率和偏差的陣列，會傳回從每個機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="3fcd1-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="3fcd1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3fcd1-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="3fcd1-107">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3fcd1-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3fcd1-108">兩個類別之間的偏差，通常是將分類器定型的結果。</span><span class="sxs-lookup"><span data-stu-id="3fcd1-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="3fcd1-109">機率： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3fcd1-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3fcd1-110">一組範例的分類機率陣列，通常是因為估計分類頻率所產生。</span><span class="sxs-lookup"><span data-stu-id="3fcd1-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="3fcd1-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3fcd1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3fcd1-112">從每個分類機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="3fcd1-112">The label inferred from each classification probability.</span></span>