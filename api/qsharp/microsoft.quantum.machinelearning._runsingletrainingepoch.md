---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 71780645a025972f11f32f8ba8fd94d098604f9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196747"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="57e5f-102">_RunSingleTrainingEpoch 操作</span><span class="sxs-lookup"><span data-stu-id="57e5f-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="57e5f-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="57e5f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="57e5f-104">封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="57e5f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="57e5f-105">針對資料樣本的子集，執行連續分類器定型的一個 epoch。</span><span class="sxs-lookup"><span data-stu-id="57e5f-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="57e5f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="57e5f-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="57e5f-107">encodedSamples： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)、[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="57e5f-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="57e5f-108">排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="57e5f-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="57e5f-109">periodScore： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57e5f-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57e5f-110">計分點之間要執行的漸層步驟數目。</span><span class="sxs-lookup"><span data-stu-id="57e5f-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="57e5f-111">為了達到最佳精確度，請設定為1。</span><span class="sxs-lookup"><span data-stu-id="57e5f-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="57e5f-112">選項： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="57e5f-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="57e5f-113">用於定型的選項。</span><span class="sxs-lookup"><span data-stu-id="57e5f-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="57e5f-114">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="57e5f-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="57e5f-115">要定型的連續模型。</span><span class="sxs-lookup"><span data-stu-id="57e5f-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="57e5f-116">nPreviousBestMisses： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57e5f-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57e5f-117">在先前的 epoch 中觀察到的最大情形數目。</span><span class="sxs-lookup"><span data-stu-id="57e5f-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="57e5f-118">輸出： ([Int](xref:microsoft.quantum.lang-ref.int)，[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) </span><span class="sxs-lookup"><span data-stu-id="57e5f-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="57e5f-119">透過此 epoch 觀察到的最小情形數。</span><span class="sxs-lookup"><span data-stu-id="57e5f-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="57e5f-120">找到新的最佳順序模型。</span><span class="sxs-lookup"><span data-stu-id="57e5f-120">The new best sequential model found.</span></span>