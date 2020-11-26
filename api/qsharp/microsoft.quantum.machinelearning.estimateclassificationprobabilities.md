---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211894"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="bbd28-102">EstimateClassificationProbabilities 操作</span><span class="sxs-lookup"><span data-stu-id="bbd28-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="bbd28-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bbd28-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bbd28-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bbd28-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="bbd28-105">假設有一組範例和連續的分類器，請重複測量每個樣本上的分類器輸出，以估計這些樣本的分類機率。</span><span class="sxs-lookup"><span data-stu-id="bbd28-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="bbd28-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bbd28-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="bbd28-107">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="bbd28-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="bbd28-108">允許將範例編碼為狀態準備作業的容錯功能。</span><span class="sxs-lookup"><span data-stu-id="bbd28-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="bbd28-109">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="bbd28-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="bbd28-110">用來估計給定範例之分類機率的連續模型。</span><span class="sxs-lookup"><span data-stu-id="bbd28-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="bbd28-111">範例： [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="bbd28-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="bbd28-112">要分類的每個範例的功能向量陣列。</span><span class="sxs-lookup"><span data-stu-id="bbd28-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="bbd28-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bbd28-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bbd28-114">估計分類機率時要使用的度量數目。</span><span class="sxs-lookup"><span data-stu-id="bbd28-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="bbd28-115">輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bbd28-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bbd28-116">每個給定範例的分類機率估計值陣列。</span><span class="sxs-lookup"><span data-stu-id="bbd28-116">An array of estimates of the classification probability for each given sample.</span></span>