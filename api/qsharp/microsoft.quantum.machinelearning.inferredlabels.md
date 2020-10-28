---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700283"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="0d697-102">InferredLabels 函式</span><span class="sxs-lookup"><span data-stu-id="0d697-102">InferredLabels function</span></span>

<span data-ttu-id="0d697-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0d697-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0d697-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d697-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d697-105">由於分類機率和偏差的陣列，會傳回從每個機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="0d697-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0d697-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0d697-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="0d697-107">偏差： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d697-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d697-108">兩個類別之間的偏差，通常是將分類器定型的結果。</span><span class="sxs-lookup"><span data-stu-id="0d697-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="0d697-109">機率： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0d697-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0d697-110">一組範例的分類機率陣列，通常是因為估計分類頻率所產生。</span><span class="sxs-lookup"><span data-stu-id="0d697-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="0d697-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0d697-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0d697-112">從每個分類機率推斷的標籤。</span><span class="sxs-lookup"><span data-stu-id="0d697-112">The label inferred from each classification probability.</span></span>