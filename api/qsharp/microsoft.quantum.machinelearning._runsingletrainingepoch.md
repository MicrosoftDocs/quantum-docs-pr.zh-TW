---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699715"
---
# <a name="_runsingletrainingepoch-operation"></a>_RunSingleTrainingEpoch 操作

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


針對資料樣本的子集，執行連續分類器定型的一個 epoch。

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>輸入

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)、[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>排程： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore： [Int](xref:microsoft.quantum.lang-ref.int)

計分點之間要執行的漸層步驟數目。
為了達到最佳精確度，請設定為1。


### <a name="options--trainingoptions"></a>選項： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

用於定型的選項。


### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要定型的連續模型。


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses： [Int](xref:microsoft.quantum.lang-ref.int)

在先前的 epoch 中觀察到的最大情形數目。



## <a name="output--intsequentialmodel"></a>輸出： ([Int](xref:microsoft.quantum.lang-ref.int)，[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) 

- 透過此 epoch 觀察到的最小情形數。
- 找到新的最佳順序模型。