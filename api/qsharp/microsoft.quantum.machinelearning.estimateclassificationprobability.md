---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697238"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="227c2-102">EstimateClassificationProbability 操作</span><span class="sxs-lookup"><span data-stu-id="227c2-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="227c2-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="227c2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="227c2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="227c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="227c2-105">假設有一個範例和一連串的分類器，請重複測量給定範例上的分類器輸出，以估計該範例的分類機率。</span><span class="sxs-lookup"><span data-stu-id="227c2-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="227c2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="227c2-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="227c2-107">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="227c2-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="227c2-108">允許將範例編碼為狀態準備作業的容錯功能。</span><span class="sxs-lookup"><span data-stu-id="227c2-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="227c2-109">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="227c2-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="227c2-110">用來估計給定範例之分類機率的連續模型。</span><span class="sxs-lookup"><span data-stu-id="227c2-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="227c2-111">範例： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="227c2-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="227c2-112">要分類之範例的功能向量。</span><span class="sxs-lookup"><span data-stu-id="227c2-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="227c2-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="227c2-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="227c2-114">估計分類機率時要使用的度量數目。</span><span class="sxs-lookup"><span data-stu-id="227c2-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="227c2-115">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="227c2-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="227c2-116">給定範例之分類機率的估計值。</span><span class="sxs-lookup"><span data-stu-id="227c2-116">An estimate of the classification probability for the given sample.</span></span>