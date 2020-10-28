---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697675"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="c3f0e-102">TrainSequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="c3f0e-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="c3f0e-103">命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c3f0e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c3f0e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3f0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3f0e-105">給定順序分類器的結構，在指定的標示定型集上訓練分類器。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="c3f0e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c3f0e-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="c3f0e-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="c3f0e-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="c3f0e-108">要在定型期間用作起點的模型陣列。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="c3f0e-109">範例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="c3f0e-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="c3f0e-110">一組已加上標籤的定型資料，將用來執行定型。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="c3f0e-111">選項： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="c3f0e-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="c3f0e-112">定型時要使用的設定;如需詳細 @"microsoft.quantum.machinelearning.trainingoptions" 資訊，請參閱和 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="c3f0e-113">trainingSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="c3f0e-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="c3f0e-114">在定型步驟期間從定型資料選取樣本時要使用的取樣排程。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="c3f0e-115">validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="c3f0e-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="c3f0e-116">當您選取要產生最佳分類分數的起點時，從定型資料選取樣本時所要使用的取樣排程。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="c3f0e-117">Output： ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)，[Int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="c3f0e-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="c3f0e-118">指定分類器的參數化以及兩個類別之間的偏差，這兩者會對應到每個指定起點的最佳結果。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="c3f0e-119">在最佳分類器模型中觀察到的遺漏數目。</span><span class="sxs-lookup"><span data-stu-id="c3f0e-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3f0e-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3f0e-120">See Also</span></span>

- [<span data-ttu-id="c3f0e-121">MachineLearning. TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="c3f0e-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="c3f0e-122">MachineLearning. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="c3f0e-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)